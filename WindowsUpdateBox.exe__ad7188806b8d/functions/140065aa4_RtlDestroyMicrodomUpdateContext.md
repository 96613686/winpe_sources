# RtlDestroyMicrodomUpdateContext

- ea: `0x140065aa4`
- end: `0x140065b55`
- name: `RtlDestroyMicrodomUpdateContext`
- size: `177`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002e7a0`
- `0x14005c1f8`
- `0x14005c9b0`
- `0x14005d3e0`
- `0x14005d9bc`
- `0x14006160c`

## callees

- `0x140062958`
- `0x1400645c0`
- `0x140065aa4`
- `0x140072764`
- `0x140080d70`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140065b35`
- `KERNEL32!HeapFree` at `0x140065b35`
- `KERNEL32!GetProcessHeap` at `0x140065b21`
- `KERNEL32!GetProcessHeap` at `0x140065b21`
- `ntdll!RtlRaiseStatus` at `0x140065b0f`
- `ntdll!RtlRaiseStatus` at `0x140065b0f`

## string_xrefs

- `0x140065ac3`: `onecore\base\xml\udom_modify.cpp`
- `0x140065ada`: `Windows::uDom::Rtl::RtlDestroyMicrodomUpdateContext`
- `0x140065af3`: `RtlIsMicrodomUpdateContextValid(TheContext)`

## pseudocode

```c

```
