# LiteCryptUtilities::DeriveKeyWithSP800108(uchar const *,ulong,uchar const *,ulong,char const *,uchar *,ulong)

- ea: `0x180028710`
- end: `0x180028966`
- name: `?DeriveKeyWithSP800108@LiteCryptUtilities@@YAJPEBEK0KPEBDPEAEK@Z`
- size: `598`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, __int64, const unsigned __int8 *, __int64, const char *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002e7b0`

## callees

- `0x180003160`
- `0x180008440`
- `0x18000baac`
- `0x180023b5c`
- `0x180023c04`
- `0x180026c8c`
- `0x1800280dc`
- `0x180028110`
- `0x180028710`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028881`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028881`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028830`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180028830`
- `bcrypt!BCryptKeyDerivation` at `0x1800288ca`
- `bcrypt!BCryptKeyDerivation` at `0x1800288ca`

## string_xrefs

- `0x18002884c`: `hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spDeriveAlg, BCRYPT_SP800108_CTR_HMAC_ALGORITHM, nullptr, 0))`

## pseudocode

```c
__int64 __fastcall LiteCryptUtilities::DeriveKeyWithSP800108(
        PUCHAR pbSecret,
        ULONG cbSecret,
        __int64 a3,
        const unsigned __int8 *a4,
        __int64 a5,
        const char *a6,
        unsigned __int8 *a7)
{
  int v7; // r15d
  __int64 v11; // rax
  int v12; // eax
  int SymmetricKey; // eax
  const char *v14; // rcx
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rdx
  int v18; // r8d
  const unsigned __int16 *pbSecreta; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v24; // [rsp+50h] [rbp-B0h]
  BCRYPT_ALG_HANDLE phAlgorithm[3]; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_KEY_HANDLE phKey[3]; // [rsp+70h] [rbp-90h] BYREF
  int *v27[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v28[4]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v29[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-30h]
  int v31; // [rsp+D8h] [rbp-28h]
  int v32; // [rsp+DCh] [rbp-24h]
  __int64 v33; // [rsp+E0h] [rbp-20h]
  __int64 v34; // [rsp+E8h] [rbp-18h]
  const WCHAR *v35; // [rsp+F0h] [rbp-10h]

  v7 = (int)a4;
  v21 = 0;
  v22 = 0;
  memset(phKey, 0, sizeof(phKey));
  memset(phAlgorithm, 0, sizeof(phAlgorithm));
  v28[0] = "LiteCryptUtilities::DeriveKeyWithSP800108";
  v28[1] = &v21;
  v28[2] = 0;
  v28[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::DeriveKeyWithSP800108",
    (const char *)0x477,
    0,
    pbSecreta);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v27,
    "LiteCryptUtilities::DeriveKeyWithSP800108",
    &v21,
    10,
    &qword_180041DC0);
  v11 = -1;
  do
    ++v11;
  while ( *(_BYTE *)(a5 + v11) );
  v29[0] = v11;
  v29[1] = 13;
  v30 = a5;
  v31 = v7;
  v32 = 14;
  v33 = a3;
  v34 = 14;
  v35 = L"SHA256";
  v23[0] = 0;
  v23[1] = 3;
  v24 = v29;
  v12 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SP800_108_CTR_HMAC", 0, 0);
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v21 = v12;
  if ( v12 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyWithSP800108",
      0x49Fu,
      v12,
      "hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spDeriveAlg, BCRYPT_SP800108_CTR_HMAC_ALGORITHM, nullptr, 0))");
    goto LABEL_16;
  }
  SymmetricKey = BCryptGenerateSymmetricKey(phAlgorithm[0], phKey, 0, 0, pbSecret, cbSecret, 0);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v14 = "hr = HRESULT_FROM_WIN32(::BCryptGenerateSymmetricKey( spDeriveAlg, &spDeriveKey, nullptr, 0, static_cast<PUCHA"
          "R>(const_cast<BYTE*>(pSecret)), secretSizeBytes, 0))";
    v15 = 1192;
LABEL_15:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DeriveKeyWithSP800108",
      v15,
      SymmetricKey,
      v14);
    goto LABEL_16;
  }
  SymmetricKey = BCryptKeyDerivation(phKey[0], v23, a6, (unsigned int)a7, &v22, 0);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v14 = "hr = HRESULT_FROM_WIN32(::BCryptKeyDerivation( spDeriveKey, &keyDerivationDescription, pDerivedKey, derivedKey"
          "SizeBytes, &keySizeBytes, 0))";
    v15 = 1200;
    goto LABEL_15;
  }
LABEL_16:
  v16 = v21;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v27[3], *v27[2], (unsigned __int64)v27[1], v27[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v28, v17, v18);
  Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(phAlgorithm);
  Auto<void *,BCryptKeyFunctor<void *>,DummyContext>::~Auto<void *,BCryptKeyFunctor<void *>,DummyContext>(phKey);
  return v16;
}

```

## disassembly

```asm
0x180028710  push    rbp
0x180028712  push    rbx
0x180028713  push    rsi
0x180028714  push    rdi
0x180028715  push    r12
0x180028717  push    r13
0x180028719  push    r14
0x18002871b  push    r15
0x18002871d  lea     rbp, [rsp-8]
0x180028722  sub     rsp, 108h
0x180028729  mov     rax, cs:__security_cookie
0x180028730  xor     rax, rsp
0x180028733  mov     [rbp+40h+var_48], rax
0x180028737  mov     r15d, r9d
0x18002873a  mov     r14, r8
0x18002873d  mov     esi, edx
0x18002873f  mov     rdi, rcx
0x180028742  mov     rbx, [rbp+40h+arg_20]
0x180028746  mov     r12, [rbp+40h+arg_28]
0x18002874a  xor     r13d, r13d
0x18002874d  mov     [rsp+140h+var_100], r13d
0x180028752  mov     [rsp+140h+var_FC], r13d
0x180028757  mov     [rsp+140h+phKey], r13
0x18002875c  mov     [rbp+40h+var_C0], r13
0x180028760  mov     [rsp+140h+var_C8], r13
0x180028765  mov     [rsp+140h+phAlgorithm], r13
0x18002876a  mov     [rsp+140h+var_D8], r13
0x18002876f  mov     [rsp+140h+var_E0], r13
0x180028774  lea     rcx, aLitecryptutili; "LiteCryptUtilities::DeriveKeyWithSP8001"...
0x18002877b  mov     [rbp+40h+var_98], rcx
0x18002877f  lea     rax, [rsp+140h+var_100]
0x180028784  mov     [rbp+40h+var_90], rax
0x180028788  mov     [rbp+40h+var_88], r13
0x18002878c  mov     [rbp+40h+var_80], r13
0x180028790  xor     r9d, r9d; unsigned int
0x180028793  mov     r8d, 477h; char *
0x180028799  mov     rdx, rcx; char *
0x18002879c  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800287a3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800287a8  nop
0x1800287a9  lea     rax, qword_180041DC0
0x1800287b0  mov     [rsp+140h+pbSecret], rax; int *
0x1800287b5  lea     r9d, [r13+0Ah]; unsigned __int64
0x1800287b9  lea     r8, [rsp+140h+var_100]; int *
0x1800287be  lea     rdx, aLitecryptutili; "LiteCryptUtilities::DeriveKeyWithSP8001"...
0x1800287c5  lea     rcx, [rbp+40h+var_B8]; this
0x1800287c9  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800287ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800287d2  inc     rax
0x1800287d5  cmp     [rbx+rax], r13b
0x1800287d9  jnz     short loc_1800287D2
0x1800287db  mov     [rbp+40h+var_78], eax
0x1800287de  mov     [rbp+40h+var_74], 0Dh
0x1800287e5  mov     [rbp+40h+var_70], rbx
0x1800287e9  mov     [rbp+40h+var_68], r15d
0x1800287ed  mov     eax, 0Eh
0x1800287f2  mov     [rbp+40h+var_64], eax
0x1800287f5  mov     [rbp+40h+var_60], r14
0x1800287f9  mov     [rbp+40h+var_58], rax
0x1800287fd  lea     rax, aSha256_0; "SHA256"
0x180028804  mov     [rbp+40h+var_50], rax
0x180028808  mov     [rsp+140h+var_F8], r13d
0x18002880d  mov     [rsp+140h+var_F4], 3
0x180028815  lea     rax, [rbp+40h+var_78]
0x180028819  mov     [rsp+140h+var_F0], rax
0x18002881e  xor     r9d, r9d; dwFlags
0x180028821  xor     r8d, r8d; pszImplementation
0x180028824  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x18002882b  lea     rcx, [rsp+140h+phAlgorithm]; phAlgorithm
0x180028830  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180028836  mov     ebx, 80070000h
0x18002883b  test    eax, eax
0x18002883d  jle     short loc_180028844
0x18002883f  movzx   eax, ax
0x180028842  or      eax, ebx
0x180028844  mov     [rsp+140h+var_100], eax
0x180028848  test    eax, eax
0x18002884a  jns     short loc_180028863
0x18002884c  lea     r8, aHrHresultFromW_5; "hr = HRESULT_FROM_WIN32(::BCryptOpenAlg"...
0x180028853  mov     [rsp+140h+pbSecret], r8
0x180028858  mov     r8d, 49Fh
0x18002885e  jmp     loc_1800288F3
0x180028863  mov     [rsp+140h+dwFlags], r13d; dwFlags
0x180028868  mov     [rsp+140h+cbSecret], esi; cbSecret
0x18002886c  mov     [rsp+140h+pbSecret], rdi; pbSecret
0x180028871  xor     r9d, r9d; cbKeyObject
0x180028874  xor     r8d, r8d; pbKeyObject
0x180028877  lea     rdx, [rsp+140h+phKey]; phKey
0x18002887c  mov     rcx, [rsp+140h+phAlgorithm]; hAlgorithm
0x180028881  call    cs:__imp_BCryptGenerateSymmetricKey
0x180028887  test    eax, eax
0x180028889  jle     short loc_180028890
0x18002888b  movzx   eax, ax
0x18002888e  or      eax, ebx
0x180028890  mov     [rsp+140h+var_100], eax
0x180028894  test    eax, eax
0x180028896  jns     short loc_1800288A7
0x180028898  lea     rcx, aHrHresultFromW_9; "hr = HRESULT_FROM_WIN32(::BCryptGenerat"...
0x18002889f  mov     r8d, 4A8h
0x1800288a5  jmp     short loc_1800288EE
0x1800288a7  mov     [rsp+140h+cbSecret], r13d
0x1800288ac  lea     rax, [rsp+140h+var_FC]
0x1800288b1  mov     [rsp+140h+pbSecret], rax
0x1800288b6  mov     r9d, dword ptr [rbp+40h+arg_30]
0x1800288bd  mov     r8, r12
0x1800288c0  lea     rdx, [rsp+140h+var_F8]
0x1800288c5  mov     rcx, [rsp+140h+phKey]
0x1800288ca  call    cs:__imp_BCryptKeyDerivation
0x1800288d0  test    eax, eax
0x1800288d2  jle     short loc_1800288D9
0x1800288d4  movzx   eax, ax
0x1800288d7  or      eax, ebx
0x1800288d9  mov     [rsp+140h+var_100], eax
0x1800288dd  test    eax, eax
0x1800288df  jns     short loc_180028909
0x1800288e1  lea     rcx, aHrHresultFromW_6; "hr = HRESULT_FROM_WIN32(::BCryptKeyDeri"...
0x1800288e8  mov     r8d, 4B0h; unsigned int
0x1800288ee  mov     [rsp+140h+pbSecret], rcx; char *
0x1800288f3  mov     r9d, eax; int
0x1800288f6  lea     rdx, aLitecryptutili; "LiteCryptUtilities::DeriveKeyWithSP8001"...
0x1800288fd  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180028904  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180028909  mov     ebx, [rsp+140h+var_100]
0x18002890d  mov     r9, [rbp+40h+var_B8]; int *
0x180028911  mov     r8, [rbp+40h+var_B0]; unsigned __int64
0x180028915  mov     rdx, [rbp+40h+var_A8]
0x180028919  mov     edx, [rdx]; int
0x18002891b  mov     rcx, [rbp+40h+var_A0]; char *
0x18002891f  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180028924  nop
0x180028925  lea     rcx, [rbp+40h+var_98]
0x180028929  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002892e  nop
0x18002892f  lea     rcx, [rsp+140h+phAlgorithm]
0x180028934  call    ??1?$Auto@PEAXV?$BCryptAlgFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(void)
0x180028939  nop
0x18002893a  lea     rcx, [rsp+140h+phKey]
0x18002893f  call    ??1?$Auto@PEAXV?$BCryptKeyFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptKeyFunctor<void *>,DummyContext>::~Auto<void *,BCryptKeyFunctor<void *>,DummyContext>(void)
0x180028944  mov     eax, ebx
0x180028946  mov     rcx, [rbp+40h+var_48]
0x18002894a  xor     rcx, rsp; StackCookie
0x18002894d  call    __security_check_cookie
0x180028952  add     rsp, 108h
0x180028959  pop     r15
0x18002895b  pop     r14
0x18002895d  pop     r13
0x18002895f  pop     r12
0x180028961  pop     rdi
0x180028962  pop     rsi
0x180028963  pop     rbx
0x180028964  pop     rbp
0x180028965  retn
```
