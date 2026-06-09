# CFDRPlugin::PromptForEnableFDR(void *)

- ea: `0x140053bbc`
- end: `0x140053f74`
- name: `?PromptForEnableFDR@CFDRPlugin@@AEAAHPEAX@Z`
- size: `952`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140052e04`

## callees

- `0x140002728`
- `0x140012510`
- `0x140014474`
- `0x140024414`
- `0x140030150`
- `0x140053bbc`
- `0x14005acd0`

## import_xrefs

- `wer!WerpSetReportFlags` at `0x140053ea1`
- `wer!WerpSetReportFlags` at `0x140053ea1`
- `wer!WerpGetReportFlags` at `0x140053c5f`
- `wer!WerpGetReportFlags` at `0x140053e8b`
- `wer!WerpGetReportFlags` at `0x140053c5f`
- `wer!WerpGetReportFlags` at `0x140053e8b`
- `wer!WerpPromptUser` at `0x140053e7c`
- `wer!WerpPromptUser` at `0x140053e7c`

## string_xrefs

- `0x140053ef3`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

## pseudocode

```c

```
