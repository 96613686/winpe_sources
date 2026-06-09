# wil::details::FormatNtStatusMsg(long,wchar_t *,ulong)

- ea: `0x14001cc10`
- end: `0x14001cc80`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEA_WK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14001cc10`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14001cc6a`
- `KERNEL32!FormatMessageW` at `0x14001cc6a`
- `KERNEL32!GetModuleHandleW` at `0x14001cc3a`
- `KERNEL32!GetModuleHandleW` at `0x14001cc3a`

## string_xrefs

- `0x14001cc33`: `ntdll.dll`

## pseudocode

```c

```
