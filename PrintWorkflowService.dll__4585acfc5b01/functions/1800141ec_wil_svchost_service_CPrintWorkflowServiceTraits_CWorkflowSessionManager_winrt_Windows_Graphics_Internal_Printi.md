# wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::start(void)

- ea: `0x1800141ec`
- end: `0x18001432a`
- name: `?start@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@AEAAXXZ`
- size: `318`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013390`

## callees

- `0x180003cd0`
- `0x1800089cc`
- `0x180009f80`
- `0x18000ab44`
- `0x1800129f8`
- `0x180012bf8`
- `0x180014000`
- `0x1800141ec`
- `0x1800148b4`
- `0x18005e010`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180014229`
- `combase!__imp_CoGetSharedServiceId` at `0x180014229`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001426d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001426d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::start(
        void *a1)
{
  unsigned int SharedServiceId; // eax
  unsigned int v2; // eax
  __int64 v3; // rax
  __int64 v4; // rdx
  void (__fastcall *v5)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int); // rdi
  __int64 v6; // rbx
  int v8; // [rsp+40h] [rbp-20h] BYREF
  __int128 v9; // [rsp+48h] [rbp-18h]
  void *v10; // [rsp+80h] [rbp+20h] BYREF
  char v11; // [rsp+88h] [rbp+28h] BYREF

  v10 = a1;
  wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(
    &g_serviceWithPsa,
    2,
    0);
  LODWORD(v10) = 0;
  v8 = 0;
  v9 = 0;
  SharedServiceId = CoGetSharedServiceId(&v10);
  winrt::check_hresult(&v11, SharedServiceId, &v8);
  wil::details::g_service_id = (unsigned int)v10;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &xmmword_180084260,
    1);
  v8 = 0;
  v9 = 0;
  v2 = CoRegisterServerShutdownDelay(xmmword_180084260, 60000);
  winrt::check_hresult(&v10, v2, &v8);
  v10 = operator new(0x18u);
  v3 = wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>(v10);
  v10 = 0;
  v4 = *((_QWORD *)&xmmword_180084260 + 1);
  *((_QWORD *)&xmmword_180084260 + 1) = v3;
  if ( v4 )
    std::default_delete<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>::operator()();
  std::unique_ptr<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>::~unique_ptr<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>(&v10);
  v5 = *(void (__fastcall **)(char *, const WCHAR *, __int64, __int64 (__fastcall *)(void *, unsigned __int8), __int128 *, int))(g_serviceWithPsa + 192);
  v6 = xmmword_180084260;
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)&g_serviceWithPsa + 8,
    0);
  v5(
    (char *)&g_serviceWithPsa + 8,
    L"PrintWorkflowUserSvc",
    v6,
    _lambda_1153abc37d9ba0efad3ea61ad6027b23_::_lambda_invoker_cdecl_,
    &g_serviceWithPsa,
    8);
  return wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(
           &g_serviceWithPsa,
           4,
           0);
}

```

## disassembly

```asm
0x1800141ec  mov     [rsp-18h+arg_10], rbx
0x1800141f1  mov     [rsp-18h+arg_0], rcx
0x1800141f6  push    rbp
0x1800141f7  push    rsi
0x1800141f8  push    rdi
0x1800141f9  mov     rbp, rsp
0x1800141fc  sub     rsp, 60h
0x180014200  xor     ebx, ebx
0x180014202  xor     r8d, r8d
0x180014205  lea     edx, [rbx+2]
0x180014208  lea     rsi, ?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> g_serviceWithPsa
0x18001420f  mov     rcx, rsi
0x180014212  call    ?update_status@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@AEAAXKK@Z; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(ulong,ulong)
0x180014217  mov     dword ptr [rbp+arg_0], ebx
0x18001421a  mov     [rbp+var_20], ebx
0x18001421d  xorps   xmm0, xmm0
0x180014220  movdqu  [rbp+var_18], xmm0
0x180014225  lea     rcx, [rbp+arg_0]
0x180014229  call    cs:__imp_CoGetSharedServiceId
0x18001422f  lea     r8, [rbp+var_20]
0x180014233  mov     edx, eax
0x180014235  lea     rcx, [rbp+arg_8]
0x180014239  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001423e  mov     eax, dword ptr [rbp+arg_0]
0x180014241  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x180014247  lea     edx, [rbx+1]
0x18001424a  lea     rcx, xmmword_180084260
0x180014251  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180014256  mov     [rbp+var_20], ebx
0x180014259  xorps   xmm0, xmm0
0x18001425c  movdqu  [rbp+var_18], xmm0
0x180014261  mov     edx, 0EA60h
0x180014266  mov     rcx, qword ptr cs:xmmword_180084260
0x18001426d  call    cs:__imp_CoRegisterServerShutdownDelay
0x180014273  lea     r8, [rbp+var_20]
0x180014277  mov     edx, eax
0x180014279  lea     rcx, [rbp+arg_0]
0x18001427d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180014282  lea     ecx, [rbx+18h]; Size
0x180014285  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001428a  mov     [rbp+arg_0], rax
0x18001428e  mov     rcx, rax
0x180014291  call    ??0?$svchost_module@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@345678@UIppPrintCredentialHandler@IppAuthentication@45678@UWindowsProtectedPrintHandler@WindowsProtectedPrint@45678@UPrintSupportIppPrintDeviceBroker@345678@@details@wil@@QEAA@XZ; wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>(void)
0x180014296  nop
0x180014297  mov     [rbp+arg_0], rbx
0x18001429b  mov     rdx, qword ptr cs:xmmword_180084260+8
0x1800142a2  mov     qword ptr cs:xmmword_180084260+8, rax
0x1800142a9  test    rdx, rdx
0x1800142ac  jz      short loc_1800142B3
0x1800142ae  call    ??R?$default_delete@V?$svchost_module@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@345678@UIppPrintCredentialHandler@IppAuthentication@45678@UWindowsProtectedPrintHandler@WindowsProtectedPrint@45678@UPrintSupportIppPrintDeviceBroker@345678@@details@wil@@@std@@QEBAXPEAV?$svchost_module@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@345678@UIppPrintCredentialHandler@IppAuthentication@45678@UWindowsProtectedPrintHandler@WindowsProtectedPrint@45678@UPrintSupportIppPrintDeviceBroker@345678@@details@wil@@@Z; std::default_delete<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>::operator()(wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> *)
0x1800142b3  lea     rcx, [rbp+arg_0]
0x1800142b7  call    ??1?$unique_ptr@V?$svchost_module@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@345678@UIppPrintCredentialHandler@IppAuthentication@45678@UWindowsProtectedPrintHandler@WindowsProtectedPrint@45678@UPrintSupportIppPrintDeviceBroker@345678@@details@wil@@U?$default_delete@V?$svchost_module@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@345678@UIppPrintCredentialHandler@IppAuthentication@45678@UWindowsProtectedPrintHandler@WindowsProtectedPrint@45678@UPrintSupportIppPrintDeviceBroker@345678@@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>::~unique_ptr<wil::details::svchost_module<CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>>(void)
0x1800142bc  mov     rax, qword ptr cs:?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> g_serviceWithPsa
0x1800142c3  mov     rdi, [rax+0C0h]
0x1800142ca  mov     rbx, qword ptr cs:xmmword_180084260
0x1800142d1  xor     edx, edx
0x1800142d3  lea     rcx, ?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A+8; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> g_serviceWithPsa
0x1800142da  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?UnregisterWait@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800142df  mov     [rsp+60h+var_38], 8
0x1800142e7  mov     [rsp+60h+var_40], rsi
0x1800142ec  lea     r9, ?_lambda_invoker_cdecl_@_lambda_1153abc37d9ba0efad3ea61ad6027b23_@@CA@PEAXE@Z; _lambda_1153abc37d9ba0efad3ea61ad6027b23_::_lambda_invoker_cdecl_(void *,uchar)
0x1800142f3  mov     r8, rbx
0x1800142f6  lea     rdx, ServiceName; "PrintWorkflowUserSvc"
0x1800142fd  lea     rcx, ?g_serviceWithPsa@@3V?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@A+8; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker> g_serviceWithPsa
0x180014304  mov     rax, rdi
0x180014307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001430c  xor     r8d, r8d
0x18001430f  lea     edx, [r8+4]
0x180014313  mov     rcx, rsi
0x180014316  mov     rbx, [rsp+60h+arg_10]
0x18001431e  add     rsp, 60h
0x180014322  pop     rdi
0x180014323  pop     rsi
0x180014324  pop     rbp
0x180014325  jmp     ?update_status@?$svchost_service@UCPrintWorkflowServiceTraits@@VCWorkflowSessionManager@@UPrintSupportSettingsBroker@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@UPrintSupportSessionManager@456789@UIppPrintCredentialHandler@IppAuthentication@56789@UWindowsProtectedPrintHandler@WindowsProtectedPrint@56789@UPrintSupportIppPrintDeviceBroker@456789@@wil@@AEAAXKK@Z; wil::svchost_service<CPrintWorkflowServiceTraits,CWorkflowSessionManager,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBroker,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionManager,winrt::Windows::Graphics::Internal::Printing::IppAuthentication::IppPrintCredentialHandler,winrt::Windows::Graphics::Internal::Printing::WindowsProtectedPrint::WindowsProtectedPrintHandler,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportIppPrintDeviceBroker>::update_status(ulong,ulong)
```
