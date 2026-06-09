# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::BuildObjectFolderAndFilePath(void)

- ea: `0x1800750c0`
- end: `0x18007631a`
- name: `?BuildObjectFolderAndFilePath@StoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@AEAAJXZ`
- size: `4698`
- prototype: `__int64 __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180111c50`

## callees

- `0x180009e80`
- `0x18000bd40`
- `0x180023c50`
- `0x180030f90`
- `0x18003ffa0`
- `0x180052698`
- `0x180053cfc`
- `0x180061b84`
- `0x1800750c0`
- `0x18007c220`
- `0x18007f9b0`
- `0x18008e690`
- `0x18008e6b4`
- `0x18008e6cc`
- `0x18008eb90`
- `0x180091388`
- `0x1800913f4`
- `0x180091975`
- `0x180091981`
- `0x1800d6d80`
- `0x180113a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075137`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800752ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075137`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800752ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007511d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800752d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007511d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800752d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007514d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007514d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800751c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800761df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800761ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800751c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800761df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800761ef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075190`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800753b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800757de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075bc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075202`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800753b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800757de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075bc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076147`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075344`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075214`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180075344`

## string_xrefs

- `0x18007519e`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800751e5`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180075273`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180075295`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800753a3`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800753c5`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x18007576d`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180075b51`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800760d1`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x1800755d1`: `TokenBroker`
- `0x1800756a6`: `TokenBroker`
- `0x18007570c`: `TokenBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo::BuildObjectFolderAndFilePath(
        HSTRING *this)
{
  WCHAR *v2; // rax
  unsigned __int16 *v3; // r14
  const char *v5; // r9
  PCWSTR v6; // rax
  int AppContainerFolderPathFromPfn; // ebx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // edi
  unsigned __int64 v12; // rdx
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  const char *v15; // r9
  __int64 v16; // rdx
  PCWSTR StringRawBuffer; // rax
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // r8
  unsigned __int64 v20; // rdx
  int ExpandedEnvironmentStringForUser; // eax
  __int64 v22; // r8
  char *v23; // r12
  unsigned __int64 v24; // r15
  __int64 v25; // rsi
  char *v26; // rdx
  void **v27; // rcx
  char *v28; // r13
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // rcx
  size_t v31; // rcx
  _QWORD *v32; // rbx
  void *v33; // rax
  size_t v34; // r8
  _WORD *v35; // r12
  void *v36; // rdi
  _BYTE *v37; // rcx
  char *v38; // r12
  unsigned __int64 v39; // r15
  char *v40; // rdi
  void **v41; // rbx
  _QWORD *v42; // rbx
  char *v43; // r13
  unsigned __int64 v44; // rdi
  unsigned __int64 v45; // rcx
  size_t v46; // rcx
  void *v47; // rax
  size_t v48; // r8
  char *v49; // r12
  void *v50; // rdi
  _BYTE *v51; // rcx
  void *v52; // rcx
  char *v53; // r12
  unsigned __int64 v54; // r15
  char *v55; // rdx
  void **v56; // rcx
  char *v57; // r13
  unsigned __int64 v58; // rdi
  unsigned __int64 v59; // rcx
  size_t v60; // rcx
  _QWORD *v61; // rbx
  void *v62; // rax
  size_t v63; // r8
  _WORD *v64; // r12
  void *v65; // rdi
  _BYTE *v66; // rcx
  _WORD *v67; // r12
  unsigned __int64 v68; // r15
  char *v69; // rcx
  unsigned __int64 v70; // r13
  char *v71; // rdi
  void **v72; // rbx
  _QWORD *v73; // rbx
  unsigned __int64 v74; // rdi
  unsigned __int64 v75; // rcx
  size_t v76; // rcx
  void *v77; // rax
  size_t v78; // r8
  size_t v79; // r15
  char *v80; // rdi
  void *v81; // rdi
  _BYTE *v82; // rcx
  void *v83; // rcx
  char *v84; // r12
  unsigned __int64 v85; // r15
  void **v86; // rcx
  char *v87; // r13
  unsigned __int64 v88; // rdi
  unsigned __int64 v89; // rcx
  size_t v90; // rcx
  _QWORD *v91; // rbx
  void *v92; // rax
  size_t v93; // r8
  _WORD *v94; // r12
  void *v95; // rdi
  _BYTE *v96; // rcx
  PCWSTR v97; // rax
  PCWSTR v98; // r12
  unsigned __int64 v99; // r15
  char *v100; // r13
  unsigned __int64 v101; // rdx
  char *v102; // rdi
  void **v103; // rbx
  unsigned __int64 v104; // rdi
  unsigned __int64 v105; // rcx
  size_t v106; // rcx
  _QWORD *v107; // rbx
  void *v108; // rax
  size_t v109; // r8
  size_t v110; // r15
  char *v111; // r13
  void *v112; // rdi
  _BYTE *v113; // rcx
  char *v114; // rdi
  unsigned __int64 v115; // r15
  void **v116; // rcx
  char *v117; // r12
  unsigned __int64 v118; // rcx
  __int64 v119; // rdx
  size_t v120; // rax
  _QWORD *v121; // rbx
  void *v122; // rax
  size_t v123; // r8
  _WORD *v124; // rsi
  void *v125; // rdi
  void *v126; // rcx
  PCWSTR v127; // rsi
  __int64 v128; // rax
  void **v129; // rdx
  void *v130; // rcx
  _QWORD *v131; // rax
  _QWORD *v132; // rax
  unsigned int v133; // [rsp+20h] [rbp-79h]
  INT32 result[2]; // [rsp+40h] [rbp-59h] BYREF
  void *v135; // [rsp+48h] [rbp-51h]
  PCWSTR v136; // [rsp+50h] [rbp-49h]
  LPVOID pv; // [rsp+58h] [rbp-41h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-39h] BYREF
  char *v139; // [rsp+70h] [rbp-29h]
  unsigned __int64 v140; // [rsp+78h] [rbp-21h]
  HSTRING string; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v136 = (PCWSTR)this;
  pv = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
  {
    if ( WindowsCreateStringReference(L"NO_APPLICATION", 0xEu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    result[0] = 0;
    WindowsCompareStringOrdinal(this[9], string, result);
    if ( result[0] )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(this[9], 0);
      AppContainerFolderPathFromPfn = Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(
                                        StringRawBuffer,
                                        &pv);
      if ( AppContainerFolderPathFromPfn < 0 )
      {
        v8 = 1099;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
          (const char *)(unsigned int)AppContainerFolderPathFromPfn,
          v133);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)AppContainerFolderPathFromPfn;
      }
LABEL_29:
      v3 = (unsigned __int16 *)pv;
      goto LABEL_37;
    }
    v18 = (unsigned __int16 *)CoTaskMemAlloc(0x20Au);
    v3 = v18;
    if ( v18 )
    {
      v135 = v18;
      v20 = (unsigned int)tls_index;
      if ( dword_180176B60 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 8LL) )
      {
        Init_thread_header(&dword_180176B60);
        if ( dword_180176B60 == -1 )
        {
          qword_180176B70 = 0;
          qword_180176B78 = 0;
          v132 = operator new(0x60u);
          *v132 = v132;
          v132[1] = v132;
          v132[2] = v132;
          *((_WORD *)v132 + 12) = 257;
          qword_180176B70 = v132;
          qword_180176B80 = 0;
          atexit(Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetInstance_::_2_::_dynamic_atexit_destructor_for__cache__);
          Init_thread_footer(&dword_180176B60);
        }
      }
      ExpandedEnvironmentStringForUser = Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetExpandedEnvironmentStringForUser(
                                           (Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache *)&qword_180176B70,
                                           (void *)v20,
                                           v19,
                                           v3,
                                           v133);
      v11 = ExpandedEnvironmentStringForUser;
      if ( ExpandedEnvironmentStringForUser >= 0 )
      {
        pv = v3;
        goto LABEL_37;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)ExpandedEnvironmentStringForUser,
        v133);
      CoTaskMemFree(v3);
    }
    else
    {
      v11 = -2147024882;
    }
    v14 = retaddr;
    v15 = (const char *)v11;
    v16 = 1103;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      v14,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      v15,
      v133);
    return v11;
  }
  if ( WindowsCreateStringReference(L"NO_APPLICATION", 0xEu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  result[0] = 0;
  WindowsCompareStringOrdinal(this[9], string, result);
  if ( !result[0] )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc(0x20Au);
    v3 = v9;
    if ( v9 )
    {
      v135 = v9;
      v12 = (unsigned int)tls_index;
      if ( dword_180176B60 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 8LL) )
      {
        Init_thread_header(&dword_180176B60);
        if ( dword_180176B60 == -1 )
        {
          qword_180176B70 = 0;
          qword_180176B78 = 0;
          v131 = operator new(0x60u);
          *v131 = v131;
          v131[1] = v131;
          v131[2] = v131;
          *((_WORD *)v131 + 12) = 257;
          qword_180176B70 = v131;
          qword_180176B80 = 0;
          atexit(Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetInstance_::_2_::_dynamic_atexit_destructor_for__cache__);
          Init_thread_footer(&dword_180176B60);
        }
      }
      v13 = Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetExpandedEnvironmentStringForUser(
              (Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache *)&qword_180176B70,
              (void *)v12,
              v10,
              v3,
              v133);
      v11 = v13;
      if ( v13 >= 0 )
      {
        pv = v3;
        goto LABEL_37;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)v13,
        v133);
      CoTaskMemFree(v3);
    }
    else
    {
      v11 = -2147024882;
    }
    v14 = retaddr;
    v15 = (const char *)v11;
    v16 = 1091;
    goto LABEL_22;
  }
  if ( !*((_BYTE *)this + 100) )
  {
    v6 = WindowsGetStringRawBuffer(this[9], 0);
    AppContainerFolderPathFromPfn = Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(
                                      v6,
                                      &pv);
    if ( AppContainerFolderPathFromPfn < 0 )
    {
      v8 = 1086;
      goto LABEL_13;
    }
    goto LABEL_29;
  }
  v2 = (WCHAR *)CoTaskMemAlloc(0x20Au);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  if ( !ExpandEnvironmentStringsW(L"%USERPROFILE%\\AppData\\Local\\Microsoft", v2, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x439,
             (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
             v5);
  pv = v3;
LABEL_37:
  *(_OWORD *)Src = 0;
  v139 = 0;
  v140 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v3[v22] );
  std::wstring::_Construct<1,unsigned short const *>(Src, v3);
  v23 = v139;
  v24 = v140;
  v25 = 0x7FFFFFFFFFFFFFFELL;
  if ( (char *)v140 != v139 )
  {
    v26 = ++v139;
    v27 = Src;
    if ( v140 > 7 )
      v27 = (void **)Src[0];
    *((_WORD *)v27 + (_QWORD)v23) = asc_1801369E8[0];
    *((_WORD *)v27 + (_QWORD)v26) = 0;
    goto LABEL_64;
  }
  if ( v139 == (char *)0x7FFFFFFFFFFFFFFELL )
    goto LABEL_269;
  v28 = v139 + 1;
  v29 = (unsigned __int64)(v139 + 1) | 7;
  if ( v29 > 0x7FFFFFFFFFFFFFFELL || (v30 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v29 = 0x7FFFFFFFFFFFFFFELL;
    v31 = -2;
LABEL_52:
    if ( v31 < 0x1000 )
    {
      v32 = operator new(v31);
    }
    else
    {
      if ( v31 + 39 < v31 )
        goto LABEL_268;
      v33 = operator new(v31 + 39);
      if ( !v33 )
        goto LABEL_243;
      v32 = (_QWORD *)(((unsigned __int64)v33 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v32 - 1) = v33;
    }
    goto LABEL_57;
  }
  if ( v29 < v140 + v30 )
    v29 = v140 + v30;
  if ( v29 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v31 = 2 * (v29 + 1);
  if ( v31 )
    goto LABEL_52;
  v32 = 0;
LABEL_57:
  v139 = v23 + 1;
  v140 = v29;
  v34 = 2LL * (_QWORD)v23;
  v35 = (_WORD *)v32 + (_QWORD)v23;
  if ( v24 <= 7 )
  {
    memcpy_0(v32, Src, v34);
    *v35 = asc_1801369E8[0];
    *((_WORD *)v32 + (_QWORD)v28) = 0;
  }
  else
  {
    v36 = Src[0];
    memcpy_0(v32, Src[0], v34);
    *v35 = asc_1801369E8[0];
    *((_WORD *)v32 + (_QWORD)v28) = 0;
    if ( 2 * v24 + 2 < 0x1000 )
    {
      operator delete(v36);
    }
    else
    {
      v37 = (_BYTE *)*((_QWORD *)v36 - 1);
      if ( (unsigned __int64)((_BYTE *)v36 - v37 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v37);
    }
  }
  Src[0] = v32;
LABEL_64:
  v38 = v139;
  v39 = v140;
  if ( v140 - (unsigned __int64)v139 >= 0xB )
  {
    v40 = v139 + 11;
    v139 += 11;
    v41 = Src;
    if ( v140 > 7 )
      v41 = (void **)Src[0];
    memmove_0((char *)v41 + 2 * (_QWORD)v38, L"TokenBroker", 0x16u);
    *((_WORD *)v41 + (_QWORD)v40) = 0;
    v42 = Src[0];
    goto LABEL_89;
  }
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v139) < 0xB )
    goto LABEL_269;
  v43 = v139 + 11;
  v44 = (unsigned __int64)(v139 + 11) | 7;
  if ( v44 > 0x7FFFFFFFFFFFFFFELL || (v45 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v44 = 0x7FFFFFFFFFFFFFFELL;
    v46 = -2;
LABEL_77:
    if ( v46 < 0x1000 )
    {
      v42 = operator new(v46);
    }
    else
    {
      if ( v46 + 39 < v46 )
        goto LABEL_268;
      v47 = operator new(v46 + 39);
      if ( !v47 )
        goto LABEL_243;
      v42 = (_QWORD *)(((unsigned __int64)v47 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v42 - 1) = v47;
    }
    goto LABEL_82;
  }
  if ( v44 < v140 + v45 )
    v44 = v140 + v45;
  if ( v44 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v46 = 2 * (v44 + 1);
  if ( v46 )
    goto LABEL_77;
  v42 = 0;
LABEL_82:
  v139 = v38 + 11;
  v140 = v44;
  v48 = 2LL * (_QWORD)v38;
  v49 = (char *)v42 + 2 * (_QWORD)v38;
  if ( v39 <= 7 )
  {
    memcpy_0(v42, Src, v48);
    *(_OWORD *)v49 = *(_OWORD *)L"TokenBroker";
    *(_QWORD *)(v49 + 14) = *(_QWORD *)L"oker";
    *((_WORD *)v42 + (_QWORD)v43) = 0;
  }
  else
  {
    v50 = Src[0];
    memcpy_0(v42, Src[0], v48);
    *(_OWORD *)v49 = *(_OWORD *)L"TokenBroker";
    *(_QWORD *)(v49 + 14) = *(_QWORD *)L"oker";
    *((_WORD *)v42 + (_QWORD)v43) = 0;
    if ( 2 * v39 + 2 < 0x1000 )
    {
      operator delete(v50);
    }
    else
    {
      v51 = (_BYTE *)*((_QWORD *)v50 - 1);
      if ( (unsigned __int64)((_BYTE *)v50 - v51 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v51);
    }
  }
  Src[0] = v42;
LABEL_89:
  if ( v140 <= 7 )
  {
    v42 = Src;
  }
  else if ( !v42 )
  {
    AppContainerFolderPathFromPfn = -2147467261;
LABEL_94:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x458,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)AppContainerFolderPathFromPfn,
      v133);
    if ( v140 <= 7 )
      goto LABEL_100;
    if ( 2 * v140 + 2 < 0x1000 )
    {
      v52 = Src[0];
LABEL_99:
      operator delete(v52);
LABEL_100:
      v139 = 0;
      v140 = 7;
      LOWORD(Src[0]) = 0;
      if ( v3 )
        goto LABEL_261;
      return (unsigned int)AppContainerFolderPathFromPfn;
    }
    v52 = (void *)*((_QWORD *)Src[0] - 1);
    if ( (unsigned __int64)((char *)Src[0] - (char *)v52 - 8) <= 0x1F )
      goto LABEL_99;
LABEL_267:
    __fastfail(5u);
  }
  AppContainerFolderPathFromPfn = Windows::Internal::String::_InitializeHelper(
                                    (Windows::Internal::String *)(v136 + 12),
                                    (const unsigned __int16 *)v42);
  if ( AppContainerFolderPathFromPfn < 0 )
    goto LABEL_94;
  v53 = v139;
  v54 = v140;
  if ( (char *)v140 != v139 )
  {
    v55 = ++v139;
    v56 = Src;
    if ( v140 > 7 )
      v56 = (void **)Src[0];
    *((_WORD *)v56 + (_QWORD)v53) = asc_1801369E8[0];
    *((_WORD *)v56 + (_QWORD)v55) = 0;
    goto LABEL_127;
  }
  if ( v139 == (char *)0x7FFFFFFFFFFFFFFELL )
    goto LABEL_269;
  v57 = v139 + 1;
  v58 = (unsigned __int64)(v139 + 1) | 7;
  if ( v58 > 0x7FFFFFFFFFFFFFFELL || (v59 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v58 = 0x7FFFFFFFFFFFFFFELL;
    v60 = -2;
LABEL_115:
    if ( v60 < 0x1000 )
    {
      v61 = operator new(v60);
    }
    else
    {
      if ( v60 + 39 < v60 )
        goto LABEL_268;
      v62 = operator new(v60 + 39);
      if ( !v62 )
        goto LABEL_243;
      v61 = (_QWORD *)(((unsigned __int64)v62 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v61 - 1) = v62;
    }
    goto LABEL_120;
  }
  if ( v58 < v140 + v59 )
    v58 = v140 + v59;
  if ( v58 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v60 = 2 * (v58 + 1);
  if ( v60 )
    goto LABEL_115;
  v61 = 0;
LABEL_120:
  v139 = v53 + 1;
  v140 = v58;
  v63 = 2LL * (_QWORD)v53;
  v64 = (_WORD *)v61 + (_QWORD)v53;
  if ( v54 <= 7 )
  {
    memcpy_0(v61, Src, v63);
    *v64 = asc_1801369E8[0];
    *((_WORD *)v61 + (_QWORD)v57) = 0;
  }
  else
  {
    v65 = Src[0];
    memcpy_0(v61, Src[0], v63);
    *v64 = asc_1801369E8[0];
    *((_WORD *)v61 + (_QWORD)v57) = 0;
    if ( 2 * v54 + 2 < 0x1000 )
    {
      operator delete(v65);
    }
    else
    {
      v66 = (_BYTE *)*((_QWORD *)v65 - 1);
      if ( (unsigned __int64)((_BYTE *)v65 - v66 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v66);
    }
  }
  Src[0] = v61;
LABEL_127:
  v67 = (_WORD *)*((_QWORD *)v136 + 1);
  v68 = -1;
  do
    ++v68;
  while ( v67[v68] );
  v69 = v139;
  v135 = v139;
  v70 = v140;
  if ( v68 <= v140 - (unsigned __int64)v139 )
  {
    v71 = &v139[v68];
    v139 += v68;
    v72 = Src;
    if ( v140 > 7 )
      v72 = (void **)Src[0];
    memmove_0((char *)v72 + 2 * (_QWORD)v69, v67, 2 * v68);
    *((_WORD *)v72 + (_QWORD)v71) = 0;
    v73 = Src[0];
    goto LABEL_154;
  }
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v139 < v68 )
    goto LABEL_269;
  *(_QWORD *)result = &v139[v68];
  v74 = (unsigned __int64)&v139[v68] | 7;
  if ( v74 > 0x7FFFFFFFFFFFFFFELL || (v75 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v74 = 0x7FFFFFFFFFFFFFFELL;
    v76 = -2;
LABEL_142:
    if ( v76 < 0x1000 )
    {
      v73 = operator new(v76);
    }
    else
    {
      if ( v76 + 39 < v76 )
        goto LABEL_268;
      v77 = operator new(v76 + 39);
      if ( !v77 )
        goto LABEL_243;
      v73 = (_QWORD *)(((unsigned __int64)v77 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v73 - 1) = v77;
    }
    goto LABEL_147;
  }
  if ( v74 < v75 + v140 )
    v74 = v75 + v140;
  if ( v74 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v76 = 2 * (v74 + 1);
  if ( v76 )
    goto LABEL_142;
  v73 = 0;
LABEL_147:
  v139 = *(char **)result;
  v140 = v74;
  v78 = 2LL * (_QWORD)v135;
  v79 = 2 * v68;
  v80 = (char *)v73 + 2 * (_QWORD)v135;
  v135 = v80;
  if ( v70 <= 7 )
  {
    memcpy_0(v73, Src, v78);
    memcpy_0(v80, v67, v79);
    *((_WORD *)v73 + *(_QWORD *)result) = 0;
  }
  else
  {
    v81 = Src[0];
    memcpy_0(v73, Src[0], v78);
    memcpy_0(v135, v67, v79);
    *((_WORD *)v73 + *(_QWORD *)result) = 0;
    if ( 2 * v70 + 2 < 0x1000 )
    {
      operator delete(v81);
    }
    else
    {
      v82 = (_BYTE *)*((_QWORD *)v81 - 1);
      if ( (unsigned __int64)((_BYTE *)v81 - v82 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v82);
    }
  }
  Src[0] = v73;
LABEL_154:
  if ( v140 <= 7 )
  {
    v73 = Src;
  }
  else if ( !v73 )
  {
    AppContainerFolderPathFromPfn = -2147467261;
LABEL_159:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)AppContainerFolderPathFromPfn,
      v133);
    goto LABEL_160;
  }
  AppContainerFolderPathFromPfn = Windows::Internal::String::_InitializeHelper(
                                    (Windows::Internal::String *)(v136 + 16),
                                    (const unsigned __int16 *)v73);
  if ( AppContainerFolderPathFromPfn < 0 )
    goto LABEL_159;
  v84 = v139;
  v85 = v140;
  if ( (char *)v140 != v139 )
  {
    ++v139;
    v86 = Src;
    if ( v140 > 7 )
      v86 = (void **)Src[0];
    *((_WORD *)v86 + (_QWORD)v84) = asc_1801369E8[0];
    *((_WORD *)v86 + (_QWORD)(v84 + 1)) = 0;
    goto LABEL_193;
  }
  if ( v139 == (char *)0x7FFFFFFFFFFFFFFELL )
    goto LABEL_269;
  v87 = v139 + 1;
  v88 = (unsigned __int64)(v139 + 1) | 7;
  if ( v88 > 0x7FFFFFFFFFFFFFFELL || (v89 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v88 = 0x7FFFFFFFFFFFFFFELL;
    v90 = -2;
LABEL_181:
    if ( v90 < 0x1000 )
    {
      v91 = operator new(v90);
    }
    else
    {
      if ( v90 + 39 < v90 )
        goto LABEL_268;
      v92 = operator new(v90 + 39);
      if ( !v92 )
        goto LABEL_243;
      v91 = (_QWORD *)(((unsigned __int64)v92 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v91 - 1) = v92;
    }
    goto LABEL_186;
  }
  if ( v88 < v89 + v140 )
    v88 = v89 + v140;
  if ( v88 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v90 = 2 * (v88 + 1);
  if ( v90 )
    goto LABEL_181;
  v91 = 0;
LABEL_186:
  v139 = v84 + 1;
  v140 = v88;
  v93 = 2LL * (_QWORD)v84;
  v94 = (_WORD *)v91 + (_QWORD)v84;
  if ( v85 <= 7 )
  {
    memcpy_0(v91, Src, v93);
    *v94 = asc_1801369E8[0];
    *((_WORD *)v91 + (_QWORD)v87) = 0;
  }
  else
  {
    v95 = Src[0];
    memcpy_0(v91, Src[0], v93);
    *v94 = asc_1801369E8[0];
    *((_WORD *)v91 + (_QWORD)v87) = 0;
    if ( 2 * v85 + 2 < 0x1000 )
    {
      operator delete(v95);
    }
    else
    {
      v96 = (_BYTE *)*((_QWORD *)v95 - 1);
      if ( (unsigned __int64)((_BYTE *)v95 - v96 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v96);
    }
  }
  Src[0] = v91;
LABEL_193:
  v97 = WindowsGetStringRawBuffer(*((HSTRING *)v136 + 8), 0);
  v98 = v97;
  v99 = -1;
  do
    ++v99;
  while ( v97[v99] );
  v100 = v139;
  v101 = v140;
  *(_QWORD *)result = v140;
  if ( v99 <= v140 - (unsigned __int64)v139 )
  {
    v102 = &v139[v99];
    v139 += v99;
    v103 = Src;
    if ( v140 > 7 )
      v103 = (void **)Src[0];
    memmove_0((char *)v103 + 2 * (_QWORD)v100, v97, 2 * v99);
    *((_WORD *)v103 + (_QWORD)v102) = 0;
    goto LABEL_221;
  }
  if ( 0x7FFFFFFFFFFFFFFELL - (__int64)v139 < v99 )
    goto LABEL_269;
  v135 = &v139[v99];
  v104 = (unsigned __int64)&v139[v99] | 7;
  if ( v104 > 0x7FFFFFFFFFFFFFFELL || (v105 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
  {
    v104 = 0x7FFFFFFFFFFFFFFELL;
    v106 = -2;
LABEL_208:
    if ( v106 < 0x1000 )
    {
      v107 = operator new(v106);
    }
    else
    {
      if ( v106 + 39 < v106 )
        goto LABEL_268;
      v108 = operator new(v106 + 39);
      if ( !v108 )
        goto LABEL_243;
      v107 = (_QWORD *)(((unsigned __int64)v108 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v107 - 1) = v108;
    }
    v101 = *(_QWORD *)result;
    goto LABEL_214;
  }
  if ( v104 < v105 + v140 )
    v104 = v105 + v140;
  if ( v104 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_268;
  v106 = 2 * (v104 + 1);
  if ( v106 )
    goto LABEL_208;
  v107 = 0;
LABEL_214:
  v139 = &v100[v99];
  v140 = v104;
  v109 = 2LL * (_QWORD)v100;
  v110 = 2 * v99;
  v111 = (char *)v107 + 2 * (_QWORD)v100;
  if ( v101 <= 7 )
  {
    memcpy_0(v107, Src, v109);
    memcpy_0(v111, v98, v110);
    *((_WORD *)v107 + (_QWORD)v135) = 0;
  }
  else
  {
    v112 = Src[0];
    memcpy_0(v107, Src[0], v109);
    memcpy_0(v111, v98, v110);
    *((_WORD *)v107 + (_QWORD)v135) = 0;
    if ( (unsigned __int64)(2LL * *(_QWORD *)result + 2) < 0x1000 )
    {
      operator delete(v112);
    }
    else
    {
      v113 = (_BYTE *)*((_QWORD *)v112 - 1);
      if ( (unsigned __int64)((_BYTE *)v112 - v113 - 8) > 0x1F )
        goto LABEL_243;
      operator delete(v113);
    }
  }
  Src[0] = v107;
LABEL_221:
  v114 = v139;
  v115 = v140;
  if ( (char *)v140 == v139 )
  {
    if ( v139 != (char *)0x7FFFFFFFFFFFFFFELL )
    {
      v117 = v139 + 1;
      v118 = (unsigned __int64)(v139 + 1) | 7;
      if ( v118 > 0x7FFFFFFFFFFFFFFELL || (v119 = v140 >> 1, v140 > 0x7FFFFFFFFFFFFFFELL - (v140 >> 1)) )
      {
        v120 = -2;
      }
      else
      {
        v25 = (unsigned __int64)(v139 + 1) | 7;
        if ( v118 < v119 + v140 )
          v25 = v119 + v140;
        if ( (unsigned __int64)(v25 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_268;
        v120 = 2 * (v25 + 1);
        if ( !v120 )
        {
          v121 = 0;
          goto LABEL_239;
        }
      }
      if ( v120 < 0x1000 )
      {
        v121 = operator new(v120);
        goto LABEL_239;
      }
      if ( v120 + 39 >= v120 )
      {
        v122 = operator new(v120 + 39);
        if ( !v122 )
          goto LABEL_243;
        v121 = (_QWORD *)(((unsigned __int64)v122 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v121 - 1) = v122;
LABEL_239:
        v139 = v114 + 1;
        v140 = v25;
        v123 = 2LL * (_QWORD)v114;
        v124 = (_WORD *)v121 + (_QWORD)v114;
        if ( v115 <= 7 )
        {
          memcpy_0(v121, Src, v123);
          *v124 = asc_1801414BC[0];
          *((_WORD *)v121 + (_QWORD)v117) = 0;
          goto LABEL_246;
        }
        v125 = Src[0];
        memcpy_0(v121, Src[0], v123);
        *v124 = asc_1801414BC[0];
        *((_WORD *)v121 + (_QWORD)v117) = 0;
        if ( 2 * v115 + 2 < 0x1000 )
        {
          operator delete(v125);
          goto LABEL_246;
        }
        v126 = (void *)*((_QWORD *)v125 - 1);
        if ( (unsigned __int64)((_BYTE *)v125 - (_BYTE *)v126 - 8) <= 0x1F )
        {
          operator delete(v126);
LABEL_246:
          Src[0] = v121;
          goto LABEL_247;
        }
LABEL_243:
        __fastfail(5u);
      }
LABEL_268:
      std::_Throw_bad_array_new_length();
    }
LABEL_269:
    std::_Xlen_string();
  }
  ++v139;
  v116 = Src;
  if ( v140 > 7 )
    v116 = (void **)Src[0];
  *((_WORD *)v116 + (_QWORD)v114) = asc_1801414BC[0];
  *((_WORD *)v116 + (_QWORD)(v114 + 1)) = 0;
LABEL_247:
  v127 = v136;
  v128 = -1;
  do
    ++v128;
  while ( *(_WORD *)(*((_QWORD *)v136 + 2) + 2 * v128) );
  std::wstring::_Append<unsigned short>(Src);
  if ( v140 <= 7 )
  {
    v129 = Src;
  }
  else
  {
    v129 = (void **)Src[0];
    if ( !Src[0] )
    {
      AppContainerFolderPathFromPfn = -2147467261;
      goto LABEL_254;
    }
  }
  AppContainerFolderPathFromPfn = Windows::Internal::String::_InitializeHelper(
                                    (Windows::Internal::String *)(v127 + 20),
                                    (const unsigned __int16 *)v129);
  if ( AppContainerFolderPathFromPfn >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_180175000 > 4 )
      {
        result[0] = *((unsigned __int8 *)v127 + 100);
        v135 = (void *)WindowsGetStringRawBuffer(*((HSTRING *)v127 + 5), 0);
        v136 = WindowsGetStringRawBuffer(*((HSTRING *)v127 + 4), 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          &dword_180175000,
          byte_180159AF5,
          0);
      }
    }
    else if ( (unsigned int)dword_180175000 > 4 )
    {
      v135 = (void *)WindowsGetStringRawBuffer(*((HSTRING *)v127 + 5), 0);
      v136 = WindowsGetStringRawBuffer(*((HSTRING *)v127 + 4), 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        &dword_180175000,
        &word_180159AA6,
        0);
    }
LABEL_160:
    if ( v140 > 7 )
    {
      if ( 2 * v140 + 2 < 0x1000 )
      {
        v83 = Src[0];
      }
      else
      {
        v83 = (void *)*((_QWORD *)Src[0] - 1);
        if ( (unsigned __int64)((char *)Src[0] - (char *)v83 - 8) > 0x1F )
          goto LABEL_267;
      }
      operator delete(v83);
    }
    v139 = 0;
    v140 = 7;
    LOWORD(Src[0]) = 0;
    if ( v3 )
      goto LABEL_261;
    return (unsigned int)AppContainerFolderPathFromPfn;
  }
LABEL_254:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x462,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)(unsigned int)AppContainerFolderPathFromPfn,
    v133);
  if ( v140 > 7 )
  {
    if ( 2 * v140 + 2 < 0x1000 )
    {
      v130 = Src[0];
    }
    else
    {
      v130 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v130 - 8) > 0x1F )
        goto LABEL_267;
    }
    operator delete(v130);
  }
  v139 = 0;
  v140 = 7;
  LOWORD(Src[0]) = 0;
  if ( !v3 )
    return (unsigned int)AppContainerFolderPathFromPfn;
LABEL_261:
  CoTaskMemFree(v3);
  return (unsigned int)AppContainerFolderPathFromPfn;
}

```

## disassembly

```asm
0x1800750c0  push    rbp
0x1800750c2  push    rbx
0x1800750c3  push    rsi
0x1800750c4  push    rdi
0x1800750c5  push    r12
0x1800750c7  push    r13
0x1800750c9  push    r14
0x1800750cb  push    r15
0x1800750cd  lea     rbp, [rsp-1Fh]
0x1800750d2  sub     rsp, 0B8h
0x1800750d9  mov     rax, cs:__security_cookie
0x1800750e0  xor     rax, rsp
0x1800750e3  mov     [rbp+57h+var_50], rax
0x1800750e7  mov     rdi, rcx
0x1800750ea  mov     [rbp+57h+var_A0], rcx
0x1800750ee  xor     r13d, r13d
0x1800750f1  mov     [rbp+57h+pv], r13
0x1800750f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x1800750fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x180075101  lea     r9, [rbp+57h+string]; string
0x180075105  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180075109  mov     edx, 0Eh; length
0x18007510e  lea     rcx, aNoApplication; "NO_APPLICATION"
0x180075115  test    al, al
0x180075117  jz      loc_1800752D2
0x18007511d  call    cs:__imp_WindowsCreateStringReference
0x180075123  test    eax, eax
0x180075125  jns     short loc_18007513D
0x180075127  xor     r9d, r9d; lpArguments
0x18007512a  xor     r8d, r8d; nNumberOfArguments
0x18007512d  mov     edx, 1; dwExceptionFlags
0x180075132  mov     ecx, 0C000000Dh; dwExceptionCode
0x180075137  call    cs:__imp_RaiseException
0x18007513d  mov     [rbp+57h+result], r13d
0x180075141  lea     r8, [rbp+57h+result]; result
0x180075145  mov     rdx, [rbp+57h+string]; string2
0x180075149  mov     rcx, [rdi+48h]; string1
0x18007514d  call    cs:__imp_WindowsCompareStringOrdinal
0x180075153  cmp     [rbp+57h+result], 0
0x180075157  jz      loc_18007520F
0x18007515d  cmp     byte ptr [rdi+64h], 0
0x180075161  jz      short loc_1800751BE
0x180075163  mov     ecx, 20Ah; cb
0x180075168  call    cs:__imp_CoTaskMemAlloc
0x18007516e  mov     r14, rax
0x180075171  test    rax, rax
0x180075174  jnz     short loc_180075180
0x180075176  mov     eax, 8007000Eh
0x18007517b  jmp     loc_1800752A9
0x180075180  mov     r8d, 104h; nSize
0x180075186  mov     rdx, r14; lpDst
0x180075189  lea     rcx, aUserprofileApp; "%USERPROFILE%\\AppData\\Local\\Microsof"...
0x180075190  call    cs:__imp_ExpandEnvironmentStringsW
0x180075196  test    eax, eax
0x180075198  jnz     short loc_1800751B5
0x18007519a  mov     rcx, [rbp+5Fh]; this
0x18007519e  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800751a5  mov     edx, 439h; void *
0x1800751aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800751af  nop
0x1800751b0  jmp     loc_1800752A9
0x1800751b5  mov     [rbp+57h+pv], r14
0x1800751b9  jmp     loc_1800753DA
0x1800751be  xor     edx, edx; length
0x1800751c0  mov     rcx, [rdi+48h]; string
0x1800751c4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800751ca  lea     rdx, [rbp+57h+pv]
0x1800751ce  mov     rcx, rax
0x1800751d1  call    ?GetAppContainerFolderPathFromPfn@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEBGAEAV?$unique_ptr@PEAXUCoTaskMemFreeDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(ushort const *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::CoTaskMemFreeDeleter> &)
0x1800751d6  mov     ebx, eax
0x1800751d8  test    eax, eax
0x1800751da  jns     loc_180075336
0x1800751e0  mov     edx, 43Eh; void *
0x1800751e5  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800751ec  mov     r9d, ebx; char *
0x1800751ef  mov     rcx, [rbp+5Fh]; this
0x1800751f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800751f8  nop
0x1800751f9  mov     rcx, [rbp+57h+pv]; pv
0x1800751fd  test    rcx, rcx
0x180075200  jz      short loc_180075208
0x180075202  call    cs:__imp_CoTaskMemFree
0x180075208  mov     eax, ebx
0x18007520a  jmp     loc_1800752A9
0x18007520f  mov     ecx, 20Ah; cb
0x180075214  call    cs:__imp_CoTaskMemAlloc
0x18007521a  mov     r14, rax
0x18007521d  test    rax, rax
0x180075220  jnz     short loc_180075229
0x180075222  mov     edi, 8007000Eh
0x180075227  jmp     short loc_18007528E
0x180075229  mov     [rbp+57h+var_A8], r14
0x18007522d  mov     edx, cs:_tls_index; void *
0x180075233  mov     rax, gs:58h
0x18007523c  mov     ecx, 8
0x180075241  mov     rax, [rax+rdx*8]
0x180075245  lea     rdi, qword_180176B70
0x18007524c  mov     eax, [rcx+rax]
0x18007524f  cmp     cs:dword_180176B60, eax
0x180075255  jg      loc_180076239
0x18007525b  mov     r9, r14; unsigned __int16 *
0x18007525e  mov     rcx, rdi; this
0x180075261  call    ?GetExpandedEnvironmentStringForUser@EnvironmentStringCache@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAXPEBGPEAGK@Z; Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetExpandedEnvironmentStringForUser(void *,ushort const *,ushort *,ulong)
0x180075266  mov     edi, eax
0x180075268  test    eax, eax
0x18007526a  jns     short loc_1800752C9
0x18007526c  mov     rcx, [rbp+5Fh]; this
0x180075270  mov     r9d, eax; char *
0x180075273  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007527a  mov     edx, 9Bh; void *
0x18007527f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075284  nop
0x180075285  mov     rcx, r14; pv
0x180075288  call    cs:__imp_CoTaskMemFree
0x18007528e  mov     rcx, [rbp+5Fh]; this
0x180075292  mov     r9d, edi; char *
0x180075295  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18007529c  mov     edx, 443h; void *
0x1800752a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800752a6  nop
0x1800752a7  mov     eax, edi
0x1800752a9  mov     rcx, [rbp+57h+var_50]
0x1800752ad  xor     rcx, rsp; StackCookie
0x1800752b0  call    __security_check_cookie
0x1800752b5  add     rsp, 0B8h
0x1800752bc  pop     r15
0x1800752be  pop     r14
0x1800752c0  pop     r13
0x1800752c2  pop     r12
0x1800752c4  pop     rdi
0x1800752c5  pop     rsi
0x1800752c6  pop     rbx
0x1800752c7  pop     rbp
0x1800752c8  retn
0x1800752c9  mov     [rbp+57h+pv], r14
0x1800752cd  jmp     loc_1800753DA
0x1800752d2  call    cs:__imp_WindowsCreateStringReference
0x1800752d8  test    eax, eax
0x1800752da  jns     short loc_1800752F2
0x1800752dc  xor     r9d, r9d; lpArguments
0x1800752df  xor     r8d, r8d; nNumberOfArguments
0x1800752e2  mov     edx, 1; dwExceptionFlags
0x1800752e7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800752ec  call    cs:__imp_RaiseException
0x1800752f2  mov     [rbp+57h+result], r13d
0x1800752f6  lea     r8, [rbp+57h+result]; result
0x1800752fa  mov     rdx, [rbp+57h+string]; string2
0x1800752fe  mov     rcx, [rdi+48h]; string1
0x180075302  call    cs:__imp_WindowsCompareStringOrdinal
0x180075308  cmp     [rbp+57h+result], 0
0x18007530c  jz      short loc_18007533F
0x18007530e  xor     edx, edx; length
0x180075310  mov     rcx, [rdi+48h]; string
0x180075314  call    cs:__imp_WindowsGetStringRawBuffer
0x18007531a  lea     rdx, [rbp+57h+pv]
0x18007531e  mov     rcx, rax
0x180075321  call    ?GetAppContainerFolderPathFromPfn@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEBGAEAV?$unique_ptr@PEAXUCoTaskMemFreeDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetAppContainerFolderPathFromPfn(ushort const *,std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::CoTaskMemFreeDeleter> &)
0x180075326  mov     ebx, eax
0x180075328  test    eax, eax
0x18007532a  jns     short loc_180075336
0x18007532c  mov     edx, 44Bh
0x180075331  jmp     loc_1800751E5
0x180075336  mov     r14, [rbp+57h+pv]
0x18007533a  jmp     loc_1800753DA
0x18007533f  mov     ecx, 20Ah; cb
0x180075344  call    cs:__imp_CoTaskMemAlloc
0x18007534a  mov     r14, rax
0x18007534d  test    rax, rax
0x180075350  jnz     short loc_180075359
0x180075352  mov     edi, 8007000Eh
0x180075357  jmp     short loc_1800753BE
0x180075359  mov     [rbp+57h+var_A8], r14
0x18007535d  mov     edx, cs:_tls_index; void *
0x180075363  mov     rax, gs:58h
0x18007536c  mov     ecx, 8
0x180075371  mov     rax, [rax+rdx*8]
0x180075375  lea     rdi, qword_180176B70
0x18007537c  mov     eax, [rcx+rax]
0x18007537f  cmp     cs:dword_180176B60, eax
0x180075385  jg      loc_1800762A9
0x18007538b  mov     r9, r14; unsigned __int16 *
0x18007538e  mov     rcx, rdi; this
0x180075391  call    ?GetExpandedEnvironmentStringForUser@EnvironmentStringCache@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEAXPEBGPEAGK@Z; Windows::Internal::Security::Authentication::TokenBroker::EnvironmentStringCache::GetExpandedEnvironmentStringForUser(void *,ushort const *,ushort *,ulong)
0x180075396  mov     edi, eax
0x180075398  test    eax, eax
0x18007539a  jns     short loc_1800753D6
0x18007539c  mov     rcx, [rbp+5Fh]; this
0x1800753a0  mov     r9d, eax; char *
0x1800753a3  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800753aa  mov     edx, 9Bh; void *
0x1800753af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800753b4  nop
0x1800753b5  mov     rcx, r14; pv
0x1800753b8  call    cs:__imp_CoTaskMemFree
0x1800753be  mov     rcx, [rbp+5Fh]
0x1800753c2  mov     r9d, edi
0x1800753c5  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x1800753cc  mov     edx, 44Fh
0x1800753d1  jmp     loc_1800752A1
0x1800753d6  mov     [rbp+57h+pv], r14
0x1800753da  xorps   xmm0, xmm0
0x1800753dd  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800753e1  mov     [rbp+57h+var_80], r13
0x1800753e5  mov     [rbp+57h+var_78], r13
0x1800753e9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800753f0  inc     r8
0x1800753f3  cmp     word ptr [r14+r8*2], 0
0x1800753f9  jnz     short loc_1800753F0
0x1800753fb  mov     rdx, r14
0x1800753fe  lea     rcx, [rbp+57h+Src]
0x180075402  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180075407  nop
0x180075408  mov     r12, [rbp+57h+var_80]
0x18007540c  mov     r15, [rbp+57h+var_78]
0x180075410  mov     rax, r15
0x180075413  sub     rax, r12
0x180075416  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180075420  mov     r8, 0FFFFFFFFFFFFFFFEh
0x180075427  mov     r9, 7FFFFFFFFFFFFFFFh
0x180075431  cmp     rax, 1
0x180075435  jb      short loc_180075462
0x180075437  lea     rdx, [r12+1]
0x18007543c  mov     [rbp+57h+var_80], rdx
0x180075440  lea     rcx, [rbp+57h+Src]
0x180075444  cmp     r15, 7
0x180075448  cmova   rcx, [rbp+57h+Src]
0x18007544d  mov     eax, dword ptr cs:asc_1801369E8; "\\"
0x180075453  mov     [rcx+r12*2], ax
0x180075458  mov     [rcx+rdx*2], r13w
0x18007545d  jmp     loc_18007559D
0x180075462  mov     rax, rsi
0x180075465  sub     rax, r12
0x180075468  cmp     rax, 1
0x18007546c  jb      loc_180076233
0x180075472  lea     r13, [r12+1]
0x180075477  mov     rdi, r13
0x18007547a  or      rdi, 7
0x18007547e  cmp     rdi, rsi
0x180075481  ja      short loc_1800754B5
0x180075483  mov     rcx, r15
0x180075486  shr     rcx, 1
0x180075489  mov     rax, rsi
0x18007548c  sub     rax, rcx
0x18007548f  cmp     r15, rax
0x180075492  ja      short loc_1800754B5
0x180075494  lea     rax, [r15+rcx]
0x180075498  cmp     rdi, rax
0x18007549b  cmovb   rdi, rax
0x18007549f  lea     rcx, [rdi+1]
0x1800754a3  cmp     rcx, r9
0x1800754a6  ja      loc_18007622D
0x1800754ac  add     rcx, rcx
0x1800754af  jnz     short loc_1800754BB
0x1800754b1  xor     ebx, ebx
0x1800754b3  jmp     short loc_1800754F8
0x1800754b5  mov     rdi, rsi
0x1800754b8  mov     rcx, r8; Size
0x1800754bb  cmp     rcx, 1000h
0x1800754c2  jb      short loc_1800754F0
0x1800754c4  lea     rax, [rcx+27h]
0x1800754c8  cmp     rax, rcx
0x1800754cb  jbe     loc_18007622D
0x1800754d1  mov     rcx, rax; Size
0x1800754d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800754d9  test    rax, rax
0x1800754dc  jz      loc_180076049
0x1800754e2  lea     rbx, [rax+27h]
0x1800754e6  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1800754ea  mov     [rbx-8], rax
0x1800754ee  jmp     short loc_1800754F8
0x1800754f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800754f5  mov     rbx, rax
0x1800754f8  mov     [rbp+57h+var_80], r13
0x1800754fc  mov     [rbp+57h+var_78], rdi
0x180075500  lea     r8, [r12+r12]; Size
0x180075504  lea     r12, [rbx+r8]
0x180075508  mov     rcx, rbx; void *
0x18007550b  cmp     r15, 7
0x18007550f  jbe     short loc_18007556A
0x180075511  mov     rdi, [rbp+57h+Src]
0x180075515  mov     rdx, rdi; Src
0x180075518  call    memcpy_0
0x18007551d  mov     eax, dword ptr cs:asc_1801369E8; "\\"
0x180075523  mov     [r12], ax
0x180075528  xor     eax, eax
0x18007552a  mov     [rbx+r13*2], ax
0x18007552f  lea     rdx, ds:2[r15*2]
0x180075537  cmp     rdx, 1000h
0x18007553e  jb      short loc_180075560
0x180075540  mov     rcx, [rdi-8]; Block
0x180075544  sub     rdi, rcx
0x180075547  sub     rdi, 8
0x18007554b  cmp     rdi, 1Fh
0x18007554f  ja      loc_180076049
0x180075555  add     rdx, 27h ; '''
0x180075559  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007555e  jmp     short loc_180075585
0x180075560  mov     rcx, rdi; Block
0x180075563  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180075568  jmp     short loc_180075585
  ... truncated ...
```
