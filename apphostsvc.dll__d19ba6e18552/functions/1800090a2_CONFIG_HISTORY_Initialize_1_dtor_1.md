# _CONFIG_HISTORY::Initialize_::_1_::dtor$1

- ea: `0x1800090a2`
- end: `0x1800090b4`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$1`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800090ad`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU_PATH::~STRU_PATH((STRU_PATH *)(*(_QWORD *)(a2 + 72) + 8LL));
}

```

## disassembly

```asm
0x1800090a2  mov     rcx, [rdx+48h]
0x1800090a9  add     rcx, 8
0x1800090ad  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
