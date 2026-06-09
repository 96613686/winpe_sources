# ___acrt_fenv_get_common_round_control

- ea: `0x4171da`
- end: `0x4171fc`
- name: `___acrt_fenv_get_common_round_control`
- size: `34`
- prototype: `int __cdecl(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x41681f`

## callees

- `0x4171da`

## pseudocode

```c
int __cdecl __acrt_fenv_get_common_round_control(unsigned int a1)
{
  int result; // eax

  result = (a1 >> 14) & 0x300;
  if ( result != ((a1 >> 22) & 0x300) )
    return -1;
  return result;
}

```

## disassembly

```asm
0x4171da  mov     edi, edi
0x4171dc  push    ebp
0x4171dd  mov     ebp, esp
0x4171df  mov     ecx, [ebp+arg_0]
0x4171e2  mov     edx, 300h
0x4171e7  mov     eax, ecx
0x4171e9  shr     ecx, 16h
0x4171ec  shr     eax, 0Eh
0x4171ef  and     ecx, edx
0x4171f1  and     eax, edx
0x4171f3  cmp     eax, ecx
0x4171f5  jz      short loc_4171FA
0x4171f7  or      eax, 0FFFFFFFFh
0x4171fa  pop     ebp
0x4171fb  retn
```
