# _CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$0

- ea: `0x18000916f`
- end: `0x18000917d`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180009176`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 48));
}

```

## disassembly

```asm
0x18000916f  lea     rcx, [rdx+30h]
0x180009176  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
