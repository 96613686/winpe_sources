# _CONFIG_HISTORY_ENTITY::TrimHistory_::_1_::dtor$0

- ea: `0x18000915b`
- end: `0x180009169`
- name: `_CONFIG_HISTORY_ENTITY::TrimHistory_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180009162`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::TrimHistory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 32));
}

```

## disassembly

```asm
0x18000915b  lea     rcx, [rdx+20h]
0x180009162  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
