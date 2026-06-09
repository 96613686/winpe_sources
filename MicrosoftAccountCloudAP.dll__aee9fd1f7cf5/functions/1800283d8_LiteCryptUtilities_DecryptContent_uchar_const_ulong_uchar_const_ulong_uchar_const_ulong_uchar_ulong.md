# LiteCryptUtilities::DecryptContent(uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800283d8`
- end: `0x180028707`
- name: `?DecryptContent@LiteCryptUtilities@@YAJPEBEK0K0KPEAPEAEPEAK@Z`
- size: `815`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret, PUCHAR pbIV, ULONG cbIV, PUCHAR pbInput, ULONG cbInput, UCHAR **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002e5b0`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000def8`
- `0x180023b5c`
- `0x180023c04`
- `0x180026c8c`
- `0x1800280dc`
- `0x180028110`
- `0x1800283d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800285f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800285f4`
- `bcrypt!BCryptSetProperty` at `0x18002850c`
- `bcrypt!BCryptSetProperty` at `0x18002850c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028556`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180028556`
- `bcrypt!BCryptDecrypt` at `0x1800285bd`
- `bcrypt!BCryptDecrypt` at `0x18002866a`
- `bcrypt!BCryptDecrypt` at `0x1800285bd`
- `bcrypt!BCryptDecrypt` at `0x18002866a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800284a8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800284a8`

## string_xrefs

- `0x1800284c2`: `hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spAlgorithm, BCRYPT_AES_ALGORITHM, nullptr, 0))`

## pseudocode

```c
__int64 __fastcall LiteCryptUtilities::DecryptContent(
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR pbIV,
        ULONG cbIV,
        PUCHAR pbInput,
        ULONG cbInput,
        UCHAR **a7,
        unsigned __int8 **a8)
{
  int SymmetricKey; // eax
  unsigned int v13; // r8d
  UCHAR *v14; // rbx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  int v17; // r8d
  const unsigned __int16 *dwFlags; // [rsp+20h] [rbp-C1h]
  const char *dwFlagsa; // [rsp+20h] [rbp-C1h]
  int v21; // [rsp+50h] [rbp-91h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-8Dh] BYREF
  UCHAR *v23; // [rsp+58h] [rbp-89h] BYREF
  __int64 v24; // [rsp+60h] [rbp-81h]
  __int64 v25; // [rsp+68h] [rbp-79h]
  BCRYPT_ALG_HANDLE phAlgorithm[3]; // [rsp+70h] [rbp-71h] BYREF
  BCRYPT_KEY_HANDLE phKey[3]; // [rsp+88h] [rbp-59h] BYREF
  int *v28[4]; // [rsp+A0h] [rbp-41h] BYREF
  _QWORD v29[12]; // [rsp+C0h] [rbp-21h] BYREF

  v21 = 0;
  pcbResult = 0;
  memset(phKey, 0, sizeof(phKey));
  memset(phAlgorithm, 0, sizeof(phAlgorithm));
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v29[0] = "LiteCryptUtilities::DecryptContent";
  v29[1] = &v21;
  v29[2] = 0;
  v29[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::DecryptContent",
    (const char *)0x4CA,
    0,
    dwFlags);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v28, "LiteCryptUtilities::DecryptContent", &v21, 10, &qword_180041D68);
  *a7 = 0;
  *(_DWORD *)a8 = 0;
  SymmetricKey = BCryptOpenAlgorithmProvider(phAlgorithm, L"AES", 0, 0);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    dwFlagsa = "hr = HRESULT_FROM_WIN32(::BCryptOpenAlgorithmProvider( &spAlgorithm, BCRYPT_AES_ALGORITHM, nullptr, 0))";
    v13 = 1245;
LABEL_5:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DecryptContent",
      v13,
      SymmetricKey,
      dwFlagsa);
    goto LABEL_26;
  }
  SymmetricKey = BCryptSetProperty(phAlgorithm[0], L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    dwFlagsa = "hr = HRESULT_FROM_WIN32(::BCryptSetProperty( spAlgorithm, BCRYPT_CHAINING_MODE, reinterpret_cast<PUCHAR>("
               "BCRYPT_CHAIN_MODE_CBC), static_cast<ULONG>(sizeof(BCRYPT_CHAIN_MODE_CBC)), 0))";
    v13 = 1252;
    goto LABEL_5;
  }
  SymmetricKey = BCryptGenerateSymmetricKey(phAlgorithm[0], phKey, 0, 0, pbSecret, cbSecret, 0);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    dwFlagsa = "hr = HRESULT_FROM_WIN32(::BCryptGenerateSymmetricKey( spAlgorithm, &spKey, nullptr, 0, static_cast<PUCHAR"
               ">(const_cast<BYTE*>(pEncryptionKey)), encryptionKeySizeBytes, 0))";
    v13 = 1261;
    goto LABEL_5;
  }
  SymmetricKey = BCryptDecrypt(phKey[0], pbInput, cbInput, 0, pbIV, cbIV, 0, 0, &pcbResult, 1u);
  if ( SymmetricKey > 0 )
    SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
  v21 = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    dwFlagsa = "hr = HRESULT_FROM_WIN32(::BCryptDecrypt( spKey, static_cast<PUCHAR>(const_cast<BYTE*>(pEncryptedBlob)), e"
               "ncryptedBlobSizeBytes, nullptr, static_cast<PUCHAR>(const_cast<BYTE*>(pInitializationVector)), initializa"
               "tionVectorSizeBytes, nullptr, 0, &resultSizeBytes, BCRYPT_BLOCK_PADDING))";
    v13 = 1273;
    goto LABEL_5;
  }
  v14 = (UCHAR *)LocalAlloc(0x40u, pcbResult);
  Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)&v23);
  v23 = v14;
  if ( v14 )
  {
    SymmetricKey = BCryptDecrypt(phKey[0], pbInput, cbInput, 0, pbIV, cbIV, v14, pcbResult, &pcbResult, 1u);
    if ( SymmetricKey > 0 )
      SymmetricKey = (unsigned __int16)SymmetricKey | 0x80070000;
    v21 = SymmetricKey;
    if ( SymmetricKey < 0 )
    {
      dwFlagsa = "hr = HRESULT_FROM_WIN32(::BCryptDecrypt( spKey, static_cast<PUCHAR>(const_cast<BYTE*>(pEncryptedBlob)),"
                 " encryptedBlobSizeBytes, nullptr, static_cast<PUCHAR>(const_cast<BYTE*>(pInitializationVector)), initia"
                 "lizationVectorSizeBytes, spDecryptedBlob, resultSizeBytes, &resultSizeBytes, BCRYPT_BLOCK_PADDING))";
      v13 = 1291;
      goto LABEL_5;
    }
    v23 = 0;
    v24 = 0;
    *a7 = v14;
    *(_DWORD *)a8 = pcbResult;
  }
  else
  {
    v21 = -2147024882;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::DecryptContent",
      0x4FEu,
      -2147024882,
      "hr = E_OUTOFMEMORY");
  }
LABEL_26:
  v15 = v21;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v28[3], *v28[2], (unsigned __int64)v28[1], v28[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v29, v16, v17);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v23);
  Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(phAlgorithm);
  Auto<void *,BCryptKeyFunctor<void *>,DummyContext>::~Auto<void *,BCryptKeyFunctor<void *>,DummyContext>(phKey);
  return v15;
}

```

## disassembly

```asm
0x1800283d8  push    rbp
0x1800283da  push    rbx
0x1800283db  push    rsi
0x1800283dc  push    rdi
0x1800283dd  push    r12
0x1800283df  push    r13
0x1800283e1  push    r14
0x1800283e3  push    r15
0x1800283e5  lea     rbp, [rsp-7]
0x1800283ea  sub     rsp, 0E8h
0x1800283f1  mov     esi, r9d
0x1800283f4  mov     r14, r8
0x1800283f7  mov     ebx, edx
0x1800283f9  mov     rdi, rcx
0x1800283fc  xor     r13d, r13d
0x1800283ff  mov     [rsp+120h+var_D0], r13d
0x180028404  mov     [rsp+120h+var_CC], r13d
0x180028409  mov     [rbp+3Fh+phKey], r13
0x18002840d  mov     [rbp+3Fh+var_88], r13
0x180028411  mov     [rbp+3Fh+var_90], r13
0x180028415  mov     [rbp+3Fh+phAlgorithm], r13
0x180028419  mov     [rbp+3Fh+var_A0], r13
0x18002841d  mov     [rbp+3Fh+var_A8], r13
0x180028421  mov     [rsp+120h+var_C8], r13
0x180028426  mov     [rbp+3Fh+var_B8], r13
0x18002842a  mov     [rsp+120h+var_C0], r13
0x18002842f  lea     r15, aLitecryptutili_1; "LiteCryptUtilities::DecryptContent"
0x180028436  mov     [rbp+3Fh+var_60], r15
0x18002843a  lea     rax, [rsp+120h+var_D0]
0x18002843f  mov     [rbp+3Fh+var_58], rax
0x180028443  mov     [rbp+3Fh+var_50], r13
0x180028447  mov     [rbp+3Fh+var_48], r13
0x18002844b  xor     r9d, r9d; unsigned int
0x18002844e  mov     r8d, 4CAh; char *
0x180028454  mov     rdx, r15; char *
0x180028457  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18002845e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180028463  nop
0x180028464  lea     rax, qword_180041D68
0x18002846b  mov     qword ptr [rsp+120h+dwFlags], rax; int *
0x180028470  lea     r9d, [r13+0Ah]; unsigned __int64
0x180028474  lea     r8, [rsp+120h+var_D0]; int *
0x180028479  mov     rdx, r15; char *
0x18002847c  lea     rcx, [rbp+3Fh+var_80]; this
0x180028480  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180028485  mov     r15, [rbp+3Fh+arg_30]
0x180028489  mov     [r15], r13
0x18002848c  mov     r12, [rbp+3Fh+arg_38]
0x180028493  mov     [r12], r13d
0x180028497  xor     r9d, r9d; dwFlags
0x18002849a  xor     r8d, r8d; pszImplementation
0x18002849d  lea     rdx, pszAlgId; "AES"
0x1800284a4  lea     rcx, [rbp+3Fh+phAlgorithm]; phAlgorithm
0x1800284a8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800284ae  test    eax, eax
0x1800284b0  jle     short loc_1800284BA
0x1800284b2  movzx   eax, ax
0x1800284b5  or      eax, 80070000h
0x1800284ba  mov     [rsp+120h+var_D0], eax
0x1800284be  test    eax, eax
0x1800284c0  jns     short loc_1800284EF
0x1800284c2  lea     r8, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(::BCryptOpenAlg"...
0x1800284c9  mov     qword ptr [rsp+120h+dwFlags], r8; char *
0x1800284ce  mov     r8d, 4DDh; unsigned int
0x1800284d4  mov     r9d, eax; int
0x1800284d7  lea     rdx, aLitecryptutili_1; "LiteCryptUtilities::DecryptContent"
0x1800284de  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800284e5  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800284ea  jmp     loc_1800286AD
0x1800284ef  mov     [rsp+120h+dwFlags], r13d; dwFlags
0x1800284f4  mov     r9d, 20h ; ' '; cbInput
0x1800284fa  lea     r8, pbInput; "ChainingModeCBC"
0x180028501  lea     rdx, pszProperty; "ChainingMode"
0x180028508  mov     rcx, [rbp+3Fh+phAlgorithm]; hObject
0x18002850c  call    cs:__imp_BCryptSetProperty
0x180028512  test    eax, eax
0x180028514  jle     short loc_18002851E
0x180028516  movzx   eax, ax
0x180028519  or      eax, 80070000h
0x18002851e  mov     [rsp+120h+var_D0], eax
0x180028522  test    eax, eax
0x180028524  jns     short loc_18002853A
0x180028526  lea     rcx, aHrHresultFromW_3; "hr = HRESULT_FROM_WIN32(::BCryptSetProp"...
0x18002852d  mov     qword ptr [rsp+120h+dwFlags], rcx
0x180028532  mov     r8d, 4E4h
0x180028538  jmp     short loc_1800284D4
0x18002853a  mov     [rsp+120h+var_F0], r13d; dwFlags
0x18002853f  mov     [rsp+120h+cbSecret], ebx; cbSecret
0x180028543  mov     qword ptr [rsp+120h+dwFlags], rdi; pbSecret
0x180028548  xor     r9d, r9d; cbKeyObject
0x18002854b  xor     r8d, r8d; pbKeyObject
0x18002854e  lea     rdx, [rbp+3Fh+phKey]; phKey
0x180028552  mov     rcx, [rbp+3Fh+phAlgorithm]; hAlgorithm
0x180028556  call    cs:__imp_BCryptGenerateSymmetricKey
0x18002855c  mov     edi, 80070000h
0x180028561  test    eax, eax
0x180028563  jle     short loc_18002856A
0x180028565  movzx   eax, ax
0x180028568  or      eax, edi
0x18002856a  mov     [rsp+120h+var_D0], eax
0x18002856e  test    eax, eax
0x180028570  jns     short loc_180028589
0x180028572  lea     rcx, aHrHresultFromW_2; "hr = HRESULT_FROM_WIN32(::BCryptGenerat"...
0x180028579  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18002857e  mov     r8d, 4EDh
0x180028584  jmp     loc_1800284D4
0x180028589  mov     [rsp+120h+var_D8], 1; dwFlags
0x180028591  lea     rax, [rsp+120h+var_CC]
0x180028596  mov     [rsp+120h+pcbResult], rax; pcbResult
0x18002859b  mov     [rsp+120h+cbOutput], r13d; cbOutput
0x1800285a0  mov     qword ptr [rsp+120h+var_F0], r13; pbOutput
0x1800285a5  mov     [rsp+120h+cbSecret], esi; cbIV
0x1800285a9  mov     qword ptr [rsp+120h+dwFlags], r14; pbIV
0x1800285ae  xor     r9d, r9d; pPaddingInfo
0x1800285b1  mov     r8d, [rbp+3Fh+cbInput]; cbInput
0x1800285b5  mov     rdx, [rbp+3Fh+pbInput]; pbInput
0x1800285b9  mov     rcx, [rbp+3Fh+phKey]; hKey
0x1800285bd  call    cs:__imp_BCryptDecrypt
0x1800285c3  test    eax, eax
0x1800285c5  jle     short loc_1800285CC
0x1800285c7  movzx   eax, ax
0x1800285ca  or      eax, edi
0x1800285cc  mov     [rsp+120h+var_D0], eax
0x1800285d0  test    eax, eax
0x1800285d2  jns     short loc_1800285EB
0x1800285d4  lea     rcx, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(::BCryptDecrypt"...
0x1800285db  mov     qword ptr [rsp+120h+dwFlags], rcx
0x1800285e0  mov     r8d, 4F9h
0x1800285e6  jmp     loc_1800284D4
0x1800285eb  mov     edx, [rsp+120h+var_CC]; uBytes
0x1800285ef  mov     ecx, 40h ; '@'; uFlags
0x1800285f4  call    cs:__imp_LocalAlloc
0x1800285fa  mov     rbx, rax
0x1800285fd  lea     rcx, [rsp+120h+var_C8]
0x180028602  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180028607  mov     [rsp+120h+var_C8], rbx
0x18002860c  test    rbx, rbx
0x18002860f  jnz     short loc_180028633
0x180028611  mov     r9d, 8007000Eh
0x180028617  mov     [rsp+120h+var_D0], r9d
0x18002861c  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180028623  mov     qword ptr [rsp+120h+dwFlags], rax
0x180028628  mov     r8d, 4FEh
0x18002862e  jmp     loc_1800284D7
0x180028633  mov     eax, [rsp+120h+var_CC]
0x180028637  mov     [rsp+120h+var_D8], 1; dwFlags
0x18002863f  lea     rcx, [rsp+120h+var_CC]
0x180028644  mov     [rsp+120h+pcbResult], rcx; pcbResult
0x180028649  mov     [rsp+120h+cbOutput], eax; cbOutput
0x18002864d  mov     qword ptr [rsp+120h+var_F0], rbx; pbOutput
0x180028652  mov     [rsp+120h+cbSecret], esi; cbIV
0x180028656  mov     qword ptr [rsp+120h+dwFlags], r14; pbIV
0x18002865b  xor     r9d, r9d; pPaddingInfo
0x18002865e  mov     r8d, [rbp+3Fh+cbInput]; cbInput
0x180028662  mov     rdx, [rbp+3Fh+pbInput]; pbInput
0x180028666  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18002866a  call    cs:__imp_BCryptDecrypt
0x180028670  test    eax, eax
0x180028672  jle     short loc_180028679
0x180028674  movzx   eax, ax
0x180028677  or      eax, edi
0x180028679  mov     [rsp+120h+var_D0], eax
0x18002867d  test    eax, eax
0x18002867f  jns     short loc_180028698
0x180028681  lea     rcx, aHrHresultFromW_8; "hr = HRESULT_FROM_WIN32(::BCryptDecrypt"...
0x180028688  mov     qword ptr [rsp+120h+dwFlags], rcx
0x18002868d  mov     r8d, 50Bh
0x180028693  jmp     loc_1800284D4
0x180028698  mov     [rsp+120h+var_C8], r13
0x18002869d  mov     [rsp+120h+var_C0], r13
0x1800286a2  mov     [r15], rbx
0x1800286a5  mov     eax, [rsp+120h+var_CC]
0x1800286a9  mov     [r12], eax
0x1800286ad  mov     ebx, [rsp+120h+var_D0]
0x1800286b1  mov     r9, [rbp+3Fh+var_80]; int *
0x1800286b5  mov     r8, [rbp+3Fh+var_78]; unsigned __int64
0x1800286b9  mov     rdx, [rbp+3Fh+var_70]
0x1800286bd  mov     edx, [rdx]; int
0x1800286bf  mov     rcx, [rbp+3Fh+var_68]; char *
0x1800286c3  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800286c8  nop
0x1800286c9  lea     rcx, [rbp+3Fh+var_60]
0x1800286cd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800286d2  nop
0x1800286d3  lea     rcx, [rsp+120h+var_C8]
0x1800286d8  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800286dd  nop
0x1800286de  lea     rcx, [rbp+3Fh+phAlgorithm]
0x1800286e2  call    ??1?$Auto@PEAXV?$BCryptAlgFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptAlgFunctor<void *>,DummyContext>::~Auto<void *,BCryptAlgFunctor<void *>,DummyContext>(void)
0x1800286e7  nop
0x1800286e8  lea     rcx, [rbp+3Fh+phKey]
0x1800286ec  call    ??1?$Auto@PEAXV?$BCryptKeyFunctor@PEAX@@VDummyContext@@@@QEAA@XZ; Auto<void *,BCryptKeyFunctor<void *>,DummyContext>::~Auto<void *,BCryptKeyFunctor<void *>,DummyContext>(void)
0x1800286f1  mov     eax, ebx
0x1800286f3  add     rsp, 0E8h
0x1800286fa  pop     r15
0x1800286fc  pop     r14
0x1800286fe  pop     r13
0x180028700  pop     r12
0x180028702  pop     rdi
0x180028703  pop     rsi
0x180028704  pop     rbx
0x180028705  pop     rbp
0x180028706  retn
```
