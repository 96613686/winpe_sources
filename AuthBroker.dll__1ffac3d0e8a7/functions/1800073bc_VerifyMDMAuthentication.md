# VerifyMDMAuthentication

- ea: `0x1800073bc`
- end: `0x18000766e`
- name: `VerifyMDMAuthentication`
- size: `690`
- prototype: `HRESULT __fastcall(const wchar_t *host, const wchar_t *request, void *clientTokenHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f568`

## callees

- `0x1800045c0`
- `0x180004f00`
- `0x1800060b8`
- `0x1800060f8`
- `0x180006650`
- `0x1800066d4`
- `0x1800073bc`
- `0x18000ed64`
- `0x18000f544`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800074c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000749b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000749b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800074fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007563`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800075e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007563`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800075e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000757c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000757c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180007443`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180007443`
- `ntdll!_wcsicmp` at `0x180007414`
- `ntdll!_wcsicmp` at `0x18000742d`
- `ntdll!_wcsicmp` at `0x18000760c`
- `ntdll!_wcsicmp` at `0x180007414`
- `ntdll!_wcsicmp` at `0x18000742d`
- `ntdll!_wcsicmp` at `0x18000760c`

## string_xrefs

- `0x1800073f1`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`
- `0x18000750d`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`
- `0x18000759c`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`
- `0x1800075ee`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`
- `0x18000763f`: `onecore\ds\security\webauth\authbroker\lib\brokeractivate.cpp`

## pseudocode

```c
__int64 __fastcall VerifyMDMAuthentication(const wchar_t *host, const wchar_t *request, void *clientTokenHandle)
{
  HRESULT AuthBrokerClientAppContainerStringInfo; // eax
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // sf
  HKEY__ *m_ptr; // rbx
  LSTATUS ValueW; // eax
  unsigned int v11; // edx
  wchar_t *v12; // rbx
  unsigned int v13; // edx
  LSTATUS v14; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hKeyEnrollment; // [rsp+40h] [rbp-28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > uriToAllow; // [rsp+48h] [rbp-20h] BYREF
  wchar_t *clientSid; // [rsp+50h] [rbp-18h] BYREF
  void *retaddr; // [rsp+88h] [rbp+20h]
  unsigned int bufferSize; // [rsp+A8h] [rbp+40h] BYREF

  clientSid = 0;
  AuthBrokerClientAppContainerStringInfo = GetAuthBrokerClientAppContainerStringInfo(0, clientTokenHandle, &clientSid);
  v6 = AuthBrokerClientAppContainerStringInfo;
  if ( AuthBrokerClientAppContainerStringInfo >= 0 )
  {
    if ( _wcsicmp(L"windows.immersivecontrolpanel", host)
      || _wcsicmp(L"s-1-15-2-2434737943-167758768-3180539153-984336765-1107280622-3591121930-2677285773", clientSid) )
    {
      v6 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x522u,
        "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
        -2147024809);
      goto LABEL_27;
    }
    hKeyEnrollment.m_ptr = 0;
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
      goto LABEL_31;
    hKeyEnrollment.m_ptr = 0;
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"OSData\\Software\\Microsoft\\Enrollments",
           0,
           0x20019u,
           &hKeyEnrollment.m_ptr);
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( v8 )
    {
LABEL_31:
      m_ptr = hKeyEnrollment.m_ptr;
      if ( hKeyEnrollment.m_ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&uriToAllow);
        RegCloseKey(m_ptr);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&uriToAllow);
      }
      hKeyEnrollment.m_ptr = 0;
      ValueW = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Enrollments",
                 0,
                 0x20019u,
                 &hKeyEnrollment.m_ptr);
      if ( ValueW )
      {
        v11 = 1337;
LABEL_13:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               v11,
               "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
               ValueW);
LABEL_14:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyEnrollment);
LABEL_27:
        FreeAuthBrokerClientAppContainerString(ClientAppContainerHostSidInfo, clientSid);
        return v6;
      }
    }
    bufferSize = 0;
    ValueW = RegGetValueW(hKeyEnrollment.m_ptr, 0, L"authAllowList", 2u, 0, 0, &bufferSize);
    if ( ValueW )
    {
      v11 = 1341;
      goto LABEL_13;
    }
    uriToAllow.m_ptr = (wchar_t *)LocalAlloc(0x40u, bufferSize);
    v12 = uriToAllow.m_ptr;
    if ( uriToAllow.m_ptr )
    {
      v14 = RegGetValueW(hKeyEnrollment.m_ptr, 0, L"authAllowList", 2u, 0, uriToAllow.m_ptr, &bufferSize);
      if ( v14 )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               0x541u,
               "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
               v14);
        goto LABEL_20;
      }
      if ( !_wcsicmp(v12, request) )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&uriToAllow);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyEnrollment);
        v6 = 0;
        goto LABEL_27;
      }
      v6 = -2147024809;
      v13 = 1346;
    }
    else
    {
      v6 = -2147024882;
      v13 = 1344;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v13,
      "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
      v6);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&uriToAllow);
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    0x518u,
    "onecore\\ds\\security\\webauth\\authbroker\\lib\\brokeractivate.cpp",
    AuthBrokerClientAppContainerStringInfo);
  return v6;
}

```

## disassembly

```asm
0x1800073bc  push    rbp
0x1800073be  push    rbx
0x1800073bf  push    rsi
0x1800073c0  push    rdi
0x1800073c1  mov     rbp, rsp
0x1800073c4  sub     rsp, 68h
0x1800073c8  mov     rax, clientTokenHandle
0x1800073cb  mov     [rbp+clientSid], 0
0x1800073d3  mov     rsi, request
0x1800073d6  lea     clientTokenHandle, [rbp+clientSid]; string
0x1800073da  mov     rdi, host
0x1800073dd  mov     request, rax; clientTokenHandle
0x1800073e0  xor     ecx, ecx; infoType
0x1800073e2  call    ?GetAuthBrokerClientAppContainerStringInfo@@YAJW4ClientAppContainerStringInfoType@@PEAXPEAPEAG@Z; GetAuthBrokerClientAppContainerStringInfo(ClientAppContainerStringInfoType,void *,ushort * *)
0x1800073e7  mov     ebx, eax
0x1800073e9  test    eax, eax
0x1800073eb  jns     short loc_18000740A
0x1800073ed  mov     host, [rbp+20h]; callerReturnAddress
0x1800073f1  lea     clientTokenHandle, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x1800073f8  mov     r9d, eax; hr
0x1800073fb  mov     edx, 518h; lineNumber
0x180007400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007405  jmp     loc_180007663
0x18000740a  mov     request, rdi; String2
0x18000740d  lea     host, aWindowsImmersi; "windows.immersivecontrolpanel"
0x180007414  call    cs:__imp__wcsicmp
0x18000741a  test    eax, eax
0x18000741c  jnz     loc_18000763B
0x180007422  mov     request, [rbp+clientSid]; String2
0x180007426  lea     host, aS1152243473794; "s-1-15-2-2434737943-167758768-318053915"...
0x18000742d  call    cs:__imp__wcsicmp
0x180007433  test    eax, eax
0x180007435  jnz     loc_18000763B
0x18000743b  mov     [rbp+hKeyEnrollment.m_ptr], 0
0x180007443  call    cs:__imp_RtlIsStateSeparationEnabled
0x180007449  mov     edi, 20019h
0x18000744e  test    al, al
0x180007450  jz      short loc_1800074B1
0x180007452  mov     rbx, [rbp+hKeyEnrollment.m_ptr]
0x180007456  test    rbx, rbx
0x180007459  jz      short loc_180007476
0x18000745b  lea     host, [rbp+uriToAllow]; this
0x18000745f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007464  mov     host, rbx; hKey
0x180007467  call    cs:__imp_RegCloseKey
0x18000746d  lea     host, [rbp+uriToAllow]; this
0x180007471  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007476  lea     rax, [rbp+hKeyEnrollment]
0x18000747a  mov     [rbp+hKeyEnrollment.m_ptr], 0
0x180007482  mov     r9d, edi; samDesired
0x180007485  mov     [rsp+68h+phkResult], rax; phkResult
0x18000748a  xor     r8d, r8d; ulOptions
0x18000748d  lea     request, aOsdataSoftware; "OSData\\Software\\Microsoft\\Enrollment"...
0x180007494  mov     host, 0FFFFFFFF80000002h; hKey
0x18000749b  call    cs:__imp_RegOpenKeyExW
0x1800074a1  test    eax, eax
0x1800074a3  jle     short loc_1800074AF
0x1800074a5  movzx   eax, ax
0x1800074a8  or      eax, 80070000h
0x1800074ad  test    eax, eax
0x1800074af  jns     short loc_18000752C
0x1800074b1  mov     rbx, [rbp+hKeyEnrollment.m_ptr]
0x1800074b5  test    rbx, rbx
0x1800074b8  jz      short loc_1800074D5
0x1800074ba  lea     host, [rbp+uriToAllow]; this
0x1800074be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800074c3  mov     host, rbx; hKey
0x1800074c6  call    cs:__imp_RegCloseKey
0x1800074cc  lea     host, [rbp+uriToAllow]; this
0x1800074d0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800074d5  lea     rax, [rbp+hKeyEnrollment]
0x1800074d9  mov     [rbp+hKeyEnrollment.m_ptr], 0
0x1800074e1  mov     r9d, edi; samDesired
0x1800074e4  mov     [rsp+68h+phkResult], rax; phkResult
0x1800074e9  xor     r8d, r8d; ulOptions
0x1800074ec  lea     request, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments"
0x1800074f3  mov     host, 0FFFFFFFF80000002h; hKey
0x1800074fa  call    cs:__imp_RegOpenKeyExW
0x180007500  test    eax, eax
0x180007502  jz      short loc_18000752C
0x180007504  mov     edx, 539h; lineNumber
0x180007509  mov     host, [rbp+20h]; callerReturnAddress
0x18000750d  lea     clientTokenHandle, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x180007514  mov     r9d, eax; err
0x180007517  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000751c  mov     ebx, eax
0x18000751e  lea     host, [rbp+hKeyEnrollment]; this
0x180007522  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007527  jmp     loc_180007658
0x18000752c  mov     host, [rbp+hKeyEnrollment.m_ptr]; hkey
0x180007530  lea     rax, [rbp+bufferSize]
0x180007534  mov     [rsp+68h+pcbData], rax; pcbData
0x180007539  lea     clientTokenHandle, aAuthallowlist; "authAllowList"
0x180007540  mov     edi, 2
0x180007545  mov     [rsp+68h+pvData], 0; pvData
0x18000754e  mov     r9d, edi; dwFlags
0x180007551  mov     [rsp+68h+phkResult], 0; pdwType
0x18000755a  xor     edx, edx; lpSubKey
0x18000755c  mov     [rbp+bufferSize], 0
0x180007563  call    cs:__imp_RegGetValueW
0x180007569  test    eax, eax
0x18000756b  jz      short loc_180007574
0x18000756d  mov     edx, 53Dh
0x180007572  jmp     short loc_180007509
0x180007574  mov     edx, [rbp+bufferSize]; uBytes
0x180007577  mov     ecx, 40h ; '@'; uFlags
0x18000757c  call    cs:__imp_LocalAlloc
0x180007582  mov     [rbp+uriToAllow.m_ptr], rax
0x180007586  mov     rbx, rax
0x180007589  test    rax, rax
0x18000758c  jnz     short loc_1800075B9
0x18000758e  mov     ebx, 8007000Eh
0x180007593  mov     edx, 540h; lineNumber
0x180007598  mov     host, [rbp+20h]; callerReturnAddress
0x18000759c  lea     clientTokenHandle, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x1800075a3  mov     r9d, ebx; hr
0x1800075a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075ab  lea     host, [rbp+uriToAllow]; this
0x1800075af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800075b4  jmp     loc_18000751E
0x1800075b9  mov     host, [rbp+hKeyEnrollment.m_ptr]; hkey
0x1800075bd  lea     rax, [rbp+bufferSize]
0x1800075c1  mov     [rsp+68h+pcbData], rax; pcbData
0x1800075c6  lea     clientTokenHandle, aAuthallowlist; "authAllowList"
0x1800075cd  mov     [rsp+68h+pvData], rbx; pvData
0x1800075d2  mov     r9d, edi; dwFlags
0x1800075d5  xor     edx, edx; lpSubKey
0x1800075d7  mov     [rsp+68h+phkResult], 0; pdwType
0x1800075e0  call    cs:__imp_RegGetValueW
0x1800075e6  test    eax, eax
0x1800075e8  jz      short loc_180007606
0x1800075ea  mov     host, [rbp+20h]; callerReturnAddress
0x1800075ee  lea     clientTokenHandle, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x1800075f5  mov     r9d, eax; err
0x1800075f8  mov     edx, 541h; lineNumber
0x1800075fd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007602  mov     ebx, eax
0x180007604  jmp     short loc_1800075AB
0x180007606  mov     request, rsi; String2
0x180007609  mov     host, rbx; String1
0x18000760c  call    cs:__imp__wcsicmp
0x180007612  test    eax, eax
0x180007614  jz      short loc_180007625
0x180007616  mov     ebx, 80070057h
0x18000761b  mov     edx, 542h
0x180007620  jmp     loc_180007598
0x180007625  lea     host, [rbp+uriToAllow]; this
0x180007629  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000762e  lea     host, [rbp+hKeyEnrollment]; this
0x180007632  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007637  xor     ebx, ebx
0x180007639  jmp     short loc_180007658
0x18000763b  mov     host, [rbp+20h]; callerReturnAddress
0x18000763f  lea     clientTokenHandle, aOnecoreDsSecur; "onecore\\ds\\security\\webauth\\authbro"...
0x180007646  mov     ebx, 80070057h
0x18000764b  mov     edx, 522h; lineNumber
0x180007650  mov     r9d, ebx; hr
0x180007653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007658  mov     request, [rbp+clientSid]; string
0x18000765c  xor     ecx, ecx; infoType
0x18000765e  call    ?FreeAuthBrokerClientAppContainerString@@YAXW4ClientAppContainerStringInfoType@@PEAG@Z; FreeAuthBrokerClientAppContainerString(ClientAppContainerStringInfoType,ushort *)
0x180007663  mov     eax, ebx
0x180007665  add     rsp, 68h
0x180007669  pop     rdi
0x18000766a  pop     rsi
0x18000766b  pop     rbx
0x18000766c  pop     rbp
0x18000766d  retn
```
