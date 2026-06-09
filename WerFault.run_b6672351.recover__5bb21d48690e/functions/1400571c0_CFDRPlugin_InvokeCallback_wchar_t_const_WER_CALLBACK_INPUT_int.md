# CFDRPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x1400571c0`
- end: `0x140057562`
- name: `?InvokeCallback@CFDRPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `930`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x140002748`
- `0x140003b10`
- `0x14000ca20`
- `0x140014ee4`
- `0x140014f14`
- `0x1400561ac`
- `0x14005666c`
- `0x140056730`
- `0x1400571c0`
- `0x140057b3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005739a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140057470`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005739a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140057470`
- `wer!WerpSetReportFlags` at `0x1400572dc`
- `wer!WerpSetReportFlags` at `0x1400572dc`
- `wer!WerpGetReportFlags` at `0x140057282`
- `wer!WerpGetReportFlags` at `0x140057282`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140057327`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140057327`

## pseudocode

```c

```
