# PoqParsePoqexecLog(_LUNICODE_STRING const *,long *,_LUNICODE_STRING *,_LUNICODE_STRING *,_LUNICODE_STRING *)

- ea: `0x1801f0840`
- end: `0x1801f1090`
- name: `?PoqParsePoqexecLog@@YAJPEBU_LUNICODE_STRING@@PEAJPEAU1@22@Z`
- size: `2128`
- prototype: `__int64 __fastcall(const struct _LUNICODE_STRING *, int *, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180141808`

## callees

- `0x18001a160`
- `0x18002e280`
- `0x18002ec34`
- `0x18004f454`
- `0x180070adc`
- `0x1800eb920`
- `0x1800ecb50`
- `0x1801026fc`
- `0x1801f0840`
- `0x1801fbac0`
- `0x1801fbdac`
- `0x1801fbf50`

## import_xrefs

- `ntdll!NtReadFile` at `0x1801f0ab9`
- `ntdll!NtReadFile` at `0x1801f0ab9`
- `ntdll!NtQueryInformationFile` at `0x1801f09cb`
- `ntdll!NtQueryInformationFile` at `0x1801f09cb`
- `ntdll!NtOpenFile` at `0x1801f0991`
- `ntdll!NtOpenFile` at `0x1801f0991`
- `ntdll!RtlRaiseStatus` at `0x1801f0fc2`
- `ntdll!RtlRaiseStatus` at `0x1801f0fc2`

## string_xrefs

- `0x1801f0ceb`: `CriticalPOQComplete`

## pseudocode

```c

```
