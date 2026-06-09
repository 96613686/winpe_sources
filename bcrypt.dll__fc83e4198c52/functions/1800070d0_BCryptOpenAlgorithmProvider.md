# BCryptOpenAlgorithmProvider

- ea: `0x1800070d0`
- end: `0x1800078cb`
- name: `BCryptOpenAlgorithmProvider`
- size: `2043`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId, LPCWSTR pszImplementation, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000466c`
- `0x180006bd0`
- `0x180016298`

## callees

- `0x180002de0`
- `0x180004200`
- `0x180005060`
- `0x1800070d0`
- `0x180007d60`
- `0x180009430`
- `0x18000b094`
- `0x18000ccf0`
- `0x18000d030`
- `0x18000d8e0`
- `0x18000d948`
- `0x18000dc6c`
- `0x18000e150`
- `0x18000f9a8`
- `0x180010ed4`
- `0x180010f80`
- `0x180014f98`
- `0x18001b7a9`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x18000733b`
- `ntdll!wcsncpy_s` at `0x18000733b`
- `ntdll!RtlDllShutdownInProgress` at `0x1800077a3`
- `ntdll!RtlDllShutdownInProgress` at `0x1800077a3`

## string_xrefs

- `0x180007247`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800072a1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800072da`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000734d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000776f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptOpenAlgorithmProvider(
        BCRYPT_ALG_HANDLE *phAlgorithm,
        LPCWSTR pszAlgId,
        LPCWSTR pszImplementation,
        ULONG dwFlags)
{
  const WCHAR *v4; // rsi
  __int64 v5; // rdi
  PCRYPT_PROVIDER_REFS v6; // r13
  __int64 (__fastcall *v7)(_QWORD, const wchar_t *, char *, __int64, unsigned int *, _DWORD); // r12
  ULONG v8; // r15d
  LPCWSTR v9; // r14
  __int64 v11; // r9
  char TrustedEnvironment; // al
  NTSTATUS Provider; // ebx
  ULONG v14; // r8d
  const WCHAR *v15; // rdi
  int v16; // eax
  char *v17; // rax
  char *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // r12d
  void *v22; // r8
  __int64 *v23; // rdx
  PCRYPT_PROVIDER_REF *rgpProviders; // rcx
  PWSTR pszProvider; // rax
  __int64 v26; // r9
  __int64 v27; // rdx
  _OWORD *v28; // rax
  _OWORD *v29; // rcx
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  ULONG v37; // r12d
  _QWORD *v38; // r15
  NTSTATUS v39; // eax
  __int64 v40; // r15
  __int64 v41; // rcx
  __int64 v42; // r9
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rdi
  PCRYPT_PROVIDER_REF *v46; // rcx
  __int64 v47; // rbx
  PCRYPT_PROPERTY_REF v48; // rdx
  char v49; // al
  __int64 v50; // r8
  int v51; // r9d
  int v52; // r8d
  char v54; // [rsp+40h] [rbp-C0h]
  _BYTE pcbBuffer[15]; // [rsp+41h] [rbp-BFh] BYREF
  LPCWSTR v56; // [rsp+50h] [rbp-B0h]
  ULONG v57; // [rsp+58h] [rbp-A8h] BYREF
  PCRYPT_PROVIDER_REFS v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-98h] BYREF
  int v60; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 (__fastcall *v61)(char *, LPCWSTR, _QWORD); // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v63)(_QWORD, const wchar_t *, char *, __int64, unsigned int *, _DWORD); // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR v64; // [rsp+88h] [rbp-78h]
  __int64 v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  void (__fastcall *v67)(_QWORD, _QWORD); // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v68)(_QWORD, PWSTR, PUCHAR, _QWORD, _DWORD); // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v69[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v70; // [rsp+D0h] [rbp-30h]
  __int64 v71; // [rsp+D8h] [rbp-28h]
  __int64 *v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  ULONG *v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  _BYTE *v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  char v78[16]; // [rsp+110h] [rbp+10h] BYREF
  char v79[16]; // [rsp+120h] [rbp+20h] BYREF
  char v80[16]; // [rsp+130h] [rbp+30h] BYREF
  char v81[256]; // [rsp+140h] [rbp+40h] BYREF

  v4 = pszAlgId;
  v56 = pszAlgId;
  v57 = dwFlags;
  v67 = 0;
  v5 = 0;
  *(_QWORD *)&pcbBuffer[7] = 0;
  v6 = 0;
  v58 = 0;
  v7 = 0;
  pcbBuffer[0] = 0;
  v8 = dwFlags;
  v60 = 0;
  v9 = pszImplementation;
  v68 = 0;
  v63 = 0;
  v61 = 0;
  v64 = pszImplementation;
  v66 = (__int64)phAlgorithm;
  v59 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      (_DWORD)pszImplementation,
      (_DWORD)pszAlgId,
      (__int64)pszImplementation,
      dwFlags);
  if ( !phAlgorithm || !v4 )
  {
    v11 = 1955;
    goto LABEL_69;
  }
  if ( (v8 & 1) != 0 )
  {
    v11 = 1965;
LABEL_69:
    Provider = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v11);
    goto LABEL_70;
  }
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) == 0 )
  {
    Provider = VsmOpenAlgorithmProvider(phAlgorithm, v4, v9, v8);
    goto LABEL_70;
  }
  v14 = 0;
  v54 = 0;
  if ( g_fLoadCNGDone )
  {
    v15 = v9;
    if ( !v9 )
    {
      v54 = 1;
      v14 = 2;
    }
  }
  else
  {
    v15 = L"Microsoft Primitive Provider";
  }
  *(_DWORD *)&pcbBuffer[3] = 0;
  v16 = BCryptResolveProvidersForBcoapCached(v4, v15, v14, (ULONG *)&pcbBuffer[3], &v58, (__int64)pcbBuffer);
  Provider = v16;
  if ( v16 < 0 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v15, (_DWORD)v4, v8, v16, 1);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2030);
    v6 = v58;
LABEL_18:
    v5 = 0;
    goto LABEL_70;
  }
  v6 = v58;
  LODWORD(v58) = **(_DWORD **)v58->rgpProviders;
  if ( (unsigned int)((_DWORD)v58 - 1) > 7 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v15, (_DWORD)v4, v8, v16, 1);
    Provider = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2061);
    goto LABEL_18;
  }
  v17 = (char *)SafeAllocaAllocateFromHeap(968);
  v18 = v17;
  if ( !v17 )
  {
    Provider = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2076);
    v9 = v64;
    goto LABEL_18;
  }
  memset_0(v17, 0, 0x3C8u);
  *((_DWORD *)v18 + 9) = (_DWORD)v58;
  *(_DWORD *)v18 = 968;
  *((_DWORD *)v18 + 1) = 1431655761;
  *((_DWORD *)v18 + 4) = 1;
  wcsncpy_s((wchar_t *)v18 + 222, 0x104u, v4, 0xFFFFFFFFFFFFFFFFuLL);
  v20 = 0;
  *((_DWORD *)v18 + 8) = 0;
  *(_DWORD *)&pcbBuffer[3] = 0;
  if ( !v6->cProviders )
  {
    v38 = v18 + 24;
    goto LABEL_43;
  }
  v21 = (int)v56;
  v22 = v18 + 48;
  v23 = (__int64 *)(v18 + 40);
  while ( 1 )
  {
    rgpProviders = v6->rgpProviders;
    v62 = v20;
    Provider = LoadProviderEx((__int64)rgpProviders[v20], (int)v23, (__int64)v22, v23, v22);
    pszProvider = v6->rgpProviders[v62]->pszProvider;
    *(_QWORD *)&pcbBuffer[7] = pszProvider;
    v65 = (__int64)pszProvider;
    if ( Provider >= 0 )
      break;
    LogBCryptOpenProviderFailure((_DWORD)pszProvider, v21, v8, Provider, 2);
    v26 = 2140;
LABEL_27:
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v26);
    if ( v54 != 1 )
      goto LABEL_57;
    v23 = (__int64 *)(v18 + 40);
LABEL_40:
    v22 = v18 + 48;
    v20 = (unsigned int)(*(_DWORD *)&pcbBuffer[3] + 1);
    *(_DWORD *)&pcbBuffer[3] = v20;
    if ( (unsigned int)v20 >= v6->cProviders )
    {
      v40 = v65;
      *(_QWORD *)&pcbBuffer[7] = v65;
      *(_DWORD *)&pcbBuffer[3] = v20;
      DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2276);
      v5 = v40;
      goto LABEL_58;
    }
  }
  v27 = 3;
  v28 = v18 + 48;
  v29 = v69;
  do
  {
    v30 = v28[1];
    *v29 = *v28;
    v31 = v28[2];
    v29[1] = v30;
    v32 = v28[3];
    v29[2] = v31;
    v33 = v28[4];
    v29[3] = v32;
    v34 = v28[5];
    v29[4] = v33;
    v35 = v28[6];
    v29[5] = v34;
    v36 = v28[7];
    v28 += 8;
    v29[6] = v35;
    v29[7] = v36;
    v29 += 8;
    --v27;
  }
  while ( v27 );
  *(_QWORD *)v29 = *(_QWORD *)v28;
  Provider = ValidateFunctionTable(
               (_DWORD)v58,
               (unsigned int)v69,
               (unsigned int)&v61,
               (unsigned int)&v67,
               (__int64)&v68,
               (__int64)&v63);
  if ( Provider < 0 )
  {
    LogBCryptOpenProviderFailure(v6->rgpProviders[v62]->pszProvider, v21, v8, Provider, 3);
    v26 = 2179;
    goto LABEL_27;
  }
  v37 = v57;
  v38 = v18 + 24;
  Provider = v61(v18 + 24, v56, v57);
  if ( Provider != -1073700863 )
    goto LABEL_37;
  if ( (_DWORD)v58 != 2 || (v37 & 0x68) != 8 )
    goto LABEL_38;
  v39 = v61(v18 + 24, v56, v37 & 0xFFFFFFF7);
  *((_DWORD *)v18 + 2) |= 8u;
  Provider = v39;
LABEL_37:
  if ( Provider < 0 )
  {
LABEL_38:
    v8 = v57;
    LogBCryptOpenProviderFailure(v6->rgpProviders[v62]->pszProvider, (_DWORD)v56, v57, Provider, 4);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 2243);
    if ( v54 != 1 )
      goto LABEL_57;
    UnloadProvider(*((_QWORD *)v18 + 5));
    v21 = (int)v56;
    v23 = (__int64 *)(v18 + 40);
    *((_QWORD *)v18 + 5) = 0;
    goto LABEL_40;
  }
  v7 = v63;
LABEL_43:
  if ( (_DWORD)v58 != 2 )
  {
    if ( (_DWORD)v58 == 3 )
    {
      if ( !v7 )
      {
        Provider = -1073741595;
        v41 = 3221225701LL;
        v42 = 2313;
        goto LABEL_55;
      }
      v38 = v18 + 24;
      v43 = v7(*((_QWORD *)v18 + 3), L"PaddingSchemes", v18 + 440, v59, &v59, 0);
      Provider = v43;
      if ( v43 < 0 )
      {
        v42 = 2325;
        goto LABEL_54;
      }
    }
LABEL_61:
    v45 = *(unsigned int *)&pcbBuffer[3];
    v46 = v6->rgpProviders;
    if ( v46[*(unsigned int *)&pcbBuffer[3]]->cProperties )
    {
      v47 = 0;
      do
      {
        v48 = v46[v45]->rgpProperties[v47];
        v68(*((_QWORD *)v18 + 3), v48->pszProperty, v48->pbValue, v48->cbValue, 0);
        v46 = v6->rgpProviders;
        v47 = (unsigned int)(v47 + 1);
      }
      while ( (unsigned int)v47 < v46[v45]->cProperties );
    }
    *(_QWORD *)v66 = v18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v19, v18);
    v4 = v56;
    Provider = 0;
    v9 = v64;
    v5 = *(_QWORD *)&pcbBuffer[7];
    goto LABEL_70;
  }
  if ( v7 )
  {
    v38 = v18 + 24;
    v43 = v7(*((_QWORD *)v18 + 3), L"HashBlockLength", v18 + 12, 4, (unsigned int *)&v60, 0);
    Provider = v43;
    if ( v43 < 0 )
    {
      v42 = 2304;
LABEL_54:
      v41 = (unsigned int)v43;
      goto LABEL_55;
    }
    goto LABEL_61;
  }
  Provider = -1073741595;
  v41 = 3221225701LL;
  v42 = 2292;
LABEL_55:
  DebugTraceError(v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v42);
  if ( v67 )
    v67(*v38, 0);
LABEL_57:
  v5 = *(_QWORD *)&pcbBuffer[7];
LABEL_58:
  v44 = *((_QWORD *)v18 + 5);
  if ( v44 )
    UnloadProvider(v44);
  MSCryptFree(v18);
  v4 = v56;
  v9 = v64;
LABEL_70:
  v49 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v49 = GetTrustedEnvironment();
  if ( (v49 & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x400000000000LL, v50, 0) )
  {
    v66 = 1;
    v70 = &v66;
    v71 = 8;
    v72 = &v65;
    v65 = 0x1000000;
    v74 = &v57;
    v76 = &pcbBuffer[3];
    v73 = 8;
    v57 = Provider;
    v75 = 4;
    *(_DWORD *)&pcbBuffer[3] = v51;
    v77 = 4;
    tlgCreate1Sz_wchar_t(v78, g_processImageName);
    tlgCreate1Sz_wchar_t(v79, v4);
    tlgCreate1Sz_wchar_t(v80, v9);
    tlgCreate1Sz_wchar_t(v81, v5);
    tlgWriteAgg((unsigned int)v69, (unsigned int)&byte_18001F7C7, v52, 10, (__int64)v69);
  }
  if ( pcbBuffer[0] && v6 )
    BCryptFreeBuffer(v6);
  return Provider;
}

```

## disassembly

```asm
0x1800070d0  push    rbp
0x1800070d2  push    rbx
0x1800070d3  push    rsi
0x1800070d4  push    rdi
0x1800070d5  push    r12
0x1800070d7  push    r13
0x1800070d9  push    r14
0x1800070db  push    r15
0x1800070dd  lea     rbp, [rsp-158h]
0x1800070e5  sub     rsp, 258h
0x1800070ec  mov     rax, cs:__security_cookie
0x1800070f3  xor     rax, rsp
0x1800070f6  mov     [rbp+190h+var_50], rax
0x1800070fd  mov     rsi, rdx
0x180007100  mov     [rsp+290h+var_240], rdx
0x180007105  xor     edx, edx
0x180007107  mov     [rsp+290h+var_238], r9d
0x18000710c  mov     [rbp+190h+var_1F0], rdx
0x180007110  mov     edi, edx
0x180007112  mov     qword ptr [rsp+290h+pcbBuffer+7], rdx
0x180007117  mov     r13d, edx
0x18000711a  mov     [rsp+290h+var_230], rdx
0x18000711f  mov     r12d, edx
0x180007122  mov     [rsp+290h+pcbBuffer], dl
0x180007126  mov     r15d, r9d
0x180007129  mov     [rsp+290h+var_224], edx
0x18000712d  mov     r14, r8
0x180007130  mov     [rbp+190h+var_1E8], rdx
0x180007134  mov     rbx, rcx
0x180007137  mov     [rbp+190h+var_210], rdx
0x18000713b  mov     [rsp+290h+var_220], rdx
0x180007140  mov     [rbp+190h+var_208], r8
0x180007144  mov     [rbp+190h+var_1F8], rcx
0x180007148  mov     [rsp+290h+var_228], 4
0x180007150  mov     rcx, cs:WPP_GLOBAL_Control
0x180007157  lea     rax, WPP_GLOBAL_Control
0x18000715e  cmp     rcx, rax
0x180007161  jz      short loc_180007181
0x180007163  test    byte ptr [rcx+1Ch], 4
0x180007167  jz      short loc_180007181
0x180007169  mov     rcx, [rcx+10h]
0x18000716d  mov     dword ptr [rsp+290h+var_268], r9d
0x180007172  mov     r9, rsi
0x180007175  mov     [rsp+290h+var_270], r8
0x18000717a  call    WPP_SF_SSD
0x18000717f  xor     edx, edx
0x180007181  test    rbx, rbx
0x180007184  jz      loc_180007769
0x18000718a  test    rsi, rsi
0x18000718d  jz      loc_180007769
0x180007193  test    r15b, 1
0x180007197  jz      short loc_1800071A4
0x180007199  mov     r9d, 7ADh
0x18000719f  jmp     loc_18000776F
0x1800071a4  mov     eax, cs:g_TrustedEnvironment
0x1800071aa  test    eax, eax
0x1800071ac  jnz     short loc_1800071B5
0x1800071ae  call    GetTrustedEnvironment
0x1800071b3  xor     edx, edx
0x1800071b5  test    al, 1
0x1800071b7  jnz     short loc_1800071D1
0x1800071b9  mov     r9d, r15d
0x1800071bc  mov     r8, r14
0x1800071bf  mov     rdx, rsi
0x1800071c2  mov     rcx, rbx
0x1800071c5  call    VsmOpenAlgorithmProvider
0x1800071ca  mov     ebx, eax
0x1800071cc  jmp     loc_18000778C
0x1800071d1  cmp     cs:g_fLoadCNGDone, edx
0x1800071d7  mov     r8d, edx
0x1800071da  mov     [rsp+290h+var_250], dl
0x1800071de  jnz     short loc_1800071E9
0x1800071e0  lea     rdi, pszProvider; "Microsoft Primitive Provider"
0x1800071e7  jmp     short loc_1800071FA
0x1800071e9  mov     rdi, r14
0x1800071ec  test    r14, r14
0x1800071ef  jnz     short loc_1800071FA
0x1800071f1  mov     [rsp+290h+var_250], 1
0x1800071f6  lea     r8d, [r14+2]; dwFlags
0x1800071fa  lea     rax, [rsp+290h+pcbBuffer]
0x1800071ff  mov     dword ptr [rsp+290h+pcbBuffer+3], edx
0x180007203  mov     [rsp+290h+var_268], rax; __int64
0x180007208  lea     r9, [rsp+290h+pcbBuffer+3]; pcbBuffer
0x18000720d  lea     rax, [rsp+290h+var_230]
0x180007212  mov     rdx, rdi; pszProvider
0x180007215  mov     rcx, rsi; pszFunction
0x180007218  mov     [rsp+290h+var_270], rax; PCRYPT_PROVIDER_REFS *
0x18000721d  call    BCryptResolveProvidersForBcoapCached
0x180007222  mov     ebx, eax
0x180007224  test    eax, eax
0x180007226  jns     short loc_180007269
0x180007228  mov     r9d, eax
0x18000722b  mov     dword ptr [rsp+290h+var_270], 1
0x180007233  mov     r8d, r15d
0x180007236  mov     rdx, rsi
0x180007239  mov     rcx, rdi
0x18000723c  call    _LogBCryptOpenProviderFailure
0x180007241  mov     r9d, 7EEh
0x180007247  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000724e  lea     rdx, aStatus; "Status"
0x180007255  mov     ecx, ebx
0x180007257  call    DebugTraceError
0x18000725c  mov     r13, [rsp+290h+var_230]
0x180007261  mov     rdi, r12
0x180007264  jmp     loc_18000778C
0x180007269  mov     r13, [rsp+290h+var_230]
0x18000726e  mov     rax, [r13+8]
0x180007272  mov     rcx, [rax]
0x180007275  mov     eax, [rcx]
0x180007277  mov     dword ptr [rsp+290h+var_230], eax
0x18000727b  dec     eax
0x18000727d  cmp     eax, 7
0x180007280  jbe     short loc_1800072C0
0x180007282  mov     r9d, ebx
0x180007285  mov     dword ptr [rsp+290h+var_270], 1
0x18000728d  mov     r8d, r15d
0x180007290  mov     rdx, rsi
0x180007293  mov     rcx, rdi
0x180007296  call    _LogBCryptOpenProviderFailure
0x18000729b  mov     r9d, 80Dh
0x1800072a1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800072a8  lea     rdx, aStatus; "Status"
0x1800072af  mov     ecx, 0C0000008h
0x1800072b4  mov     ebx, 0C0000008h
0x1800072b9  call    DebugTraceError
0x1800072be  jmp     short loc_180007261
0x1800072c0  mov     ebx, 3C8h
0x1800072c5  mov     ecx, ebx
0x1800072c7  call    SafeAllocaAllocateFromHeap
0x1800072cc  mov     r14, rax
0x1800072cf  test    rax, rax
0x1800072d2  jnz     short loc_180007300
0x1800072d4  mov     r9d, 81Ch
0x1800072da  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800072e1  lea     rdx, aStatus; "Status"
0x1800072e8  mov     ecx, 0C0000017h
0x1800072ed  mov     ebx, 0C0000017h
0x1800072f2  call    DebugTraceError
0x1800072f7  mov     r14, [rbp+190h+var_208]
0x1800072fb  jmp     loc_180007261
0x180007300  mov     r8, rbx; Size
0x180007303  xor     edx, edx; Val
0x180007305  mov     rcx, r14; void *
0x180007308  call    memset_0
0x18000730d  mov     eax, dword ptr [rsp+290h+var_230]
0x180007311  lea     rcx, [r14+1BCh]; Destination
0x180007318  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000731c  mov     [r14+24h], eax
0x180007320  mov     r8, rsi; Source
0x180007323  mov     [r14], ebx
0x180007326  mov     edx, 104h; SizeInWords
0x18000732b  mov     dword ptr [r14+4], 55555551h
0x180007333  mov     dword ptr [r14+10h], 1
0x18000733b  call    cs:__imp_wcsncpy_s
0x180007342  nop     dword ptr [rax+rax+00h]
0x180007347  xor     eax, eax
0x180007349  mov     [r14+20h], r12d
0x18000734d  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007354  mov     dword ptr [rsp+290h+pcbBuffer+3], eax
0x180007358  lea     rdi, aStatus; "Status"
0x18000735f  cmp     [r13+0], eax
0x180007363  jbe     loc_1800075BD
0x180007369  mov     r12, [rsp+290h+var_240]
0x18000736e  lea     r8, [r14+30h]; int
0x180007372  lea     rdx, [r14+28h]; int
0x180007376  mov     rcx, [r13+8]
0x18000737a  mov     r9, rdx; int
0x18000737d  mov     [rsp+290h+var_218], rax
0x180007382  mov     [rsp+290h+var_270], r8; void *
0x180007387  mov     rcx, [rcx+rax*8]; int
0x18000738b  call    LoadProviderEx
0x180007390  mov     rcx, [rsp+290h+var_218]
0x180007395  mov     ebx, eax
0x180007397  mov     rax, [r13+8]
0x18000739b  mov     rcx, [rax+rcx*8]
0x18000739f  mov     rax, [rcx+10h]
0x1800073a3  mov     qword ptr [rsp+290h+pcbBuffer+7], rax
0x1800073a8  mov     [rbp+190h+var_200], rax
0x1800073ac  test    ebx, ebx
0x1800073ae  jns     short loc_1800073F0
0x1800073b0  mov     r9d, ebx
0x1800073b3  mov     dword ptr [rsp+290h+var_270], 2
0x1800073bb  mov     r8d, r15d
0x1800073be  mov     rdx, r12
0x1800073c1  mov     rcx, rax
0x1800073c4  call    _LogBCryptOpenProviderFailure
0x1800073c9  mov     r9d, 85Ch
0x1800073cf  mov     r8, rsi
0x1800073d2  mov     rdx, rdi
0x1800073d5  mov     ecx, ebx
0x1800073d7  call    DebugTraceError
0x1800073dc  cmp     [rsp+290h+var_250], 1
0x1800073e1  jnz     loc_1800076AE
0x1800073e7  lea     rdx, [r14+28h]
0x1800073eb  jmp     loc_180007575
0x1800073f0  mov     edx, 3
0x1800073f5  lea     rax, [r14+30h]
0x1800073f9  lea     rcx, [rbp+190h+var_1E0]
0x1800073fd  lea     r8d, [rdx+7Dh]
0x180007401  movups  xmm0, xmmword ptr [rax]
0x180007404  movups  xmm1, xmmword ptr [rax+10h]
0x180007408  movups  xmmword ptr [rcx], xmm0
0x18000740b  movups  xmm0, xmmword ptr [rax+20h]
0x18000740f  movups  xmmword ptr [rcx+10h], xmm1
0x180007413  movups  xmm1, xmmword ptr [rax+30h]
0x180007417  movups  xmmword ptr [rcx+20h], xmm0
0x18000741b  movups  xmm0, xmmword ptr [rax+40h]
0x18000741f  movups  xmmword ptr [rcx+30h], xmm1
0x180007423  movups  xmm1, xmmword ptr [rax+50h]
0x180007427  movups  xmmword ptr [rcx+40h], xmm0
0x18000742b  movups  xmm0, xmmword ptr [rax+60h]
0x18000742f  movups  xmmword ptr [rcx+50h], xmm1
0x180007433  movups  xmm1, xmmword ptr [rax+70h]
0x180007437  add     rax, r8
0x18000743a  movups  xmmword ptr [rcx+60h], xmm0
0x18000743e  movups  xmmword ptr [rcx+70h], xmm1
0x180007442  add     rcx, r8
0x180007445  sub     rdx, 1
0x180007449  jnz     short loc_180007401
0x18000744b  mov     rax, [rax]
0x18000744e  lea     r9, [rbp+190h+var_1F0]
0x180007452  mov     [rcx], rax
0x180007455  lea     r8, [rsp+290h+var_220]
0x18000745a  mov     ecx, dword ptr [rsp+290h+var_230]
0x18000745e  lea     rax, [rbp+190h+var_210]
0x180007462  mov     [rsp+290h+var_268], rax
0x180007467  lea     rdx, [rbp+190h+var_1E0]
0x18000746b  lea     rax, [rbp+190h+var_1E8]
0x18000746f  mov     [rsp+290h+var_270], rax
0x180007474  call    ValidateFunctionTable
0x180007479  mov     ebx, eax
0x18000747b  test    eax, eax
0x18000747d  jns     short loc_1800074B1
0x18000747f  mov     rax, [r13+8]
0x180007483  mov     r9d, ebx
0x180007486  mov     rcx, [rsp+290h+var_218]
0x18000748b  mov     r8d, r15d
0x18000748e  mov     rdx, r12
0x180007491  mov     dword ptr [rsp+290h+var_270], 3
0x180007499  mov     rcx, [rax+rcx*8]
0x18000749d  mov     rcx, [rcx+10h]
0x1800074a1  call    _LogBCryptOpenProviderFailure
0x1800074a6  mov     r9d, 883h
0x1800074ac  jmp     loc_1800073CF
0x1800074b1  mov     r12d, [rsp+290h+var_238]
0x1800074b6  lea     r15, [r14+18h]
0x1800074ba  mov     rdx, [rsp+290h+var_240]
0x1800074bf  mov     rcx, r15
0x1800074c2  mov     rax, [rsp+290h+var_220]
0x1800074c7  mov     r8d, r12d
0x1800074ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074cf  mov     ebx, eax
0x1800074d1  cmp     eax, 0C000A001h
0x1800074d6  jnz     short loc_180007508
0x1800074d8  cmp     dword ptr [rsp+290h+var_230], 2
0x1800074dd  jnz     short loc_180007510
0x1800074df  mov     eax, r12d
0x1800074e2  and     al, 68h
0x1800074e4  cmp     al, 8
0x1800074e6  jnz     short loc_180007510
0x1800074e8  mov     rdx, [rsp+290h+var_240]
0x1800074ed  mov     r8d, r12d
0x1800074f0  mov     rax, [rsp+290h+var_220]
0x1800074f5  and     r8d, 0FFFFFFF7h
0x1800074f9  mov     rcx, r15
0x1800074fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007501  or      dword ptr [r14+8], 8
0x180007506  mov     ebx, eax
0x180007508  test    ebx, ebx
0x18000750a  jns     loc_1800075E4
0x180007510  mov     rax, [r13+8]
0x180007514  mov     r9d, ebx
0x180007517  mov     rcx, [rsp+290h+var_218]
0x18000751c  mov     r15d, [rsp+290h+var_238]
0x180007521  mov     r8d, r15d
0x180007524  mov     rdx, [rsp+290h+var_240]
0x180007529  mov     dword ptr [rsp+290h+var_270], 4
0x180007531  mov     rcx, [rax+rcx*8]
0x180007535  mov     rcx, [rcx+10h]
0x180007539  call    _LogBCryptOpenProviderFailure
0x18000753e  mov     r9d, 8C3h
0x180007544  mov     r8, rsi
0x180007547  mov     rdx, rdi
0x18000754a  mov     ecx, ebx
0x18000754c  call    DebugTraceError
0x180007551  cmp     [rsp+290h+var_250], 1
0x180007556  jnz     loc_1800076AE
0x18000755c  mov     rcx, [r14+28h]
0x180007560  call    UnloadProvider
0x180007565  mov     r12, [rsp+290h+var_240]
0x18000756a  lea     rdx, [r14+28h]
0x18000756e  mov     qword ptr [rdx], 0
0x180007575  mov     eax, dword ptr [rsp+290h+pcbBuffer+3]
0x180007579  lea     r8, [r14+30h]
0x18000757d  inc     eax
0x18000757f  mov     dword ptr [rsp+290h+pcbBuffer+3], eax
0x180007583  cmp     eax, [r13+0]
0x180007587  jb      loc_180007376
0x18000758d  mov     r15, [rbp+190h+var_200]
0x180007591  mov     qword ptr [rsp+290h+pcbBuffer+7], r15
  ... truncated ...
```
