# __rtcMIRR

- ea: `0x18037d64c`
- end: `0x18037da40`
- name: `__rtcMIRR`
- size: `1012`
- prototype: `__int64 __fastcall(double80trunc *this)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18037b0e8`

## callees

- `0x180102a4c`
- `0x180212a34`
- `0x1802ece2c`
- `0x180379520`
- `0x18037d64c`
- `0x18037dc54`
- `0x18037fbb0`
- `0x18037fc38`
- `0x18037fcc8`
- `0x18037fcf0`
- `0x18037fd80`
- `0x18037fda8`
- `0x18037fdc4`
- `0x18037ff44`
- `0x18037ffc8`
- `0x18037fff0`
- `0x18038005c`
- `0x180397d97`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18037d6bf`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18037d6bf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18037d702`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18037d702`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18037d6df`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18037d6df`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18037d72d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18037d72d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d793`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d819`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d960`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d793`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d819`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18037d960`

## pseudocode

```c
double80trunc *__fastcall _rtcMIRR(double80trunc *this, SAFEARRAY **a2, __int64 *a3, __int64 *a4)
{
  unsigned int LBound; // eax
  unsigned int v9; // eax
  unsigned int UBound; // eax
  unsigned int v11; // eax
  int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  double v22; // xmm0_8
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned int v30; // eax
  unsigned int v31; // eax
  double v32; // xmm0_8
  __int64 v33; // rax
  const struct double80 *v34; // rax
  __int16 v36; // [rsp+28h] [rbp-E0h]
  int v37; // [rsp+28h] [rbp-E0h]
  LONG plLbound[2]; // [rsp+38h] [rbp-D0h] BYREF
  void *ppvData; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v41; // [rsp+50h] [rbp-B8h]
  unsigned __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-A0h] BYREF
  __int16 v44; // [rsp+70h] [rbp-98h]
  _BYTE v45[16]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 v46[2]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v47; // [rsp+98h] [rbp-70h] BYREF
  __int16 v48; // [rsp+A0h] [rbp-68h]
  _BYTE v49[16]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v50[16]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v51[2]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v52[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[16]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v54[16]; // [rsp+108h] [rbp+0h] BYREF

  PgenprojOfHproj((unsigned __int64)&v47);
  PgenprojOfHproj((unsigned __int64)&v43);
  PgenprojOfHproj((unsigned __int64)v46);
  PgenprojOfHproj((unsigned __int64)&v42);
  PgenprojOfHproj((unsigned __int64)v51);
  if ( !*a2 || SafeArrayGetDim(*a2) != 1 )
    EbRaiseExceptionCode(5);
  LBound = SafeArrayGetLBound(*a2, 1u, plLbound);
  v9 = EberrOfScode(LBound);
  if ( v9 )
    EbRaiseExceptionCode(v9);
  UBound = SafeArrayGetUBound(*a2, 1u, &plLbound[1]);
  v11 = EberrOfScode(UBound);
  if ( v11 )
    EbRaiseExceptionCode(v11);
  v12 = plLbound[1] - plLbound[0] + 1;
  v13 = SafeArrayAccessData(*a2, &ppvData);
  v14 = EberrOfScode(v13);
  if ( v14 )
    EbRaiseExceptionCode(v14);
  doubletodouble80trunc(&v40);
  if ( (unsigned __int8)double80::operator==(a3, &v40)
    || (doubletodouble80trunc(&v40), (unsigned __int8)double80::operator==(a4, &v40))
    || v12 <= 1 )
  {
    v15 = SafeArrayUnaccessData(*a2);
    v16 = EberrOfScode(v15);
    if ( v16 )
      EbRaiseExceptionCode(v16);
    EbRaiseExceptionCode(5);
  }
  v40 = *a3;
  v41 = *((_WORD *)a3 + 4);
  v36 = -1;
  v17 = LDoNPV(v45, &v40, ppvData, (unsigned int)v12, v36);
  v43 = *(_QWORD *)v17;
  v44 = *(_WORD *)(v17 + 8);
  doubletodouble80trunc(&v40);
  if ( (unsigned __int8)double80::operator==(&v43, &v40) )
  {
    v18 = SafeArrayUnaccessData(*a2);
    v19 = EberrOfScode(v18);
    if ( v19 )
      EbRaiseExceptionCode(v19);
    EbRaiseExceptionCode(11);
  }
  v40 = *a4;
  LOWORD(v37) = 1;
  v41 = *((_WORD *)a4 + 4);
  v20 = LDoNPV(v45, &v40, ppvData, (unsigned int)v12, v37);
  v47 = *(_QWORD *)v20;
  v48 = *(_WORD *)(v20 + 8);
  doubletodouble80trunc(&v40);
  v21 = double80::operator+(a4, v45, &v40);
  double80trunc::operator=(&v42, v49, v21);
  doubletodouble80trunc(&v40);
  double80trunc::operator=(v51, v49, &v40);
  v22 = doubletodouble80trunc(&v40);
  v23 = double80::operator+(a3, v49, &v40);
  v24 = double80::operator*(&v43, v45, v23);
  pow(v22, 1.0);
  v26 = v25;
  v27 = double80::operator-(&v47, v53);
  v28 = double80::operator*(v27, v54, v26);
  v29 = double80::operator/(v28, v52, v24);
  double80trunc::operator=(v46, v50, v29);
  v30 = SafeArrayUnaccessData(*a2);
  v31 = EberrOfScode(v30);
  if ( v31 )
    EbRaiseExceptionCode(v31);
  FpErrorCheck();
  doubletodouble80trunc(&v40);
  if ( (unsigned __int8)double80::operator<(v46, &v40) )
    EbRaiseExceptionCode(5);
  doubletodouble80trunc(&v40);
  double80trunc::operator=(&v42, v50, &v40);
  v32 = doubletodouble80trunc(&v40);
  pow(v32, 1.0);
  v34 = (const struct double80 *)double80::operator-(v33, v52, &v40);
  double80trunc::double80trunc(this, v34);
  return this;
}

```

## disassembly

```asm
0x18037d64c  mov     rax, rsp
0x18037d64f  push    rbp
0x18037d650  push    rbx
0x18037d651  push    rsi
0x18037d652  push    rdi
0x18037d653  push    r12
0x18037d655  push    r14
0x18037d657  push    r15
0x18037d659  lea     rbp, [rax-68h]
0x18037d65d  sub     rsp, 130h
0x18037d664  movaps  xmmword ptr [rax-48h], xmm7
0x18037d668  mov     rax, cs:__security_cookie
0x18037d66f  xor     rax, rsp
0x18037d672  mov     [rbp+60h+var_50], rax
0x18037d676  mov     r14, rcx
0x18037d679  lea     rcx, [rbp+60h+var_D0]; unsigned __int64
0x18037d67d  mov     r15, r9
0x18037d680  mov     rdi, r8
0x18037d683  mov     rsi, rdx
0x18037d686  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037d68b  lea     rcx, [rsp+160h+var_100]; unsigned __int64
0x18037d690  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037d695  lea     rcx, [rbp+60h+var_E0]; unsigned __int64
0x18037d699  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037d69e  lea     rcx, [rsp+160h+var_110]; unsigned __int64
0x18037d6a3  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037d6a8  lea     rcx, [rbp+60h+var_A0]; unsigned __int64
0x18037d6ac  call    ?PgenprojOfHproj@@YAPEAVGEN_PROJECT@@_K@Z; PgenprojOfHproj(unsigned __int64)
0x18037d6b1  mov     rcx, [rsi]; psa
0x18037d6b4  mov     r12d, 1
0x18037d6ba  test    rcx, rcx
0x18037d6bd  jz      short loc_18037D6CA
0x18037d6bf  call    cs:__imp_SafeArrayGetDim
0x18037d6c5  cmp     eax, r12d
0x18037d6c8  jz      short loc_18037D6D4
0x18037d6ca  mov     ecx, 5
0x18037d6cf  call    EbRaiseExceptionCode
0x18037d6d4  mov     rcx, [rsi]; psa
0x18037d6d7  lea     r8, [rsp+160h+plLbound]; plLbound
0x18037d6dc  mov     edx, r12d; nDim
0x18037d6df  call    cs:__imp_SafeArrayGetLBound
0x18037d6e5  mov     ecx, eax
0x18037d6e7  call    EberrOfScode
0x18037d6ec  test    eax, eax
0x18037d6ee  jz      short loc_18037D6F7
0x18037d6f0  mov     ecx, eax
0x18037d6f2  call    EbRaiseExceptionCode
0x18037d6f7  mov     rcx, [rsi]; psa
0x18037d6fa  lea     r8, [rsp+160h+plLbound+4]; plUbound
0x18037d6ff  mov     edx, r12d; nDim
0x18037d702  call    cs:__imp_SafeArrayGetUBound
0x18037d708  mov     ecx, eax
0x18037d70a  call    EberrOfScode
0x18037d70f  test    eax, eax
0x18037d711  jz      short loc_18037D71A
0x18037d713  mov     ecx, eax
0x18037d715  call    EbRaiseExceptionCode
0x18037d71a  mov     ebx, [rsp+160h+plLbound+4]
0x18037d71e  mov     rcx, [rsi]; psa
0x18037d721  lea     rdx, [rsp+160h+ppvData]; ppvData
0x18037d726  sub     ebx, [rsp+160h+plLbound]
0x18037d72a  add     ebx, r12d
0x18037d72d  call    cs:__imp_SafeArrayAccessData
0x18037d733  mov     ecx, eax
0x18037d735  call    EberrOfScode
0x18037d73a  test    eax, eax
0x18037d73c  jz      short loc_18037D745
0x18037d73e  mov     ecx, eax
0x18037d740  call    EbRaiseExceptionCode
0x18037d745  movsd   xmm1, cs:__real@bff0000000000000
0x18037d74d  lea     rcx, [rsp+160h+var_120]
0x18037d752  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d757  lea     rdx, [rsp+160h+var_120]
0x18037d75c  mov     rcx, rdi
0x18037d75f  call    ??8double80@@QEBA_NAEBV0@@Z; double80::operator==(double80 const &)
0x18037d764  test    al, al
0x18037d766  jnz     short loc_18037D790
0x18037d768  movsd   xmm1, cs:__real@bff0000000000000
0x18037d770  lea     rcx, [rsp+160h+var_120]
0x18037d775  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d77a  lea     rdx, [rsp+160h+var_120]
0x18037d77f  mov     rcx, r15
0x18037d782  call    ??8double80@@QEBA_NAEBV0@@Z; double80::operator==(double80 const &)
0x18037d787  test    al, al
0x18037d789  jnz     short loc_18037D790
0x18037d78b  cmp     ebx, r12d
0x18037d78e  jg      short loc_18037D7B5
0x18037d790  mov     rcx, [rsi]; psa
0x18037d793  call    cs:__imp_SafeArrayUnaccessData
0x18037d799  mov     ecx, eax
0x18037d79b  call    EberrOfScode
0x18037d7a0  test    eax, eax
0x18037d7a2  jz      short loc_18037D7AB
0x18037d7a4  mov     ecx, eax
0x18037d7a6  call    EbRaiseExceptionCode
0x18037d7ab  mov     ecx, 5
0x18037d7b0  call    EbRaiseExceptionCode
0x18037d7b5  mov     rax, [rdi]
0x18037d7b8  mov     r8, [rsp+160h+ppvData]
0x18037d7bd  lea     rdx, [rsp+160h+var_120]
0x18037d7c2  mov     [rsp+160h+var_120], rax
0x18037d7c7  movzx   eax, word ptr [rdi+8]
0x18037d7cb  lea     rcx, [rsp+70h]
0x18037d7d0  mov     [rsp+160h+var_118], ax
0x18037d7d5  or      eax, 0FFFFFFFFh
0x18037d7d8  mov     r9d, ebx
0x18037d7db  mov     [rsp+20h], ax
0x18037d7e0  call    ?LDoNPV@@YA?AVdouble80trunc@@V1@PEANJF@Z; LDoNPV(double80trunc,double *,long,short)
0x18037d7e5  mov     rcx, [rax]
0x18037d7e8  xorps   xmm1, xmm1
0x18037d7eb  mov     [rsp+160h+var_100], rcx
0x18037d7f0  movzx   eax, word ptr [rax+8]
0x18037d7f4  lea     rcx, [rsp+160h+var_120]
0x18037d7f9  mov     [rsp+160h+var_F8], ax
0x18037d7fe  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d803  lea     rdx, [rsp+160h+var_120]
0x18037d808  lea     rcx, [rsp+160h+var_100]
0x18037d80d  call    ??8double80@@QEBA_NAEBV0@@Z; double80::operator==(double80 const &)
0x18037d812  test    al, al
0x18037d814  jz      short loc_18037D83B
0x18037d816  mov     rcx, [rsi]; psa
0x18037d819  call    cs:__imp_SafeArrayUnaccessData
0x18037d81f  mov     ecx, eax
0x18037d821  call    EberrOfScode
0x18037d826  test    eax, eax
0x18037d828  jz      short loc_18037D831
0x18037d82a  mov     ecx, eax
0x18037d82c  call    EbRaiseExceptionCode
0x18037d831  mov     ecx, 0Bh
0x18037d836  call    EbRaiseExceptionCode
0x18037d83b  mov     rax, [r15]
0x18037d83e  mov     r8, [rsp+160h+ppvData]
0x18037d843  lea     rdx, [rsp+160h+var_120]
0x18037d848  mov     [rsp+160h+var_120], rax
0x18037d84d  movzx   eax, word ptr [r15+8]
0x18037d852  lea     rcx, [rsp+70h]
0x18037d857  mov     r9d, ebx
0x18037d85a  mov     [rsp+20h], r12w
0x18037d860  mov     [rsp+160h+var_118], ax
0x18037d865  call    ?LDoNPV@@YA?AVdouble80trunc@@V1@PEANJF@Z; LDoNPV(double80trunc,double *,long,short)
0x18037d86a  movsd   xmm1, cs:__real@3ff0000000000000
0x18037d872  mov     rcx, [rax]
0x18037d875  mov     [rbp+60h+var_D0], rcx
0x18037d879  movzx   eax, word ptr [rax+8]
0x18037d87d  lea     rcx, [rsp+160h+var_120]
0x18037d882  mov     [rbp+60h+var_C8], ax
0x18037d886  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d88b  lea     r8, [rsp+160h+var_120]
0x18037d890  lea     rdx, [rsp+70h]
0x18037d895  mov     rcx, r15
0x18037d898  call    ??Hdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator+(double80 const &)
0x18037d89d  lea     rdx, [rbp+60h+var_C0]
0x18037d8a1  lea     rcx, [rsp+160h+var_110]
0x18037d8a6  mov     r8, rax
0x18037d8a9  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d8ae  lea     rcx, [rsp+160h+var_120]
0x18037d8b3  movd    xmm7, ebx
0x18037d8b7  cvtdq2pd xmm7, xmm7
0x18037d8bb  movaps  xmm1, xmm7
0x18037d8be  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d8c3  lea     r8, [rsp+160h+var_120]
0x18037d8c8  lea     rdx, [rbp+60h+var_C0]
0x18037d8cc  lea     rcx, [rbp+60h+var_A0]
0x18037d8d0  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d8d5  lea     rcx, [rsp+160h+var_120]
0x18037d8da  movsd   xmm1, cs:__real@3ff0000000000000
0x18037d8e2  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d8e7  lea     r8, [rsp+160h+var_120]
0x18037d8ec  lea     rdx, [rbp+60h+var_C0]
0x18037d8f0  mov     rcx, rdi
0x18037d8f3  call    ??Hdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator+(double80 const &)
0x18037d8f8  lea     rdx, [rsp+70h]
0x18037d8fd  lea     rcx, [rsp+160h+var_100]
0x18037d902  mov     r8, rax
0x18037d905  call    ??Ddouble80@@QEBA?AV0@AEBV0@@Z; double80::operator*(double80 const &)
0x18037d90a  lea     r8, [rbp+60h+var_A0]
0x18037d90e  lea     rdx, [rsp+160h+var_110]
0x18037d913  lea     rcx, [rbp+60h+var_80]
0x18037d917  mov     rdi, rax
0x18037d91a  call    ?pow@@YA?AVdouble80@@AEBV1@0@Z; pow(double80 const &,double80 const &)
0x18037d91f  lea     rdx, [rbp+60h+var_70]
0x18037d923  lea     rcx, [rbp+60h+var_D0]
0x18037d927  mov     rbx, rax
0x18037d92a  call    ??Gdouble80@@QEBA?AV0@XZ; double80::operator-(void)
0x18037d92f  lea     rdx, [rbp+60h+var_60]
0x18037d933  mov     rcx, rax
0x18037d936  mov     r8, rbx
0x18037d939  call    ??Ddouble80@@QEBA?AV0@AEBV0@@Z; double80::operator*(double80 const &)
0x18037d93e  lea     rdx, [rbp+60h+var_90]
0x18037d942  mov     r8, rdi
0x18037d945  mov     rcx, rax
0x18037d948  call    ??Kdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator/(double80 const &)
0x18037d94d  lea     rdx, [rbp+60h+var_B0]
0x18037d951  lea     rcx, [rbp+60h+var_E0]
0x18037d955  mov     r8, rax
0x18037d958  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d95d  mov     rcx, [rsi]; psa
0x18037d960  call    cs:__imp_SafeArrayUnaccessData
0x18037d966  mov     ecx, eax
0x18037d968  call    EberrOfScode
0x18037d96d  test    eax, eax
0x18037d96f  jz      short loc_18037D978
0x18037d971  mov     ecx, eax
0x18037d973  call    EbRaiseExceptionCode
0x18037d978  call    FpErrorCheck
0x18037d97d  xorps   xmm1, xmm1
0x18037d980  lea     rcx, [rsp+160h+var_120]
0x18037d985  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d98a  lea     rdx, [rsp+160h+var_120]
0x18037d98f  lea     rcx, [rbp+60h+var_E0]
0x18037d993  call    ??Mdouble80@@QEBA_NAEBV0@@Z; double80::operator<(double80 const &)
0x18037d998  test    al, al
0x18037d99a  jz      short loc_18037D9A6
0x18037d99c  mov     ecx, 5
0x18037d9a1  call    EbRaiseExceptionCode
0x18037d9a6  movsd   xmm1, cs:__real@3ff0000000000000
0x18037d9ae  subsd   xmm7, cs:__real@3ff0000000000000
0x18037d9b6  lea     rcx, [rsp+160h+var_120]
0x18037d9bb  divsd   xmm1, xmm7
0x18037d9bf  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d9c4  lea     r8, [rsp+160h+var_120]
0x18037d9c9  lea     rdx, [rbp+60h+var_B0]
0x18037d9cd  lea     rcx, [rsp+160h+var_110]
0x18037d9d2  call    ??4double80trunc@@QEAA?AV0@AEBVdouble80@@@Z; double80trunc::operator=(double80 const &)
0x18037d9d7  lea     rcx, [rsp+160h+var_120]
0x18037d9dc  movsd   xmm1, cs:__real@3ff0000000000000
0x18037d9e4  call    ?doubletodouble80trunc@@YA?AVdouble80trunc@@N@Z; doubletodouble80trunc(double)
0x18037d9e9  lea     r8, [rsp+160h+var_110]
0x18037d9ee  lea     rdx, [rbp+60h+var_E0]
0x18037d9f2  lea     rcx, [rbp+60h+var_B0]
0x18037d9f6  call    ?pow@@YA?AVdouble80@@AEBV1@0@Z; pow(double80 const &,double80 const &)
0x18037d9fb  lea     r8, [rsp+160h+var_120]
0x18037da00  lea     rdx, [rbp+60h+var_90]
0x18037da04  mov     rcx, rax
0x18037da07  call    ??Gdouble80@@QEBA?AV0@AEBV0@@Z; double80::operator-(double80 const &)
0x18037da0c  mov     rcx, r14; this
0x18037da0f  mov     rdx, rax; struct double80 *
0x18037da12  call    ??0double80trunc@@QEAA@AEBVdouble80@@@Z; double80trunc::double80trunc(double80 const &)
0x18037da17  mov     rax, r14
0x18037da1a  mov     rcx, [rbp+60h+var_50]
0x18037da1e  xor     rcx, rsp; StackCookie
0x18037da21  call    __security_check_cookie
0x18037da26  movaps  xmm7, [rsp+160h+var_48+8]
0x18037da2e  add     rsp, 130h
0x18037da35  pop     r15
0x18037da37  pop     r14
0x18037da39  pop     r12
0x18037da3b  pop     rdi
0x18037da3c  pop     rsi
0x18037da3d  pop     rbx
0x18037da3e  pop     rbp
0x18037da3f  retn
```
