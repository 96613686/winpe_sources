# _CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$2

- ea: `0x1800091d3`
- end: `0x1800091e1`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$2`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800091da`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 88));
}

```

## disassembly

```asm
0x1800091d3  lea     rcx, [rdx+58h]
0x1800091da  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
