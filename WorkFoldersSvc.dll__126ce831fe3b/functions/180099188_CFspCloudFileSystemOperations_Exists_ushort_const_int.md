# CFspCloudFileSystemOperations::Exists(ushort const *,int *)

- ea: `0x180099188`
- end: `0x180099371`
- name: `?Exists@CFspCloudFileSystemOperations@@SAJPEBGPEAH@Z`
- size: `489`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180090ac0`
- `0x180091074`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180099188`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180099282`
- `ntdll!RtlInitUnicodeString` at `0x180099282`
- `ntdll!NtCreateFile` at `0x1800992e3`
- `ntdll!NtCreateFile` at `0x1800992e3`
- `ntdll!NtClose` at `0x1800992f3`
- `ntdll!NtClose` at `0x1800992f3`

## pseudocode

```c

```
