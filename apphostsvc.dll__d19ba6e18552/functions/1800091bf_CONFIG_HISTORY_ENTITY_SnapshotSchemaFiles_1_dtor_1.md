# _CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$1

- ea: `0x1800091bf`
- end: `0x1800091cd`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800091c6`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotSchemaFiles_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 200));
}

```

## disassembly

```asm
0x1800091bf  lea     rcx, [rdx+0C8h]
0x1800091c6  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
