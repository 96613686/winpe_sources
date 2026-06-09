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
  char TrustedEnvironment; // al
  NTSTATUS Provider; // ebx
  ULONG v13; // r8d
  const WCHAR *v14; // rdi
  int v15; // eax
  char *v16; // rax
  char *v17; // r14
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // r12d
  void *v21; // r8
  __int64 *v22; // rdx
  PCRYPT_PROVIDER_REF *rgpProviders; // rcx
  PWSTR pszProvider; // rax
  __int64 v25; // rdx
  _OWORD *v26; // rax
  _OWORD *v27; // rcx
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  ULONG v35; // r12d
  _QWORD *v36; // r15
  NTSTATUS v37; // eax
  __int64 v38; // r15
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rdi
  PCRYPT_PROVIDER_REF *v43; // rcx
  __int64 v44; // rbx
  PCRYPT_PROPERTY_REF v45; // rdx
  char v46; // al
  __int64 v47; // r8
  int v48; // r9d
  int v49; // r8d
  char v51; // [rsp+40h] [rbp-C0h]
  _BYTE pcbBuffer[15]; // [rsp+41h] [rbp-BFh] BYREF
  LPCWSTR v53; // [rsp+50h] [rbp-B0h]
  ULONG v54; // [rsp+58h] [rbp-A8h] BYREF
  PCRYPT_PROVIDER_REFS v55; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v56; // [rsp+68h] [rbp-98h] BYREF
  int v57; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 (__fastcall *v58)(char *, LPCWSTR, _QWORD); // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v60)(_QWORD, const wchar_t *, char *, __int64, unsigned int *, _DWORD); // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR v61; // [rsp+88h] [rbp-78h]
  __int64 v62; // [rsp+90h] [rbp-70h] BYREF
  __int64 v63; // [rsp+98h] [rbp-68h] BYREF
  void (__fastcall *v64)(_QWORD, _QWORD); // [rsp+A0h] [rbp-60h] BYREF
  void (__fastcall *v65)(_QWORD, PWSTR, PUCHAR, _QWORD, _DWORD); // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v66[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  __int64 *v69; // [rsp+E0h] [rbp-20h]
  __int64 v70; // [rsp+E8h] [rbp-18h]
  ULONG *v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  _BYTE *v73; // [rsp+100h] [rbp+0h]
  __int64 v74; // [rsp+108h] [rbp+8h]
  char v75[16]; // [rsp+110h] [rbp+10h] BYREF
  char v76[16]; // [rsp+120h] [rbp+20h] BYREF
  char v77[16]; // [rsp+130h] [rbp+30h] BYREF
  char v78[256]; // [rsp+140h] [rbp+40h] BYREF

  v4 = pszAlgId;
  v53 = pszAlgId;
  v54 = dwFlags;
  v64 = 0;
  v5 = 0;
  *(_QWORD *)&pcbBuffer[7] = 0;
  v6 = 0;
  v55 = 0;
  v7 = 0;
  pcbBuffer[0] = 0;
  v8 = dwFlags;
  v57 = 0;
  v9 = pszImplementation;
  v65 = 0;
  v60 = 0;
  v58 = 0;
  v61 = pszImplementation;
  v63 = (__int64)phAlgorithm;
  v56 = 4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      (_DWORD)pszImplementation,
      (_DWORD)pszAlgId,
      (__int64)pszImplementation,
      dwFlags);
  if ( !phAlgorithm || !v4 || (v8 & 1) != 0 )
  {
    Provider = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    goto LABEL_67;
  }
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) == 0 )
  {
    Provider = VsmOpenAlgorithmProvider(phAlgorithm, v4, v9, v8);
    goto LABEL_67;
  }
  v13 = 0;
  v51 = 0;
  if ( g_fLoadCNGDone )
  {
    v14 = v9;
    if ( !v9 )
    {
      v51 = 1;
      v13 = 2;
    }
  }
  else
  {
    v14 = L"Microsoft Primitive Provider";
  }
  *(_DWORD *)&pcbBuffer[3] = 0;
  v15 = BCryptResolveProvidersForBcoapCached(v4, v14, v13, (ULONG *)&pcbBuffer[3], &v55, (__int64)pcbBuffer);
  Provider = v15;
  if ( v15 < 0 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v14, (_DWORD)v4, v8, v15, 1);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    v6 = v55;
LABEL_17:
    v5 = 0;
    goto LABEL_67;
  }
  v6 = v55;
  LODWORD(v55) = **(_DWORD **)v55->rgpProviders;
  if ( (unsigned int)((_DWORD)v55 - 1) > 7 )
  {
    LogBCryptOpenProviderFailure((_DWORD)v14, (_DWORD)v4, v8, v15, 1);
    Provider = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    goto LABEL_17;
  }
  v16 = (char *)SafeAllocaAllocateFromHeap(968);
  v17 = v16;
  if ( !v16 )
  {
    Provider = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    v9 = v61;
    goto LABEL_17;
  }
  memset_0(v16, 0, 0x3C8u);
  *((_DWORD *)v17 + 9) = (_DWORD)v55;
  *(_DWORD *)v17 = 968;
  *((_DWORD *)v17 + 1) = 1431655761;
  *((_DWORD *)v17 + 4) = 1;
  wcsncpy_s((wchar_t *)v17 + 222, 0x104u, v4, 0xFFFFFFFFFFFFFFFFuLL);
  v19 = 0;
  *((_DWORD *)v17 + 8) = 0;
  *(_DWORD *)&pcbBuffer[3] = 0;
  if ( !v6->cProviders )
  {
    v36 = v17 + 24;
    goto LABEL_42;
  }
  v20 = (int)v53;
  v21 = v17 + 48;
  v22 = (__int64 *)(v17 + 40);
  while ( 1 )
  {
    rgpProviders = v6->rgpProviders;
    v59 = v19;
    Provider = LoadProviderEx((__int64)rgpProviders[v19], (int)v22, (__int64)v21, v22, v21);
    pszProvider = v6->rgpProviders[v59]->pszProvider;
    *(_QWORD *)&pcbBuffer[7] = pszProvider;
    v62 = (__int64)pszProvider;
    if ( Provider >= 0 )
      break;
    LogBCryptOpenProviderFailure((_DWORD)pszProvider, v20, v8, Provider, 2);
LABEL_26:
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    if ( v51 != 1 )
      goto LABEL_55;
    v22 = (__int64 *)(v17 + 40);
LABEL_39:
    v21 = v17 + 48;
    v19 = (unsigned int)(*(_DWORD *)&pcbBuffer[3] + 1);
    *(_DWORD *)&pcbBuffer[3] = v19;
    if ( (unsigned int)v19 >= v6->cProviders )
    {
      v38 = v62;
      *(_QWORD *)&pcbBuffer[7] = v62;
      *(_DWORD *)&pcbBuffer[3] = v19;
      DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
      v5 = v38;
      goto LABEL_56;
    }
  }
  v25 = 3;
  v26 = v17 + 48;
  v27 = v66;
  do
  {
    v28 = v26[1];
    *v27 = *v26;
    v29 = v26[2];
    v27[1] = v28;
    v30 = v26[3];
    v27[2] = v29;
    v31 = v26[4];
    v27[3] = v30;
    v32 = v26[5];
    v27[4] = v31;
    v33 = v26[6];
    v27[5] = v32;
    v34 = v26[7];
    v26 += 8;
    v27[6] = v33;
    v27[7] = v34;
    v27 += 8;
    --v25;
  }
  while ( v25 );
  *(_QWORD *)v27 = *(_QWORD *)v26;
  Provider = ValidateFunctionTable(
               (_DWORD)v55,
               (unsigned int)v66,
               (unsigned int)&v58,
               (unsigned int)&v64,
               (__int64)&v65,
               (__int64)&v60);
  if ( Provider < 0 )
  {
    LogBCryptOpenProviderFailure(v6->rgpProviders[v59]->pszProvider, v20, v8, Provider, 3);
    goto LABEL_26;
  }
  v35 = v54;
  v36 = v17 + 24;
  Provider = v58(v17 + 24, v53, v54);
  if ( Provider != -1073700863 )
    goto LABEL_36;
  if ( (_DWORD)v55 != 2 || (v35 & 0x68) != 8 )
    goto LABEL_37;
  v37 = v58(v17 + 24, v53, v35 & 0xFFFFFFF7);
  *((_DWORD *)v17 + 2) |= 8u;
  Provider = v37;
LABEL_36:
  if ( Provider < 0 )
  {
LABEL_37:
    v8 = v54;
    LogBCryptOpenProviderFailure(v6->rgpProviders[v59]->pszProvider, (_DWORD)v53, v54, Provider, 4);
    DebugTraceError((unsigned int)Provider, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    if ( v51 != 1 )
      goto LABEL_55;
    UnloadProvider(*((_QWORD *)v17 + 5));
    v20 = (int)v53;
    v22 = (__int64 *)(v17 + 40);
    *((_QWORD *)v17 + 5) = 0;
    goto LABEL_39;
  }
  v7 = v60;
LABEL_42:
  if ( (_DWORD)v55 != 2 )
  {
    if ( (_DWORD)v55 == 3 )
    {
      if ( !v7 )
      {
        Provider = -1073741595;
        v39 = 3221225701LL;
        goto LABEL_53;
      }
      v36 = v17 + 24;
      v40 = v7(*((_QWORD *)v17 + 3), L"PaddingSchemes", v17 + 440, v56, &v56, 0);
      Provider = v40;
      if ( v40 < 0 )
      {
LABEL_52:
        v39 = (unsigned int)v40;
        goto LABEL_53;
      }
    }
LABEL_59:
    v42 = *(unsigned int *)&pcbBuffer[3];
    v43 = v6->rgpProviders;
    if ( v43[*(unsigned int *)&pcbBuffer[3]]->cProperties )
    {
      v44 = 0;
      do
      {
        v45 = v43[v42]->rgpProperties[v44];
        v65(*((_QWORD *)v17 + 3), v45->pszProperty, v45->pbValue, v45->cbValue, 0);
        v43 = v6->rgpProviders;
        v44 = (unsigned int)(v44 + 1);
      }
      while ( (unsigned int)v44 < v43[v42]->cProperties );
    }
    *(_QWORD *)v63 = v17;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v18, v17);
    v4 = v53;
    Provider = 0;
    v9 = v61;
    v5 = *(_QWORD *)&pcbBuffer[7];
    goto LABEL_67;
  }
  if ( v7 )
  {
    v36 = v17 + 24;
    v40 = v7(*((_QWORD *)v17 + 3), L"HashBlockLength", v17 + 12, 4, (unsigned int *)&v57, 0);
    Provider = v40;
    if ( v40 < 0 )
      goto LABEL_52;
    goto LABEL_59;
  }
  Provider = -1073741595;
  v39 = 3221225701LL;
LABEL_53:
  DebugTraceError(v39, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
  if ( v64 )
    v64(*v36, 0);
LABEL_55:
  v5 = *(_QWORD *)&pcbBuffer[7];
LABEL_56:
  v41 = *((_QWORD *)v17 + 5);
  if ( v41 )
    UnloadProvider(v41);
  MSCryptFree(v17);
  v4 = v53;
  v9 = v61;
LABEL_67:
  v46 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v46 = GetTrustedEnvironment();
  if ( (v46 & 1) != 0
    && !RtlDllShutdownInProgress()
    && (unsigned int)dword_180024050 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180024050, 0x400000000000LL, v47, 0) )
  {
    v63 = 1;
    v67 = &v63;
    v68 = 8;
    v69 = &v62;
    v62 = 0x1000000;
    v71 = &v54;
    v73 = &pcbBuffer[3];
    v70 = 8;
    v54 = Provider;
    v72 = 4;
    *(_DWORD *)&pcbBuffer[3] = v48;
    v74 = 4;
    tlgCreate1Sz_wchar_t(v75, g_processImageName);
    tlgCreate1Sz_wchar_t(v76, v4);
    tlgCreate1Sz_wchar_t(v77, v9);
    tlgCreate1Sz_wchar_t(v78, v5);
    tlgWriteAgg((unsigned int)v66, (unsigned int)byte_18001F835, v49, 10, (__int64)v66);
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
