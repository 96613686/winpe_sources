# CAppRecorderPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x1400507f0`
- end: `0x140050aa0`
- name: `?InvokeCallback@CAppRecorderPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `688`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140003b10`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x14005009c`
- `0x14005014c`
- `0x1400507f0`
- `0x140051348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140050996`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140050996`
- `wer!WerpSetReportFlags` at `0x140050900`
- `wer!WerpSetReportFlags` at `0x1400509fe`
- `wer!WerpSetReportFlags` at `0x140050900`
- `wer!WerpSetReportFlags` at `0x1400509fe`
- `wer!WerpGetReportFlags` at `0x1400508ab`
- `wer!WerpGetReportFlags` at `0x1400509e1`
- `wer!WerpGetReportFlags` at `0x1400508ab`
- `wer!WerpGetReportFlags` at `0x1400509e1`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140050944`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140050944`

## pseudocode

```c

```
