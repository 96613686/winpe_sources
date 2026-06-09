# BfsGetFinalPathComponent

- ea: `0x140006d20`
- end: `0x140006dab`
- name: `BfsGetFinalPathComponent`
- size: `139`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140009d2c`
- `0x140012608`

## callees

- `0x140006d20`

## pseudocode

```c
unsigned __int16 *__fastcall BfsGetFinalPathComponent(unsigned __int16 *a1, __int64 a2)
{
  unsigned __int64 v2; // r9
  unsigned __int64 v3; // r8
  _WORD *v4; // rax
  _WORD *v5; // rdx

  *(_OWORD *)a1 = *(_OWORD *)a2;
  v2 = *((_QWORD *)a1 + 1) + 2 * (((unsigned __int64)*a1 >> 1) - 1);
  v3 = *(_QWORD *)(a2 + 8);
  *((_QWORD *)a1 + 1) = v2;
  *a1 = 0;
  if ( v2 <= v3 )
  {
    v5 = (_WORD *)v2;
  }
  else
  {
    v4 = (_WORD *)v2;
    do
    {
      v5 = v4;
      if ( *v4 != 92 )
        break;
      v2 -= 2LL;
      *((_QWORD *)a1 + 1) = v2;
      v4 = (_WORD *)v2;
      v5 = (_WORD *)v2;
    }
    while ( v2 > v3 );
  }
  while ( (unsigned __int64)v5 > v3 )
  {
    if ( *v5 == 92 )
    {
      *((_QWORD *)a1 + 1) = v5 + 1;
      break;
    }
    if ( *v5 == 58 )
      *a1 = 0;
    else
      *a1 += 2;
    *((_QWORD *)a1 + 1) = --v5;
  }
  a1[1] = *a1;
  return a1;
}

```

## disassembly

```asm
0x140006d20  movups  xmm0, xmmword ptr [rdx]
0x140006d23  movdqu  xmmword ptr [rcx], xmm0
0x140006d27  mov     rax, [rcx+8]
0x140006d2b  movzx   r8d, word ptr [rcx]
0x140006d2f  shr     r8, 1
0x140006d32  dec     r8
0x140006d35  lea     r9, [rax+r8*2]
0x140006d39  mov     r8, [rdx+8]
0x140006d3d  xor     eax, eax
0x140006d3f  mov     [rcx+8], r9
0x140006d43  mov     [rcx], ax
0x140006d46  cmp     r9, r8
0x140006d49  jbe     short loc_140006D6C
0x140006d4b  mov     rax, r9
0x140006d4e  cmp     word ptr [rax], 5Ch ; '\'
0x140006d52  mov     rdx, rax
0x140006d55  jnz     short loc_140006D6F
0x140006d57  add     r9, 0FFFFFFFFFFFFFFFEh
0x140006d5b  mov     [rcx+8], r9
0x140006d5f  mov     rax, r9
0x140006d62  mov     rdx, r9
0x140006d65  cmp     r9, r8
0x140006d68  ja      short loc_140006D4E
0x140006d6a  jmp     short loc_140006D6F
0x140006d6c  mov     rdx, r9
0x140006d6f  cmp     rdx, r8
0x140006d72  jbe     short loc_140006DA0
0x140006d74  movzx   eax, word ptr [rdx]
0x140006d77  cmp     ax, 5Ch ; '\'
0x140006d7b  jz      short loc_140006D98
0x140006d7d  cmp     ax, 3Ah ; ':'
0x140006d81  jnz     short loc_140006D8A
0x140006d83  xor     eax, eax
0x140006d85  mov     [rcx], ax
0x140006d88  jmp     short loc_140006D8E
0x140006d8a  add     word ptr [rcx], 2
0x140006d8e  add     rdx, 0FFFFFFFFFFFFFFFEh
0x140006d92  mov     [rcx+8], rdx
0x140006d96  jmp     short loc_140006D6F
0x140006d98  lea     rax, [rdx+2]
0x140006d9c  mov     [rcx+8], rax
0x140006da0  movzx   eax, word ptr [rcx]
0x140006da3  mov     [rcx+2], ax
0x140006da7  mov     rax, rcx
0x140006daa  retn
```
