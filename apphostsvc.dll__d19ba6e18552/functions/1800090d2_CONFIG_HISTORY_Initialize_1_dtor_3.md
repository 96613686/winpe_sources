# _CONFIG_HISTORY::Initialize_::_1_::dtor$3

- ea: `0x1800090d2`
- end: `0x1800090e7`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$3`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x1800090e0`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  STRU_PATH::~STRU_PATH((STRU_PATH *)(*(_QWORD *)(a2 + 72) + 136LL));
}

```

## disassembly

```asm
0x1800090d2  mov     rcx, [rdx+48h]
0x1800090d9  add     rcx, 88h
0x1800090e0  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
