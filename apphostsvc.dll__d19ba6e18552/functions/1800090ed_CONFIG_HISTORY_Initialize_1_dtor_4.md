# _CONFIG_HISTORY::Initialize_::_1_::dtor$4

- ea: `0x1800090ed`
- end: `0x180009100`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$4`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002cac`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  SMALL_STRU::~SMALL_STRU((SMALL_STRU *)(*(_QWORD *)(a2 + 72) + 200LL));
}

```

## disassembly

```asm
0x1800090ed  mov     rcx, [rdx+48h]
0x1800090f4  add     rcx, 0C8h; this
0x1800090fb  jmp     ??1SMALL_STRU@@QEAA@XZ; SMALL_STRU::~SMALL_STRU(void)
```
