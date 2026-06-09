# ___acrt_fenv_get_common_round_control

- ea: `0x41bb3a`
- end: `0x41bb5c`
- name: `___acrt_fenv_get_common_round_control`
- size: `34`
- prototype: `int __cdecl(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x41b17f`

## callees

- `0x41bb3a`

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
0x41bb3a  mov     edi, edi
0x41bb3c  push    ebp
0x41bb3d  mov     ebp, esp
0x41bb3f  mov     ecx, [ebp+arg_0]
0x41bb42  mov     edx, 300h
0x41bb47  mov     eax, ecx
0x41bb49  shr     ecx, 16h
0x41bb4c  shr     eax, 0Eh
0x41bb4f  and     ecx, edx
0x41bb51  and     eax, edx
0x41bb53  cmp     eax, ecx
0x41bb55  jz      short loc_41BB5A
0x41bb57  or      eax, 0FFFFFFFFh
0x41bb5a  pop     ebp
0x41bb5b  retn
```
