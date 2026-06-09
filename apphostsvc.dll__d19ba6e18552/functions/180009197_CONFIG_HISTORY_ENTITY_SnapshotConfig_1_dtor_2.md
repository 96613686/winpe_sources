# _CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$2

- ea: `0x180009197`
- end: `0x1800091a5`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$2`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000919e`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 160));
}

```

## disassembly

```asm
0x180009197  lea     rcx, [rdx+0A0h]
0x18000919e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
