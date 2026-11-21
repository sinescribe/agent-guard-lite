# agent-guard-lite

Zero-dependency Python prompt-injection scanner, canary token leak detector, and XML/markdown tag sanitizer for autonomous LLM agents.

## Features
- Detects instruction-override patterns (`ignore previous instructions`, jailbreak preambles, system-tag spoofing).
- Detects leaked internal canary tokens in untrusted tool outputs or web pages.
- Sanitizes `<system>` and prompt-fenced blocks before feeding external text back into an LLM context.

## Quickstart

```bash
pip install promptguard-api
```

```python
from agent_guard import PromptDefenseFilter

guard = PromptDefenseFilter(canary_token="CANARY-TOKEN-HERE")
safe, reasons = guard.scan_untrusted_input(web_page_text)
if not safe:
    print("Blocked untrusted input:", reasons)
```

## Full Production Toolkits
- **PromptGuard Pro API ($15/mo):** https://sinescribe5.gumroad.com/l/qzubcy
- **Production Multi-Agent Architecture & Protocol Pack ($29):** https://sinescribe5.gumroad.com/l/phhyon
- **Autonomous Security & Bug Bounty Recon Kit ($19):** https://sinescribe5.gumroad.com/l/jyubxd
- **AI Agent Production Guardrail Cheat Sheet + Python Starter ($5):** https://sinescribe5.gumroad.com/l/cpfgbj

## License
MIT License - sinescribe
