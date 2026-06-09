# IsHPFeatureEnabled(ushort const *,ushort const *,ushort const *,ushort const *,int *,ushort * *)

- ea: `0x18003c99c`
- end: `0x18003d045`
- name: `?IsHPFeatureEnabled@@YAJPEBG000PEAHPEAPEAG@Z`
- size: `1705`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003d444`

## callees

- `0x18001bddc`
- `0x18003c0b8`
- `0x18003c150`
- `0x18003c1b4`
- `0x18003c99c`
- `0x18003d250`
- `0x18003e5bc`
- `0x18005e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003cdf0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ceb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003cdf0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003ceb3`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cdb2`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ce65`
- `OLEAUT32!__imp_SysStringLen` at `0x18003cdb2`
- `OLEAUT32!__imp_SysStringLen` at `0x18003ce65`
- `OLEAUT32!__imp_VariantInit` at `0x18003cd15`
- `OLEAUT32!__imp_VariantInit` at `0x18003cd15`
- `OLEAUT32!__imp_VariantClear` at `0x18003cee7`
- `OLEAUT32!__imp_VariantClear` at `0x18003cf39`
- `OLEAUT32!__imp_VariantClear` at `0x18003cf7d`
- `OLEAUT32!__imp_VariantClear` at `0x18003cee7`
- `OLEAUT32!__imp_VariantClear` at `0x18003cf39`
- `OLEAUT32!__imp_VariantClear` at `0x18003cf7d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cd88`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003cd88`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003cd79`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003cd79`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003cda2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003ce55`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003cda2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003ce55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ce0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce1e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ce1e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cb28`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cdc7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cf2a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cb28`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cdc7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003cf2a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c9e5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003c9e5`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18003ca48`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18003ca48`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003cb7b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003cb7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ca7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ca7f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003d029`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003d029`

## string_xrefs

- `0x18003ca57`: `CoInitializeSecurity Ignoring failure RPC_E_TOO_LATE`
- `0x18003ca0e`: `Failed to initialize COM library with error %x`
- `0x18003ca8b`: `CoCreateInstance Failed to create IWbemLocator object failed with error %x`
- `0x18003ca9b`: `CoInitializeSecurity failed with error %x`
- `0x18003cfb1`: `Failed to read the Next item in the list with error %x`
- `0x18003cb9f`: `SELECT * FROM Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsHPFeatureEnabled(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        _bstr_t::Data_t *a3,
        _bstr_t::Data_t *a4,
        int *a5,
        unsigned __int16 **a6)
{
  int *v6; // r13
  HRESULT v7; // eax
  HRESULT Element; // edi
  HRESULT v9; // eax
  HRESULT v10; // eax
  __int64 (__fastcall *v11)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // rbx
  _bstr_t *v12; // rax
  __int64 v13; // rdx
  HRESULT v14; // eax
  char IsEnabled; // al
  ULONG (__stdcall *Release)(IUnknown *); // rdi
  _bstr_t *v17; // rax
  __int64 v18; // rbx
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  _bstr_t *v21; // rax
  const char *v22; // rdx
  __int64 v23; // rbx
  _bstr_t *v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  SAFEARRAY *parray; // r14
  int v29; // ebx
  int i; // eax
  __int64 v31; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v33; // rax
  unsigned __int16 *v34; // rbx
  unsigned __int16 *v35; // r12
  __int64 v36; // r11
  __int64 v37; // r11
  IUnknown *pProxy; // [rsp+58h] [rbp-39h] BYREF
  __int64 v40; // [rsp+60h] [rbp-31h] BYREF
  __int64 v41; // [rsp+68h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-21h] BYREF
  OLECHAR *pv; // [rsp+78h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-11h] BYREF
  int v45; // [rsp+E8h] [rbp+57h]
  const unsigned __int16 *plLbound; // [rsp+F0h] [rbp+5Fh] BYREF
  _bstr_t::Data_t *rgIndices; // [rsp+F8h] [rbp+67h] BYREF
  _bstr_t::Data_t *plUbound; // [rsp+100h] [rbp+6Fh] BYREF

  plUbound = a4;
  rgIndices = a3;
  plLbound = a2;
  ppv = 0;
  pProxy = 0;
  v41 = 0;
  v40 = 0;
  v6 = a5;
  *a5 = 0;
  v7 = CoInitializeEx(0, 0);
  Element = v7;
  if ( v7 )
  {
    if ( v7 == 1 || v7 == -2147417850 )
    {
      v45 = 0;
    }
    else
    {
      v45 = 0;
      if ( v7 < 0 )
      {
        SBServicingLogMessage(L"Failed to initialize COM library with error %x", (unsigned int)v7);
        goto LABEL_78;
      }
    }
  }
  else
  {
    v45 = 1;
  }
  v9 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  Element = v9;
  if ( v9 == -2147417831 )
  {
    SBServicingLogMessage((wchar_t *)L"CoInitializeSecurity Ignoring failure RPC_E_TOO_LATE");
  }
  else if ( v9 < 0 )
  {
    SBServicingLogMessage(L"CoInitializeSecurity failed with error %x", (unsigned int)v9);
    goto LABEL_78;
  }
  v10 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  Element = v10;
  if ( v10 < 0 )
  {
    SBServicingLogMessage(
      L"CoCreateInstance Failed to create IWbemLocator object failed with error %x",
      (unsigned int)v10);
    goto LABEL_78;
  }
  v11 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL);
  v12 = _bstr_t::_bstr_t((_bstr_t *)&plUbound, L"Root\\CIMV2");
  if ( *(_QWORD *)v12 )
    v13 = **(_QWORD **)v12;
  else
    v13 = 0;
  Element = v11(ppv, v13, 0, 0, 0, 0, 0, 0, &pProxy);
  if ( plUbound )
    _bstr_t::Data_t::Release(plUbound);
  if ( Element == -2147217394 )
  {
    if ( StrStrIW(L"Root\\CIMV2", L"HP") )
    {
      Element = 0;
      SBServicingLogMessage((wchar_t *)L"ROOT-HP-InstrumentedBIOS WMI namespace not found, EpSC and Sure Start SBKP not supported");
      goto LABEL_78;
    }
    goto LABEL_23;
  }
  if ( Element < 0 )
  {
LABEL_23:
    SBServicingLogMessage(
      L"Could not connect to ROOT-HP-InstrumentedBIOS WMI namespace with error %x",
      (unsigned int)Element);
    goto LABEL_78;
  }
  v14 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  Element = v14;
  if ( v14 < 0 )
  {
    SBServicingLogMessage(L"CoSetProxyBlanket failed with error %x", (unsigned int)v14);
    goto LABEL_78;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SBAITickler>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SBAITickler>::GetImpl'::`2'::impl);
  Release = pProxy->lpVtbl[6].Release;
  if ( IsEnabled )
  {
    v17 = _bstr_t::_bstr_t((_bstr_t *)&rgIndices, L"SELECT * FROM Win32_ComputerSystem");
    if ( *(_QWORD *)v17 )
      v18 = **(_QWORD **)v17;
    else
      v18 = 0;
    v19 = _bstr_t::_bstr_t((_bstr_t *)&plUbound, L"WQL");
    if ( *(_QWORD *)v19 )
      v20 = **(_QWORD **)v19;
    else
      v20 = 0;
    Element = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, __int64 *))Release)(
                pProxy,
                v20,
                v18,
                48,
                0,
                &v41);
    if ( plUbound )
    {
      _bstr_t::Data_t::Release(plUbound);
      plUbound = 0;
    }
  }
  else
  {
    v21 = _bstr_t::_bstr_t((_bstr_t *)&rgIndices, L"SELECT * FROM Win32_ComputerSystem");
    if ( *(_QWORD *)v21 )
      v23 = **(_QWORD **)v21;
    else
      v23 = 0;
    v24 = _bstr_t::_bstr_t((_bstr_t *)&plUbound, v22);
    if ( *(_QWORD *)v24 )
      v25 = **(_QWORD **)v24;
    else
      v25 = 0;
    Element = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, __int64 *))Release)(
                pProxy,
                v25,
                v23,
                48,
                0,
                &v41);
    if ( plUbound )
    {
      _bstr_t::Data_t::Release(plUbound);
      plUbound = 0;
    }
  }
  if ( rgIndices )
    _bstr_t::Data_t::Release(rgIndices);
  if ( Element < 0 )
  {
    SBServicingLogMessage(L"Query for HP_BIOSSetting failed with error %x", (unsigned int)Element);
    goto LABEL_78;
  }
  LODWORD(a5) = 0;
  if ( v41 )
  {
    while ( 1 )
    {
      v26 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int **))(*(_QWORD *)v41 + 32LL))(
              v41,
              0xFFFFFFFFLL,
              1,
              &v40,
              &a5);
      Element = v26;
      if ( v26 < 0 )
      {
        SBServicingLogMessage((wchar_t *)L"Failed to read the Next item in the list with error %x", (unsigned int)v26);
        goto LABEL_78;
      }
      if ( !(_DWORD)a5 )
      {
        SBServicingLogMessage((wchar_t *)L"Reached end of the list, didn't find %ls:%ls", L"OEMStringArray", L"EDK2_1");
        goto LABEL_78;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
              v40,
              L"OEMStringArray",
              0,
              &pvarg,
              0,
              0);
      Element = v27;
      if ( v27 < 0 )
      {
        SBServicingLogMessage(
          (wchar_t *)L"Getting %ls property failed with error %x",
          L"OEMStringArray",
          (unsigned int)v27);
        goto LABEL_78;
      }
      if ( pvarg.vt != 8200 )
        break;
      parray = pvarg.parray;
      if ( !pvarg.llVal )
        goto LABEL_71;
      v29 = 0;
      LODWORD(plLbound) = 0;
      LODWORD(plUbound) = 0;
      SafeArrayGetLBound(pvarg.parray, 1u, (LONG *)&plLbound);
      SafeArrayGetUBound(parray, 1u, (LONG *)&plUbound);
      for ( i = (int)plLbound; ; i = (_DWORD)rgIndices + 1 )
      {
        LODWORD(rgIndices) = i;
        if ( i > (int)plUbound )
          break;
        pv = 0;
        Element = SafeArrayGetElement(parray, (LONG *)&rgIndices, &pv);
        if ( Element >= 0 )
        {
          v29 += SysStringLen(pv) + 1;
          if ( StrStrIW(pv, L"EDK2_1") )
          {
            *v6 = 1;
            SBServicingLogMessage((wchar_t *)L"Found %ls:%ls", L"OEMStringArray", L"EDK2_1");
          }
          SysFreeString(pv);
        }
      }
      v31 = (unsigned int)(v29 + 1);
      ProcessHeap = GetProcessHeap();
      v33 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v31);
      v34 = v33;
      if ( v33 )
      {
        v35 = v33;
        LODWORD(rgIndices) = (_DWORD)plLbound;
        if ( (int)plLbound <= (int)plUbound )
        {
          do
          {
            pv = 0;
            Element = SafeArrayGetElement(parray, (LONG *)&rgIndices, &pv);
            if ( Element >= 0 )
            {
              SysStringLen(pv);
              StringCchCopyW(v35, v31 - (v35 - v34), pv);
              StringCchCopyW(&v35[v36], v31 - (&v35[v36] - v34), &dword_18007BE3C);
              v35 = (unsigned __int16 *)(v37 + 2);
              SysFreeString(pv);
            }
            LODWORD(rgIndices) = (_DWORD)rgIndices + 1;
          }
          while ( (int)rgIndices <= (int)plUbound );
        }
        *a6 = v34;
      }
      SBServicingLogMessage((wchar_t *)L"pLocalOEMStringArray %ls", v34);
      VariantClear(&pvarg);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v40 = 0;
      if ( *v6 == 1 )
        goto LABEL_78;
LABEL_72:
      if ( !v41 )
        goto LABEL_78;
    }
    if ( pvarg.vt == 8 && StrStrIW(pvarg.bstrVal, L"EDK2_1") )
    {
      *v6 = 1;
      SBServicingLogMessage((wchar_t *)L"Found %ls:%ls", L"OEMStringArray", L"EDK2_1");
      VariantClear(&pvarg);
      goto LABEL_78;
    }
LABEL_71:
    VariantClear(&pvarg);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
    goto LABEL_72;
  }
LABEL_78:
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v45 )
    CoUninitialize();
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18003c99c  mov     rax, rsp
0x18003c99f  mov     [rax+20h], r9
0x18003c9a3  mov     [rax+18h], r8
0x18003c9a7  mov     [rax+10h], rdx
0x18003c9ab  mov     [rax+8], rcx
0x18003c9af  push    rbp
0x18003c9b0  push    rbx
0x18003c9b1  push    rsi
0x18003c9b2  push    rdi
0x18003c9b3  push    r12
0x18003c9b5  push    r13
0x18003c9b7  push    r14
0x18003c9b9  push    r15
0x18003c9bb  lea     rbp, [rax-4Fh]
0x18003c9bf  sub     rsp, 98h
0x18003c9c6  xor     r12d, r12d
0x18003c9c9  mov     [rbp+47h+ppv], r12
0x18003c9cd  mov     [rbp+47h+pProxy], r12
0x18003c9d1  mov     [rbp+47h+var_70], r12
0x18003c9d5  mov     [rbp+47h+var_78], r12
0x18003c9d9  mov     r13, [rbp+47h+arg_20]
0x18003c9dd  mov     [r13+0], r12d
0x18003c9e1  xor     edx, edx; dwCoInit
0x18003c9e3  xor     ecx, ecx; pvReserved
0x18003c9e5  call    cs:__imp_CoInitializeEx
0x18003c9eb  mov     edi, eax
0x18003c9ed  lea     esi, [r12+1]
0x18003c9f2  test    eax, eax
0x18003c9f4  jnz     short loc_18003C9FB
0x18003c9f6  mov     [rbp+47h+arg_0], esi
0x18003c9f9  jmp     short loc_18003CA1E
0x18003c9fb  cmp     eax, esi
0x18003c9fd  jz      short loc_18003CA1A
0x18003c9ff  cmp     eax, 80010106h
0x18003ca04  jz      short loc_18003CA1A
0x18003ca06  mov     [rbp+47h+arg_0], r12d
0x18003ca0a  test    eax, eax
0x18003ca0c  jns     short loc_18003CA1E
0x18003ca0e  lea     rcx, aFailedToInitia_0; "Failed to initialize COM library with e"...
0x18003ca15  jmp     loc_18003CFB8
0x18003ca1a  mov     [rbp+47h+arg_0], r12d
0x18003ca1e  mov     [rsp+40h], r12; pReserved3
0x18003ca23  mov     [rsp+0D0h+dwCapabilities], r12d; dwCapabilities
0x18003ca28  mov     [rsp+0D0h+pAuthList], r12; pAuthList
0x18003ca2d  mov     r14d, 3
0x18003ca33  mov     [rsp+0D0h+dwImpLevel], r14d; dwImpLevel
0x18003ca38  mov     [rsp+0D0h+dwAuthnLevel], r12d; dwAuthnLevel
0x18003ca3d  xor     r9d, r9d; pReserved1
0x18003ca40  xor     r8d, r8d; asAuthSvc
0x18003ca43  or      edx, 0FFFFFFFFh; cAuthSvc
0x18003ca46  xor     ecx, ecx; pSecDesc
0x18003ca48  call    cs:__imp_CoInitializeSecurity
0x18003ca4e  mov     edi, eax
0x18003ca50  cmp     eax, 80010119h
0x18003ca55  jnz     short loc_18003CA97
0x18003ca57  lea     rcx, aCoinitializese_0; "CoInitializeSecurity Ignoring failure R"...
0x18003ca5e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003ca63  lea     rax, [rbp+47h+ppv]
0x18003ca67  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rax; ppv
0x18003ca6c  lea     r9, IID_IWbemLocator; riid
0x18003ca73  mov     r8d, esi; dwClsContext
0x18003ca76  xor     edx, edx; pUnkOuter
0x18003ca78  lea     rcx, CLSID_WbemLocator; rclsid
0x18003ca7f  call    cs:__imp_CoCreateInstance
0x18003ca85  mov     edi, eax
0x18003ca87  test    eax, eax
0x18003ca89  jns     short loc_18003CAA7
0x18003ca8b  lea     rcx, aCocreateinstan_0; "CoCreateInstance Failed to create IWbem"...
0x18003ca92  jmp     loc_18003CFB8
0x18003ca97  test    eax, eax
0x18003ca99  jns     short loc_18003CA63
0x18003ca9b  lea     rcx, aCoinitializese_1; "CoInitializeSecurity failed with error "...
0x18003caa2  jmp     loc_18003CFB8
0x18003caa7  mov     rax, [rbp+47h+ppv]
0x18003caab  mov     rcx, [rax]
0x18003caae  mov     rbx, [rcx+18h]
0x18003cab2  lea     rdx, pszFirst; "Root\\CIMV2"
0x18003cab9  lea     rcx, [rbp+47h+plUbound]; this
0x18003cabd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cac2  nop
0x18003cac3  mov     rdx, [rax]
0x18003cac6  test    rdx, rdx
0x18003cac9  jz      short loc_18003CAD0
0x18003cacb  mov     rdx, [rdx]
0x18003cace  jmp     short loc_18003CAD3
0x18003cad0  mov     rdx, r12
0x18003cad3  lea     rax, [rbp+47h+pProxy]
0x18003cad7  mov     [rsp+40h], rax
0x18003cadc  mov     qword ptr [rsp+0D0h+dwCapabilities], r12
0x18003cae1  mov     [rsp+0D0h+pAuthList], r12
0x18003cae6  mov     [rsp+0D0h+dwImpLevel], r12d
0x18003caeb  mov     qword ptr [rsp+0D0h+dwAuthnLevel], r12
0x18003caf0  xor     r9d, r9d
0x18003caf3  xor     r8d, r8d
0x18003caf6  mov     rcx, [rbp+47h+ppv]
0x18003cafa  mov     rax, rbx
0x18003cafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb02  mov     edi, eax
0x18003cb04  mov     rcx, [rbp+47h+plUbound]; this
0x18003cb08  test    rcx, rcx
0x18003cb0b  jz      short loc_18003CB12
0x18003cb0d  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18003cb12  cmp     edi, 8004100Eh
0x18003cb18  jnz     short loc_18003CB47
0x18003cb1a  lea     rdx, aHp; "HP"
0x18003cb21  lea     rcx, pszFirst; "Root\\CIMV2"
0x18003cb28  call    cs:__imp_StrStrIW
0x18003cb2e  test    rax, rax
0x18003cb31  jz      short loc_18003CB4B
0x18003cb33  mov     edi, r12d
0x18003cb36  lea     rcx, aRootHpInstrume; "ROOT-HP-InstrumentedBIOS WMI namespace "...
0x18003cb3d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003cb42  jmp     loc_18003CFBF
0x18003cb47  test    edi, edi
0x18003cb49  jns     short loc_18003CB59
0x18003cb4b  mov     edx, edi
0x18003cb4d  lea     rcx, aCouldNotConnec; "Could not connect to ROOT-HP-Instrument"...
0x18003cb54  jmp     loc_18003CFBA
0x18003cb59  mov     [rsp+0D0h+dwCapabilities], r12d; dwCapabilities
0x18003cb5e  mov     [rsp+0D0h+pAuthList], r12; pAuthInfo
0x18003cb63  mov     [rsp+0D0h+dwImpLevel], r14d; dwImpLevel
0x18003cb68  mov     [rsp+0D0h+dwAuthnLevel], r14d; dwAuthnLevel
0x18003cb6d  xor     r9d, r9d; pServerPrincName
0x18003cb70  xor     r8d, r8d; dwAuthzSvc
0x18003cb73  lea     edx, [r9+0Ah]; dwAuthnSvc
0x18003cb77  mov     rcx, [rbp+47h+pProxy]; pProxy
0x18003cb7b  call    cs:__imp_CoSetProxyBlanket
0x18003cb81  mov     edi, eax
0x18003cb83  test    eax, eax
0x18003cb85  jns     short loc_18003CB93
0x18003cb87  lea     rcx, aCosetproxyblan_0; "CoSetProxyBlanket failed with error %x"
0x18003cb8e  jmp     loc_18003CFB8
0x18003cb93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SBAITickler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SBAITickler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SBAITickler> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SBAITickler>::GetImpl(void)'::`2'::impl
0x18003cb9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SBAITickler@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SBAITickler>::__private_IsEnabled(void)
0x18003cb9f  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_ComputerSystem"
0x18003cba6  test    al, al
0x18003cba8  mov     rax, [rbp+47h+pProxy]
0x18003cbac  mov     rcx, [rax]
0x18003cbaf  mov     rdi, [rcx+0A0h]
0x18003cbb6  lea     rcx, [rbp+47h+rgIndices]; this
0x18003cbba  jz      short loc_18003CC2C
0x18003cbbc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cbc1  nop
0x18003cbc2  mov     rcx, [rax]
0x18003cbc5  test    rcx, rcx
0x18003cbc8  jz      short loc_18003CBCF
0x18003cbca  mov     rbx, [rcx]
0x18003cbcd  jmp     short loc_18003CBD2
0x18003cbcf  mov     rbx, r12
0x18003cbd2  lea     rdx, aWql_0; "WQL"
0x18003cbd9  lea     rcx, [rbp+47h+plUbound]; this
0x18003cbdd  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cbe2  nop
0x18003cbe3  mov     rcx, [rax]
0x18003cbe6  test    rcx, rcx
0x18003cbe9  jz      short loc_18003CBF0
0x18003cbeb  mov     rdx, [rcx]
0x18003cbee  jmp     short loc_18003CBF3
0x18003cbf0  mov     rdx, r12
0x18003cbf3  lea     rax, [rbp+47h+var_70]
0x18003cbf7  mov     qword ptr [rsp+0D0h+dwImpLevel], rax
0x18003cbfc  mov     qword ptr [rsp+0D0h+dwAuthnLevel], r12
0x18003cc01  mov     r9d, 30h ; '0'
0x18003cc07  mov     r8, rbx
0x18003cc0a  mov     rcx, [rbp+47h+pProxy]
0x18003cc0e  mov     rax, rdi
0x18003cc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc16  mov     edi, eax
0x18003cc18  mov     rcx, [rbp+47h+plUbound]; this
0x18003cc1c  test    rcx, rcx
0x18003cc1f  jz      short loc_18003CC2A
0x18003cc21  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18003cc26  mov     [rbp+47h+plUbound], r12
0x18003cc2a  jmp     short loc_18003CC93
0x18003cc2c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003cc31  nop
0x18003cc32  mov     rcx, [rax]
0x18003cc35  test    rcx, rcx
0x18003cc38  jz      short loc_18003CC3F
0x18003cc3a  mov     rbx, [rcx]
0x18003cc3d  jmp     short loc_18003CC42
0x18003cc3f  mov     rbx, r12
0x18003cc42  lea     rcx, [rbp+47h+plUbound]; this
0x18003cc46  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18003cc4b  nop
0x18003cc4c  mov     rcx, [rax]
0x18003cc4f  test    rcx, rcx
0x18003cc52  jz      short loc_18003CC59
0x18003cc54  mov     rdx, [rcx]
0x18003cc57  jmp     short loc_18003CC5C
0x18003cc59  mov     rdx, r12
0x18003cc5c  lea     rax, [rbp+47h+var_70]
0x18003cc60  mov     qword ptr [rsp+0D0h+dwImpLevel], rax
0x18003cc65  mov     qword ptr [rsp+0D0h+dwAuthnLevel], r12
0x18003cc6a  mov     r9d, 30h ; '0'
0x18003cc70  mov     r8, rbx
0x18003cc73  mov     rcx, [rbp+47h+pProxy]
0x18003cc77  mov     rax, rdi
0x18003cc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc7f  mov     edi, eax
0x18003cc81  mov     rcx, [rbp+47h+plUbound]; this
0x18003cc85  test    rcx, rcx
0x18003cc88  jz      short loc_18003CC93
0x18003cc8a  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18003cc8f  mov     [rbp+47h+plUbound], r12
0x18003cc93  mov     rcx, [rbp+47h+rgIndices]; this
0x18003cc97  test    rcx, rcx
0x18003cc9a  jz      short loc_18003CCA1
0x18003cc9c  call    ?Release@Data_t@_bstr_t@@QEAAKXZ; _bstr_t::Data_t::Release(void)
0x18003cca1  test    edi, edi
0x18003cca3  jns     short loc_18003CCB3
0x18003cca5  mov     edx, edi
0x18003cca7  lea     rcx, aQueryForHpBios; "Query for HP_BIOSSetting failed with er"...
0x18003ccae  jmp     loc_18003CFBA
0x18003ccb3  mov     dword ptr [rbp+47h+arg_20], r12d
0x18003ccb7  cmp     [rbp+47h+var_70], r12
0x18003ccbb  jz      loc_18003CFBF
0x18003ccc1  lea     r15, aOemstringarray; "OEMStringArray"
0x18003ccc8  mov     ebx, 8
0x18003cccd  mov     rcx, [rbp+47h+var_70]
0x18003ccd1  mov     rax, [rcx]
0x18003ccd4  lea     rdx, [rbp+47h+arg_20]
0x18003ccd8  mov     qword ptr [rsp+0D0h+dwAuthnLevel], rdx
0x18003ccdd  lea     r9, [rbp+47h+var_78]
0x18003cce1  mov     r8d, esi
0x18003cce4  or      edx, 0FFFFFFFFh
0x18003cce7  mov     rax, [rax+20h]
0x18003cceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccf0  mov     edi, eax
0x18003ccf2  test    eax, eax
0x18003ccf4  js      loc_18003CFB1
0x18003ccfa  cmp     dword ptr [rbp+47h+arg_20], r12d
0x18003ccfe  jz      loc_18003CF99
0x18003cd04  xorps   xmm0, xmm0
0x18003cd07  xor     eax, eax
0x18003cd09  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18003cd0d  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18003cd11  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18003cd15  call    cs:__imp_VariantInit
0x18003cd1b  mov     rcx, [rbp+47h+var_78]
0x18003cd1f  mov     rax, [rcx]
0x18003cd22  mov     qword ptr [rsp+0D0h+dwImpLevel], r12
0x18003cd27  mov     qword ptr [rsp+0D0h+dwAuthnLevel], r12
0x18003cd2c  lea     r9, [rbp+47h+pvarg]
0x18003cd30  xor     r8d, r8d
0x18003cd33  mov     rdx, r15
0x18003cd36  mov     rax, [rax+20h]
0x18003cd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd3f  mov     edi, eax
0x18003cd41  test    eax, eax
0x18003cd43  js      loc_18003CF85
0x18003cd49  mov     eax, 2008h
0x18003cd4e  cmp     word ptr [rbp+47h+pvarg], ax
0x18003cd52  jnz     loc_18003CF19
0x18003cd58  mov     r14, qword ptr [rbp+47h+pvarg+8]
0x18003cd5c  test    r14, r14
0x18003cd5f  jz      loc_18003CF35
0x18003cd65  mov     ebx, r12d
0x18003cd68  mov     dword ptr [rbp+47h+plLbound], r12d
0x18003cd6c  mov     dword ptr [rbp+47h+plUbound], r12d
0x18003cd70  lea     r8, [rbp+47h+plLbound]; plLbound
0x18003cd74  mov     edx, esi; nDim
0x18003cd76  mov     rcx, r14; psa
0x18003cd79  call    cs:__imp_SafeArrayGetLBound
0x18003cd7f  lea     r8, [rbp+47h+plUbound]; plUbound
0x18003cd83  mov     edx, esi; nDim
0x18003cd85  mov     rcx, r14; psa
0x18003cd88  call    cs:__imp_SafeArrayGetUBound
0x18003cd8e  mov     eax, dword ptr [rbp+47h+plLbound]
0x18003cd91  jmp     short loc_18003CDFB
0x18003cd93  mov     [rbp+47h+pv], r12
0x18003cd97  lea     r8, [rbp+47h+pv]; pv
0x18003cd9b  lea     rdx, [rbp+47h+rgIndices]; rgIndices
0x18003cd9f  mov     rcx, r14; psa
0x18003cda2  call    cs:__imp_SafeArrayGetElement
0x18003cda8  mov     edi, eax
0x18003cdaa  test    eax, eax
0x18003cdac  js      short loc_18003CDF6
0x18003cdae  mov     rcx, [rbp+47h+pv]; pbstr
0x18003cdb2  call    cs:__imp_SysStringLen
0x18003cdb8  inc     eax
0x18003cdba  add     ebx, eax
0x18003cdbc  lea     rdx, aEdk21; "EDK2_1"
0x18003cdc3  mov     rcx, [rbp+47h+pv]; pszFirst
0x18003cdc7  call    cs:__imp_StrStrIW
0x18003cdcd  test    rax, rax
0x18003cdd0  jz      short loc_18003CDEC
0x18003cdd2  mov     [r13+0], esi
0x18003cdd6  lea     r8, aEdk21; "EDK2_1"
0x18003cddd  mov     rdx, r15
0x18003cde0  lea     rcx, aFoundLsLs; "Found %ls:%ls"
0x18003cde7  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003cdec  mov     rcx, [rbp+47h+pv]; bstrString
0x18003cdf0  call    cs:__imp_SysFreeString
0x18003cdf6  mov     eax, dword ptr [rbp+47h+rgIndices]
0x18003cdf9  add     eax, esi
0x18003cdfb  cmp     eax, dword ptr [rbp+47h+plUbound]
0x18003cdfe  mov     dword ptr [rbp+47h+rgIndices], eax
0x18003ce01  jle     short loc_18003CD93
0x18003ce03  lea     eax, [rbx+1]
  ... truncated ...
```
