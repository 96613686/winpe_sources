# BCommonDIBBlt

- ea: `0x180005c48`
- end: `0x18000604f`
- name: `BCommonDIBBlt`
- size: `1031`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, __int64, int, int, __int64)`
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800067a0`
- `0x180006950`
- `0x180006de0`
- `0x1800071b0`
- `0x180007378`

## callees

- `0x180005b1c`
- `0x180005c48`
- `0x1800061c0`
- `0x180011c50`
- `0x180011fd4`
- `0x18001241c`
- `0x18001247c`
- `0x18001283c`
- `0x180015f84`
- `0x180016940`
- `0x180016bdc`
- `0x180016cd4`
- `0x180016e24`
- `0x180018a14`
- `0x180018cac`
- `0x180018ec4`
- `0x180019724`
- `0x180020644`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180005cbf`
- `KERNEL32!SetLastError` at `0x180005cbf`
- `KERNEL32!LocalFree` at `0x180006031`
- `KERNEL32!LocalFree` at `0x180006031`
- `GDI32!XLATEOBJ_piVector` at `0x180005f6b`
- `GDI32!XLATEOBJ_piVector` at `0x180005f6b`

## pseudocode

```c
_BOOL8 __fastcall BCommonDIBBlt(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int *a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _DWORD *a10)
{
  __int64 v13; // rcx
  int v15; // eax
  int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  int v19; // edx
  unsigned int v20; // ecx
  float v21; // xmm3_4
  float v22; // xmm2_4
  int v23; // edx
  unsigned int v24; // ecx
  ULONG *v25; // r12
  void *v26; // rcx
  signed int v27; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-34h]
  signed int v29; // [rsp+48h] [rbp-30h]
  unsigned int v30; // [rsp+4Ch] [rbp-2Ch]
  __int128 v31; // [rsp+50h] [rbp-28h] BYREF
  int v32; // [rsp+60h] [rbp-18h]

  v32 = 0;
  v31 = 0;
  if ( !(unsigned int)SMChangeState(a1, 5) )
    return 0;
  if ( *(_DWORD *)(a2 + 72) == 9 )
  {
    if ( *a5 == a5[2]
      || a5[1] == a5[3]
      || !(unsigned int)BJPEGFormatSupported(v13, *(unsigned int *)(a2 + 40), *(_QWORD *)(a2 + 48), &v31) )
    {
      SetLastError(0x32u);
      return 0;
    }
  }
  else if ( !(unsigned int)BGetDIBInfo(a8, a2, a4, a1) )
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
  v15 = *(_DWORD *)(a2 + 32);
  if ( a5[2] > v15 )
    a5[2] = v15;
  v16 = *(_DWORD *)(a2 + 36);
  if ( a5[3] > v16 )
    a5[3] = v16;
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
    GSSendAttributes((_DWORD)a1, a4, 0, 0, a3, (__int64)&v27);
  }
  else
  {
    GSSendAttributes((_DWORD)a1, a4, 0, 0, a3, (__int64)a6);
  }
  if ( a7 )
    a1[538] &= ~0x200u;
  GSSendGsave(a1);
  if ( a7 )
    BChangeTransMatrix(a1, a7, a6);
  if ( *(_DWORD *)(a2 + 72) == 9 )
  {
    if ( *a5 || a5[1] || a5[2] != *(_DWORD *)(a2 + 32) || a5[3] != *(_DWORD *)(a2 + 36) )
    {
      OPSendInt(a1, (unsigned int)*a6);
      OPSendInt(a1, (unsigned int)a6[1]);
      OPSendInt(a1, (unsigned int)(a6[2] - *a6));
      OPSendInt(a1, (unsigned int)(a6[3] - a6[1]));
      OPRawPortWrite(a1, "rc ", 3);
      v20 = a6[1];
      v21 = (float)(a6[2] - *a6) / (float)(a5[2] - *a5);
      v22 = (float)(int)(a6[3] - v20) / (float)(a5[3] - a5[1]);
      v23 = *a6 - (int)(float)((float)*a5 * v21);
      *a6 = v23;
      v24 = v20 - (int)(float)((float)a5[1] * v22);
      a6[1] = v24;
      a6[2] = v23 + (int)(float)((float)*(int *)(a2 + 32) * v21);
      a6[3] = v24 + (int)(float)((float)*(int *)(a2 + 36) * v22);
    }
    OPSendJPEGImage(a1, a2, a6, &v31);
  }
  else
  {
    if ( *(_DWORD *)a8 == 1 && (*(_BYTE *)(a8 + 12) & 0x10) == 0 && !*(_DWORD *)(a8 + 28) )
    {
      if ( (*(_BYTE *)(a4 + 4) & 2) != 0
        && ((v25 = *(ULONG **)(a4 + 16)) != 0 || (v25 = XLATEOBJ_piVector((XLATEOBJ *)a4)) != 0) )
      {
        GSSendGsave(a1);
        GBSendRect(a1, a6, 1);
        GSSendColor(a1, v25[1], 3);
        OPSendOperator(a1, 9);
        GSSendGrestore(a1);
      }
      else
      {
        a1[860] = 1;
      }
    }
    GBBitmapHeader((int)a1, v19, a8, (int)a5, (__int64)a6, (XLATEOBJ *)a4, *(_DWORD *)(a8 + 28), *(_DWORD *)(a8 + 32));
    GBBitmapOperator(a1, a4, a8);
    GBBitmapData((_DWORD)a1, a2, (_DWORD)a5, a4, a8);
  }
  GSSendGrestore(a1);
  if ( *(_DWORD *)(a2 + 72) != 9 && (*(_DWORD *)(a8 + 12) & 0x2000) != 0 )
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
0x180005c48  mov     [rsp-40h+arg_10], r8
0x180005c4d  push    rbp
0x180005c4e  push    rbx
0x180005c4f  push    rsi
0x180005c50  push    rdi
0x180005c51  push    r12
0x180005c53  push    r13
0x180005c55  push    r14
0x180005c57  push    r15
0x180005c59  mov     rbp, rsp
0x180005c5c  sub     rsp, 78h
0x180005c60  xor     eax, eax
0x180005c62  mov     r14, rdx
0x180005c65  xorps   xmm0, xmm0
0x180005c68  mov     [rbp+var_18], eax
0x180005c6b  mov     r13, r9
0x180005c6e  mov     rbx, rcx
0x180005c71  movups  [rbp+var_28], xmm0
0x180005c75  lea     edx, [rax+5]
0x180005c78  call    SMChangeState
0x180005c7d  xor     r15d, r15d
0x180005c80  test    eax, eax
0x180005c82  jz      short loc_180005CC5
0x180005c84  cmp     dword ptr [r14+48h], 9
0x180005c89  mov     rsi, [rbp+arg_38]
0x180005c90  mov     rdi, [rbp+arg_20]
0x180005c94  jnz     short loc_180005CD8
0x180005c96  mov     eax, [rdi+8]
0x180005c99  cmp     [rdi], eax
0x180005c9b  jz      short loc_180005CBA
0x180005c9d  mov     eax, [rdi+0Ch]
0x180005ca0  cmp     [rdi+4], eax
0x180005ca3  jz      short loc_180005CBA
0x180005ca5  mov     r8, [r14+30h]
0x180005ca9  lea     r9, [rbp+var_28]
0x180005cad  mov     edx, [r14+28h]
0x180005cb1  call    BJPEGFormatSupported
0x180005cb6  test    eax, eax
0x180005cb8  jnz     short loc_180005CED
0x180005cba  mov     ecx, 32h ; '2'; dwErrCode
0x180005cbf  call    cs:__imp_SetLastError
0x180005cc5  xor     eax, eax
0x180005cc7  add     rsp, 78h
0x180005ccb  pop     r15
0x180005ccd  pop     r14
0x180005ccf  pop     r13
0x180005cd1  pop     r12
0x180005cd3  pop     rdi
0x180005cd4  pop     rsi
0x180005cd5  pop     rbx
0x180005cd6  pop     rbp
0x180005cd7  retn
0x180005cd8  mov     r9, rbx
0x180005cdb  mov     r8, r13
0x180005cde  mov     rdx, r14
0x180005ce1  mov     rcx, rsi
0x180005ce4  call    BGetDIBInfo
0x180005ce9  test    eax, eax
0x180005ceb  jz      short loc_180005CC5
0x180005ced  mov     rdx, [rbp+arg_48]
0x180005cf4  test    rdx, rdx
0x180005cf7  jz      short loc_180005CFC
0x180005cf9  mov     [rdx], r15d
0x180005cfc  cmp     [rsi+1Ch], r15d
0x180005d00  jz      short loc_180005D40
0x180005d02  mov     ecx, [rsi+4]
0x180005d05  sub     ecx, 1
0x180005d08  jz      short loc_180005D2E
0x180005d0a  sub     ecx, 3
0x180005d0d  jz      short loc_180005D2E
0x180005d0f  sub     ecx, 4
0x180005d12  jz      short loc_180005D20
0x180005d14  sub     ecx, 10h
0x180005d17  jz      short loc_180005D2E
0x180005d19  cmp     ecx, 8
0x180005d1c  jz      short loc_180005D2E
0x180005d1e  jmp     short loc_180005D29
0x180005d20  cmp     [rbx+2C4h], r15d
0x180005d27  jnz     short loc_180005D2E
0x180005d29  cmp     dword ptr [rsi], 1
0x180005d2c  jnz     short loc_180005D33
0x180005d2e  cmp     dword ptr [rsi], 10h
0x180005d31  jb      short loc_180005D40
0x180005d33  test    rdx, rdx
0x180005d36  jz      short loc_180005CC5
0x180005d38  mov     dword ptr [rdx], 1
0x180005d3e  jmp     short loc_180005CC5
0x180005d40  cmp     [rdi], r15d
0x180005d43  jge     short loc_180005D48
0x180005d45  mov     [rdi], r15d
0x180005d48  cmp     [rdi+4], r15d
0x180005d4c  jge     short loc_180005D52
0x180005d4e  mov     [rdi+4], r15d
0x180005d52  mov     eax, [r14+20h]
0x180005d56  cmp     [rdi+8], eax
0x180005d59  jle     short loc_180005D5E
0x180005d5b  mov     [rdi+8], eax
0x180005d5e  mov     eax, [r14+24h]
0x180005d62  cmp     [rdi+0Ch], eax
0x180005d65  jle     short loc_180005D6A
0x180005d67  mov     [rdi+0Ch], eax
0x180005d6a  mov     edx, 11h
0x180005d6f  mov     rcx, rbx
0x180005d72  call    PSProcsetSend
0x180005d77  mov     r12, [rbp+arg_30]
0x180005d7b  test    r12, r12
0x180005d7e  jz      short loc_180005D88
0x180005d80  bts     dword ptr [rbx+868h], 9
0x180005d88  mov     r15, [rbp+arg_28]
0x180005d8c  test    r15, r15
0x180005d8f  jz      short loc_180005DD8
0x180005d91  cmp     [rbp+arg_40], 0
0x180005d98  jz      short loc_180005DD8
0x180005d9a  mov     eax, [r15+8]
0x180005d9e  mov     ecx, [r15]
0x180005da1  cmp     ecx, eax
0x180005da3  jge     short loc_180005DAD
0x180005da5  mov     [rbp+var_38], ecx
0x180005da8  mov     [rbp+var_30], eax
0x180005dab  jmp     short loc_180005DB3
0x180005dad  mov     [rbp+var_30], ecx
0x180005db0  mov     [rbp+var_38], eax
0x180005db3  mov     eax, [r15+0Ch]
0x180005db7  mov     ecx, [r15+4]
0x180005dbb  cmp     ecx, eax
0x180005dbd  jge     short loc_180005DC7
0x180005dbf  mov     [rbp+var_34], ecx
0x180005dc2  mov     [rbp+var_2C], eax
0x180005dc5  jmp     short loc_180005DCD
0x180005dc7  mov     [rbp+var_2C], ecx
0x180005dca  mov     [rbp+var_34], eax
0x180005dcd  lea     rax, [rbp+var_38]
0x180005dd1  mov     [rsp+78h+pxlo], rax
0x180005dd6  jmp     short loc_180005DDD
0x180005dd8  mov     [rsp+78h+pxlo], r15
0x180005ddd  mov     rax, [rbp+arg_10]
0x180005de1  xor     r9d, r9d
0x180005de4  xor     r8d, r8d
0x180005de7  mov     [rsp+78h+var_58], rax
0x180005dec  mov     rdx, r13
0x180005def  mov     rcx, rbx
0x180005df2  call    GSSendAttributes
0x180005df7  test    r12, r12
0x180005dfa  jz      short loc_180005E04
0x180005dfc  btr     dword ptr [rbx+868h], 9
0x180005e04  mov     rcx, rbx
0x180005e07  call    GSSendGsave
0x180005e0c  test    r12, r12
0x180005e0f  jz      short loc_180005E1F
0x180005e11  mov     r8, r15
0x180005e14  mov     rdx, r12
0x180005e17  mov     rcx, rbx
0x180005e1a  call    BChangeTransMatrix
0x180005e1f  cmp     dword ptr [r14+48h], 9
0x180005e24  jnz     loc_180005F47
0x180005e2a  cmp     dword ptr [rdi], 0
0x180005e2d  jnz     short loc_180005E4B
0x180005e2f  cmp     dword ptr [rdi+4], 0
0x180005e33  jnz     short loc_180005E4B
0x180005e35  mov     eax, [r14+20h]
0x180005e39  cmp     [rdi+8], eax
0x180005e3c  jnz     short loc_180005E4B
0x180005e3e  mov     eax, [r14+24h]
0x180005e42  cmp     [rdi+0Ch], eax
0x180005e45  jz      loc_180005F30
0x180005e4b  mov     edx, [r15]
0x180005e4e  mov     rcx, rbx
0x180005e51  call    OPSendInt
0x180005e56  mov     edx, [r15+4]
0x180005e5a  mov     rcx, rbx
0x180005e5d  call    OPSendInt
0x180005e62  mov     edx, [r15+8]
0x180005e66  mov     rcx, rbx
0x180005e69  sub     edx, [r15]
0x180005e6c  call    OPSendInt
0x180005e71  mov     edx, [r15+0Ch]
0x180005e75  mov     rcx, rbx
0x180005e78  sub     edx, [r15+4]
0x180005e7c  call    OPSendInt
0x180005e81  mov     r8d, 3
0x180005e87  lea     rdx, PSFRAG_rc; "rc "
0x180005e8e  mov     rcx, rbx
0x180005e91  call    OPRawPortWrite
0x180005e96  movd    xmm1, dword ptr [rdi]
0x180005e9a  mov     edx, [r15]
0x180005e9d  mov     ecx, [r15+4]
0x180005ea1  mov     eax, [r15+8]
0x180005ea5  sub     eax, edx
0x180005ea7  cvtdq2ps xmm1, xmm1
0x180005eaa  movd    xmm3, eax
0x180005eae  mov     eax, [rdi+8]
0x180005eb1  sub     eax, [rdi]
0x180005eb3  cvtdq2ps xmm3, xmm3
0x180005eb6  movd    xmm0, eax
0x180005eba  mov     eax, [r15+0Ch]
0x180005ebe  cvtdq2ps xmm0, xmm0
0x180005ec1  sub     eax, ecx
0x180005ec3  movd    xmm2, eax
0x180005ec7  mov     eax, [rdi+0Ch]
0x180005eca  sub     eax, [rdi+4]
0x180005ecd  divss   xmm3, xmm0
0x180005ed1  movd    xmm0, eax
0x180005ed5  cvtdq2ps xmm0, xmm0
0x180005ed8  cvtdq2ps xmm2, xmm2
0x180005edb  mulss   xmm1, xmm3
0x180005edf  divss   xmm2, xmm0
0x180005ee3  cvttss2si eax, xmm1
0x180005ee7  sub     edx, eax
0x180005ee9  mov     [r15], edx
0x180005eec  movd    xmm0, dword ptr [rdi+4]
0x180005ef1  cvtdq2ps xmm0, xmm0
0x180005ef4  mulss   xmm0, xmm2
0x180005ef8  cvttss2si eax, xmm0
0x180005efc  sub     ecx, eax
0x180005efe  mov     [r15+4], ecx
0x180005f02  movd    xmm0, dword ptr [r14+20h]
0x180005f08  cvtdq2ps xmm0, xmm0
0x180005f0b  mulss   xmm0, xmm3
0x180005f0f  cvttss2si eax, xmm0
0x180005f13  add     eax, edx
0x180005f15  mov     [r15+8], eax
0x180005f19  movd    xmm0, dword ptr [r14+24h]
0x180005f1f  cvtdq2ps xmm0, xmm0
0x180005f22  mulss   xmm0, xmm2
0x180005f26  cvttss2si eax, xmm0
0x180005f2a  add     eax, ecx
0x180005f2c  mov     [r15+0Ch], eax
0x180005f30  lea     r9, [rbp+var_28]
0x180005f34  mov     r8, r15
0x180005f37  mov     rdx, r14
0x180005f3a  mov     rcx, rbx
0x180005f3d  call    OPSendJPEGImage
0x180005f42  jmp     loc_180006010
0x180005f47  cmp     dword ptr [rsi], 1
0x180005f4a  jnz     short loc_180005FC6
0x180005f4c  test    byte ptr [rsi+0Ch], 10h
0x180005f50  jnz     short loc_180005FC6
0x180005f52  cmp     dword ptr [rsi+1Ch], 0
0x180005f56  jnz     short loc_180005FC6
0x180005f58  test    byte ptr [r13+4], 2
0x180005f5d  jz      short loc_180005FBC
0x180005f5f  mov     r12, [r13+10h]
0x180005f63  test    r12, r12
0x180005f66  jnz     short loc_180005F79
0x180005f68  mov     rcx, r13; pxlo
0x180005f6b  call    cs:__imp_XLATEOBJ_piVector
0x180005f71  mov     r12, rax
0x180005f74  test    rax, rax
0x180005f77  jz      short loc_180005FBC
0x180005f79  mov     rcx, rbx
0x180005f7c  call    GSSendGsave
0x180005f81  mov     r8d, 1
0x180005f87  mov     rdx, r15
0x180005f8a  mov     rcx, rbx
0x180005f8d  call    GBSendRect
0x180005f92  mov     edx, [r12+4]
0x180005f97  mov     r8d, 3
0x180005f9d  mov     rcx, rbx
0x180005fa0  call    GSSendColor
0x180005fa5  mov     edx, 9
0x180005faa  mov     rcx, rbx
0x180005fad  call    OPSendOperator
0x180005fb2  mov     rcx, rbx
0x180005fb5  call    GSSendGrestore
0x180005fba  jmp     short loc_180005FC6
0x180005fbc  mov     dword ptr [rbx+0D70h], 1
0x180005fc6  mov     eax, [rsi+20h]
0x180005fc9  mov     r9, rdi; int
0x180005fcc  mov     [rsp+78h+iColor], eax; iColor
0x180005fd0  mov     r8, rsi; int
0x180005fd3  mov     eax, [rsi+1Ch]
0x180005fd6  mov     rcx, rbx; int
0x180005fd9  mov     [rsp+78h+var_48], eax; int
0x180005fdd  mov     [rsp+78h+pxlo], r13; pxlo
0x180005fe2  mov     [rsp+78h+var_58], r15; __int64
0x180005fe7  call    GBBitmapHeader
0x180005fec  mov     r8, rsi
0x180005fef  mov     rdx, r13
0x180005ff2  mov     rcx, rbx
0x180005ff5  call    GBBitmapOperator
0x180005ffa  mov     r9, r13
0x180005ffd  mov     [rsp+78h+var_58], rsi
0x180006002  mov     r8, rdi
0x180006005  mov     rdx, r14
0x180006008  mov     rcx, rbx
0x18000600b  call    GBBitmapData
0x180006010  mov     rcx, rbx
0x180006013  call    GSSendGrestore
0x180006018  cmp     dword ptr [r14+48h], 9
0x18000601d  jz      short loc_18000603F
0x18000601f  test    dword ptr [rsi+0Ch], 2000h
0x180006026  jz      short loc_18000603F
0x180006028  mov     rcx, [rsi+28h]; hMem
0x18000602c  test    rcx, rcx
0x18000602f  jz      short loc_180006037
0x180006031  call    cs:__imp_LocalFree
0x180006037  mov     qword ptr [rsi+28h], 0
0x18000603f  xor     eax, eax
0x180006041  cmp     [rbx+0D70h], eax
0x180006047  setz    al
  ... truncated ...
```
