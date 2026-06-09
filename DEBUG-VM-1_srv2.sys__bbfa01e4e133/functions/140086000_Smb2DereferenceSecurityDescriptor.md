# Smb2DereferenceSecurityDescriptor

- ea: `0x140086000`
- end: `0x140086041`
- name: `Smb2DereferenceSecurityDescriptor`
- size: `65`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f4d0`
- `0x140017170`
- `0x1400200ac`
- `0x14002d904`
- `0x1400770c8`
- `0x140085f90`

## callees

- `0x140086000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140086033`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086033`
- `srvnet!SrvNetFreePool` at `0x140086022`
- `srvnet!SrvNetFreePool` at `0x140086022`

## pseudocode

```c

```
