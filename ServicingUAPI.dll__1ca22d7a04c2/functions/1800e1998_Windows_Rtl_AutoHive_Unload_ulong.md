# Windows::Rtl::AutoHive::Unload(ulong)

- ea: `0x1800e1998`
- end: `0x1800e1e93`
- name: `?Unload@AutoHive@Rtl@Windows@@QEAAJK@Z`
- size: `1275`
- prototype: `__int64 __fastcall(Windows::Rtl::AutoHive *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800deec4`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18003104c`
- `0x1800497c0`
- `0x18004d970`
- `0x18004e028`
- `0x18004e0d4`
- `0x1800e1998`
- `0x1801a18f4`

## import_xrefs

- `ntdll!NtFlushKey` at `0x1800e1a23`
- `ntdll!NtFlushKey` at `0x1800e1a23`
- `ntdll!NtUnloadKey2` at `0x1800e1aea`
- `ntdll!NtUnloadKey2` at `0x1800e1aea`
- `ntdll!NtCreateFile` at `0x1800e1c09`
- `ntdll!NtCreateFile` at `0x1800e1c09`
- `ntdll!NtClose` at `0x1800e1a37`
- `ntdll!NtClose` at `0x1800e1c54`
- `ntdll!NtClose` at `0x1800e1de3`
- `ntdll!NtClose` at `0x1800e1e0c`
- `ntdll!NtClose` at `0x1800e1a37`
- `ntdll!NtClose` at `0x1800e1c54`
- `ntdll!NtClose` at `0x1800e1de3`
- `ntdll!NtClose` at `0x1800e1e0c`

## string_xrefs

- `0x1800e1b6f`: `Open keys still exist for {}`

## pseudocode

```c

```
