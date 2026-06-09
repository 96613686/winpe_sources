# CConvertToQueryPropVariant::ConvertPropVariant(ushort const *,ushort const *)

- ea: `0x180028df0`
- end: `0x18002905f`
- name: `?ConvertPropVariant@CConvertToQueryPropVariant@@QEAAJPEBG0@Z`
- size: `623`
- prototype: `__int64 __fastcall(CConvertToQueryPropVariant *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800297f0`

## callees

- `0x180028df0`
- `0x180037a04`
- `0x180040e54`
- `0x180042ae8`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028e5a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028eac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028e5a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028eac`

## pseudocode

```c
__int64 __fastcall CConvertToQueryPropVariant::ConvertPropVariant(
        CConvertToQueryPropVariant *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  _OWORD *v4; // rsi
  unsigned int v5; // ebx
  HRESULT v7; // eax
  BYTE *pData; // xmm1_8
  int v9; // ecx
  __int64 v10; // r12
  __int64 v11; // rax
  int v12; // edx
  BYTE *v13; // r13
  bool v14; // zf
  __int64 v15; // r14
  int v16; // ecx
  unsigned __int16 *v17; // [rsp+20h] [rbp-E0h]
  ULONGLONG pullResult; // [rsp+30h] [rbp-D0h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v21; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v22; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v23[256]; // [rsp+70h] [rbp-90h] BYREF

  v22 = a2;
  v21 = a3;
  memset(&pvar, 0, sizeof(pvar));
  v4 = (_OWORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) == 13 )
  {
    v7 = CConvertToQueryPropVariant::InitializePropVariant(
           this,
           (struct tagPROPVARIANT *)((char *)this + 16),
           &pvar,
           a2,
           a3);
    v5 = v7;
    if ( v7 >= 0 )
    {
LABEL_5:
      v7 = PropVariantClear((PROPVARIANT *)this + 2);
      v5 = v7;
      if ( v7 >= 0 )
      {
        pData = pvar.bstrblobVal.pData;
        *v4 = *(_OWORD *)&pvar.vt;
        pvar.bstrblobVal.pData = 0;
        *((_QWORD *)this + 4) = pData;
        *(_OWORD *)&pvar.vt = 0;
        goto LABEL_3;
      }
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_8;
    }
LABEL_7:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_3;
LABEL_8:
    v9 = v7;
LABEL_9:
    DoStackCapture(v9);
    goto LABEL_3;
  }
  v5 = 0;
  if ( *(_WORD *)v4 != 4108 )
    goto LABEL_3;
  v10 = *((unsigned int *)this + 6);
  v11 = *((_QWORD *)this + 4);
  pullResult = 0;
  v20 = v11;
  v7 = ULongLongMult((unsigned int)v10, 0x18u, &pullResult);
  v5 = v7;
  if ( v7 < 0 )
    goto LABEL_7;
  v13 = (BYTE *)CoTaskMemAlloc(pullResult);
  if ( v13 )
  {
    pvar.lVal = v10;
    pvar.vt = 4108;
    pvar.bstrblobVal.pData = v13;
    if ( (_DWORD)v10 )
    {
      LOBYTE(v12) = 0;
      memset_0(v13, v12, 24 * v10);
    }
    v16 = (int)g_doStackCaptures;
    v15 = 0;
    while ( (unsigned int)v15 < (unsigned int)v10 )
    {
      pullResult = 3 * v15;
      if ( *(_WORD *)(v20 + 24 * v15) != 13 )
      {
        v5 = -2003292274;
        v14 = v16 == 0;
        goto LABEL_12;
      }
      v15 = (unsigned int)(v15 + 1);
      LODWORD(v17) = v15;
      v7 = StringCchPrintfW(v23, 0x100u, L"%s(%d)", v21, v17);
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_8;
        goto LABEL_3;
      }
      v7 = CConvertToQueryPropVariant::InitializePropVariant(
             this,
             (struct tagPROPVARIANT *)(v20 + 8 * pullResult),
             (struct tagPROPVARIANT *)&v13[8 * pullResult],
             v22,
             v23);
      v16 = (int)g_doStackCaptures;
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_8;
        goto LABEL_3;
      }
    }
    goto LABEL_5;
  }
  v14 = (_DWORD)g_doStackCaptures == 0;
  v5 = -2147024882;
LABEL_12:
  if ( !v14 )
  {
    v9 = v5;
    goto LABEL_9;
  }
LABEL_3:
  PropVariantClear((PROPVARIANT *)&pvar);
  return v5;
}

```

## disassembly

```asm
0x180028df0  push    rbp
0x180028df2  push    rbx
0x180028df3  push    rsi
0x180028df4  push    r12
0x180028df6  push    r13
0x180028df8  push    r14
0x180028dfa  push    r15
0x180028dfc  lea     rbp, [rsp-180h]
0x180028e04  sub     rsp, 280h
0x180028e0b  mov     rax, cs:__security_cookie
0x180028e12  xor     rax, rsp
0x180028e15  mov     [rbp+1B0h+var_40], rax
0x180028e1c  mov     r15, rcx
0x180028e1f  mov     [rsp+2B0h+var_250], rdx
0x180028e24  xor     ecx, ecx
0x180028e26  mov     rax, r8
0x180028e29  xorps   xmm0, xmm0
0x180028e2c  mov     [rsp+2B0h+var_258], rax
0x180028e31  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x180028e36  lea     rsi, [r15+10h]
0x180028e3a  mov     [rsp+2B0h+var_268], rcx
0x180028e3f  cmp     word ptr [rsi], 0Dh
0x180028e43  jz      short loc_180028E8B
0x180028e45  xor     ebx, ebx
0x180028e47  mov     eax, 100Ch
0x180028e4c  cmp     [rsi], ax
0x180028e4f  jz      loc_180028F1B
0x180028e55  lea     rcx, [rsp+2B0h+pvar]; pvar
0x180028e5a  call    cs:__imp_PropVariantClear
0x180028e61  nop     dword ptr [rax+rax+00h]
0x180028e66  mov     eax, ebx
0x180028e68  mov     rcx, [rbp+1B0h+var_40]
0x180028e6f  xor     rcx, rsp; StackCookie
0x180028e72  call    __security_check_cookie
0x180028e77  add     rsp, 280h
0x180028e7e  pop     r15
0x180028e80  pop     r14
0x180028e82  pop     r13
0x180028e84  pop     r12
0x180028e86  pop     rsi
0x180028e87  pop     rbx
0x180028e88  pop     rbp
0x180028e89  retn
0x180028e8b  mov     r9, rdx; unsigned __int16 *
0x180028e8e  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x180028e93  mov     rdx, rsi; struct tagPROPVARIANT *
0x180028e96  lea     r8, [rsp+2B0h+pvar]; struct tagPROPVARIANT *
0x180028e9b  mov     rcx, r15; this
0x180028e9e  call    ?InitializePropVariant@CConvertToQueryPropVariant@@AEAAJPEAUtagPROPVARIANT@@0PEBG1@Z; CConvertToQueryPropVariant::InitializePropVariant(tagPROPVARIANT *,tagPROPVARIANT *,ushort const *,ushort const *)
0x180028ea3  mov     ebx, eax
0x180028ea5  test    eax, eax
0x180028ea7  js      short loc_180028EE5
0x180028ea9  mov     rcx, rsi; pvar
0x180028eac  call    cs:__imp_PropVariantClear
0x180028eb3  nop     dword ptr [rax+rax+00h]
0x180028eb8  mov     ebx, eax
0x180028eba  test    eax, eax
0x180028ebc  js      short loc_180028EFE
0x180028ebe  movups  xmm0, xmmword ptr [rsp+2B0h+pvar]
0x180028ec3  xor     eax, eax
0x180028ec5  movsd   xmm1, [rsp+2B0h+var_268]
0x180028ecb  movups  xmmword ptr [rsi], xmm0
0x180028ece  mov     [rsp+2B0h+var_268], rax
0x180028ed3  xorps   xmm0, xmm0
0x180028ed6  movsd   qword ptr [rsi+10h], xmm1
0x180028edb  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x180028ee0  jmp     loc_180028E55
0x180028ee5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180028eec  jz      loc_180028E55
0x180028ef2  mov     ecx, eax; int
0x180028ef4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180028ef9  jmp     loc_180028E55
0x180028efe  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180028f05  jnz     short loc_180028EF2
0x180028f07  test    eax, eax
0x180028f09  js      loc_180028E55
0x180028f0f  jmp     short loc_180028EBE
0x180028f11  jz      loc_180028E55
0x180028f17  mov     ecx, ebx
0x180028f19  jmp     short loc_180028EF4
0x180028f1b  mov     r12d, [r15+18h]
0x180028f1f  lea     r8, [rsp+2B0h+pullResult]; pullResult
0x180028f24  mov     rax, [r15+20h]
0x180028f28  mov     edx, 18h; ullMultiplier
0x180028f2d  mov     [rsp+2B0h+pullResult], rcx
0x180028f32  mov     ecx, r12d; ullMultiplicand
0x180028f35  mov     [rsp+2B0h+var_260], rax
0x180028f3a  call    ULongLongMult
0x180028f3f  mov     ebx, eax
0x180028f41  test    eax, eax
0x180028f43  js      short loc_180028EE5
0x180028f45  mov     rcx, [rsp+2B0h+pullResult]; cb
0x180028f4a  call    cs:__imp_CoTaskMemAlloc
0x180028f51  nop     dword ptr [rax+rax+00h]
0x180028f56  mov     r13, rax
0x180028f59  test    rax, rax
0x180028f5c  jnz     loc_180028FFA
0x180028f62  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180028f68  mov     ebx, 8007000Eh
0x180028f6d  jmp     short loc_180028F11
0x180028f6f  mov     r9, [rsp+2B0h+var_258]
0x180028f74  lea     r8, aSD; "%s(%d)"
0x180028f7b  inc     r14d
0x180028f7e  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x180028f83  mov     edx, 100h; unsigned __int64
0x180028f88  mov     dword ptr [rsp+2B0h+var_290], r14d
0x180028f8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028f92  mov     ebx, eax
0x180028f94  test    eax, eax
0x180028f96  jns     short loc_180028FAD
0x180028f98  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180028f9f  jnz     loc_180028EF2
0x180028fa5  test    eax, eax
0x180028fa7  js      loc_180028E55
0x180028fad  mov     rax, [rsp+2B0h+pullResult]
0x180028fb2  lea     rcx, [rsp+2B0h+var_240]
0x180028fb7  mov     r9, [rsp+2B0h+var_250]; unsigned __int16 *
0x180028fbc  mov     [rsp+2B0h+var_290], rcx; unsigned __int16 *
0x180028fc1  mov     rcx, [rsp+2B0h+var_260]
0x180028fc6  lea     r8, ds:0[rax*8]
0x180028fce  add     r8, r13; struct tagPROPVARIANT *
0x180028fd1  lea     rdx, [rcx+rax*8]; struct tagPROPVARIANT *
0x180028fd5  mov     rcx, r15; this
0x180028fd8  call    ?InitializePropVariant@CConvertToQueryPropVariant@@AEAAJPEAUtagPROPVARIANT@@0PEBG1@Z; CConvertToQueryPropVariant::InitializePropVariant(tagPROPVARIANT *,tagPROPVARIANT *,ushort const *,ushort const *)
0x180028fdd  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180028fe3  mov     ebx, eax
0x180028fe5  test    eax, eax
0x180028fe7  jns     short loc_18002902E
0x180028fe9  test    ecx, ecx
0x180028feb  jnz     loc_180028EF2
0x180028ff1  test    eax, eax
0x180028ff3  jns     short loc_18002902E
0x180028ff5  jmp     loc_180028E55
0x180028ffa  mov     dword ptr [rsp+2B0h+pvar+8], r12d
0x180028fff  mov     eax, 100Ch
0x180029004  mov     word ptr [rsp+2B0h+pvar], ax
0x180029009  mov     [rsp+2B0h+var_268], r13
0x18002900e  test    r12d, r12d
0x180029011  jz      short loc_180029025
0x180029013  lea     r8, [r12+r12*2]
0x180029017  xor     dl, dl; Val
0x180029019  shl     r8, 3; Size
0x18002901d  mov     rcx, r13; void *
0x180029020  call    memset_0
0x180029025  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18002902b  xor     r14d, r14d
0x18002902e  cmp     r14d, r12d
0x180029031  jnb     loc_180028EA9
0x180029037  mov     rdx, [rsp+2B0h+var_260]
0x18002903c  lea     rax, [r14+r14*2]
0x180029040  mov     [rsp+2B0h+pullResult], rax
0x180029045  lea     rax, [rdx+rax*8]
0x180029049  cmp     word ptr [rax], 0Dh
0x18002904d  jz      loc_180028F6F
0x180029053  mov     ebx, 88982F8Eh
0x180029058  test    ecx, ecx
0x18002905a  jmp     loc_180028F11
```
