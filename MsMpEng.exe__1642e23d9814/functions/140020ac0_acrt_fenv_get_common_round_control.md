# __acrt_fenv_get_common_round_control

- ea: `0x140020ac0`
- end: `0x140020ac9`
- name: `__acrt_fenv_get_common_round_control`
- size: `9`
- prototype: `__int64 __fastcall(__int16)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001bb00`

## pseudocode

```c
__int64 __fastcall _acrt_fenv_get_common_round_control(__int16 a1)
{
  return a1 & 0x300;
}

```

## disassembly

```asm
0x140020ac0  and     ecx, 300h
0x140020ac6  mov     eax, ecx
0x140020ac8  retn
```
