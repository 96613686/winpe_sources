# _CWbemBackupRestore::GetDefaultRepDriverClsId_::_1_::dtor$0

- ea: `0x18001d538`
- end: `0x18001d546`
- name: `_CWbemBackupRestore::GetDefaultRepDriverClsId_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001d53f`

## pseudocode

```c
void __fastcall CWbemBackupRestore::GetDefaultRepDriverClsId_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 40));
}

```

## disassembly

```asm
0x18001d538  lea     rcx, [rdx+28h]
0x18001d53f  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
