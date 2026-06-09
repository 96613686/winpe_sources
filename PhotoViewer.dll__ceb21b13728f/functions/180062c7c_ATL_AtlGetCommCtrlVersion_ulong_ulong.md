# ATL::AtlGetCommCtrlVersion(ulong *,ulong *)

- ea: `0x180062c7c`
- end: `0x180062d61`
- name: `?AtlGetCommCtrlVersion@ATL@@YAJPEAK0@Z`
- size: `229`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066358`

## callees

- `0x18002cf3c`
- `0x18003f800`
- `0x180042228`
- `0x180062c7c`
- `0x180080010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180062d0b`
- `KERNEL32!FreeLibrary` at `0x180062d0b`
- `KERNEL32!GetProcAddress` at `0x180062cea`
- `KERNEL32!GetProcAddress` at `0x180062cea`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180062d5a`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180062d5a`

## string_xrefs

- `0x180062ce0`: `DllGetVersion`
- `0x180062cbd`: `comctl32.dll`

## pseudocode

```c

```
