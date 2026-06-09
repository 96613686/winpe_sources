# TestStrokeRectangle

- ea: `0x18004e06c`
- end: `0x18004e20b`
- name: `TestStrokeRectangle`
- size: `415`
- prototype: `__int64 __fastcall(__int64, PATHOBJ *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e050`

## callees

- `0x180049d00`
- `0x18004c748`
- `0x18004e06c`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18004e0b8`
- `GDI32!PATHOBJ_bEnum` at `0x18004e0b8`
- `GDI32!PATHOBJ_vEnumStart` at `0x18004e0a5`
- `GDI32!PATHOBJ_vEnumStart` at `0x18004e0a5`

## pseudocode

```c
__int64 __fastcall TestStrokeRectangle(__int64 a1, PATHOBJ *a2, __int64 a3, int a4)
{
  ULONG count; // r9d
  POINTFIX *pptfx; // r10
  unsigned int i; // ecx
  int v11; // edx
  __int64 v12; // rax
  int v13; // r8d
  __int64 v14; // rax
  int v15; // r9d
  __int64 v16; // rdi
  int v17; // r10d
  int v18; // r9d
  int v19; // ebx
  int v20; // r8d
  _DWORD *v21; // r11
  int v22; // edx
  int v23; // ecx
  int v24; // eax
  int v25; // eax
  PATHDATA ppd; // [rsp+20h] [rbp-40h] BYREF
  int v28; // [rsp+30h] [rbp-30h]
  _DWORD v29[9]; // [rsp+34h] [rbp-2Ch]

  ppd = 0;
  PATHOBJ_vEnumStart(a2);
  if ( PATHOBJ_bEnum(a2, &ppd) )
    return 0;
  count = ppd.count;
  if ( ppd.count != 4 && (ppd.flags & 8) != 0 )
    return 0;
  if ( ppd.count != 5 && (ppd.flags & 8) == 0 || (ppd.flags & 0x11) != 1 )
    return 0;
  pptfx = ppd.pptfx;
  for ( i = 0; i <= 4; ++i )
  {
    if ( i != 4 || count == 5 )
    {
      v11 = pptfx->x >> 4;
      v12 = 2LL * i;
      v13 = pptfx->y >> 4;
      ++pptfx;
      v29[v12 - 1] = v11;
    }
    else
    {
      v11 = v28;
      v12 = 8;
      v13 = v29[0];
      v29[7] = v28;
    }
    v29[v12] = v13;
    if ( i )
    {
      v14 = i - 1;
      if ( v11 != v29[2 * v14 - 1] && v13 != v29[2 * v14] )
        return 0;
    }
  }
  v15 = 1;
  if ( a4 > 0 )
    v15 = a4;
  v16 = 0;
  v17 = v15 >> 1;
  v18 = v15 - (v15 >> 1);
  do
  {
    v19 = v29[2 * v16 - 1];
    v20 = v29[2 * v16];
    v21 = (_DWORD *)(*(_QWORD *)(a1 + 1760) + 16LL * *(unsigned int *)(a1 + 1768));
    v16 = (unsigned int)(v16 + 1);
    v22 = v29[2 * v16 - 1];
    v23 = v29[2 * v16];
    if ( v19 <= v22 )
    {
      v24 = v29[2 * v16 - 1];
      v22 = v19;
    }
    else
    {
      v24 = v19;
    }
    *v21 = v22 - v17;
    v21[2] = v18 + v24;
    if ( v20 <= v23 )
    {
      v25 = v23;
      v23 = v20;
    }
    else
    {
      v25 = v20;
    }
    v21[1] = v23 - v17;
    v21[3] = v18 + v25;
    AddRuleToList(a1, v21, a3);
  }
  while ( (unsigned int)v16 < 4 );
  return 1;
}

```

## disassembly

```asm
0x18004e06c  mov     [rsp-18h+arg_10], rbx
0x18004e071  mov     [rsp-18h+arg_18], rsi
0x18004e076  push    rbp
0x18004e077  push    rdi
0x18004e078  push    r14
0x18004e07a  mov     rbp, rsp
0x18004e07d  sub     rsp, 60h
0x18004e081  mov     rax, cs:__security_cookie
0x18004e088  xor     rax, rsp
0x18004e08b  mov     [rbp+var_8], rax
0x18004e08f  mov     rsi, rcx
0x18004e092  xorps   xmm0, xmm0
0x18004e095  mov     rcx, rdx; ppo
0x18004e098  mov     edi, r9d
0x18004e09b  movups  xmmword ptr [rbp+ppd.flags], xmm0
0x18004e09f  mov     r14, r8
0x18004e0a2  mov     rbx, rdx
0x18004e0a5  call    cs:__imp_PATHOBJ_vEnumStart
0x18004e0ac  nop     dword ptr [rax+rax+00h]
0x18004e0b1  lea     rdx, [rbp+ppd]; ppd
0x18004e0b5  mov     rcx, rbx; ppo
0x18004e0b8  call    cs:__imp_PATHOBJ_bEnum
0x18004e0bf  nop     dword ptr [rax+rax+00h]
0x18004e0c4  test    eax, eax
0x18004e0c6  jnz     loc_18004E1E7
0x18004e0cc  mov     r9d, [rbp+ppd.count]
0x18004e0d0  mov     eax, [rbp+ppd.flags]
0x18004e0d3  cmp     r9d, 4
0x18004e0d7  jz      short loc_18004E0E1
0x18004e0d9  test    al, 8
0x18004e0db  jnz     loc_18004E1E7
0x18004e0e1  cmp     r9d, 5
0x18004e0e5  jz      short loc_18004E0EF
0x18004e0e7  test    al, 8
0x18004e0e9  jz      loc_18004E1E7
0x18004e0ef  and     al, 11h
0x18004e0f1  cmp     al, 1
0x18004e0f3  jnz     loc_18004E1E7
0x18004e0f9  mov     r10, [rbp+ppd.pptfx]
0x18004e0fd  xor     ecx, ecx
0x18004e0ff  cmp     ecx, 4
0x18004e102  ja      short loc_18004E15A
0x18004e104  jnz     short loc_18004E11D
0x18004e106  cmp     r9d, 5
0x18004e10a  jz      short loc_18004E11D
0x18004e10c  mov     edx, [rbp+var_30]
0x18004e10f  mov     eax, 20h ; ' '
0x18004e114  mov     r8d, [rbp+var_2C]
0x18004e118  mov     [rbp+var_10], edx
0x18004e11b  jmp     short loc_18004E139
0x18004e11d  mov     edx, [r10]
0x18004e120  mov     r8d, [r10+4]
0x18004e124  sar     edx, 4
0x18004e127  mov     eax, ecx
0x18004e129  shl     rax, 3
0x18004e12d  sar     r8d, 4
0x18004e131  add     r10, 8
0x18004e135  mov     [rbp+rax+var_30], edx
0x18004e139  mov     [rbp+rax+var_2C], r8d
0x18004e13e  test    ecx, ecx
0x18004e140  jz      short loc_18004E156
0x18004e142  lea     eax, [rcx-1]
0x18004e145  cmp     edx, [rbp+rax*8+var_30]
0x18004e149  jz      short loc_18004E156
0x18004e14b  cmp     r8d, [rbp+rax*8+var_2C]
0x18004e150  jnz     loc_18004E1E7
0x18004e156  inc     ecx
0x18004e158  jmp     short loc_18004E0FF
0x18004e15a  test    edi, edi
0x18004e15c  mov     r9d, 1
0x18004e162  cmovg   r9d, edi
0x18004e166  xor     edi, edi
0x18004e168  mov     r10d, r9d
0x18004e16b  sar     r10d, 1
0x18004e16e  sub     r9d, r10d
0x18004e171  mov     ebx, [rbp+rdi*8+var_30]
0x18004e175  mov     r11d, [rsi+6E8h]
0x18004e17c  mov     r8d, [rbp+rdi*8+var_2C]
0x18004e181  shl     r11, 4
0x18004e185  add     r11, [rsi+6E0h]
0x18004e18c  inc     edi
0x18004e18e  mov     edx, [rbp+rdi*8+var_30]
0x18004e192  mov     ecx, [rbp+rdi*8+var_2C]
0x18004e196  cmp     ebx, edx
0x18004e198  jle     short loc_18004E19E
0x18004e19a  mov     eax, ebx
0x18004e19c  jmp     short loc_18004E1A2
0x18004e19e  mov     eax, edx
0x18004e1a0  mov     edx, ebx
0x18004e1a2  sub     edx, r10d
0x18004e1a5  add     eax, r9d
0x18004e1a8  mov     [r11], edx
0x18004e1ab  mov     [r11+8], eax
0x18004e1af  cmp     r8d, ecx
0x18004e1b2  jle     short loc_18004E1B9
0x18004e1b4  mov     eax, r8d
0x18004e1b7  jmp     short loc_18004E1BE
0x18004e1b9  mov     eax, ecx
0x18004e1bb  mov     ecx, r8d
0x18004e1be  sub     ecx, r10d
0x18004e1c1  mov     r8, r14
0x18004e1c4  mov     [r11+4], ecx
0x18004e1c8  mov     rdx, r11
0x18004e1cb  lea     ecx, [r9+rax]
0x18004e1cf  mov     [r11+0Ch], ecx
0x18004e1d3  mov     rcx, rsi
0x18004e1d6  call    AddRuleToList
0x18004e1db  cmp     edi, 4
0x18004e1de  jb      short loc_18004E171
0x18004e1e0  mov     eax, 1
0x18004e1e5  jmp     short loc_18004E1E9
0x18004e1e7  xor     eax, eax
0x18004e1e9  mov     rcx, [rbp+var_8]
0x18004e1ed  xor     rcx, rsp; StackCookie
0x18004e1f0  call    __security_check_cookie
0x18004e1f5  lea     r11, [rsp+60h+var_s0]
0x18004e1fa  mov     rbx, [r11+30h]
0x18004e1fe  mov     rsi, [r11+38h]
0x18004e202  mov     rsp, r11
0x18004e205  pop     r14
0x18004e207  pop     rdi
0x18004e208  pop     rbp
0x18004e209  retn
```
