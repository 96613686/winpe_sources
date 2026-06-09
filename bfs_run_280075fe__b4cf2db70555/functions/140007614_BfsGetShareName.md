# BfsGetShareName

- ea: `0x140007614`
- end: `0x14000768c`
- name: `BfsGetShareName`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009b9c`

## callees

- `0x140007614`

## pseudocode

```c
__int64 __fastcall BfsGetShareName(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  unsigned __int16 v4; // cx
  __int64 v5; // r9
  unsigned __int16 v6; // ax
  unsigned __int16 v7; // dx

  v2 = *(_QWORD *)(a2 + 48);
  *(_OWORD *)a1 = 0;
  if ( v2 )
  {
    *(_QWORD *)(a1 + 8) = v2;
    v4 = *(_WORD *)(a2 + 40);
    *(_WORD *)a1 = v4;
    if ( v4 < 2u || (v4 -= 2, v5 = v2 + 2, *(_QWORD *)(a1 + 8) = v2 + 2, *(_WORD *)a1 = v4, v4 < 2u) )
    {
      v7 = v4;
    }
    else
    {
      v6 = v4;
      do
      {
        v7 = v6;
        if ( *(_WORD *)(v5 + 2LL * (unsigned __int16)((v6 >> 1) - 1)) != 92 )
          break;
        v4 -= 2;
        *(_WORD *)a1 = v4;
        v6 = v4;
        v7 = v4;
      }
      while ( v4 >= 2u );
    }
    *(_WORD *)(a1 + 2) = v7;
  }
  return a1;
}

```

## disassembly

```asm
0x140007614  mov     rax, [rdx+30h]
0x140007618  xorps   xmm0, xmm0
0x14000761b  mov     r8, rcx
0x14000761e  movups  xmmword ptr [rcx], xmm0
0x140007621  test    rax, rax
0x140007624  jz      short loc_140007688
0x140007626  mov     [rcx+8], rax
0x14000762a  mov     r10w, 2
0x14000762f  movzx   ecx, word ptr [rdx+28h]
0x140007633  mov     [r8], cx
0x140007637  cmp     cx, r10w
0x14000763b  jb      short loc_140007680
0x14000763d  sub     cx, r10w
0x140007641  lea     r9, [rax+2]
0x140007645  mov     [r8+8], r9
0x140007649  mov     [r8], cx
0x14000764d  cmp     cx, r10w
0x140007651  jb      short loc_140007680
0x140007653  movzx   eax, cx
0x140007656  movzx   edx, ax
0x140007659  shr     ax, 1
0x14000765c  dec     ax
0x14000765f  movzx   eax, ax
0x140007662  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140007668  jnz     short loc_140007683
0x14000766a  sub     cx, r10w
0x14000766e  mov     [r8], cx
0x140007672  movzx   eax, cx
0x140007675  movzx   edx, cx
0x140007678  cmp     cx, r10w
0x14000767c  jnb     short loc_140007656
0x14000767e  jmp     short loc_140007683
0x140007680  movzx   edx, cx
0x140007683  mov     [r8+2], dx
0x140007688  mov     rax, r8
0x14000768b  retn
```
