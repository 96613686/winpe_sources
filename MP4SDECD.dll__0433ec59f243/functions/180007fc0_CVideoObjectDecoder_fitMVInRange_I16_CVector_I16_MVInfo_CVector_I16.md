# CVideoObjectDecoder::fitMVInRange_I16(CVector_I16 &,MVInfo &,CVector_I16 &)

- ea: `0x180007fc0`
- end: `0x1800081a2`
- name: `?fitMVInRange_I16@CVideoObjectDecoder@@AEAAXAEAVCVector_I16@@AEAUMVInfo@@0@Z`
- size: `482`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, struct CVector_I16 *, struct MVInfo *, struct CVector_I16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038e0`
- `0x1800065b0`
- `0x18000b748`

## callees

- `0x180007fc0`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::fitMVInRange_I16(
        CVideoObjectDecoder *this,
        struct CVector_I16 *a2,
        struct MVInfo *a3,
        struct CVector_I16 *a4)
{
  int v4; // ecx
  int v5; // r9d
  int v6; // eax
  int v7; // r8d
  __int16 v8; // ax
  __int16 v9; // ax
  int v10; // ecx
  int v11; // ecx
  __int16 v12; // ax
  int v13; // r8d
  int v14; // r8d
  __int16 v15; // cx
  __int16 v16; // ax

  if ( !*((_DWORD *)this + 18) || !*((_DWORD *)this + 19) )
  {
    v4 = *((_DWORD *)a3 + 1);
    v5 = *(__int16 *)a2;
    if ( v5 < -v4 )
    {
      *(_WORD *)a2 = v5 + 2 * v4;
    }
    else if ( v5 >= v4 )
    {
      *(_WORD *)a2 = v5 - 2 * v4;
    }
    v6 = *((_DWORD *)a3 + 1);
    v7 = *((__int16 *)a2 + 1);
    if ( v7 < -v6 )
    {
      *((_WORD *)a2 + 1) = v7 + 2 * v6;
    }
    else if ( v7 >= v6 )
    {
      *((_WORD *)a2 + 1) = v7 - 2 * v6;
    }
    return;
  }
  if ( *(__int16 *)a4 < -31 && *(__int16 *)a2 < -63 )
    *(_WORD *)a2 += 64;
  if ( *(__int16 *)a4 > 32 && *(__int16 *)a2 > 63 )
    *(_WORD *)a2 -= 64;
  if ( *((__int16 *)a4 + 1) < -31 )
  {
    v8 = *((_WORD *)a2 + 1);
    if ( v8 < -63 )
      *((_WORD *)a2 + 1) = v8 + 64;
  }
  if ( *((__int16 *)a4 + 1) > 32 )
  {
    v9 = *((_WORD *)a2 + 1);
    if ( v9 > 63 )
      *((_WORD *)a2 + 1) = v9 - 64;
  }
  v10 = *(__int16 *)a4;
  if ( (unsigned __int16)(*(_WORD *)a4 + 63) > 0x1Fu )
  {
    if ( (unsigned __int16)(v10 + 31) > 0x3Fu )
    {
      if ( (unsigned __int16)(v10 - 33) > 0x1Eu || *(__int16 *)a2 < 0 )
      {
LABEL_27:
        *(_WORD *)a2 = 0;
        goto LABEL_28;
      }
      if ( *(__int16 *)a2 > 63 )
        *(_WORD *)a2 = 63;
    }
    else
    {
      v13 = *(__int16 *)a2;
      if ( v13 >= v10 - 32 )
      {
        if ( v13 > v10 + 31 )
          *(_WORD *)a2 = v10 + 31;
      }
      else
      {
        *(_WORD *)a2 = v10 - 32;
      }
    }
  }
  else
  {
    if ( *(__int16 *)a2 < -63 )
    {
      *(_WORD *)a2 = -63;
      goto LABEL_28;
    }
    if ( *(__int16 *)a2 > 0 )
      goto LABEL_27;
  }
LABEL_28:
  v11 = *((__int16 *)a4 + 1);
  if ( (unsigned __int16)(*((_WORD *)a4 + 1) + 63) > 0x1Fu )
  {
    if ( (unsigned __int16)(v11 + 31) <= 0x3Fu )
    {
      v14 = *((__int16 *)a2 + 1);
      if ( v14 >= v11 - 32 )
      {
        if ( v14 <= v11 + 31 )
          return;
        v15 = v11 + 31;
      }
      else
      {
        v15 = v11 - 32;
      }
      *((_WORD *)a2 + 1) = v15;
      return;
    }
    if ( (unsigned __int16)(v11 - 33) > 0x1Eu || (v16 = *((_WORD *)a2 + 1), v16 < 0) )
    {
LABEL_41:
      *((_WORD *)a2 + 1) = 0;
      return;
    }
    if ( v16 > 63 )
      *((_WORD *)a2 + 1) = 63;
  }
  else
  {
    v12 = *((_WORD *)a2 + 1);
    if ( v12 < -63 )
    {
      *((_WORD *)a2 + 1) = -63;
      return;
    }
    if ( v12 > 0 )
      goto LABEL_41;
  }
}

```

## disassembly

```asm
0x180007fc0  sub     rsp, 8
0x180007fc4  cmp     dword ptr [rcx+48h], 0
0x180007fc8  jnz     short loc_18000802E
0x180007fca  mov     ecx, [r8+4]
0x180007fce  mov     eax, ecx
0x180007fd0  movsx   r9d, word ptr [rdx]
0x180007fd4  neg     eax
0x180007fd6  cmp     r9d, eax
0x180007fd9  jl      loc_180008193
0x180007fdf  cmp     r9d, ecx
0x180007fe2  jge     short loc_180008000
0x180007fe4  mov     eax, [r8+4]
0x180007fe8  mov     ecx, eax
0x180007fea  movsx   r8d, word ptr [rdx+2]
0x180007fef  neg     ecx
0x180007ff1  cmp     r8d, ecx
0x180007ff4  jl      short loc_18000800D
0x180007ff6  cmp     r8d, eax
0x180007ff9  jge     short loc_18000801D
0x180007ffb  add     rsp, 8
0x180007fff  retn
0x180008000  add     cx, cx
0x180008003  sub     r9w, cx
0x180008007  mov     [rdx], r9w
0x18000800b  jmp     short loc_180007FE4
0x18000800d  add     ax, ax
0x180008010  add     ax, r8w
0x180008014  mov     [rdx+2], ax
0x180008018  add     rsp, 8
0x18000801c  retn
0x18000801d  add     ax, ax
0x180008020  sub     r8w, ax
0x180008024  mov     [rdx+2], r8w
0x180008029  add     rsp, 8
0x18000802d  retn
0x18000802e  cmp     dword ptr [rcx+4Ch], 0
0x180008032  jz      short loc_180007FCA
0x180008034  cmp     word ptr [r9], 0FFE1h
0x180008039  mov     [rsp+8+var_8], rbx
0x18000803d  jge     short loc_18000804F
0x18000803f  movzx   eax, word ptr [rdx]
0x180008042  cmp     ax, 0FFC1h
0x180008046  jge     short loc_18000804F
0x180008048  add     ax, 40h ; '@'
0x18000804c  mov     [rdx], ax
0x18000804f  cmp     word ptr [r9], 20h ; ' '
0x180008054  jle     short loc_180008066
0x180008056  movzx   eax, word ptr [rdx]
0x180008059  cmp     ax, 3Fh ; '?'
0x18000805d  jle     short loc_180008066
0x18000805f  sub     ax, 40h ; '@'
0x180008063  mov     [rdx], ax
0x180008066  cmp     word ptr [r9+2], 0FFE1h
0x18000806c  jge     short loc_180008080
0x18000806e  movzx   eax, word ptr [rdx+2]
0x180008072  cmp     ax, 0FFC1h
0x180008076  jge     short loc_180008080
0x180008078  add     ax, 40h ; '@'
0x18000807c  mov     [rdx+2], ax
0x180008080  cmp     word ptr [r9+2], 20h ; ' '
0x180008086  jle     short loc_18000809A
0x180008088  movzx   eax, word ptr [rdx+2]
0x18000808c  cmp     ax, 3Fh ; '?'
0x180008090  jle     short loc_18000809A
0x180008092  sub     ax, 40h ; '@'
0x180008096  mov     [rdx+2], ax
0x18000809a  movsx   ecx, word ptr [r9]
0x18000809e  mov     ebx, 3Fh ; '?'
0x1800080a3  mov     r11d, 0FFFFFFC1h
0x1800080a9  lea     eax, [rcx+3Fh]
0x1800080ac  cmp     ax, 1Fh
0x1800080b0  ja      short loc_1800080EA
0x1800080b2  movzx   eax, word ptr [rdx]
0x1800080b5  cmp     ax, r11w
0x1800080b9  jge     short loc_1800080C1
0x1800080bb  mov     [rdx], r11w
0x1800080bf  jmp     short loc_1800080CB
0x1800080c1  test    ax, ax
0x1800080c4  jle     short loc_1800080CB
0x1800080c6  xor     eax, eax
0x1800080c8  mov     [rdx], ax
0x1800080cb  movsx   ecx, word ptr [r9+2]
0x1800080d0  lea     eax, [rcx+3Fh]
0x1800080d3  cmp     ax, 1Fh
0x1800080d7  ja      short loc_180008141
0x1800080d9  movzx   eax, word ptr [rdx+2]
0x1800080dd  cmp     ax, r11w
0x1800080e1  jge     short loc_180008134
0x1800080e3  mov     [rdx+2], r11w
0x1800080e8  jmp     short loc_18000815E
0x1800080ea  lea     eax, [rcx+1Fh]
0x1800080ed  cmp     ax, bx
0x1800080f0  ja      short loc_180008118
0x1800080f2  movsx   r8d, word ptr [rdx]
0x1800080f6  lea     eax, [rcx-20h]
0x1800080f9  cmp     r8d, eax
0x1800080fc  jge     short loc_180008107
0x1800080fe  sub     cx, 20h ; ' '
0x180008102  mov     [rdx], cx
0x180008105  jmp     short loc_1800080CB
0x180008107  lea     eax, [rcx+1Fh]
0x18000810a  cmp     r8d, eax
0x18000810d  jle     short loc_1800080CB
0x18000810f  add     cx, 1Fh
0x180008113  mov     [rdx], cx
0x180008116  jmp     short loc_1800080CB
0x180008118  sub     cx, 21h ; '!'
0x18000811c  cmp     cx, 1Eh
0x180008120  ja      short loc_1800080C6
0x180008122  movzx   eax, word ptr [rdx]
0x180008125  test    ax, ax
0x180008128  js      short loc_1800080C6
0x18000812a  cmp     ax, bx
0x18000812d  jle     short loc_1800080CB
0x18000812f  mov     [rdx], bx
0x180008132  jmp     short loc_1800080CB
0x180008134  test    ax, ax
0x180008137  jle     short loc_18000815E
0x180008139  xor     eax, eax
0x18000813b  mov     [rdx+2], ax
0x18000813f  jmp     short loc_18000815E
0x180008141  lea     eax, [rcx+1Fh]
0x180008144  cmp     ax, bx
0x180008147  ja      short loc_180008175
0x180008149  movsx   r8d, word ptr [rdx+2]
0x18000814e  lea     eax, [rcx-20h]
0x180008151  cmp     r8d, eax
0x180008154  jge     short loc_180008167
0x180008156  sub     cx, 20h ; ' '
0x18000815a  mov     [rdx+2], cx
0x18000815e  mov     rbx, [rsp+8+var_8]
0x180008162  jmp     loc_180007FFB
0x180008167  lea     eax, [rcx+1Fh]
0x18000816a  cmp     r8d, eax
0x18000816d  jle     short loc_18000815E
0x18000816f  add     cx, 1Fh
0x180008173  jmp     short loc_18000815A
0x180008175  sub     cx, 21h ; '!'
0x180008179  cmp     cx, 1Eh
0x18000817d  ja      short loc_180008139
0x18000817f  movzx   eax, word ptr [rdx+2]
0x180008183  test    ax, ax
0x180008186  js      short loc_180008139
0x180008188  cmp     ax, bx
0x18000818b  jle     short loc_18000815E
0x18000818d  mov     [rdx+2], bx
0x180008191  jmp     short loc_18000815E
0x180008193  add     cx, cx
0x180008196  add     cx, r9w
0x18000819a  mov     [rdx], cx
0x18000819d  jmp     loc_180007FE4
```
