# CDriverVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x140051b80`
- end: `0x140051dbd`
- name: `?InvokeCallback@CDriverVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `573`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140003ac0`
- `0x14001444c`
- `0x140014474`
- `0x1400517bc`
- `0x14005188c`
- `0x140051b80`
- `0x140051dc4`
- `0x1400525e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140051c8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140051c8d`
- `ntdll!NtQuerySystemInformation` at `0x140051ccd`
- `ntdll!NtQuerySystemInformation` at `0x140051ccd`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140051c45`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140051c45`

## pseudocode

```c

```
