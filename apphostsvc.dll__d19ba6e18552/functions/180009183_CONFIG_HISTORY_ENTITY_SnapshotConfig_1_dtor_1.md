# _CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$1

- ea: `0x180009183`
- end: `0x180009191`
- name: `_CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000918a`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::SnapshotConfig_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 104));
}

```

## disassembly

```asm
0x180009183  lea     rcx, [rdx+68h]
0x18000918a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
