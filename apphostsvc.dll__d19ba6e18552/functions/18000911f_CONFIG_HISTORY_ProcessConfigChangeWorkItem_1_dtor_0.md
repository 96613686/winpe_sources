# _CONFIG_HISTORY::ProcessConfigChangeWorkItem_::_1_::dtor$0

- ea: `0x18000911f`
- end: `0x18000912d`
- name: `_CONFIG_HISTORY::ProcessConfigChangeWorkItem_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180009126`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::ProcessConfigChangeWorkItem_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU_PATH::~STRU_PATH((STRU_PATH *)(a2 + 144));
}

```

## disassembly

```asm
0x18000911f  lea     rcx, [rdx+90h]
0x180009126  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
