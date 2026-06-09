# IsValidURL

- ea: `0x180016640`
- end: `0x180017584`
- name: `IsValidURL`
- size: `3908`
- prototype: `HRESULT __stdcall(LPBC pBC, LPCWSTR szURL, DWORD dwReserved)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001063c`
- `0x1800150e0`
- `0x18001511c`
- `0x180015fc0`
- `0x180016640`
- `0x180017590`
- `0x18001879c`
- `0x1800197a0`
- `0x18001e160`
- `0x18001e2cc`
- `0x180030880`
- `0x18006d398`
- `0x18009f200`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011bb60`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180016e55`
- `msvcrt!wcschr` at `0x180016e55`
- `iertutil!CreateUri` at `0x1800167fb`
- `iertutil!CreateUri` at `0x1800168e6`
- `iertutil!CreateUri` at `0x1800167fb`
- `iertutil!CreateUri` at `0x1800168e6`
- `iertutil!PrivateCoInternetCombineIUri` at `0x1800169b8`
- `iertutil!PrivateCoInternetCombineIUri` at `0x1800169b8`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800172fc`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180017323`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1800172fc`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x180017323`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180016720`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001681f`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180016720`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18001681f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016941`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016941`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016edb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016d38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016edb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180016da5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180016da5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017244`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180017244`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016773`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016796`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800167cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016863`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016886`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800168bb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016773`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016796`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800167cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016863`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016886`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800168bb`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001729e`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001729e`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180016ef2`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180016ef2`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180017564`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180017564`
- `OLEAUT32!__imp_SysFreeString` at `0x180017462`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174be`
- `OLEAUT32!__imp_SysFreeString` at `0x180017462`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174be`
- `OLEAUT32!__imp_SysStringLen` at `0x1800174a5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800174a5`

## pseudocode

```c
HRESULT __stdcall IsValidURL(LPBC pBC, LPCWSTR szURL, DWORD dwReserved)
{
  const WCHAR *v5; // rbx
  LPVOID v6; // rcx
  HRESULT v7; // esi
  int v8; // r14d
  bool ShouldUseEdge; // r15
  int v10; // edi
  int v11; // ecx
  DWORD v12; // edx
  HRESULT v13; // ebx
  bool v14; // bl
  int v15; // ecx
  DWORD v16; // edx
  IUri *v17; // r15
  LPVOID v18; // rdi
  COInetSession *v19; // rax
  int v20; // r14d
  volatile signed __int32 *v21; // rbx
  struct IUri *v22; // rdi
  _BOOL8 v23; // r14
  _BOOL8 v24; // r15
  __int64 v25; // rdx
  __int64 v26; // rcx
  WCHAR *v27; // rax
  BSTR v28; // r8
  WCHAR *v29; // rcx
  _BOOL8 v30; // rdi
  unsigned int v31; // ebx
  int v32; // ebx
  __int64 v33; // rax
  int v34; // r15d
  WCHAR v35; // cx
  int v36; // edx
  int v37; // ecx
  IID *v38; // rax
  COInetSession *v40; // rax
  int v41; // ebx
  COInetSession *v42; // r13
  int i; // ebx
  COInetSession *v44; // rax
  __int64 v45; // rcx
  int ClassObject; // r14d
  WCHAR *v47; // r9
  wchar_t *v48; // rax
  __int64 v49; // r8
  wchar_t *v50; // rcx
  wchar_t *v51; // rax
  char *v52; // rdi
  struct _RTL_CRITICAL_SECTION *v53; // rbx
  ATOM AtomW; // ax
  __int64 j; // rcx
  __int64 v56; // rax
  __int64 v57; // rcx
  unsigned int v58; // ecx
  IID *KnownOInetProtocolClsID; // rax
  unsigned int v60; // ecx
  __int64 v61; // rbx
  __int64 (__fastcall ***v62)(CEasyClassFactory *__hidden, const struct _GUID *, void **); // rcx
  unsigned int k; // r14d
  __int64 v64; // rdi
  const void *v65; // rdx
  struct IUriVtbl *lpVtbl; // rax
  int v67; // ebx
  COInetSession *v68; // rax
  __int64 m; // r12
  int v70; // ecx
  unsigned int v71; // r12d
  ATOM v72; // ax
  ATOM v73; // bx
  struct _GUID *v74; // rax
  struct _GUID v75; // xmm0
  int IsFeatureEnabledInternal; // eax
  int v77; // eax
  CProtocolData *v78; // rax
  CProtocolData *v79; // r12
  unsigned int v80; // edx
  DWORD cchResult[2]; // [rsp+20h] [rbp-E0h]
  int pcchResult; // [rsp+28h] [rbp-D8h]
  IUri *v83; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v84; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v86[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v87; // [rsp+60h] [rbp-A0h] BYREF
  void *v88; // [rsp+68h] [rbp-98h] BYREF
  IUri *ppURI; // [rsp+70h] [rbp-90h] BYREF
  IID Buf1; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v91[64]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Str[4]; // [rsp+490h] [rbp+390h] BYREF
  struct IUri *v93; // [rsp+498h] [rbp+398h]
  unsigned int v94; // [rsp+4A0h] [rbp+3A0h]
  BSTR bstrString[2]; // [rsp+4A8h] [rbp+3A8h] BYREF
  UINT v96[6]; // [rsp+4B8h] [rbp+3B8h] BYREF
  WCHAR pszStr1[2088]; // [rsp+4D0h] [rbp+3D0h] BYREF

  if ( !szURL )
    return -2147024809;
  v84 = 0;
  v5 = 0;
  v88 = 0;
  v87 = 0;
  pszStr1[0] = 0;
  if ( pBC )
  {
    if ( ((unsigned int (__fastcall *)(LPBC, const wchar_t *, LPVOID *))pBC->lpVtbl->GetObjectParam)(
           pBC,
           L"URL Context",
           &v87) )
    {
      v6 = 0;
      v87 = 0;
    }
    else
    {
      v6 = v87;
    }
    if ( v6 )
    {
      (*(void (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v6 + 176LL))(v6, &v84);
      if ( v84 == 6 )
        (*(void (__fastcall **)(LPVOID, LPBC, _QWORD, void **))(*(_QWORD *)v87 + 160LL))(v87, pBC, 0, &v88);
    }
    v5 = (const WCHAR *)v88;
  }
  if ( !v5 )
  {
    v86[0] = 2085;
    v7 = 1;
    v31 = (unsigned int)CoInternetParseUrl(szURL, PARSE_CANONICALIZE, 0x10000u, pszStr1, 0x825u, v86, 0) >> 31;
    goto LABEL_78;
  }
  v93 = 0;
  *(_QWORD *)Str = &CUString::`vftable';
  *(_OWORD *)bstrString = 0;
  v94 = 11;
  v96[0] = 0;
  ppURI = 0;
  *(_QWORD *)v86 = 0;
  v7 = 1;
  v8 = 50342821;
  ShouldUseEdge = InternalForkingSupport_ShouldUseEdge();
  if ( !ShouldUseEdge )
  {
LABEL_11:
    v10 = 33565605;
    if ( !ShouldUseEdge )
      goto LABEL_15;
    goto LABEL_12;
  }
  v10 = 50342821;
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
    if ( IsFeatureEnabledInternal < 0 )
      goto LABEL_12;
    dword_180159BE8 = IsFeatureEnabledInternal == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180159BE8 )
    goto LABEL_11;
LABEL_12:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 1) != 0 )
  {
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
    if ( (dword_18015E75C & 2) != 0 || (unsigned int)IsABrowserApp() )
      goto LABEL_16;
  }
LABEL_15:
  v10 &= ~0x2000000u;
  if ( ShouldUseEdge )
LABEL_16:
    InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  v11 = v10 | 0x2000000;
  if ( (v10 & 0x2000000) != 0 )
    v11 = v10;
  v12 = v11 | 0x1000000;
  if ( (v11 & 0x1000000) != 0 )
    v12 = v11;
  v13 = CreateUri(v5, v12, 0, &ppURI);
  if ( v13 < 0 )
    goto LABEL_67;
  *(_QWORD *)&Buf1.Data1 = ppURI;
  v83 = 0;
  *(_QWORD *)v86 = 0;
  v14 = InternalForkingSupport_ShouldUseEdge();
  if ( !v14 )
    goto LABEL_25;
  if ( FCK::FEATURE_DISABLE_DATAURI_SUPPORT )
  {
    v77 = CoInternetIsFeatureEnabledInternal();
    if ( v77 < 0 )
      goto LABEL_26;
    dword_180159BE8 = v77 == 0;
    FCK::FEATURE_DISABLE_DATAURI_SUPPORT = 0;
  }
  if ( dword_180159BE8 )
  {
LABEL_25:
    v8 = 33565605;
    if ( !v14 )
      goto LABEL_29;
  }
LABEL_26:
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
  if ( (dword_18015E75C & 1) == 0
    || (InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0), (dword_18015E75C & 2) == 0)
    && !(unsigned int)IsABrowserApp() )
  {
LABEL_29:
    v8 &= ~0x2000000u;
    if ( !v14 )
      goto LABEL_31;
  }
  InitOnceExecuteOnce(&stru_18015DE28, GlobalInitOnceUrlMon, 0, 0);
LABEL_31:
  v15 = v8 | 0x2000000;
  if ( (v8 & 0x2000000) != 0 )
    v15 = v8;
  v16 = v15 | 0x1000000;
  if ( (v15 & 0x1000000) != 0 )
    v16 = v15;
  v13 = CreateUri(szURL, v16, 0, &v83);
  if ( v13 < 0 )
    goto LABEL_48;
  v17 = v83;
  if ( v83 )
  {
    ppv = 0;
    v18 = 0;
    EnterCriticalSection(&g_mxsOInet);
    v19 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      v20 = 0;
    }
    else
    {
      v68 = (COInetSession *)operator new(0x180u);
      if ( v68 && (v19 = COInetSession::COInetSession(v68)) != 0 )
      {
        v20 = 0;
        g_pCOInetSession = v19;
      }
      else
      {
        v19 = g_pCOInetSession;
        v20 = -2147024882;
      }
      if ( !v19 )
      {
        v21 = 0;
        v20 = -2147024882;
        goto LABEL_40;
      }
    }
    _InterlockedAdd((volatile signed __int32 *)v19 + 4, 1u);
    v21 = (volatile signed __int32 *)g_pCOInetSession;
LABEL_40:
    LeaveCriticalSection(&g_mxsOInet);
    if ( !v20 )
    {
      if ( v21 )
      {
        if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
        {
          v18 = (LPVOID)(v21 + 2);
          _InterlockedAdd(v21 + 4, 1u);
        }
        else if ( !(unsigned int)COInetSession::QueryInterface(
                                   (COInetSession *)v21,
                                   &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b,
                                   &ppv) )
        {
          v18 = ppv;
        }
      }
      _InterlockedDecrement(v21 + 4);
    }
    v13 = PrivateCoInternetCombineIUri(*(_QWORD *)&Buf1.Data1, v17, 0x10000, v86, 0, v18, 0, 0);
    if ( v18 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_48:
    if ( v83 )
      ((void (__fastcall *)(IUri *))v83->lpVtbl->Release)(v83);
    if ( v13 >= 0 )
    {
      v22 = *(struct IUri **)v86;
      v13 = 0;
      v23 = *(_QWORD *)v86 != (_QWORD)v93;
      v24 = v94 != 0;
      if ( *(struct IUri **)v86 != v93 || v94 )
      {
        if ( bstrString[0] )
        {
          SysFreeString(bstrString[0]);
          bstrString[0] = 0;
        }
        bstrString[1] = 0;
        v96[0] = 0;
        if ( v23 && v93 )
        {
          ((void (__fastcall *)(struct IUri *))v93->lpVtbl->Release)(v93);
          v93 = 0;
        }
      }
      v94 = 0;
      if ( !v22 || !v24 && !v23 )
        goto LABEL_58;
      lpVtbl = v22->lpVtbl;
      v83 = 0;
      if ( ((int (__fastcall *)(struct IUri *, GUID *, IUri **))lpVtbl->QueryInterface)(
             v22,
             &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
             &v83) < 0 )
      {
        v13 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, _QWORD))v22->lpVtbl->GetPropertyBSTR)(
                v22,
                v94,
                bstrString,
                0);
        if ( v13 >= 0 )
        {
          bstrString[1] = bstrString[0];
          v96[0] = SysStringLen(bstrString[0]);
        }
      }
      else
      {
        v13 = ((__int64 (__fastcall *)(IUri *, _QWORD, BSTR *, UINT *))v83->lpVtbl[1].QueryInterface)(
                v83,
                v94,
                &bstrString[1],
                v96);
        ((void (__fastcall *)(IUri *))v83->lpVtbl->Release)(v83);
      }
      if ( v23 && v13 >= 0 )
      {
        v93 = v22;
        ((void (__fastcall *)(struct IUri *))v22->lpVtbl->AddRef)(v22);
      }
      if ( v13 == 1 && (v13 = CUString::Set((CUString *)Str, *(struct IUri **)v86, Uri_PROPERTY_RAW_URI), v13 == 1) )
      {
        v13 = -2146697214;
      }
      else
      {
LABEL_58:
        if ( v13 >= 0 )
        {
          v25 = 2085;
          if ( v96[0] >= 0x825 )
          {
            v13 = -2147467261;
          }
          else
          {
            v26 = v96[0];
            v27 = pszStr1;
            v28 = bstrString[1];
            do
            {
              if ( !v26 )
                break;
              if ( !*v28 )
                break;
              *v27++ = *v28++;
              --v26;
              --v25;
            }
            while ( v25 );
            v29 = v27 - 1;
            if ( v25 )
              v29 = v27;
            v13 = v25 == 0 ? 0x8007007A : 0;
            *v29 = 0;
          }
        }
      }
    }
    goto LABEL_67;
  }
  v13 = -2147418113;
LABEL_67:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( *(_QWORD *)v86 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v86 + 16LL))(*(_QWORD *)v86);
    *(_QWORD *)v86 = 0;
  }
  *(_QWORD *)Str = &CUString::`vftable';
  v30 = v93 != 0;
  if ( v93 || v94 != 11 )
  {
    if ( bstrString[0] )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
    }
    bstrString[1] = 0;
    v96[0] = 0;
    if ( v30 && v93 )
      ((void (__fastcall *)(struct IUri *))v93->lpVtbl->Release)(v93);
  }
  v31 = (unsigned int)v13 >> 31;
LABEL_78:
  if ( v31 )
    goto LABEL_213;
  v32 = 0;
  v33 = -1;
  do
    ++v33;
  while ( pszStr1[v33] );
  if ( !v33 )
LABEL_213:
    v32 = -2147221020;
  if ( v88 )
    operator delete(v88);
  if ( v32 )
    return v7;
  v88 = 0;
  v83 = 0;
  v34 = 0;
  Buf1 = 0;
  if ( pBC
    && ((int (__fastcall *)(LPBC, const wchar_t *, IUri **))pBC->lpVtbl->GetObjectParam)(pBC, L"_BSCB_Holder_", &v83) >= 0
    && (v67 = ((__int64 (__fastcall *)(IUri *, GUID *, void **))v83->lpVtbl->QueryInterface)(
                v83,
                &IID_IBindStatusCallback,
                &v88),
        ((void (__fastcall *)(IUri *))v83->lpVtbl->Release)(v83),
        v67 >= 0) )
  {
    v83 = 0;
    if ( (**(int (__fastcall ***)(void *, GUID *, IUri **))v88)(v88, &IID_IServiceProvider, &v83) >= 0 )
    {
      ppv = 0;
      if ( ((int (__fastcall *)(IUri *, GUID *, GUID *, LPVOID *))v83->lpVtbl->GetPropertyBSTR)(
             v83,
             &IID_IInternetProtocol,
             &IID_IInternetProtocol,
             &ppv) >= 0
        && ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v34 = 1;
      }
      ((void (__fastcall *)(IUri *))v83->lpVtbl->Release)(v83);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v88 + 16LL))(v88);
    if ( v34 )
      return 0;
  }
  else
  {
    v88 = 0;
  }
  EnterCriticalSection(&g_mxsOInet);
  v40 = g_pCOInetSession;
  if ( g_pCOInetSession )
  {
    v41 = 0;
LABEL_109:
    _InterlockedAdd((volatile signed __int32 *)v40 + 4, 1u);
    v42 = g_pCOInetSession;
    goto LABEL_110;
  }
  v44 = (COInetSession *)operator new(0x180u);
  if ( v44 && (v40 = COInetSession::COInetSession(v44)) != 0 )
  {
    v41 = 0;
    g_pCOInetSession = v40;
  }
  else
  {
    v40 = g_pCOInetSession;
    v41 = -2147024882;
  }
  if ( v40 )
    goto LABEL_109;
  v42 = 0;
  v41 = -2147024882;
LABEL_110:
  ppv = v42;
  LeaveCriticalSection(&g_mxsOInet);
  if ( v41 )
    return v7;
  for ( i = 0; ; ++i )
  {
    if ( i >= 12 )
      goto LABEL_120;
    if ( !StrCmpNICW(pszStr1, (LPCWSTR)*(&off_18011D010 + 5 * i), dword_18011D030[10 * i]) )
    {
      v35 = pszStr1[dword_18011D030[10 * i]];
      if ( v35 == 58 || !v35 )
        break;
    }
  }
  v36 = dword_18011D020[10 * i];
  if ( v36 )
  {
    v37 = 0;
    while ( v36 != dword_18011D020[10 * v37] )
    {
      ++v37;
      v38 = 0;
      if ( v37 >= 12 )
        goto LABEL_94;
    }
    v38 = *(&off_18011D028 + 5 * v37);
LABEL_94:
    Buf1 = *v38;
    goto LABEL_95;
  }
LABEL_120:
  v45 = 31;
  v87 = 0;
  ClassObject = -2146697203;
  v47 = pszStr1;
  v48 = Str;
  v49 = 32;
  do
  {
    if ( !v45 )
      break;
    if ( !*v47 )
      break;
    *v48++ = *v47++;
    --v45;
    --v49;
  }
  while ( v49 );
  v50 = v48 - 1;
  if ( v49 )
    v50 = v48;
  *v50 = 0;
  v51 = wcschr(Str, 0x3Au);
  if ( v51 )
  {
    v52 = (char *)v42 + 96;
    *v51 = 0;
    v53 = (struct _RTL_CRITICAL_SECTION *)((char *)v42 + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v42 + 112));
    *((_QWORD *)v42 + 20) = 0;
    if ( *((int *)v42 + 27) > 0 )
    {
      AtomW = FindAtomW(Str);
      if ( AtomW )
      {
        for ( j = *((_QWORD *)v42 + 19); ; j = *(_QWORD *)(j + 32) )
        {
          *((_QWORD *)v42 + 20) = j;
          if ( !j || *(_WORD *)j == AtomW )
            break;
        }
      }
    }
    if ( *((_QWORD *)v42 + 20) )
    {
LABEL_141:
      v56 = *((_QWORD *)v52 + 8);
      if ( v56 )
      {
        Buf1 = *(IID *)(v56 + 16);
        v57 = *((_QWORD *)v52 + 8);
        if ( *(_QWORD *)(v57 + 8) )
        {
          v87 = *(LPVOID *)(v57 + 8);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v57 + 8) + 8LL))(*(_QWORD *)(v57 + 8));
          ClassObject = 0;
        }
        else
        {
          ppv = 0;
          ClassObject = CoGetClassObject(&Buf1, 1u, 0, &IID_IClassFactory, &ppv);
          if ( !ClassObject )
            v87 = ppv;
        }
        *((_QWORD *)v52 + 8) = *(_QWORD *)(*((_QWORD *)v52 + 8) + 32LL);
      }
      LeaveCriticalSection(v53);
      if ( ClassObject )
      {
        v58 = IsKnownProtocol(Str);
        if ( !v58 )
        {
LABEL_156:
          ClassObject = (**((__int64 (__fastcall ***)(__int64, wchar_t *, LPVOID *, IID *, DWORD *, int))v42 + 3))(
                          (__int64)v42 + 24,
                          Str,
                          &v87,
                          &Buf1,
                          *(DWORD **)cchResult,
                          pcchResult);
          goto LABEL_127;
        }
        KnownOInetProtocolClsID = (IID *)GetKnownOInetProtocolClsID(v58);
        v61 = 16LL * v60;
        Buf1 = *KnownOInetProtocolClsID;
        v62 = *(__int64 (__fastcall ****)(CEasyClassFactory *__hidden, const struct _GUID *, void **))((char *)v42 + v61 + 264);
        if ( !v62 )
        {
          if ( !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IClassFactory, 0x10u)
            || !memcmp_0(&GUID_00000001_0000_0000_c000_000000000046, &IID_IUnknown, 0x10u) )
          {
            for ( k = 0; ; ++k )
            {
              v64 = 4LL * k;
              v65 = *(const void **)((char *)&off_180120328 + v64 * 8);
              if ( !v65 )
                break;
              if ( !memcmp_0(&Buf1, v65, 0x10u) )
              {
                _InterlockedAdd((volatile signed __int32 *)&g_cRef, 1u);
                v62 = &(&off_180120320)[v64];
                if ( !&(&off_180120320)[v64] )
                  goto LABEL_156;
                if ( _InterlockedCompareExchange64(
                       (volatile signed __int64 *)((char *)v42 + v61 + 264),
                       (signed __int64)v62,
                       0) )
                {
                  ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v62)[2])(v62);
                  v62 = *(__int64 (__fastcall ****)(CEasyClassFactory *__hidden, const struct _GUID *, void **))((char *)v42 + v61 + 264);
                  if ( !v62 )
                    goto LABEL_156;
                }
                else
                {
                  _InterlockedAdd(&g_lCOInetSessionDllRefcount, 1u);
                }
                goto LABEL_154;
              }
            }
          }
          goto LABEL_156;
        }
LABEL_154:
        v87 = v62;
        ((void (__fastcall *)(__int64 (__fastcall ***)(CEasyClassFactory *__hidden, const struct _GUID *, void **)))(*v62)[1])(v62);
      }
      ClassObject = 0;
      goto LABEL_127;
    }
    for ( m = *((_QWORD *)v42 + 21); m; m = *(_QWORD *)(m + 8) )
    {
      if ( !StrCmpICW(Str, *(LPCWSTR *)m) )
      {
        v70 = 1;
        goto LABEL_185;
      }
    }
    v78 = (CProtocolData *)operator new(0x10u);
    v79 = v78;
    if ( v78 )
    {
      *(_QWORD *)v78 = 0;
      *((_QWORD *)v78 + 1) = 0;
      if ( CProtocolData::Init(v78, Str, *((struct CProtocolData **)v42 + 21)) )
      {
        *((_QWORD *)v42 + 21) = v79;
        v70 = 0;
LABEL_185:
        v71 = 0;
        if ( !v70 )
        {
          pcchResult = 0;
          *(_QWORD *)cchResult = 0;
          v84 = 64;
          ClassObject = CProtMgrNameSpace::LookupClsIDFromReg((COInetSession *)((char *)v42 + 96), Str, v91, &v84);
          if ( !ClassObject )
          {
            v72 = AddAtomW(Str);
            if ( v84 )
            {
              v73 = v72;
              do
              {
                v74 = (struct _GUID *)operator new(0x38u);
                if ( v74 )
                {
                  LOWORD(v74->Data1) = v73;
                  v75 = v91[v71];
                  *(_QWORD *)v74->Data4 = 0;
                  *(_QWORD *)v74[2].Data4 = 0;
                  v74[1] = v75;
                  *(_QWORD *)&v74[3].Data1 = 0;
                  *(_QWORD *)&v74[2].Data1 = *((_QWORD *)v42 + 19);
                  *((_QWORD *)v42 + 19) = v74;
                  _InterlockedAdd((volatile signed __int32 *)v42 + 27, 1u);
                }
                else
                {
                  v74 = 0;
                }
                if ( !*((_QWORD *)v42 + 20) )
                  *((_QWORD *)v42 + 20) = v74;
                ++v71;
              }
              while ( v71 < v84 );
              v42 = (COInetSession *)ppv;
              v53 = (struct _RTL_CRITICAL_SECTION *)(v52 + 16);
            }
          }
        }
        goto LABEL_141;
      }
      CProtocolData::`scalar deleting destructor'(v79, v80);
    }
    v70 = -2147024882;
    goto LABEL_185;
  }
LABEL_127:
  if ( v87 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v87 + 16LL))(v87);
  if ( !ClassObject
    || ClassObject != -2146697202
    && !(*(unsigned int (__fastcall **)(__int64, WCHAR *, IID *, _QWORD, _QWORD, _DWORD))(*((_QWORD *)v42 + 3) + 16LL))(
          (__int64)v42 + 24,
          pszStr1,
          &Buf1,
          0,
          0,
          0) )
  {
LABEL_95:
    v34 = 1;
  }
  _InterlockedDecrement((volatile signed __int32 *)v42 + 4);
  if ( v34 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x180016640  mov     [rsp-8+arg_10], rbx
0x180016645  push    rbp
0x180016646  push    rsi
0x180016647  push    rdi
0x180016648  push    r12
0x18001664a  push    r13
0x18001664c  push    r14
0x18001664e  push    r15
0x180016650  lea     rbp, [rsp-1430h]
0x180016658  mov     eax, 1530h
0x18001665d  call    _alloca_probe
0x180016662  sub     rsp, rax
0x180016665  mov     rax, cs:__security_cookie
0x18001666c  xor     rax, rsp
0x18001666f  mov     [rbp+1460h+var_40], rax
0x180016676  xor     esi, esi
0x180016678  mov     r12, rdx
0x18001667b  mov     r13, rcx
0x18001667e  test    rdx, rdx
0x180016681  jz      loc_180016C0C
0x180016687  mov     [rsp+1560h+var_1518], esi
0x18001668b  mov     ebx, esi
0x18001668d  mov     [rsp+1560h+var_14F8], rbx
0x180016692  mov     [rsp+1560h+var_1500], rsi
0x180016697  mov     [rbp+1460h+pszStr1], si
0x18001669e  test    rcx, rcx
0x1800166a1  jz      short loc_1800166D8
0x1800166a3  mov     rax, [rcx]
0x1800166a6  lea     r8, [rsp+1560h+var_1500]
0x1800166ab  lea     rdx, aUrlContext; "URL Context"
0x1800166b2  mov     rax, [rax+50h]
0x1800166b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166bb  test    eax, eax
0x1800166bd  jz      loc_18001740B
0x1800166c3  mov     ecx, esi
0x1800166c5  mov     [rsp+1560h+var_1500], rcx
0x1800166ca  test    rcx, rcx
0x1800166cd  jnz     loc_180017415
0x1800166d3  mov     rbx, [rsp+1560h+var_14F8]
0x1800166d8  mov     edi, 8007000Eh
0x1800166dd  test    rbx, rbx
0x1800166e0  jz      loc_1800171E8
0x1800166e6  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x1800166ed  mov     [rbp+1460h+var_10C8], rsi
0x1800166f4  xorps   xmm0, xmm0
0x1800166f7  mov     qword ptr [rbp+1460h+Str], rax
0x1800166fe  movdqu  xmmword ptr [rbp+1460h+bstrString], xmm0
0x180016706  mov     [rbp+1460h+var_10C0], 0Bh
0x180016710  mov     [rbp+1460h+var_10A8], esi
0x180016716  mov     [rsp+1560h+ppURI], rsi
0x18001671b  mov     qword ptr [rsp+1560h+var_1508], rsi
0x180016720  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x180016726  mov     esi, 1
0x18001672b  mov     r14d, 3002BA5h
0x180016731  mov     r15b, al
0x180016734  test    al, al
0x180016736  jz      short loc_180016755
0x180016738  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x18001673f  mov     edi, r14d
0x180016742  test    rcx, rcx
0x180016745  jnz     loc_1800172FC
0x18001674b  mov     eax, cs:dword_180159BE8
0x180016751  test    eax, eax
0x180016753  jz      short loc_18001675F
0x180016755  mov     edi, 2002BA5h
0x18001675a  test    r15b, r15b
0x18001675d  jz      short loc_1800167AE
0x18001675f  xor     r9d, r9d; Context
0x180016762  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180016769  xor     r8d, r8d; Parameter
0x18001676c  lea     rcx, stru_18015DE28; InitOnce
0x180016773  call    cs:__imp_InitOnceExecuteOnce
0x180016779  test    byte ptr cs:dword_18015E75C, sil
0x180016780  jz      short loc_1800167AE
0x180016782  xor     r9d, r9d; Context
0x180016785  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001678c  xor     r8d, r8d; Parameter
0x18001678f  lea     rcx, stru_18015DE28; InitOnce
0x180016796  call    cs:__imp_InitOnceExecuteOnce
0x18001679c  test    byte ptr cs:dword_18015E75C, 2
0x1800167a3  jnz     short loc_1800167B7
0x1800167a5  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x1800167aa  test    eax, eax
0x1800167ac  jnz     short loc_1800167B7
0x1800167ae  btr     edi, 19h
0x1800167b2  test    r15b, r15b
0x1800167b5  jz      short loc_1800167D1
0x1800167b7  xor     r9d, r9d; Context
0x1800167ba  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800167c1  xor     r8d, r8d; Parameter
0x1800167c4  lea     rcx, stru_18015DE28; InitOnce
0x1800167cb  call    cs:__imp_InitOnceExecuteOnce
0x1800167d1  mov     edx, 2000000h
0x1800167d6  lea     r9, [rsp+1560h+ppURI]; ppURI
0x1800167db  mov     ecx, edi
0x1800167dd  xor     r15d, r15d
0x1800167e0  or      ecx, edx
0x1800167e2  test    edx, edi
0x1800167e4  cmovnz  ecx, edi
0x1800167e7  mov     edi, 1000000h
0x1800167ec  mov     edx, ecx
0x1800167ee  or      edx, edi
0x1800167f0  test    edi, ecx
0x1800167f2  cmovnz  edx, ecx; dwFlags
0x1800167f5  xor     r8d, r8d; dwReserved
0x1800167f8  mov     rcx, rbx; pwzURI
0x1800167fb  call    cs:__imp_CreateUri
0x180016801  mov     ebx, eax
0x180016803  test    eax, eax
0x180016805  js      loc_1800174B6
0x18001680b  mov     rax, [rsp+1560h+ppURI]
0x180016810  mov     qword ptr [rsp+1560h+Buf1.Data1], rax
0x180016815  mov     [rsp+1560h+var_1520], r15
0x18001681a  mov     qword ptr [rsp+1560h+var_1508], r15
0x18001681f  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x180016825  mov     bl, al
0x180016827  test    al, al
0x180016829  jz      short loc_180016845
0x18001682b  mov     rcx, cs:?FEATURE_DISABLE_DATAURI_SUPPORT@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_DISABLE_DATAURI_SUPPORT
0x180016832  test    rcx, rcx
0x180016835  jnz     loc_180017323
0x18001683b  mov     eax, cs:dword_180159BE8
0x180016841  test    eax, eax
0x180016843  jz      short loc_18001684F
0x180016845  mov     r14d, 2002BA5h
0x18001684b  test    bl, bl
0x18001684d  jz      short loc_18001689E
0x18001684f  xor     r9d, r9d; Context
0x180016852  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180016859  xor     r8d, r8d; Parameter
0x18001685c  lea     rcx, stru_18015DE28; InitOnce
0x180016863  call    cs:__imp_InitOnceExecuteOnce
0x180016869  test    byte ptr cs:dword_18015E75C, sil
0x180016870  jz      short loc_18001689E
0x180016872  xor     r9d, r9d; Context
0x180016875  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001687c  xor     r8d, r8d; Parameter
0x18001687f  lea     rcx, stru_18015DE28; InitOnce
0x180016886  call    cs:__imp_InitOnceExecuteOnce
0x18001688c  test    byte ptr cs:dword_18015E75C, 2
0x180016893  jnz     short loc_1800168A7
0x180016895  call    ?IsABrowserApp@@YAHXZ; IsABrowserApp(void)
0x18001689a  test    eax, eax
0x18001689c  jnz     short loc_1800168A7
0x18001689e  btr     r14d, 19h
0x1800168a3  test    bl, bl
0x1800168a5  jz      short loc_1800168C1
0x1800168a7  xor     r9d, r9d; Context
0x1800168aa  lea     rdx, ?GlobalInitOnceUrlMon@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800168b1  xor     r8d, r8d; Parameter
0x1800168b4  lea     rcx, stru_18015DE28; InitOnce
0x1800168bb  call    cs:__imp_InitOnceExecuteOnce
0x1800168c1  mov     edx, 2000000h
0x1800168c6  lea     r9, [rsp+1560h+var_1520]; ppURI
0x1800168cb  mov     ecx, r14d
0x1800168ce  or      ecx, edx
0x1800168d0  test    edx, r14d
0x1800168d3  cmovnz  ecx, r14d
0x1800168d7  mov     edx, ecx
0x1800168d9  or      edx, edi
0x1800168db  test    edi, ecx
0x1800168dd  cmovnz  edx, ecx; dwFlags
0x1800168e0  xor     r8d, r8d; dwReserved
0x1800168e3  mov     rcx, r12; pwzURI
0x1800168e6  call    cs:__imp_CreateUri
0x1800168ec  xor     r12d, r12d
0x1800168ef  mov     ebx, eax
0x1800168f1  test    eax, eax
0x1800168f3  js      loc_1800169D4
0x1800168f9  mov     r15, [rsp+1560h+var_1520]
0x1800168fe  test    r15, r15
0x180016901  jz      loc_180017458
0x180016907  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18001690e  mov     [rsp+1560h+ppv], r12
0x180016913  mov     edi, r12d
0x180016916  call    cs:__imp_EnterCriticalSection
0x18001691c  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180016923  test    rax, rax
0x180016926  jz      loc_180017170
0x18001692c  mov     r14d, r12d
0x18001692f  lock add [rax+10h], esi
0x180016933  mov     rbx, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18001693a  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180016941  call    cs:__imp_LeaveCriticalSection
0x180016947  test    r14d, r14d
0x18001694a  jnz     short loc_180016991
0x18001694c  test    rbx, rbx
0x18001694f  jz      short loc_18001698D
0x180016951  lea     r8d, [r14+10h]; Size
0x180016955  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x18001695c  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x180016963  call    memcmp_0
0x180016968  test    eax, eax
0x18001696a  jz      loc_1800171CA
0x180016970  lea     r8, [rsp+1560h+ppv]; void **
0x180016975  mov     rcx, rbx; this
0x180016978  lea     rdx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x18001697f  call    ?QueryInterface@COInetSession@@UEAAJAEBU_GUID@@PEAPEAX@Z; COInetSession::QueryInterface(_GUID const &,void * *)
0x180016984  test    eax, eax
0x180016986  jnz     short loc_18001698D
0x180016988  mov     rdi, [rsp+1560h+ppv]
0x18001698d  lock dec dword ptr [rbx+10h]
0x180016991  mov     rcx, qword ptr [rsp+1560h+Buf1.Data1]
0x180016996  lea     r9, [rsp+1560h+var_1508]
0x18001699b  mov     [rsp+1560h+var_1528], r12d
0x1800169a0  mov     r8d, 10000h
0x1800169a6  mov     [rsp+1560h+dwReserved], r12d
0x1800169ab  mov     rdx, r15
0x1800169ae  mov     [rsp+1560h+pcchResult], rdi
0x1800169b3  mov     qword ptr [rsp+1560h+cchResult], r12
0x1800169b8  call    cs:__imp_PrivateCoInternetCombineIUri
0x1800169be  mov     ebx, eax
0x1800169c0  test    rdi, rdi
0x1800169c3  jz      short loc_1800169D4
0x1800169c5  mov     rax, [rdi]
0x1800169c8  mov     rcx, rdi
0x1800169cb  mov     rax, [rax+10h]
0x1800169cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d4  mov     rcx, [rsp+1560h+var_1520]
0x1800169d9  test    rcx, rcx
0x1800169dc  jz      short loc_1800169EA
0x1800169de  mov     rax, [rcx]
0x1800169e1  mov     rax, [rax+10h]
0x1800169e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ea  test    ebx, ebx
0x1800169ec  js      loc_180016AD9
0x1800169f2  mov     rdi, qword ptr [rsp+1560h+var_1508]
0x1800169f7  mov     r14d, r12d
0x1800169fa  cmp     rdi, [rbp+1460h+var_10C8]
0x180016a01  mov     r15d, r12d
0x180016a04  mov     ebx, r12d
0x180016a07  setnz   r14b
0x180016a0b  cmp     [rbp+1460h+var_10C0], r12d
0x180016a12  setnz   r15b
0x180016a16  test    r14d, r14d
0x180016a19  jz      loc_1800171AF
0x180016a1f  mov     rcx, [rbp+1460h+bstrString]; bstrString
0x180016a26  test    rcx, rcx
0x180016a29  jnz     loc_180017462
0x180016a2f  mov     [rbp+1460h+bstrString+8], r12
0x180016a36  mov     [rbp+1460h+var_10A8], r12d
0x180016a3d  test    r14d, r14d
0x180016a40  jz      short loc_180016A61
0x180016a42  mov     rcx, [rbp+1460h+var_10C8]
0x180016a49  test    rcx, rcx
0x180016a4c  jz      short loc_180016A61
0x180016a4e  mov     rax, [rcx]
0x180016a51  mov     rax, [rax+10h]
0x180016a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a5a  mov     [rbp+1460h+var_10C8], r12
0x180016a61  mov     [rbp+1460h+var_10C0], r12d
0x180016a68  test    rdi, rdi
0x180016a6b  jnz     loc_180017077
0x180016a71  test    ebx, ebx
0x180016a73  js      short loc_180016AD9
0x180016a75  mov     edx, 825h
0x180016a7a  cmp     [rbp+1460h+var_10A8], edx
0x180016a80  jnb     loc_180017349
0x180016a86  mov     ecx, [rbp+1460h+var_10A8]
0x180016a8c  lea     rax, [rbp+1460h+pszStr1]
0x180016a93  mov     r8, [rbp+1460h+bstrString+8]
0x180016a9a  test    rcx, rcx
0x180016a9d  jz      short loc_180016ABD
0x180016a9f  movzx   r9d, word ptr [r8]
0x180016aa3  test    r9w, r9w
0x180016aa7  jz      short loc_180016ABD
0x180016aa9  mov     [rax], r9w
0x180016aad  add     r8, 2
0x180016ab1  add     rax, 2
0x180016ab5  sub     rcx, rsi
0x180016ab8  sub     rdx, rsi
0x180016abb  jnz     short loc_180016A9A
0x180016abd  test    rdx, rdx
0x180016ac0  lea     rcx, [rax-2]
0x180016ac4  cmovnz  rcx, rax
0x180016ac8  neg     rdx
0x180016acb  sbb     ebx, ebx
0x180016acd  not     ebx
0x180016acf  and     ebx, 8007007Ah
0x180016ad5  mov     [rcx], r12w
0x180016ad9  mov     rcx, [rsp+1560h+ppURI]
0x180016ade  test    rcx, rcx
0x180016ae1  jz      short loc_180016AF4
0x180016ae3  mov     rax, [rcx]
0x180016ae6  mov     rax, [rax+10h]
0x180016aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aef  mov     [rsp+1560h+ppURI], r12
0x180016af4  mov     rcx, qword ptr [rsp+1560h+var_1508]
0x180016af9  test    rcx, rcx
0x180016afc  jz      short loc_180016B0F
0x180016afe  mov     rax, [rcx]
0x180016b01  mov     rax, [rax+10h]
0x180016b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b0a  mov     qword ptr [rsp+1560h+var_1508], r12
0x180016b0f  cmp     [rbp+1460h+var_10C8], r12
0x180016b16  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180016b1d  mov     edi, r12d
0x180016b20  mov     qword ptr [rbp+1460h+Str], rax
0x180016b27  setnz   dil
0x180016b2b  mov     eax, r12d
  ... truncated ...
```
