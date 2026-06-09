# AiCheckSecureApplicationDirectoryEx(void *,ulong *,ushort * *)

- ea: `0x18003f7ac`
- end: `0x18003f85f`
- name: `?AiCheckSecureApplicationDirectoryEx@@YAKPEAXPEAKPEAPEAG@Z`
- size: `179`
- prototype: `__int64 __fastcall(void *, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002ed98`
- `0x18003d070`

## callees

- `0x1800177a4`
- `0x180017840`
- `0x18003f7ac`
- `0x180040268`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18003f838`
- `ntdll!RtlFreeUnicodeString` at `0x18003f838`
- `ntdll!RtlPrefixUnicodeString` at `0x18003f7fd`
- `ntdll!RtlPrefixUnicodeString` at `0x18003f7fd`

## pseudocode

```c

```
