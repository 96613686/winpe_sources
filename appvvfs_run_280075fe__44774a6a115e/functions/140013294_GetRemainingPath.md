# GetRemainingPath

- ea: `0x140013294`
- end: `0x14001337e`
- name: `GetRemainingPath`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008d50`
- `0x14000fd38`

## callees

- `0x140013294`

## pseudocode

```c
__int64 __fastcall GetRemainingPath(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  unsigned __int16 v3; // r9
  _WORD *v5; // r14
  unsigned __int16 v6; // r10
  unsigned __int16 v7; // dx
  __int16 v8; // r11
  __int16 v10; // r9

  v3 = *(_WORD *)a1 >> 1;
  if ( !v3 )
    return 3221225485LL;
  if ( a2 )
  {
    v5 = *(_WORD **)(a1 + 8);
    v6 = 0;
    v7 = *v5 == 92;
    if ( v7 >= v3 )
      return v6 < a2 ? 0xC000000D : 0;
    while ( 1 )
    {
      v8 = v5[v7];
      if ( v8 == 92 || v8 == 58 || v7 == v3 - 1 )
      {
        ++v6;
        if ( v8 == 58 && v6 < a2 )
          break;
      }
      if ( v6 == a2 )
      {
        if ( v8 == 92 || v8 == 58 )
        {
          v10 = 2 * (v3 - v7);
          *(_WORD *)a3 = v10;
          *(_WORD *)(a3 + 2) = v10;
          *(_QWORD *)(a3 + 8) = *(_QWORD *)(a1 + 8) + 2LL * v7;
        }
        else
        {
          *(_DWORD *)a3 = 0;
          *(_QWORD *)(a3 + 8) = 0;
        }
        return 0;
      }
      if ( ++v7 >= v3 )
        return v6 < a2 ? 0xC000000D : 0;
    }
    return 3221225485LL;
  }
  *(_OWORD *)a3 = *(_OWORD *)a1;
  return 0;
}

```

## disassembly

```asm
0x140013294  push    rbx
0x140013296  push    rbp
0x140013297  push    rsi
0x140013298  push    rdi
0x140013299  push    r14
0x14001329b  push    r15
0x14001329d  movzx   r9d, word ptr [rcx]
0x1400132a1  xor     ebp, ebp
0x1400132a3  shr     r9w, 1
0x1400132a7  movzx   ebx, dx
0x1400132aa  mov     rdi, rcx
0x1400132ad  jz      loc_14001336F
0x1400132b3  test    dx, dx
0x1400132b6  jnz     short loc_1400132C5
0x1400132b8  movups  xmm0, xmmword ptr [rcx]
0x1400132bb  movdqu  xmmword ptr [r8], xmm0
0x1400132c0  jmp     loc_14001336B
0x1400132c5  mov     r14, [rcx+8]
0x1400132c9  mov     edx, ebp
0x1400132cb  mov     r10d, ebp
0x1400132ce  cmp     word ptr [r14], 5Ch ; '\'
0x1400132d3  setz    dl
0x1400132d6  cmp     dx, r9w
0x1400132da  jnb     short loc_14001332A
0x1400132dc  mov     r15d, 1
0x1400132e2  movzx   esi, dx
0x1400132e5  movzx   r11d, word ptr [r14+rsi*2]
0x1400132ea  cmp     r11w, 5Ch ; '\'
0x1400132ef  jz      short loc_140013306
0x1400132f1  cmp     r11w, 3Ah ; ':'
0x1400132f6  jz      short loc_140013306
0x1400132f8  movzx   ecx, r9w
0x1400132fc  sub     ecx, r15d
0x1400132ff  movzx   eax, dx
0x140013302  cmp     eax, ecx
0x140013304  jnz     short loc_14001331A
0x140013306  add     r10w, r15w
0x14001330a  movzx   eax, r10w
0x14001330e  cmp     r11w, 3Ah ; ':'
0x140013313  jnz     short loc_14001331A
0x140013315  cmp     ax, bx
0x140013318  jb      short loc_14001336F
0x14001331a  cmp     r10w, bx
0x14001331e  jz      short loc_140013337
0x140013320  add     dx, r15w
0x140013324  cmp     dx, r9w
0x140013328  jb      short loc_1400132E2
0x14001332a  cmp     r10w, bx
0x14001332e  sbb     eax, eax
0x140013330  and     eax, 0C000000Dh
0x140013335  jmp     short loc_140013374
0x140013337  cmp     r11w, 5Ch ; '\'
0x14001333c  jz      short loc_14001334E
0x14001333e  cmp     r11w, 3Ah ; ':'
0x140013343  jz      short loc_14001334E
0x140013345  mov     [r8], ebp
0x140013348  mov     [r8+8], rbp
0x14001334c  jmp     short loc_14001336B
0x14001334e  sub     r9w, dx
0x140013352  add     r9w, r9w
0x140013356  mov     [r8], r9w
0x14001335a  mov     [r8+2], r9w
0x14001335f  mov     rax, [rdi+8]
0x140013363  lea     rcx, [rax+rsi*2]
0x140013367  mov     [r8+8], rcx
0x14001336b  xor     eax, eax
0x14001336d  jmp     short loc_140013374
0x14001336f  mov     eax, 0C000000Dh
0x140013374  pop     r15
0x140013376  pop     r14
0x140013378  pop     rdi
0x140013379  pop     rsi
0x14001337a  pop     rbp
0x14001337b  pop     rbx
0x14001337c  retn
```
