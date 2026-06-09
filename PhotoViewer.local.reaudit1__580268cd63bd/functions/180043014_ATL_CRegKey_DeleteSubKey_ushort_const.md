# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180043014`
- end: `0x1800430c6`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180042264`
- `0x18004391c`
- `0x180043de4`

## callees

- `0x18002cf3c`
- `0x180043014`
- `0x180080010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180043039`
- `KERNEL32!GetModuleHandleW` at `0x180043039`
- `KERNEL32!GetProcAddress` at `0x18004304e`
- `KERNEL32!GetProcAddress` at `0x180043078`
- `KERNEL32!GetProcAddress` at `0x18004304e`
- `KERNEL32!GetProcAddress` at `0x180043078`
- `KERNEL32!GetLastError` at `0x1800430b4`
- `KERNEL32!GetLastError` at `0x1800430b4`

## string_xrefs

- `0x180043032`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180043044`: `RegDeleteKeyExW`
- `0x18004305d`: `advapi32.dll`
- `0x18004306e`: `RegDeleteKeyW`

## pseudocode

```c

```
