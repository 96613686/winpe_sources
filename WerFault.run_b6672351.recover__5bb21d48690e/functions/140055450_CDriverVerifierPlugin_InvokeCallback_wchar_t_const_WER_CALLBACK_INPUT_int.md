# CDriverVerifierPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x140055450`
- end: `0x1400556a0`
- name: `?InvokeCallback@CDriverVerifierPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `592`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140003b10`
- `0x140014ee4`
- `0x140014f14`
- `0x14005505c`
- `0x140055134`
- `0x140055450`
- `0x1400556a8`
- `0x140055ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140055563`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140055563`
- `ntdll!NtQuerySystemInformation` at `0x1400555a9`
- `ntdll!NtQuerySystemInformation` at `0x1400555a9`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140055515`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x140055515`

## pseudocode

```c

```
