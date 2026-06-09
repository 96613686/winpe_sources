# _CONFIG_HISTORY::Initialize_::_1_::dtor$5

- ea: `0x180009106`
- end: `0x180009119`
- name: `_CONFIG_HISTORY::Initialize_::_1_::dtor$5`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180002cac`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Initialize_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  SMALL_STRU::~SMALL_STRU((SMALL_STRU *)(*(_QWORD *)(a2 + 72) + 208LL));
}

```

## disassembly

```asm
0x180009106  mov     rcx, [rdx+48h]
0x18000910d  add     rcx, 0D0h; this
0x180009114  jmp     ??1SMALL_STRU@@QEAA@XZ; SMALL_STRU::~SMALL_STRU(void)
```
