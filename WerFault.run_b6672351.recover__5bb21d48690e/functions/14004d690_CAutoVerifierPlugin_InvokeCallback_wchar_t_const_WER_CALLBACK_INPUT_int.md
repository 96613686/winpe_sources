# CAutoVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x14004d690`
- end: `0x14004d9b6`
- name: `?InvokeCallback@CAutoVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `806`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140002748`
- `0x140003b10`
- `0x140014ee4`
- `0x140014f14`
- `0x14004c6e0`
- `0x14004d690`
- `0x14004df60`
- `0x1400586ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d87e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d87e`
- `wer!WerpSetReportFlags` at `0x14004d76c`
- `wer!WerpSetReportFlags` at `0x14004d76c`
- `wer!WerpGetReportFlags` at `0x14004d70f`
- `wer!WerpGetReportFlags` at `0x14004d70f`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004d7bb`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004d7bb`

## pseudocode

```c

```
