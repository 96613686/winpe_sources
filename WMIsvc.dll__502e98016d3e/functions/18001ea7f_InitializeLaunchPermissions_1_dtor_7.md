# _InitializeLaunchPermissions_::_1_::dtor$7

- ea: `0x18001ea7f`
- end: `0x18001ea8d`
- name: `_InitializeLaunchPermissions_::_1_::dtor$7`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x18001ea86`

## pseudocode

```c
void __fastcall InitializeLaunchPermissions_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)(a2 + 96));
}

```

## disassembly

```asm
0x18001ea7f  lea     rcx, [rdx+60h]
0x18001ea86  jmp     cs:__imp_??1CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::~CNtSecurityDescriptor(void)
```
