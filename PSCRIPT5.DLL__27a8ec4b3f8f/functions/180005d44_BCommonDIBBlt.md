# BCommonDIBBlt

- ea: `0x180005d44`
- end: `0x180006162`
- name: `BCommonDIBBlt`
- size: `1054`
- prototype: `_BOOL8 __fastcall(_DWORD *, SURFOBJ *, __int64, __int64, int *, int *, _DWORD *, __int64, int, _DWORD *)`
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800068c0`
- `0x180006a80`
- `0x180006f30`
- `0x180007300`
- `0x1800074d0`

## callees

- `0x180005c18`
- `0x180005d44`
- `0x180006304`
- `0x180012200`
- `0x18001259c`
- `0x1800129f0`
- `0x180012a50`
- `0x180012e18`
- `0x1800166c0`
- `0x1800170a0`
- `0x180017340`
- `0x18001743c`
- `0x18001758c`
- `0x180019250`
- `0x180019508`
- `0x180019728`
- `0x180019fa0`
- `0x180021290`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005dbb`
- `KERNEL32!SetLastError` at `0x180005dbb`
- `KERNEL32!LocalFree` at `0x18000613e`
- `KERNEL32!LocalFree` at `0x18000613e`
- `GDI32!XLATEOBJ_piVector` at `0x180006072`
- `GDI32!XLATEOBJ_piVector` at `0x180006072`

## pseudocode

```c
_BOOL8 __fastcall BCommonDIBBlt(
        _DWORD *a1,
        SURFOBJ *a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int *a6,
        _DWORD *a7,
        __int64 a8,
        int a9,
        _DWORD *a10)
{
  __int64 v13; // rcx
  LONG cx; // eax
  LONG cy; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  int v20; // ecx
  float v21; // xmm3_4
  float v22; // xmm2_4
  int v23; // edx
  int v24; // ecx
  ULONG *v25; // r12
  void *v26; // rcx
  int v27; // [rsp+40h] [rbp-38h] BYREF
  int v28; // [rsp+44h] [rbp-34h]
  int v29; // [rsp+48h] [rbp-30h]
  int v30; // [rsp+4Ch] [rbp-2Ch]
  __int128 v31; // [rsp+50h] [rbp-28h] BYREF
  int v32; // [rsp+60h] [rbp-18h]

  v32 = 0;
  v31 = 0;
  if ( !(unsigned int)SMChangeState((__int64)a1, 5) )
    return 0;
  if ( a2->iBitmapFormat == 9 )
  {
    if ( *a5 == a5[2]
      || a5[1] == a5[3]
      || !(unsigned int)BJPEGFormatSupported(v13, a2->cjBits, (unsigned __int8 *)a2->pvBits, &v31) )
    {
      SetLastError(0x32u);
      return 0;
    }
  }
  else if ( !BGetDIBInfo((_DWORD *)a8, a2, a4, (__int64)a1) )
  {
    return 0;
  }
  if ( a10 )
    *a10 = 0;
  if ( !*(_DWORD *)(a8 + 28) )
    goto LABEL_23;
  if ( *(_DWORD *)(a8 + 4) != 1 && *(_DWORD *)(a8 + 4) != 4 )
  {
    if ( *(_DWORD *)(a8 + 4) == 8 )
    {
      if ( a1[177] )
        goto LABEL_20;
    }
    else if ( *(_DWORD *)(a8 + 4) == 24 || *(_DWORD *)(a8 + 4) == 32 )
    {
      goto LABEL_20;
    }
    if ( *(_DWORD *)a8 != 1 )
      goto LABEL_21;
  }
LABEL_20:
  if ( *(_DWORD *)a8 >= 0x10u )
  {
LABEL_21:
    if ( a10 )
      *a10 = 1;
    return 0;
  }
LABEL_23:
  if ( *a5 < 0 )
    *a5 = 0;
  if ( a5[1] < 0 )
    a5[1] = 0;
  cx = a2->sizlBitmap.cx;
  if ( a5[2] > cx )
    a5[2] = cx;
  cy = a2->sizlBitmap.cy;
  if ( a5[3] > cy )
    a5[3] = cy;
  PSProcsetSend(a1, 17);
  if ( a7 )
    a1[538] |= 0x200u;
  if ( a6 && a9 )
  {
    v17 = a6[2];
    if ( *a6 >= v17 )
    {
      v29 = *a6;
      v27 = v17;
    }
    else
    {
      v27 = *a6;
      v29 = v17;
    }
    v18 = a6[3];
    if ( a6[1] >= v18 )
    {
      v30 = a6[1];
      v28 = v18;
    }
    else
    {
      v28 = a6[1];
      v30 = v18;
    }
    GSSendAttributes((__int64)a1, a4, 0, 0, a3, &v27);
  }
  else
  {
    GSSendAttributes((__int64)a1, a4, 0, 0, a3, a6);
  }
  if ( a7 )
    a1[538] &= ~0x200u;
  GSSendGsave((__int64)a1);
  if ( a7 )
    BChangeTransMatrix((__int64)a1, a7, a6);
  if ( a2->iBitmapFormat == 9 )
  {
    if ( *a5 || a5[1] || a5[2] != a2->sizlBitmap.cx || a5[3] != a2->sizlBitmap.cy )
    {
      OPSendInt((__int64)a1, *a6);
      OPSendInt((__int64)a1, a6[1]);
      OPSendInt((__int64)a1, a6[2] - *a6);
      OPSendInt((__int64)a1, a6[3] - a6[1]);
      OPRawPortWrite((__int64)a1, "rc ", 3u);
      v20 = a6[1];
      v21 = (float)(a6[2] - *a6) / (float)(a5[2] - *a5);
      v22 = (float)(a6[3] - v20) / (float)(a5[3] - a5[1]);
      v23 = *a6 - (int)(float)((float)*a5 * v21);
      *a6 = v23;
      v24 = v20 - (int)(float)((float)a5[1] * v22);
      a6[1] = v24;
      a6[2] = v23 + (int)(float)((float)a2->sizlBitmap.cx * v21);
      a6[3] = v24 + (int)(float)((float)a2->sizlBitmap.cy * v22);
    }
    OPSendJPEGImage((__int64)a1, (__int64)a2, a6, (int *)&v31);
  }
  else
  {
    if ( *(_DWORD *)a8 == 1 && (*(_BYTE *)(a8 + 12) & 0x10) == 0 && !*(_DWORD *)(a8 + 28) )
    {
      if ( (*(_BYTE *)(a4 + 4) & 2) != 0
        && ((v25 = *(ULONG **)(a4 + 16)) != 0 || (v25 = XLATEOBJ_piVector((XLATEOBJ *)a4)) != 0) )
      {
        GSSendGsave((__int64)a1);
        GBSendRect((__int64)a1, a6, 1);
        GSSendColor((__int64)a1, v25[1], 3);
        OPSendOperator((__int64)a1, 9u);
        GSSendGrestore((__int64)a1);
      }
      else
      {
        a1[860] = 1;
      }
    }
    GBBitmapHeader((__int64)a1, v19, a8, a5, a6, (XLATEOBJ *)a4, *(_DWORD *)(a8 + 28), *(_DWORD *)(a8 + 32));
    GBBitmapOperator((__int64)a1, a4, a8);
    GBBitmapData((__int64)a1, (__int64)a2, a5, a4, a8);
  }
  GSSendGrestore((__int64)a1);
  if ( a2->iBitmapFormat != 9 && (*(_DWORD *)(a8 + 12) & 0x2000) != 0 )
  {
    v26 = *(void **)(a8 + 40);
    if ( v26 )
      LocalFree(v26);
    *(_QWORD *)(a8 + 40) = 0;
  }
  return a1[860] == 0;
}

```

## disassembly

```asm
0x180005d44  mov     [rsp-40h+arg_10], r8
0x180005d49  push    rbp
0x180005d4a  push    rbx
0x180005d4b  push    rsi
0x180005d4c  push    rdi
0x180005d4d  push    r12
0x180005d4f  push    r13
0x180005d51  push    r14
0x180005d53  push    r15
0x180005d55  mov     rbp, rsp
0x180005d58  sub     rsp, 78h
0x180005d5c  xor     eax, eax
0x180005d5e  mov     r14, rdx
0x180005d61  xorps   xmm0, xmm0
0x180005d64  mov     [rbp+var_18], eax
0x180005d67  mov     r13, r9
0x180005d6a  mov     rbx, rcx
0x180005d6d  movups  [rbp+var_28], xmm0
0x180005d71  lea     edx, [rax+5]
0x180005d74  call    SMChangeState
0x180005d79  xor     r15d, r15d
0x180005d7c  test    eax, eax
0x180005d7e  jz      short loc_180005DC7
0x180005d80  cmp     dword ptr [r14+48h], 9
0x180005d85  mov     rsi, [rbp+arg_38]
0x180005d8c  mov     rdi, [rbp+arg_20]
0x180005d90  jnz     short loc_180005DDB
0x180005d92  mov     eax, [rdi+8]
0x180005d95  cmp     [rdi], eax
0x180005d97  jz      short loc_180005DB6
0x180005d99  mov     eax, [rdi+0Ch]
0x180005d9c  cmp     [rdi+4], eax
0x180005d9f  jz      short loc_180005DB6
0x180005da1  mov     r8, [r14+30h]
0x180005da5  lea     r9, [rbp+var_28]
0x180005da9  mov     edx, [r14+28h]
0x180005dad  call    BJPEGFormatSupported
0x180005db2  test    eax, eax
0x180005db4  jnz     short loc_180005DF0
0x180005db6  mov     ecx, 32h ; '2'; dwErrCode
0x180005dbb  call    cs:__imp_SetLastError
0x180005dc2  nop     dword ptr [rax+rax+00h]
0x180005dc7  xor     eax, eax
0x180005dc9  add     rsp, 78h
0x180005dcd  pop     r15
0x180005dcf  pop     r14
0x180005dd1  pop     r13
0x180005dd3  pop     r12
0x180005dd5  pop     rdi
0x180005dd6  pop     rsi
0x180005dd7  pop     rbx
0x180005dd8  pop     rbp
0x180005dd9  retn
0x180005ddb  mov     r9, rbx
0x180005dde  mov     r8, r13
0x180005de1  mov     rdx, r14
0x180005de4  mov     rcx, rsi
0x180005de7  call    BGetDIBInfo
0x180005dec  test    eax, eax
0x180005dee  jz      short loc_180005DC7
0x180005df0  mov     rdx, [rbp+arg_48]
0x180005df7  test    rdx, rdx
0x180005dfa  jz      short loc_180005DFF
0x180005dfc  mov     [rdx], r15d
0x180005dff  cmp     [rsi+1Ch], r15d
0x180005e03  jz      short loc_180005E43
0x180005e05  mov     ecx, [rsi+4]
0x180005e08  sub     ecx, 1
0x180005e0b  jz      short loc_180005E31
0x180005e0d  sub     ecx, 3
0x180005e10  jz      short loc_180005E31
0x180005e12  sub     ecx, 4
0x180005e15  jz      short loc_180005E23
0x180005e17  sub     ecx, 10h
0x180005e1a  jz      short loc_180005E31
0x180005e1c  cmp     ecx, 8
0x180005e1f  jz      short loc_180005E31
0x180005e21  jmp     short loc_180005E2C
0x180005e23  cmp     [rbx+2C4h], r15d
0x180005e2a  jnz     short loc_180005E31
0x180005e2c  cmp     dword ptr [rsi], 1
0x180005e2f  jnz     short loc_180005E36
0x180005e31  cmp     dword ptr [rsi], 10h
0x180005e34  jb      short loc_180005E43
0x180005e36  test    rdx, rdx
0x180005e39  jz      short loc_180005DC7
0x180005e3b  mov     dword ptr [rdx], 1
0x180005e41  jmp     short loc_180005DC7
0x180005e43  cmp     [rdi], r15d
0x180005e46  jge     short loc_180005E4B
0x180005e48  mov     [rdi], r15d
0x180005e4b  cmp     [rdi+4], r15d
0x180005e4f  jge     short loc_180005E55
0x180005e51  mov     [rdi+4], r15d
0x180005e55  mov     eax, [r14+20h]
0x180005e59  cmp     [rdi+8], eax
0x180005e5c  jle     short loc_180005E61
0x180005e5e  mov     [rdi+8], eax
0x180005e61  mov     eax, [r14+24h]
0x180005e65  cmp     [rdi+0Ch], eax
0x180005e68  jle     short loc_180005E6D
0x180005e6a  mov     [rdi+0Ch], eax
0x180005e6d  mov     edx, 11h
0x180005e72  mov     rcx, rbx
0x180005e75  call    PSProcsetSend
0x180005e7a  mov     r12, [rbp+arg_30]
0x180005e7e  test    r12, r12
0x180005e81  jz      short loc_180005E8B
0x180005e83  bts     dword ptr [rbx+868h], 9
0x180005e8b  mov     r15, [rbp+arg_28]
0x180005e8f  test    r15, r15
0x180005e92  jz      short loc_180005EDB
0x180005e94  cmp     [rbp+arg_40], 0
0x180005e9b  jz      short loc_180005EDB
0x180005e9d  mov     eax, [r15+8]
0x180005ea1  mov     ecx, [r15]
0x180005ea4  cmp     ecx, eax
0x180005ea6  jge     short loc_180005EB0
0x180005ea8  mov     [rbp+var_38], ecx
0x180005eab  mov     [rbp+var_30], eax
0x180005eae  jmp     short loc_180005EB6
0x180005eb0  mov     [rbp+var_30], ecx
0x180005eb3  mov     [rbp+var_38], eax
0x180005eb6  mov     eax, [r15+0Ch]
0x180005eba  mov     ecx, [r15+4]
0x180005ebe  cmp     ecx, eax
0x180005ec0  jge     short loc_180005ECA
0x180005ec2  mov     [rbp+var_34], ecx
0x180005ec5  mov     [rbp+var_2C], eax
0x180005ec8  jmp     short loc_180005ED0
0x180005eca  mov     [rbp+var_2C], ecx
0x180005ecd  mov     [rbp+var_34], eax
0x180005ed0  lea     rax, [rbp+var_38]
0x180005ed4  mov     [rsp+78h+pxlo], rax
0x180005ed9  jmp     short loc_180005EE0
0x180005edb  mov     [rsp+78h+pxlo], r15
0x180005ee0  mov     rax, [rbp+arg_10]
0x180005ee4  xor     r9d, r9d
0x180005ee7  xor     r8d, r8d
0x180005eea  mov     [rsp+78h+var_58], rax
0x180005eef  mov     rdx, r13
0x180005ef2  mov     rcx, rbx
0x180005ef5  call    GSSendAttributes
0x180005efa  test    r12, r12
0x180005efd  jz      short loc_180005F07
0x180005eff  btr     dword ptr [rbx+868h], 9
0x180005f07  mov     rcx, rbx
0x180005f0a  call    GSSendGsave
0x180005f0f  test    r12, r12
0x180005f12  jz      short loc_180005F22
0x180005f14  mov     r8, r15
0x180005f17  mov     rdx, r12
0x180005f1a  mov     rcx, rbx
0x180005f1d  call    BChangeTransMatrix
0x180005f22  cmp     dword ptr [r14+48h], 9
0x180005f27  jnz     loc_18000604A
0x180005f2d  cmp     dword ptr [rdi], 0
0x180005f30  jnz     short loc_180005F4E
0x180005f32  cmp     dword ptr [rdi+4], 0
0x180005f36  jnz     short loc_180005F4E
0x180005f38  mov     eax, [r14+20h]
0x180005f3c  cmp     [rdi+8], eax
0x180005f3f  jnz     short loc_180005F4E
0x180005f41  mov     eax, [r14+24h]
0x180005f45  cmp     [rdi+0Ch], eax
0x180005f48  jz      loc_180006033
0x180005f4e  mov     edx, [r15]
0x180005f51  mov     rcx, rbx
0x180005f54  call    OPSendInt
0x180005f59  mov     edx, [r15+4]
0x180005f5d  mov     rcx, rbx
0x180005f60  call    OPSendInt
0x180005f65  mov     edx, [r15+8]
0x180005f69  mov     rcx, rbx
0x180005f6c  sub     edx, [r15]
0x180005f6f  call    OPSendInt
0x180005f74  mov     edx, [r15+0Ch]
0x180005f78  mov     rcx, rbx
0x180005f7b  sub     edx, [r15+4]
0x180005f7f  call    OPSendInt
0x180005f84  mov     r8d, 3
0x180005f8a  lea     rdx, PSFRAG_rc; "rc "
0x180005f91  mov     rcx, rbx
0x180005f94  call    OPRawPortWrite
0x180005f99  movd    xmm1, dword ptr [rdi]
0x180005f9d  mov     edx, [r15]
0x180005fa0  mov     ecx, [r15+4]
0x180005fa4  mov     eax, [r15+8]
0x180005fa8  sub     eax, edx
0x180005faa  cvtdq2ps xmm1, xmm1
0x180005fad  movd    xmm3, eax
0x180005fb1  mov     eax, [rdi+8]
0x180005fb4  sub     eax, [rdi]
0x180005fb6  cvtdq2ps xmm3, xmm3
0x180005fb9  movd    xmm0, eax
0x180005fbd  mov     eax, [r15+0Ch]
0x180005fc1  cvtdq2ps xmm0, xmm0
0x180005fc4  sub     eax, ecx
0x180005fc6  movd    xmm2, eax
0x180005fca  mov     eax, [rdi+0Ch]
0x180005fcd  sub     eax, [rdi+4]
0x180005fd0  divss   xmm3, xmm0
0x180005fd4  movd    xmm0, eax
0x180005fd8  cvtdq2ps xmm0, xmm0
0x180005fdb  cvtdq2ps xmm2, xmm2
0x180005fde  mulss   xmm1, xmm3
0x180005fe2  divss   xmm2, xmm0
0x180005fe6  cvttss2si eax, xmm1
0x180005fea  sub     edx, eax
0x180005fec  mov     [r15], edx
0x180005fef  movd    xmm0, dword ptr [rdi+4]
0x180005ff4  cvtdq2ps xmm0, xmm0
0x180005ff7  mulss   xmm0, xmm2
0x180005ffb  cvttss2si eax, xmm0
0x180005fff  sub     ecx, eax
0x180006001  mov     [r15+4], ecx
0x180006005  movd    xmm0, dword ptr [r14+20h]
0x18000600b  cvtdq2ps xmm0, xmm0
0x18000600e  mulss   xmm0, xmm3
0x180006012  cvttss2si eax, xmm0
0x180006016  add     eax, edx
0x180006018  mov     [r15+8], eax
0x18000601c  movd    xmm0, dword ptr [r14+24h]
0x180006022  cvtdq2ps xmm0, xmm0
0x180006025  mulss   xmm0, xmm2
0x180006029  cvttss2si eax, xmm0
0x18000602d  add     eax, ecx
0x18000602f  mov     [r15+0Ch], eax
0x180006033  lea     r9, [rbp+var_28]
0x180006037  mov     r8, r15
0x18000603a  mov     rdx, r14
0x18000603d  mov     rcx, rbx
0x180006040  call    OPSendJPEGImage
0x180006045  jmp     loc_18000611D
0x18000604a  cmp     dword ptr [rsi], 1
0x18000604d  jnz     loc_1800060D3
0x180006053  test    byte ptr [rsi+0Ch], 10h
0x180006057  jnz     short loc_1800060D3
0x180006059  cmp     dword ptr [rsi+1Ch], 0
0x18000605d  jnz     short loc_1800060D3
0x18000605f  test    byte ptr [r13+4], 2
0x180006064  jz      short loc_1800060C9
0x180006066  mov     r12, [r13+10h]
0x18000606a  test    r12, r12
0x18000606d  jnz     short loc_180006086
0x18000606f  mov     rcx, r13; pxlo
0x180006072  call    cs:__imp_XLATEOBJ_piVector
0x180006079  nop     dword ptr [rax+rax+00h]
0x18000607e  mov     r12, rax
0x180006081  test    rax, rax
0x180006084  jz      short loc_1800060C9
0x180006086  mov     rcx, rbx
0x180006089  call    GSSendGsave
0x18000608e  mov     r8d, 1
0x180006094  mov     rdx, r15
0x180006097  mov     rcx, rbx
0x18000609a  call    GBSendRect
0x18000609f  mov     edx, [r12+4]
0x1800060a4  mov     r8d, 3
0x1800060aa  mov     rcx, rbx
0x1800060ad  call    GSSendColor
0x1800060b2  mov     edx, 9
0x1800060b7  mov     rcx, rbx
0x1800060ba  call    OPSendOperator
0x1800060bf  mov     rcx, rbx
0x1800060c2  call    GSSendGrestore
0x1800060c7  jmp     short loc_1800060D3
0x1800060c9  mov     dword ptr [rbx+0D70h], 1
0x1800060d3  mov     eax, [rsi+20h]
0x1800060d6  mov     r9, rdi; int
0x1800060d9  mov     [rsp+78h+iColor], eax; iColor
0x1800060dd  mov     r8, rsi; int
0x1800060e0  mov     eax, [rsi+1Ch]
0x1800060e3  mov     rcx, rbx; int
0x1800060e6  mov     [rsp+78h+var_48], eax; int
0x1800060ea  mov     [rsp+78h+pxlo], r13; pxlo
0x1800060ef  mov     [rsp+78h+var_58], r15; __int64
0x1800060f4  call    GBBitmapHeader
0x1800060f9  mov     r8, rsi
0x1800060fc  mov     rdx, r13
0x1800060ff  mov     rcx, rbx
0x180006102  call    GBBitmapOperator
0x180006107  mov     r9, r13
0x18000610a  mov     [rsp+78h+var_58], rsi
0x18000610f  mov     r8, rdi
0x180006112  mov     rdx, r14
0x180006115  mov     rcx, rbx
0x180006118  call    GBBitmapData
0x18000611d  mov     rcx, rbx
0x180006120  call    GSSendGrestore
0x180006125  cmp     dword ptr [r14+48h], 9
0x18000612a  jz      short loc_180006152
0x18000612c  test    dword ptr [rsi+0Ch], 2000h
0x180006133  jz      short loc_180006152
0x180006135  mov     rcx, [rsi+28h]; hMem
0x180006139  test    rcx, rcx
0x18000613c  jz      short loc_18000614A
0x18000613e  call    cs:__imp_LocalFree
0x180006145  nop     dword ptr [rax+rax+00h]
0x18000614a  mov     qword ptr [rsi+28h], 0
  ... truncated ...
```
