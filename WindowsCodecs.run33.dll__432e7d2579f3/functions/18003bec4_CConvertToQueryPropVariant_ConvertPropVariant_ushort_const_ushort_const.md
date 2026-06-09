# CConvertToQueryPropVariant::ConvertPropVariant(ushort const *,ushort const *)

- ea: `0x18003bec4`
- end: `0x18003c11d`
- name: `?ConvertPropVariant@CConvertToQueryPropVariant@@QEAAJPEBG0@Z`
- size: `601`
- prototype: `__int64 __fastcall(CConvertToQueryPropVariant *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180039d40`

## callees

- `0x18001baa0`
- `0x18001dd10`
- `0x18003bec4`
- `0x180069234`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c00e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003bf2e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003bf79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003bf2e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003bf79`

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
0x18003bec4  push    rbp
0x18003bec6  push    rbx
0x18003bec7  push    rsi
0x18003bec8  push    r12
0x18003beca  push    r13
0x18003becc  push    r14
0x18003bece  push    r15
0x18003bed0  lea     rbp, [rsp-180h]
0x18003bed8  sub     rsp, 280h
0x18003bedf  mov     rax, cs:__security_cookie
0x18003bee6  xor     rax, rsp
0x18003bee9  mov     [rbp+1B0h+var_40], rax
0x18003bef0  mov     r15, rcx
0x18003bef3  mov     [rsp+2B0h+var_250], rdx
0x18003bef8  xor     ecx, ecx
0x18003befa  mov     rax, r8
0x18003befd  xorps   xmm0, xmm0
0x18003bf00  mov     [rsp+2B0h+var_258], rax
0x18003bf05  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x18003bf0a  lea     rsi, [r15+10h]
0x18003bf0e  mov     [rsp+2B0h+var_268], rcx
0x18003bf13  cmp     word ptr [rsi], 0Dh
0x18003bf17  jz      short loc_18003BF58
0x18003bf19  xor     ebx, ebx
0x18003bf1b  mov     eax, 100Ch
0x18003bf20  cmp     [rsi], ax
0x18003bf23  jz      loc_18003BFDF
0x18003bf29  lea     rcx, [rsp+2B0h+pvar]; pvar
0x18003bf2e  call    cs:__imp_PropVariantClear
0x18003bf34  mov     eax, ebx
0x18003bf36  mov     rcx, [rbp+1B0h+var_40]
0x18003bf3d  xor     rcx, rsp; StackCookie
0x18003bf40  call    __security_check_cookie
0x18003bf45  add     rsp, 280h
0x18003bf4c  pop     r15
0x18003bf4e  pop     r14
0x18003bf50  pop     r13
0x18003bf52  pop     r12
0x18003bf54  pop     rsi
0x18003bf55  pop     rbx
0x18003bf56  pop     rbp
0x18003bf57  retn
0x18003bf58  mov     r9, rdx; unsigned __int16 *
0x18003bf5b  mov     [rsp+2B0h+var_290], rax; unsigned __int16 *
0x18003bf60  mov     rdx, rsi; struct tagPROPVARIANT *
0x18003bf63  lea     r8, [rsp+2B0h+pvar]; struct tagPROPVARIANT *
0x18003bf68  mov     rcx, r15; this
0x18003bf6b  call    ?InitializePropVariant@CConvertToQueryPropVariant@@AEAAJPEAUtagPROPVARIANT@@0PEBG1@Z; CConvertToQueryPropVariant::InitializePropVariant(tagPROPVARIANT *,tagPROPVARIANT *,ushort const *,ushort const *)
0x18003bf70  mov     ebx, eax
0x18003bf72  test    eax, eax
0x18003bf74  js      short loc_18003BFA9
0x18003bf76  mov     rcx, rsi; pvar
0x18003bf79  call    cs:__imp_PropVariantClear
0x18003bf7f  mov     ebx, eax
0x18003bf81  test    eax, eax
0x18003bf83  js      short loc_18003BFC2
0x18003bf85  movups  xmm0, xmmword ptr [rsp+2B0h+pvar]
0x18003bf8a  xor     eax, eax
0x18003bf8c  movsd   xmm1, [rsp+2B0h+var_268]
0x18003bf92  movups  xmmword ptr [rsi], xmm0
0x18003bf95  mov     [rsp+2B0h+var_268], rax
0x18003bf9a  xorps   xmm0, xmm0
0x18003bf9d  movsd   qword ptr [rsi+10h], xmm1
0x18003bfa2  movups  xmmword ptr [rsp+2B0h+pvar], xmm0
0x18003bfa7  jmp     short loc_18003BF29
0x18003bfa9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003bfb0  jz      loc_18003BF29
0x18003bfb6  mov     ecx, eax; int
0x18003bfb8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18003bfbd  jmp     loc_18003BF29
0x18003bfc2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003bfc9  jnz     short loc_18003BFB6
0x18003bfcb  test    eax, eax
0x18003bfcd  js      loc_18003BF29
0x18003bfd3  jmp     short loc_18003BF85
0x18003bfd5  jz      loc_18003BF29
0x18003bfdb  mov     ecx, ebx
0x18003bfdd  jmp     short loc_18003BFB8
0x18003bfdf  mov     r12d, [r15+18h]
0x18003bfe3  lea     r8, [rsp+2B0h+pullResult]; pullResult
0x18003bfe8  mov     rax, [r15+20h]
0x18003bfec  mov     edx, 18h; ullMultiplier
0x18003bff1  mov     [rsp+2B0h+pullResult], rcx
0x18003bff6  mov     ecx, r12d; ullMultiplicand
0x18003bff9  mov     [rsp+2B0h+var_260], rax
0x18003bffe  call    ULongLongMult
0x18003c003  mov     ebx, eax
0x18003c005  test    eax, eax
0x18003c007  js      short loc_18003BFA9
0x18003c009  mov     rcx, [rsp+2B0h+pullResult]; cb
0x18003c00e  call    cs:__imp_CoTaskMemAlloc
0x18003c014  mov     r13, rax
0x18003c017  test    rax, rax
0x18003c01a  jnz     loc_18003C0B8
0x18003c020  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18003c026  mov     ebx, 8007000Eh
0x18003c02b  jmp     short loc_18003BFD5
0x18003c02d  mov     r9, [rsp+2B0h+var_258]
0x18003c032  lea     r8, aSD; "%s(%d)"
0x18003c039  inc     r14d
0x18003c03c  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18003c041  mov     edx, 100h; unsigned __int64
0x18003c046  mov     dword ptr [rsp+2B0h+var_290], r14d
0x18003c04b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c050  mov     ebx, eax
0x18003c052  test    eax, eax
0x18003c054  jns     short loc_18003C06B
0x18003c056  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003c05d  jnz     loc_18003BFB6
0x18003c063  test    eax, eax
0x18003c065  js      loc_18003BF29
0x18003c06b  mov     rax, [rsp+2B0h+pullResult]
0x18003c070  lea     rcx, [rsp+2B0h+var_240]
0x18003c075  mov     r9, [rsp+2B0h+var_250]; unsigned __int16 *
0x18003c07a  mov     [rsp+2B0h+var_290], rcx; unsigned __int16 *
0x18003c07f  mov     rcx, [rsp+2B0h+var_260]
0x18003c084  lea     r8, ds:0[rax*8]
0x18003c08c  add     r8, r13; struct tagPROPVARIANT *
0x18003c08f  lea     rdx, [rcx+rax*8]; struct tagPROPVARIANT *
0x18003c093  mov     rcx, r15; this
0x18003c096  call    ?InitializePropVariant@CConvertToQueryPropVariant@@AEAAJPEAUtagPROPVARIANT@@0PEBG1@Z; CConvertToQueryPropVariant::InitializePropVariant(tagPROPVARIANT *,tagPROPVARIANT *,ushort const *,ushort const *)
0x18003c09b  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18003c0a1  mov     ebx, eax
0x18003c0a3  test    eax, eax
0x18003c0a5  jns     short loc_18003C0EC
0x18003c0a7  test    ecx, ecx
0x18003c0a9  jnz     loc_18003BFB6
0x18003c0af  test    eax, eax
0x18003c0b1  jns     short loc_18003C0EC
0x18003c0b3  jmp     loc_18003BF29
0x18003c0b8  mov     dword ptr [rsp+2B0h+pvar+8], r12d
0x18003c0bd  mov     eax, 100Ch
0x18003c0c2  mov     word ptr [rsp+2B0h+pvar], ax
0x18003c0c7  mov     [rsp+2B0h+var_268], r13
0x18003c0cc  test    r12d, r12d
0x18003c0cf  jz      short loc_18003C0E3
0x18003c0d1  lea     r8, [r12+r12*2]
0x18003c0d5  xor     dl, dl; Val
0x18003c0d7  shl     r8, 3; Size
0x18003c0db  mov     rcx, r13; void *
0x18003c0de  call    memset_0
0x18003c0e3  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18003c0e9  xor     r14d, r14d
0x18003c0ec  cmp     r14d, r12d
0x18003c0ef  jnb     loc_18003BF76
0x18003c0f5  mov     rdx, [rsp+2B0h+var_260]
0x18003c0fa  lea     rax, [r14+r14*2]
0x18003c0fe  mov     [rsp+2B0h+pullResult], rax
0x18003c103  lea     rax, [rdx+rax*8]
0x18003c107  cmp     word ptr [rax], 0Dh
0x18003c10b  jz      loc_18003C02D
0x18003c111  mov     ebx, 88982F8Eh
0x18003c116  test    ecx, ecx
0x18003c118  jmp     loc_18003BFD5
```
