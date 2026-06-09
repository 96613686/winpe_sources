# LocalComLibraries::CoCreateInstance(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x18002cbc0`
- end: `0x18002cf33`
- name: `?CoCreateInstance@LocalComLibraries@@QEAAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z`
- size: `883`
- prototype: `__int64 __fastcall(LocalComLibraries *__hidden this, const unsigned __int16 *, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a5c4`
- `0x18005ac8c`
- `0x180079f08`

## callees

- `0x1800041a4`
- `0x180004908`
- `0x180004e88`
- `0x180006348`
- `0x18000cb74`
- `0x18000f780`
- `0x180021a90`
- `0x180025f90`
- `0x180026724`
- `0x18002cbc0`
- `0x18002cf3c`
- `0x18002ddc0`
- `0x18002ec48`
- `0x18002ec74`
- `0x1800320a8`
- `0x18003450c`
- `0x18003b6e4`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cc3f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002cc3f`
- `KERNEL32!GetModuleHandleW` at `0x18002cca0`
- `KERNEL32!GetModuleHandleW` at `0x18002cca0`
- `KERNEL32!FreeLibrary` at `0x18002cefa`
- `KERNEL32!FreeLibrary` at `0x18002cefa`
- `KERNEL32!GetModuleFileNameW` at `0x18002cd03`
- `KERNEL32!GetModuleFileNameW` at `0x18002cd03`
- `KERNEL32!GetProcAddress` at `0x18002cda3`
- `KERNEL32!GetProcAddress` at `0x18002cda3`
- `KERNEL32!GetLastError` at `0x18002cd69`
- `KERNEL32!GetLastError` at `0x18002cd69`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ccb2`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ce2f`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ccb2`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ce2f`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18002ceac`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18002ceac`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ceb3`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002ceb3`

## string_xrefs

- `0x18002cc99`: `PhotoBase.dll`
- `0x18002cd99`: `DllGetClassObject`
- `0x18002cbde`: `ImagingEngine.dll`

## pseudocode

```c

```
