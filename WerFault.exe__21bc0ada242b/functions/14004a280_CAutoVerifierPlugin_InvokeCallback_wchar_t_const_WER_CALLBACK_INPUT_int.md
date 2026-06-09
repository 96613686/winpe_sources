# CAutoVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x14004a280`
- end: `0x14004a58a`
- name: `?InvokeCallback@CAutoVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `778`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140002728`
- `0x140003ac0`
- `0x14001444c`
- `0x140014474`
- `0x140049364`
- `0x14004a280`
- `0x14004ab10`
- `0x140054c74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004a459`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004a459`
- `wer!WerpSetReportFlags` at `0x14004a353`
- `wer!WerpSetReportFlags` at `0x14004a353`
- `wer!WerpGetReportFlags` at `0x14004a2ff`
- `wer!WerpGetReportFlags` at `0x14004a2ff`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004a39c`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004a39c`

## pseudocode

```c

```
