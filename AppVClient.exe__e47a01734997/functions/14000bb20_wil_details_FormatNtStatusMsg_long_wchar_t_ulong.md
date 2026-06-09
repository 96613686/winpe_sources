# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x14000bb20`
- end: `0x14000bb90`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000bb20`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000bb4a`
- `KERNEL32!GetModuleHandleW` at `0x14000bb4a`
- `KERNEL32!FormatMessageW` at `0x14000bb7a`
- `KERNEL32!FormatMessageW` at `0x14000bb7a`

## string_xrefs

- `0x14000bb43`: `ntdll.dll`

## pseudocode

```c

```
