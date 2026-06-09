# _CONFIG_HISTORY_ENTITY::DeleteDirectory_::_1_::dtor$1

- ea: `0x180009147`
- end: `0x180009155`
- name: `_CONFIG_HISTORY_ENTITY::DeleteDirectory_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000914e`

## pseudocode

```c
void __fastcall CONFIG_HISTORY_ENTITY::DeleteDirectory_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 56));
}

```

## disassembly

```asm
0x180009147  lea     rcx, [rdx+38h]
0x18000914e  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
