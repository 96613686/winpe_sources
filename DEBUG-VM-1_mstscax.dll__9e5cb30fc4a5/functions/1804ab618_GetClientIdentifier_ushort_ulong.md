# GetClientIdentifier(ushort *,ulong)

- ea: `0x1804ab618`
- end: `0x1804ab93c`
- name: `?GetClientIdentifier@@YAJPEAGK@Z`
- size: `804`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1804abaa8`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1804ab618`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x1804ab8b6`
- `msvcrt!_wcslwr_s` at `0x1804ab8b6`
- `msvcrt!wcsrchr` at `0x1804ab7eb`
- `msvcrt!wcsrchr` at `0x1804ab863`
- `msvcrt!wcsrchr` at `0x1804ab7eb`
- `msvcrt!wcsrchr` at `0x1804ab863`
- `msvcrt!_errno` at `0x1804ab8be`
- `msvcrt!_errno` at `0x1804ab8c6`
- `msvcrt!_errno` at `0x1804ab907`
- `msvcrt!_errno` at `0x1804ab8be`
- `msvcrt!_errno` at `0x1804ab8c6`
- `msvcrt!_errno` at `0x1804ab907`
- `KERNEL32!GetLastError` at `0x1804ab6c2`
- `KERNEL32!GetLastError` at `0x1804ab735`
- `KERNEL32!GetLastError` at `0x1804ab6c2`
- `KERNEL32!GetLastError` at `0x1804ab735`
- `KERNEL32!GetModuleFileNameW` at `0x1804ab6b8`
- `KERNEL32!GetModuleFileNameW` at `0x1804ab6b8`

## string_xrefs

- `0x1804ab74e`: `com.microsoft.rdc.windows.%s.x64`
- `0x1804ab897`: `pszExtension`

## pseudocode

```c

```
