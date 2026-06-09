# wil::details::FormatNtStatusMsg(long,ushort *,ulong)

- ea: `0x180005a50`
- end: `0x180005ac0`
- name: `?FormatNtStatusMsg@details@wil@@YAXJPEAGK@Z`
- size: `112`
- prototype: `void __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005a50`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180005a7a`
- `KERNEL32!GetModuleHandleW` at `0x180005a7a`
- `KERNEL32!FormatMessageW` at `0x180005aaa`
- `KERNEL32!FormatMessageW` at `0x180005aaa`

## string_xrefs

- `0x180005a73`: `ntdll.dll`

## pseudocode

```c

```
