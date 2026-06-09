# _GetProviderIdForAvailableWebAuthBridgeInternet

- ea: `0x18001fab0`
- end: `0x18001fe0f`
- name: `_GetProviderIdForAvailableWebAuthBridgeInternet`
- size: `863`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *pWebAuthRequest, const wchar_t **providerId, void **handle, HSTRING__ **regValue)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fe18`

## callees

- `0x1800045c0`
- `0x1800060b8`
- `0x1800060f8`
- `0x180006650`
- `0x1800066d4`
- `0x180007a68`
- `0x18000a28c`
- `0x18000d3c0`
- `0x18000ed64`
- `0x18000f544`
- `0x1800159f4`
- `0x180016924`
- `0x18001fab0`
- `0x1800201b0`
- `0x180020354`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001fd61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001fd61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001fbf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001fbf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fd3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fd3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fcf5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fcf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbc1`

## string_xrefs

- `0x18001fb38`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x18001fc54`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x18001fc93`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x18001fd0b`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`
- `0x18001fd74`: `onecore\ds\security\webauth\authbroker\lib\wab2wambridge.cpp`

## pseudocode

```c
__int64 __fastcall GetProviderIdForAvailableWebAuthBridgeInternet(
        Windows::Security::Authentication::Web::CWebAuthOperation *pWebAuthRequest,
        const wchar_t **providerId,
        void **handle,
        HSTRING__ **regValue)
{
  bool v4; // al
  int v5; // esi
  int v6; // ebx
  HRESULT v11; // eax
  unsigned int v12; // edi
  _AUTH_BROKER_CLIENT_CONTEXT *m_ClientContext; // rdx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *v15; // rbx
  wchar_t *m_ptr; // rdi
  wchar_t *v17; // r14
  const wchar_t *const *v18; // rdi
  HRESULT v19; // eax
  unsigned int v20; // r9d
  unsigned int LastError; // ebx
  LSTATUS Key; // eax
  unsigned int v23; // edx
  Microsoft::WRL::Details::Dummy v24; // r8
  __int64 v25; // rax
  int v26; // eax
  _SECURITY_ATTRIBUTES *dwFlags; // [rsp+20h] [rbp-E0h]
  bool *samDesired; // [rsp+28h] [rbp-D8h]
  bool isAvailable; // [rsp+50h] [rbp-B0h] BYREF
  wil::unique_any_t<wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > localMutex; // [rsp+58h] [rbp-A8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hKey; // [rsp+60h] [rbp-A0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > packageName; // [rsp+68h] [rbp-98h] BYREF
  _SYSTEMTIME systemTime; // [rsp+70h] [rbp-90h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v34; // [rsp+80h] [rbp-80h] BYREF
  wchar_t mutexName[160]; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+238h] [rbp+138h]

  *handle = 0;
  v4 = 0;
  v5 = -1;
  *regValue = 0;
  *providerId = 0;
  v6 = 0;
  isAvailable = 0;
  while ( v6 < 3 )
  {
    if ( v4 )
      goto LABEL_10;
    v11 = IsMutexAvailable(v6, &isAvailable);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xD0u,
        "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
        v11);
      return v12;
    }
    v4 = isAvailable;
    if ( isAvailable )
      v5 = v6;
    ++v6;
  }
  if ( v4 )
  {
LABEL_10:
    m_ClientContext = pWebAuthRequest->m_ClientContext;
    packageName.m_ptr = 0;
    if ( (int)GetAuthBrokerClientAppContainerStringInfo(2, m_ClientContext->tokenHandle, &packageName.m_ptr) < 0 )
    {
      v15 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&localMutex,
              &source,
              0xFFFFFFFFFFFFFFFFuLL);
      if ( &packageName != v15 )
      {
        m_ptr = packageName.m_ptr;
        v17 = v15->m_ptr;
        if ( packageName.m_ptr )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&hKey);
          LocalFree(m_ptr);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&hKey);
        }
        packageName.m_ptr = v17;
        v15->m_ptr = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&localMutex);
    }
    systemTime = 0;
    GetSystemTime(&systemTime);
    v18 = &s_WAB2WAMBridgeInternetNamedMutex[v5];
    samDesired = (bool *)packageName.m_ptr;
    dwFlags = (_SECURITY_ATTRIBUTES *)*v18;
    v19 = StringCchPrintfW(mutexName, 0x9Cu, L"%s\\%s.%s:%u:%u", L"Local");
    LastError = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xF0u,
        "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
        v19);
LABEL_30:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&packageName);
      return LastError;
    }
    localMutex.m_ptr = 0;
    if ( !_try_create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &localMutex,
            mutexName,
            1u,
            v20,
            dwFlags,
            samDesired) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    0xF4u,
                    "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp");
LABEL_29:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&localMutex);
      goto LABEL_30;
    }
    if ( GetLastError() != 183 )
    {
      hKey.m_ptr = 0;
      Key = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\WebAuthBridge\\Internet",
              0,
              0,
              1u,
              0xF003Fu,
              0,
              &hKey.m_ptr,
              0);
      if ( Key )
      {
        v23 = 258;
LABEL_23:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      v23,
                      "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
                      Key);
LABEL_28:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_29;
      }
      Key = RegSetValueExW(hKey.m_ptr, *v18, 0, 1u, (const BYTE *)mutexName, 0x138u);
      if ( Key )
      {
        v23 = 265;
        goto LABEL_23;
      }
      Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, &s_WAB2WAMBridgeInternetNamedMutex[v5], v24);
      v26 = WindowsDuplicateString(*(HSTRING *)(v25 + 24), regValue);
      LastError = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x10Bu,
          "onecore\\ds\\security\\webauth\\authbroker\\lib\\wab2wambridge.cpp",
          v26);
        goto LABEL_28;
      }
      *handle = localMutex.m_ptr;
      localMutex.m_ptr = 0;
      *providerId = s_WAB2WAMBridgeInternetProviderID[v5];
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&localMutex);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&packageName);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fab0  push    rbp
0x18001fab2  push    rbx
0x18001fab3  push    rsi
0x18001fab4  push    rdi
0x18001fab5  push    r12
0x18001fab7  push    r13
0x18001fab9  push    r14
0x18001fabb  push    r15
0x18001fabd  lea     rbp, [rsp-0F8h]
0x18001fac5  sub     rsp, 1F8h
0x18001facc  mov     rax, cs:__security_cookie
0x18001fad3  xor     rax, rsp
0x18001fad6  mov     [rbp+130h+var_50], rax
0x18001fadd  mov     qword ptr [handle], 0
0x18001fae4  xor     al, al
0x18001fae6  or      esi, 0FFFFFFFFh
0x18001fae9  mov     qword ptr [regValue], 0
0x18001faf0  mov     qword ptr [providerId], 0
0x18001faf7  xor     ebx, ebx
0x18001faf9  mov     [rsp+230h+isAvailable], al
0x18001fafd  mov     r13, regValue
0x18001fb00  mov     r12, handle
0x18001fb03  mov     r15, providerId
0x18001fb06  mov     r14, pWebAuthRequest
0x18001fb09  cmp     ebx, 3
0x18001fb0c  jge     short loc_18001FB53
0x18001fb0e  test    al, al
0x18001fb10  jnz     short loc_18001FB5B
0x18001fb12  lea     providerId, [rsp+230h+isAvailable]; isAvailable
0x18001fb17  mov     ecx, ebx; mutexIndex
0x18001fb19  call    _IsMutexAvailable
0x18001fb1e  mov     edi, eax
0x18001fb20  test    eax, eax
0x18001fb22  js      short loc_18001FB31
0x18001fb24  mov     al, [rsp+230h+isAvailable]
0x18001fb28  test    al, al
0x18001fb2a  cmovnz  esi, ebx
0x18001fb2d  inc     ebx
0x18001fb2f  jmp     short loc_18001FB09
0x18001fb31  mov     pWebAuthRequest, [rbp+138h]; callerReturnAddress
0x18001fb38  lea     handle, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18001fb3f  mov     r9d, edi; hr
0x18001fb42  mov     edx, 0D0h; lineNumber
0x18001fb47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb4c  mov     eax, edi
0x18001fb4e  jmp     loc_18001FDEC
0x18001fb53  test    al, al
0x18001fb55  jz      loc_18001FDEA
0x18001fb5b  mov     providerId, [r14+0F0h]
0x18001fb62  lea     handle, [rsp+230h+packageName]; string
0x18001fb67  mov     [rsp+230h+packageName.m_ptr], 0
0x18001fb70  mov     ecx, 2; infoType
0x18001fb75  mov     providerId, [providerId+20h]; clientTokenHandle
0x18001fb79  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x18001fb7e  xor     r14d, r14d
0x18001fb81  test    eax, eax
0x18001fb83  jns     short loc_18001FBE6
0x18001fb85  or      handle, 0FFFFFFFFFFFFFFFFh; length
0x18001fb89  lea     providerId, source; source
0x18001fb90  lea     pWebAuthRequest, [rsp+230h+localMutex]; result
0x18001fb95  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001fb9a  mov     rbx, rax
0x18001fb9d  lea     rax, [rsp+230h+packageName]
0x18001fba2  cmp     rax, rbx
0x18001fba5  jz      short loc_18001FBDC
0x18001fba7  mov     rdi, [rsp+230h+packageName.m_ptr]
0x18001fbac  mov     r14, [rbx]
0x18001fbaf  test    rdi, rdi
0x18001fbb2  jz      short loc_18001FBD1
0x18001fbb4  lea     pWebAuthRequest, [rsp+230h+hKey]; this
0x18001fbb9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fbbe  mov     pWebAuthRequest, rdi; hMem
0x18001fbc1  call    cs:__imp_LocalFree
0x18001fbc7  lea     pWebAuthRequest, [rsp+230h+hKey]; this
0x18001fbcc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fbd1  mov     [rsp+230h+packageName.m_ptr], r14
0x18001fbd6  xor     r14d, r14d
0x18001fbd9  mov     [rbx], r14
0x18001fbdc  lea     pWebAuthRequest, [rsp+230h+localMutex]; this
0x18001fbe1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fbe6  xorps   xmm0, xmm0
0x18001fbe9  lea     pWebAuthRequest, [rsp+230h+systemTime]; lpSystemTime
0x18001fbee  movups  xmmword ptr [rsp+230h+systemTime.wYear], xmm0
0x18001fbf3  call    cs:__imp_GetSystemTime
0x18001fbf9  movzx   ecx, [rsp+230h+systemTime.wSecond]
0x18001fbfe  lea     rax, s_WAB2WAMBridgeInternetNamedMutex
0x18001fc05  mov     providerId, [rsp+230h+packageName.m_ptr]
0x18001fc0a  lea     regValue, aLocal; "Local"
0x18001fc11  movsxd  rsi, esi
0x18001fc14  lea     handle, aSSSUU; "%s\\%s.%s:%u:%u"
0x18001fc1b  lea     rdi, [rax+rsi*8]
0x18001fc1f  movzx   eax, [rsp+230h+systemTime.wMilliseconds]
0x18001fc24  mov     dword ptr [rsp+230h+phkResult], eax
0x18001fc28  mov     rax, [rdi]
0x18001fc2b  mov     dword ptr [rsp+230h+lpSecurityAttributes], ecx
0x18001fc2f  lea     pWebAuthRequest, [rbp+130h+mutexName]; pszDest
0x18001fc33  mov     qword ptr [rsp+230h+samDesired], providerId; bool *
0x18001fc38  mov     edx, 9Ch; cchDest
0x18001fc3d  mov     [rsp+230h+dwFlags], rax; dwFlags
0x18001fc42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fc47  mov     ebx, eax
0x18001fc49  test    eax, eax
0x18001fc4b  jns     short loc_18001FC6D
0x18001fc4d  mov     pWebAuthRequest, [rbp+138h]; callerReturnAddress
0x18001fc54  lea     handle, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18001fc5b  mov     r9d, eax; hr
0x18001fc5e  mov     edx, 0F0h; lineNumber
0x18001fc63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc68  jmp     loc_18001FD9C
0x18001fc6d  mov     ebx, 1
0x18001fc72  mov     [rsp+230h+localMutex.m_ptr], r14
0x18001fc77  mov     r8d, ebx; dwFlags
0x18001fc7a  lea     providerId, [rbp+130h+mutexName]; name
0x18001fc7e  lea     pWebAuthRequest, [rsp+230h+localMutex]; this
0x18001fc83  call    ?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001fc88  test    al, al
0x18001fc8a  jnz     short loc_18001FCAB
0x18001fc8c  mov     pWebAuthRequest, [rbp+138h]; callerReturnAddress
0x18001fc93  lea     handle, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18001fc9a  mov     edx, 0F4h; lineNumber
0x18001fc9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fca4  mov     ebx, eax
0x18001fca6  jmp     loc_18001FD92
0x18001fcab  call    cs:__imp_GetLastError
0x18001fcb1  cmp     eax, 0B7h
0x18001fcb6  jz      loc_18001FDD6
0x18001fcbc  mov     [rsp+230h+lpdwDisposition], r14; lpdwDisposition
0x18001fcc1  lea     rax, [rsp+230h+hKey]
0x18001fcc6  mov     [rsp+230h+phkResult], rax; phkResult
0x18001fccb  lea     providerId, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001fcd2  mov     [rsp+230h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001fcd7  xor     r9d, r9d; lpClass
0x18001fcda  mov     [rsp+230h+samDesired], 0F003Fh; samDesired
0x18001fce2  xor     r8d, r8d; Reserved
0x18001fce5  mov     pWebAuthRequest, 0FFFFFFFF80000001h; hKey
0x18001fcec  mov     dword ptr [rsp+230h+dwFlags], ebx; dwOptions
0x18001fcf0  mov     [rsp+230h+hKey.m_ptr], r14
0x18001fcf5  call    cs:__imp_RegCreateKeyExW
0x18001fcfb  test    eax, eax
0x18001fcfd  jz      short loc_18001FD1E
0x18001fcff  mov     edx, 102h; lineNumber
0x18001fd04  mov     pWebAuthRequest, [rbp+138h]; callerReturnAddress
0x18001fd0b  lea     handle, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18001fd12  mov     r9d, eax; err
0x18001fd15  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fd1a  mov     ebx, eax
0x18001fd1c  jmp     short loc_18001FD88
0x18001fd1e  mov     providerId, [rdi]; lpValueName
0x18001fd21  lea     rax, [rbp+130h+mutexName]
0x18001fd25  mov     pWebAuthRequest, [rsp+230h+hKey.m_ptr]; hKey
0x18001fd2a  mov     r9d, ebx; dwType
0x18001fd2d  mov     [rsp+230h+samDesired], 138h; cbData
0x18001fd35  xor     r8d, r8d; Reserved
0x18001fd38  mov     [rsp+230h+dwFlags], rax; lpData
0x18001fd3d  call    cs:__imp_RegSetValueExW
0x18001fd43  test    eax, eax
0x18001fd45  jz      short loc_18001FD4E
0x18001fd47  mov     edx, 109h
0x18001fd4c  jmp     short loc_18001FD04
0x18001fd4e  mov     providerId, rdi; strRef
0x18001fd51  lea     pWebAuthRequest, [rbp+130h+var_1B0]; this
0x18001fd55  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001fd5a  mov     providerId, r13; newString
0x18001fd5d  mov     pWebAuthRequest, [rax+18h]; string
0x18001fd61  call    cs:__imp_WindowsDuplicateString
0x18001fd67  mov     ebx, eax
0x18001fd69  test    eax, eax
0x18001fd6b  jns     short loc_18001FDAA
0x18001fd6d  mov     pWebAuthRequest, [rbp+138h]; callerReturnAddress
0x18001fd74  lea     handle, aOnecoreDsSecur_0; "onecore\\ds\\security\\webauth\\authbro"...
0x18001fd7b  mov     r9d, eax; hr
0x18001fd7e  mov     edx, 10Bh; lineNumber
0x18001fd83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd88  lea     pWebAuthRequest, [rsp+230h+hKey]; this
0x18001fd8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fd92  lea     pWebAuthRequest, [rsp+230h+localMutex]; this
0x18001fd97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fd9c  lea     pWebAuthRequest, [rsp+230h+packageName]; this
0x18001fda1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fda6  mov     eax, ebx
0x18001fda8  jmp     short loc_18001FDEC
0x18001fdaa  mov     rax, [rsp+230h+localMutex.m_ptr]
0x18001fdaf  lea     pWebAuthRequest, s_WAB2WAMBridgeInternetProviderID
0x18001fdb6  mov     [r12], rax
0x18001fdba  imul    rax, rsi, 88h
0x18001fdc1  mov     [rsp+230h+localMutex.m_ptr], r14
0x18001fdc6  add     rax, pWebAuthRequest
0x18001fdc9  lea     pWebAuthRequest, [rsp+230h+hKey]; this
0x18001fdce  mov     [r15], rax
0x18001fdd1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fdd6  lea     pWebAuthRequest, [rsp+230h+localMutex]; this
0x18001fddb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fde0  lea     pWebAuthRequest, [rsp+230h+packageName]; this
0x18001fde5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fdea  xor     eax, eax
0x18001fdec  mov     pWebAuthRequest, [rbp+130h+var_50]
0x18001fdf3  xor     pWebAuthRequest, rsp; StackCookie
0x18001fdf6  call    __security_check_cookie
0x18001fdfb  add     rsp, 1F8h
0x18001fe02  pop     r15
0x18001fe04  pop     r14
0x18001fe06  pop     r13
0x18001fe08  pop     r12
0x18001fe0a  pop     rdi
0x18001fe0b  pop     rsi
0x18001fe0c  pop     rbx
0x18001fe0d  pop     rbp
0x18001fe0e  retn
```
