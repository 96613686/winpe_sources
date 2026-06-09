# _lambda_63b5d6cab1e361052fd8439cbedfd6a8_::operator()

- ea: `0x18005a3f4`
- end: `0x18005a6b2`
- name: `_lambda_63b5d6cab1e361052fd8439cbedfd6a8_::operator()`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180059d60`

## callees

- `0x1800094c0`
- `0x180017bc4`
- `0x18001f5f4`
- `0x180021074`
- `0x18005a350`
- `0x18005a3f4`
- `0x18005c320`
- `0x18005c7f0`
- `0x18005ca24`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a43c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a43c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005a420`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005a420`
- `CoreMessaging!CoreUICreate` at `0x18005a495`
- `CoreMessaging!CoreUICreate` at `0x18005a495`

## string_xrefs

- `0x18005a419`: `user32.dll`

## pseudocode

```c
__int64 __fastcall lambda_63b5d6cab1e361052fd8439cbedfd6a8_::operator()(__int64 a1, void *a2)
{
  int (__high *v2)(enum COREMESSAGINGK_ENDPOINT_ID, struct tagMsgRoutingInfo *); // rax
  HMODULE LibraryW; // rax
  const char *v4; // r9
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // r8d
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, const wchar_t *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, __int64); // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r8d
  __int64 result; // rax
  int *v19; // [rsp+20h] [rbp-58h]
  HMODULE v20; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v21[2]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v22; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint;
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint )
  {
    LibraryW = LoadLibraryW(L"user32.dll");
    v20 = LibraryW;
    if ( !LibraryW )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x342,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        v4);
    Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint = (int (__high *)(enum COREMESSAGINGK_ENDPOINT_ID, struct tagMsgRoutingInfo *))GetProcAddress(LibraryW, (LPCSTR)0xAF8);
    if ( !Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x345,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        v5);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v20);
    v2 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint;
  }
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession )
  {
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v2)(0, 0);
    if ( v6 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(retaddr, (void *)0x34E, v7, (const char *)(unsigned int)v6, (int)v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession);
    v8 = CoreUICreate(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x353,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        (const char *)(unsigned int)v8,
        (int)v19);
    wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
      &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint,
      Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession);
    v9 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession;
    v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
                                                                        + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort);
    v11 = v10(
            v9,
            L"Kernel\\SystemCoreMessagingPort",
            &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x359,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        (const char *)(unsigned int)v11,
        (int)v19);
    v12 = Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
                                                                     + 104LL);
    wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&void wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(
      &Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint,
      Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint);
    v19 = &qword_1801693A8;
    v14 = v13(
            v12,
            Windows::Internal::CapabilityAccess::Private::Globals::OnCAMUsageReportingMessageReceived,
            0,
            Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort);
    if ( v14 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x362,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        (const char *)(unsigned int)v14,
        (int)&qword_1801693A8);
    v22 = 0;
    memset(v21, 0, sizeof(v21));
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
                                                               + 136LL))(
            Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession,
            *(_QWORD *)&qword_1801693A8,
            v21);
    if ( v15 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
        (const char *)(unsigned int)v15,
        (int)&qword_1801693A8);
    v16 = ((__int64 (__fastcall *)(_QWORD, _OWORD *))Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint)(
            0,
            v21);
    if ( v16 < 0 )
      wil::details::in1diag3::_FailFast_NtStatus(
        retaddr,
        (void *)0x36A,
        v17,
        (const char *)(unsigned int)v16,
        (int)&qword_1801693A8);
  }
  wil::details::SetEvent(
    (wil::details *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingThreadReadyEvent,
    a2);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
                                              + 232LL))(Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession);
  if ( (int)result < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)(unsigned int)result,
      (int)v19);
  return result;
}

```

## disassembly

```asm
0x18005a3f4  mov     [rsp+arg_0], rbx
0x18005a3f9  push    rdi
0x18005a3fa  sub     rsp, 70h
0x18005a3fe  mov     rax, cs:__security_cookie
0x18005a405  xor     rax, rsp
0x18005a408  mov     [rsp+78h+var_18], rax
0x18005a40d  mov     rax, cs:?m_fnRegisterCoreMessagingEndPoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0P6AHW4COREMESSAGINGK_ENDPOINT_ID@@PEAUtagMsgRoutingInfo@@@ZEA; int (*Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint)(COREMESSAGINGK_ENDPOINT_ID,tagMsgRoutingInfo *)
0x18005a414  test    rax, rax
0x18005a417  jnz     short loc_18005A463
0x18005a419  lea     rcx, LibFileName; "user32.dll"
0x18005a420  call    cs:__imp_LoadLibraryW
0x18005a426  mov     [rsp+78h+var_48], rax
0x18005a42b  test    rax, rax
0x18005a42e  jz      loc_18005A5F6
0x18005a434  mov     edx, 0AF8h; lpProcName
0x18005a439  mov     rcx, rax; hModule
0x18005a43c  call    cs:__imp_GetProcAddress
0x18005a442  mov     cs:?m_fnRegisterCoreMessagingEndPoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0P6AHW4COREMESSAGINGK_ENDPOINT_ID@@PEAUtagMsgRoutingInfo@@@ZEA, rax; int (*Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint)(COREMESSAGINGK_ENDPOINT_ID,tagMsgRoutingInfo *)
0x18005a449  test    rax, rax
0x18005a44c  jz      loc_18005A60D
0x18005a452  lea     rcx, [rsp+78h+var_48]
0x18005a457  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18005a45c  mov     rax, cs:?m_fnRegisterCoreMessagingEndPoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0P6AHW4COREMESSAGINGK_ENDPOINT_ID@@PEAUtagMsgRoutingInfo@@@ZEA; int (*Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint)(COREMESSAGINGK_ENDPOINT_ID,tagMsgRoutingInfo *)
0x18005a463  cmp     cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a46b  jnz     loc_18005A59B
0x18005a471  xor     edx, edx
0x18005a473  xor     ecx, ecx
0x18005a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a47a  test    eax, eax
0x18005a47c  js      loc_18005A624
0x18005a482  lea     rcx, ?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a489  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a48e  lea     rcx, ?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a495  call    cs:__imp_CoreUICreate
0x18005a49b  test    eax, eax
0x18005a49d  js      loc_18005A637
0x18005a4a3  mov     rdx, cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a4aa  lea     rcx, ?m_coreMessagingEndpoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@A; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint
0x18005a4b1  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x18005a4b6  mov     rdi, cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a4bd  lea     rcx, ?m_coreMessagingPort@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessagePort@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessagePort> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort
0x18005a4c4  mov     rax, [rdi]
0x18005a4c7  mov     rbx, [rax+50h]
0x18005a4cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a4d0  lea     r8, ?m_coreMessagingPort@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessagePort@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessagePort> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort
0x18005a4d7  mov     rcx, rdi
0x18005a4da  lea     rdx, aKernelSystemco; "Kernel\\SystemCoreMessagingPort"
0x18005a4e1  mov     rax, rbx
0x18005a4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4e9  test    eax, eax
0x18005a4eb  js      loc_18005A651
0x18005a4f1  mov     rdi, cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a4f8  lea     rcx, ?m_coreMessagingEndpoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@A; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint
0x18005a4ff  mov     rdx, cs:?m_coreMessagingEndpoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@A; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingEndpoint
0x18005a506  mov     rax, [rdi]
0x18005a509  mov     rbx, [rax+68h]
0x18005a50d  call    ?reset@?$unique_com_token@UIMessageSession@@_K$$A6AXPEAU1@_K@Z$1?IMessageSessionCloseEndpointFunction@details@wil@@YAX01@Z$0A@@wil@@QEAAXPEAUIMessageSession@@_K@Z; wil::unique_com_token<IMessageSession,unsigned __int64,void (IMessageSession *,unsigned __int64),&wil::details::IMessageSessionCloseEndpointFunction(IMessageSession *,unsigned __int64),0>::reset(IMessageSession *,unsigned __int64)
0x18005a512  mov     r9, cs:?m_coreMessagingPort@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessagePort@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessagePort> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingPort
0x18005a519  lea     rax, qword_1801693A8
0x18005a520  mov     qword ptr [rsp+78h+var_58], rax; int
0x18005a525  lea     rdx, ?OnCAMUsageReportingMessageReceived@Globals@Private@CapabilityAccess@Internal@Windows@@YAJPEAXPEBXH@Z; Windows::Internal::CapabilityAccess::Private::Globals::OnCAMUsageReportingMessageReceived(void *,void const *,int)
0x18005a52c  mov     rax, rbx
0x18005a52f  xor     r8d, r8d
0x18005a532  mov     rcx, rdi
0x18005a535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a53a  test    eax, eax
0x18005a53c  js      loc_18005A66B
0x18005a542  mov     rcx, cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a549  lea     r8, [rsp+78h+var_40]
0x18005a54e  mov     rdx, cs:qword_1801693A8
0x18005a555  xor     eax, eax
0x18005a557  xorps   xmm0, xmm0
0x18005a55a  mov     [rsp+78h+var_20], rax
0x18005a55f  movups  [rsp+78h+var_40], xmm0
0x18005a564  movups  [rsp+78h+var_30], xmm0
0x18005a569  mov     rax, [rcx]
0x18005a56c  mov     rax, [rax+88h]
0x18005a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a578  test    eax, eax
0x18005a57a  js      loc_18005A685
0x18005a580  mov     rax, cs:?m_fnRegisterCoreMessagingEndPoint@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0P6AHW4COREMESSAGINGK_ENDPOINT_ID@@PEAUtagMsgRoutingInfo@@@ZEA; int (*Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_fnRegisterCoreMessagingEndPoint)(COREMESSAGINGK_ENDPOINT_ID,tagMsgRoutingInfo *)
0x18005a587  lea     rdx, [rsp+78h+var_40]
0x18005a58c  xor     ecx, ecx
0x18005a58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a593  test    eax, eax
0x18005a595  js      loc_18005A69F
0x18005a59b  mov     rcx, cs:?m_coreMessagingThreadReadyEvent@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A; this
0x18005a5a2  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18005a5a7  mov     rcx, cs:?m_coreMessagingSession@CoreMessagingManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$ComPtr@UIMessageSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IMessageSession> Windows::Internal::CapabilityAccess::Private::Globals::CoreMessagingManager::m_coreMessagingSession
0x18005a5ae  mov     rax, [rcx]
0x18005a5b1  mov     rax, [rax+0E8h]
0x18005a5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5bd  test    eax, eax
0x18005a5bf  js      short loc_18005A5DC
0x18005a5c1  mov     rcx, [rsp+78h+var_18]
0x18005a5c6  xor     rcx, rsp; StackCookie
0x18005a5c9  call    __security_check_cookie
0x18005a5ce  mov     rbx, [rsp+78h+arg_0]
0x18005a5d6  add     rsp, 70h
0x18005a5da  pop     rdi
0x18005a5db  retn
0x18005a5dc  mov     rcx, [rsp+78h]; this
0x18005a5e1  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a5e8  mov     r9d, eax; char *
0x18005a5eb  mov     edx, 36Fh; void *
0x18005a5f0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a5f6  mov     rcx, [rsp+78h]; this
0x18005a5fb  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a602  mov     edx, 342h; void *
0x18005a607  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005a60d  mov     rcx, [rsp+78h]; this
0x18005a612  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a619  mov     edx, 345h; void *
0x18005a61e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18005a624  mov     rcx, [rsp+78h]; this
0x18005a629  mov     r9d, eax; char *
0x18005a62c  mov     edx, 34Eh; void *
0x18005a631  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
0x18005a637  mov     rcx, [rsp+78h]; this
0x18005a63c  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a643  mov     r9d, eax; char *
0x18005a646  mov     edx, 353h; void *
0x18005a64b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a651  mov     rcx, [rsp+78h]; this
0x18005a656  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a65d  mov     r9d, eax; char *
0x18005a660  mov     edx, 359h; void *
0x18005a665  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a66b  mov     rcx, [rsp+78h]; this
0x18005a670  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a677  mov     r9d, eax; char *
0x18005a67a  mov     edx, 362h; void *
0x18005a67f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a685  mov     rcx, [rsp+78h]; this
0x18005a68a  lea     r8, aOnecoreBaseDev_22; "onecore\\base\\devices\\cam\\core\\sync"...
0x18005a691  mov     r9d, eax; char *
0x18005a694  mov     edx, 368h; void *
0x18005a699  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005a69f  mov     rcx, [rsp+78h]; this
0x18005a6a4  mov     r9d, eax; char *
0x18005a6a7  mov     edx, 36Ah; void *
0x18005a6ac  call    ?_FailFast_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_NtStatus(void *,uint,char const *,long)
```
