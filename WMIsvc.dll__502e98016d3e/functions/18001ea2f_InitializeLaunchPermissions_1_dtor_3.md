# _InitializeLaunchPermissions_::_1_::dtor$3

- ea: `0x18001ea2f`
- end: `0x18001ea3d`
- name: `_InitializeLaunchPermissions_::_1_::dtor$3`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001ea36`

## pseudocode

```c
void __fastcall InitializeLaunchPermissions_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CNtSid::~CNtSid((CNtSid *)(a2 + 192));
}

```

## disassembly

```asm
0x18001ea2f  lea     rcx, [rdx+0C0h]
0x18001ea36  jmp     cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
```
