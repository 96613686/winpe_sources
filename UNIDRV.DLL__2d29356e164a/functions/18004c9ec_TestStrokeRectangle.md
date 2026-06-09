# TestStrokeRectangle

- ea: `0x18004c9ec`
- end: `0x18004cb7e`
- name: `TestStrokeRectangle`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d7d0`

## callees

- `0x1800487e0`
- `0x18004b140`
- `0x18004c9ec`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18004ca32`
- `GDI32!PATHOBJ_bEnum` at `0x18004ca32`
- `GDI32!PATHOBJ_vEnumStart` at `0x18004ca25`
- `GDI32!PATHOBJ_vEnumStart` at `0x18004ca25`

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
0x18004c9ec  mov     [rsp-18h+arg_10], rbx
0x18004c9f1  mov     [rsp-18h+arg_18], rsi
0x18004c9f6  push    rbp
0x18004c9f7  push    rdi
0x18004c9f8  push    r14
0x18004c9fa  mov     rbp, rsp
0x18004c9fd  sub     rsp, 60h
0x18004ca01  mov     rax, cs:__security_cookie
0x18004ca08  xor     rax, rsp
0x18004ca0b  mov     [rbp+var_8], rax
0x18004ca0f  mov     rsi, rcx
0x18004ca12  xorps   xmm0, xmm0
0x18004ca15  mov     rcx, rdx; ppo
0x18004ca18  mov     edi, r9d
0x18004ca1b  movups  xmmword ptr [rbp+ppd.flags], xmm0
0x18004ca1f  mov     r14, r8
0x18004ca22  mov     rbx, rdx
0x18004ca25  call    cs:__imp_PATHOBJ_vEnumStart
0x18004ca2b  lea     rdx, [rbp+ppd]; ppd
0x18004ca2f  mov     rcx, rbx; ppo
0x18004ca32  call    cs:__imp_PATHOBJ_bEnum
0x18004ca38  test    eax, eax
0x18004ca3a  jnz     loc_18004CB5B
0x18004ca40  mov     r9d, [rbp+ppd.count]
0x18004ca44  mov     eax, [rbp+ppd.flags]
0x18004ca47  cmp     r9d, 4
0x18004ca4b  jz      short loc_18004CA55
0x18004ca4d  test    al, 8
0x18004ca4f  jnz     loc_18004CB5B
0x18004ca55  cmp     r9d, 5
0x18004ca59  jz      short loc_18004CA63
0x18004ca5b  test    al, 8
0x18004ca5d  jz      loc_18004CB5B
0x18004ca63  and     al, 11h
0x18004ca65  cmp     al, 1
0x18004ca67  jnz     loc_18004CB5B
0x18004ca6d  mov     r10, [rbp+ppd.pptfx]
0x18004ca71  xor     ecx, ecx
0x18004ca73  cmp     ecx, 4
0x18004ca76  ja      short loc_18004CACE
0x18004ca78  jnz     short loc_18004CA91
0x18004ca7a  cmp     r9d, 5
0x18004ca7e  jz      short loc_18004CA91
0x18004ca80  mov     edx, [rbp+var_30]
0x18004ca83  mov     eax, 20h ; ' '
0x18004ca88  mov     r8d, [rbp+var_2C]
0x18004ca8c  mov     [rbp+var_10], edx
0x18004ca8f  jmp     short loc_18004CAAD
0x18004ca91  mov     edx, [r10]
0x18004ca94  mov     r8d, [r10+4]
0x18004ca98  sar     edx, 4
0x18004ca9b  mov     eax, ecx
0x18004ca9d  shl     rax, 3
0x18004caa1  sar     r8d, 4
0x18004caa5  add     r10, 8
0x18004caa9  mov     [rbp+rax+var_30], edx
0x18004caad  mov     [rbp+rax+var_2C], r8d
0x18004cab2  test    ecx, ecx
0x18004cab4  jz      short loc_18004CACA
0x18004cab6  lea     eax, [rcx-1]
0x18004cab9  cmp     edx, [rbp+rax*8+var_30]
0x18004cabd  jz      short loc_18004CACA
0x18004cabf  cmp     r8d, [rbp+rax*8+var_2C]
0x18004cac4  jnz     loc_18004CB5B
0x18004caca  inc     ecx
0x18004cacc  jmp     short loc_18004CA73
0x18004cace  test    edi, edi
0x18004cad0  mov     r9d, 1
0x18004cad6  cmovg   r9d, edi
0x18004cada  xor     edi, edi
0x18004cadc  mov     r10d, r9d
0x18004cadf  sar     r10d, 1
0x18004cae2  sub     r9d, r10d
0x18004cae5  mov     ebx, [rbp+rdi*8+var_30]
0x18004cae9  mov     r11d, [rsi+6E8h]
0x18004caf0  mov     r8d, [rbp+rdi*8+var_2C]
0x18004caf5  shl     r11, 4
0x18004caf9  add     r11, [rsi+6E0h]
0x18004cb00  inc     edi
0x18004cb02  mov     edx, [rbp+rdi*8+var_30]
0x18004cb06  mov     ecx, [rbp+rdi*8+var_2C]
0x18004cb0a  cmp     ebx, edx
0x18004cb0c  jle     short loc_18004CB12
0x18004cb0e  mov     eax, ebx
0x18004cb10  jmp     short loc_18004CB16
0x18004cb12  mov     eax, edx
0x18004cb14  mov     edx, ebx
0x18004cb16  sub     edx, r10d
0x18004cb19  add     eax, r9d
0x18004cb1c  mov     [r11], edx
0x18004cb1f  mov     [r11+8], eax
0x18004cb23  cmp     r8d, ecx
0x18004cb26  jle     short loc_18004CB2D
0x18004cb28  mov     eax, r8d
0x18004cb2b  jmp     short loc_18004CB32
0x18004cb2d  mov     eax, ecx
0x18004cb2f  mov     ecx, r8d
0x18004cb32  sub     ecx, r10d
0x18004cb35  mov     r8, r14
0x18004cb38  mov     [r11+4], ecx
0x18004cb3c  mov     rdx, r11
0x18004cb3f  lea     ecx, [r9+rax]
0x18004cb43  mov     [r11+0Ch], ecx
0x18004cb47  mov     rcx, rsi
0x18004cb4a  call    AddRuleToList
0x18004cb4f  cmp     edi, 4
0x18004cb52  jb      short loc_18004CAE5
0x18004cb54  mov     eax, 1
0x18004cb59  jmp     short loc_18004CB5D
0x18004cb5b  xor     eax, eax
0x18004cb5d  mov     rcx, [rbp+var_8]
0x18004cb61  xor     rcx, rsp; StackCookie
0x18004cb64  call    __security_check_cookie
0x18004cb69  lea     r11, [rsp+60h+var_s0]
0x18004cb6e  mov     rbx, [r11+30h]
0x18004cb72  mov     rsi, [r11+38h]
0x18004cb76  mov     rsp, r11
0x18004cb79  pop     r14
0x18004cb7b  pop     rdi
0x18004cb7c  pop     rbp
0x18004cb7d  retn
```
