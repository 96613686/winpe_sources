# _CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$0

- ea: `0x1800091ab`
- end: `0x1800091b9`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800091b2`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 144));
}

```

## disassembly

```asm
0x1800091ab  lea     rcx, [rdx+90h]
0x1800091b2  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
