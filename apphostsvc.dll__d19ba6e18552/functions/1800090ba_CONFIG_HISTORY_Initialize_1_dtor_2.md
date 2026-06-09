# _CONFIG_HISTORY::Initialize_::_1_::dtor$2

- ea: `0x1800090ba`
- end: `0x1800090cc`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$2`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800090c5`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  STRU_PATH::~STRU_PATH((STRU_PATH *)(*(_QWORD *)(a2 + 72) + 72LL));
}

```

## disassembly

```asm
0x1800090ba  mov     rcx, [rdx+48h]
0x1800090c1  add     rcx, 48h ; 'H'
0x1800090c5  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
