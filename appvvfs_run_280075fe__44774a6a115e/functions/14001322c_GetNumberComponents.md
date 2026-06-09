# GetNumberComponents

- ea: `0x14001322c`
- end: `0x14001328e`
- name: `GetNumberComponents`
- size: `98`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400034a0`
- `0x14000a088`
- `0x14000fd38`
- `0x140013030`
- `0x140013384`
- `0x14001360c`

## callees

- `0x14001322c`

## pseudocode

```c
__int64 __fastcall GetNumberComponents(__int64 a1)
{
  unsigned __int16 v1; // r10
  unsigned __int16 v2; // r9
  _WORD *v3; // r11
  unsigned __int16 i; // r8

  v1 = 0;
  v2 = *(_WORD *)a1 >> 1;
  if ( v2 )
  {
    v3 = *(_WORD **)(a1 + 8);
    for ( i = *v3 == 92; i < v2; ++i )
    {
      if ( v3[i] == 92 || i == v2 - 1 )
        ++v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x14001322c  mov     [rsp+arg_0], rbx
0x140013231  movzx   r9d, word ptr [rcx]
0x140013235  mov     r10d, 0
0x14001323b  shr     r9w, 1
0x14001323f  jz      short loc_140013283
0x140013241  mov     r11, [rcx+8]
0x140013245  xor     r8d, r8d
0x140013248  cmp     word ptr [r11], 5Ch ; '\'
0x14001324d  setz    r8b
0x140013251  cmp     r8w, r9w
0x140013255  jnb     short loc_140013283
0x140013257  lea     ebx, [r10+1]
0x14001325b  movzx   eax, r8w
0x14001325f  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x140013265  jz      short loc_140013275
0x140013267  movzx   edx, r9w
0x14001326b  sub     edx, ebx
0x14001326d  movzx   ecx, r8w
0x140013271  cmp     ecx, edx
0x140013273  jnz     short loc_140013279
0x140013275  add     r10w, bx
0x140013279  add     r8w, bx
0x14001327d  cmp     r8w, r9w
0x140013281  jb      short loc_14001325B
0x140013283  mov     rbx, [rsp+arg_0]
0x140013288  movzx   eax, r10w
0x14001328c  retn
```
