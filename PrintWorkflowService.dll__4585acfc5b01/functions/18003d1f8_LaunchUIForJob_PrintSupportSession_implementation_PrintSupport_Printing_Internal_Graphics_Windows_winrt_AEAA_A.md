# ?LaunchUIForJob@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AW4PrintWorkflowUICompletionStatusPriv@345678@AEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@W4PrintSupportUILaunchedReason@345678@@Z

- ea: `0x18003d1f8`
- end: `0x18003d49f`
- name: `?LaunchUIForJob@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AW4PrintWorkflowUICompletionStatusPriv@345678@AEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@W4PrintSupportUILaunchedReason@345678@@Z`
- size: `679`
- prototype: ``
- caller_count: `3`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a7d0`
- `0x18003d4b0`
- `0x18003d690`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x1800128a4`
- `0x1800147fc`
- `0x180014868`
- `0x180032bf4`
- `0x180033f1c`
- `0x180034a54`
- `0x180035690`
- `0x18003712c`
- `0x18003719c`
- `0x1800374d8`
- `0x1800393c8`
- `0x18003b0b4`
- `0x18003b488`
- `0x18003d1f8`
- `0x18003fa34`
- `0x18004013c`
- `0x1800405e0`
- `0x18005e010`

## string_xrefs

- `0x18003d44b`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003d463`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003d478`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003d48d`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::LaunchUIForJob(
        __int64 a1,
        __int64 a2,
        __int32 a3)
{
  int v6; // r15d
  __int64 v7; // rbx
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession **Parent; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 (__fastcall ***v12)(_QWORD, __int64 *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // r14
  __int64 (__fastcall *v15)(__int64, unsigned __int64); // rdi
  PrintSupportSessionCommon *v16; // rcx
  unsigned __int64 CurrentUserContext; // rax
  int v18; // eax
  __int64 (__fastcall *v19)(__int64, unsigned __int64); // rdi
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *v20; // rcx
  unsigned __int64 CurrentUserContextToken; // rax
  int v22; // eax
  _QWORD *v23; // rax
  __int64 v24; // rcx
  unsigned int v25; // edi
  PrintSupportSessionCommon *v27; // rcx
  _DWORD *v28; // rcx
  unsigned int v29; // edi
  __int64 (__fastcall ***v30)(_QWORD, __int64 *, __int64 *); // [rsp+20h] [rbp-40h] BYREF
  __int64 v31; // [rsp+28h] [rbp-38h] BYREF
  __int64 v32; // [rsp+30h] [rbp-30h] BYREF
  char v33; // [rsp+38h] [rbp-28h]
  IID v34; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  if ( (**(_DWORD **)(a1 + 544) & 0x20) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
      (const char *)0x8000000ELL,
      (int)v30);
  v6 = **(_DWORD **)(a1 + 544);
  v7 = *(_QWORD *)(a1 + 544);
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::SetSessionStateAndCheck(
    v7,
    32);
  _InterlockedExchange((volatile __int32 *)(v7 + 4), a3);
  Parent = (winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession **)winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::GetParent(v7, &v30);
  winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::StopMonitorIdleBackgroundTask(*Parent);
  if ( v30 )
    winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(
      &v30,
      v9,
      v10,
      v11);
  v32 = v7;
  v33 = 1;
  v34.Data1 = 1620658026;
  *(_DWORD *)&v34.Data2 = 1281174741;
  *(_DWORD *)v34.Data4 = 469523596;
  *(_DWORD *)&v34.Data4[4] = -1826355687;
  winrt::create_instance<Windows::Graphics::Internal::Printing::PrintSupport::IPrintWorkflowJobActivatedEventArgsPriv>(
    &v30,
    &v34,
    v10);
  v12 = v30;
  v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), _QWORD))(*v30)[6])(
          v30,
          *(unsigned int *)(a1 + 296));
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
      (const char *)(unsigned int)v13,
      (int)v30);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl) )
  {
    winrt::com_ptr<Windows::Graphics::Internal::Printing::PrintSupport::IPrintWorkflowJobActivatedEventArgsPriv>::as<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(
      &v30,
      &v31);
    v14 = v31;
    v15 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v31 + 56LL);
    CurrentUserContext = PrintSupportSessionCommon::GetCurrentUserContext(v16);
    v18 = v15(v14, CurrentUserContext);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
        (const char *)(unsigned int)v18,
        (int)v30);
  }
  else
  {
    winrt::com_ptr<Windows::Graphics::Internal::Printing::PrintSupport::IPrintWorkflowJobActivatedEventArgsPriv>::as<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(
      &v30,
      &v31);
    v14 = v31;
    v19 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v31 + 56LL);
    CurrentUserContextToken = winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::GetCurrentUserContextToken(v20);
    v22 = v19(v14, CurrentUserContextToken);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
        (const char *)(unsigned int)v22,
        (int)v30);
  }
  if ( v14 )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v31);
  v23 = winrt::com_ptr<WorkflowJobActivationEventArgs>::as<IInspectable>(&v30, &v31);
  v25 = (unsigned int)PrintSupportSessionCommon::LaunchAppUI(
                        (PrintSupportSessionCommon *)(a1 + 24),
                        *v23,
                        (HANDLE *)(a1 + 80)) >> 31;
  if ( v31 )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v31);
  if ( (_BYTE)v25 )
  {
    if ( v12 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v30);
    v33 = 0;
    _lambda_16a9492b11a7a08af849db298b6a4d35_::operator()(&v32);
    return 1;
  }
  else
  {
    PrintSupportSessionCommon::WaitForEventOrProcessExit(v24, a2, a1 + 80);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
      PrintSupportSessionCommon::RemoveDebugSessionData(v27, *(_DWORD *)(a1 + 296), 1);
    v28 = *(_DWORD **)(a1 + 544);
    if ( *v28 == v6 || (*v28 & 0x600) == 0 )
      v29 = 0;
    else
      v29 = 3 - (v28[2] != 0);
    if ( v12 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v30);
    v33 = 0;
    _lambda_16a9492b11a7a08af849db298b6a4d35_::operator()(&v32);
    return v29;
  }
}

```

## disassembly

```asm
0x18003d1f8  push    rbp
0x18003d1fa  push    rbx
0x18003d1fb  push    rsi
0x18003d1fc  push    rdi
0x18003d1fd  push    r12
0x18003d1ff  push    r14
0x18003d201  push    r15
0x18003d203  mov     rbp, rsp
0x18003d206  sub     rsp, 60h
0x18003d20a  mov     rax, cs:__security_cookie
0x18003d211  xor     rax, rsp
0x18003d214  mov     [rbp+var_10], rax
0x18003d218  mov     edi, r8d
0x18003d21b  mov     r12, rdx
0x18003d21e  mov     rsi, rcx
0x18003d221  mov     rax, [rcx+220h]
0x18003d228  mov     edx, [rax]
0x18003d22a  nop
0x18003d22b  mov     rcx, [rbp+38h]; this
0x18003d22f  test    dl, 20h
0x18003d232  jnz     loc_18003D45D
0x18003d238  mov     rax, [rsi+220h]
0x18003d23f  mov     r15d, [rax]
0x18003d242  nop
0x18003d243  mov     rbx, [rsi+220h]
0x18003d24a  xor     r8d, r8d
0x18003d24d  lea     edx, [r8+20h]
0x18003d251  mov     rcx, rbx
0x18003d254  call    ?SetSessionStateAndCheck@SessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXW4PrintSupportSessionState@456789@W4SessionChangeType@@@Z; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::SetSessionStateAndCheck(winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSessionState,SessionChangeType)
0x18003d259  xchg    edi, [rbx+4]
0x18003d25c  lea     rdx, [rbp+var_40]
0x18003d260  mov     rcx, rbx
0x18003d263  call    ?GetParent@SessionStateHandler@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA?AU?$com_ptr@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@9@XZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::SessionStateHandler::GetParent(void)
0x18003d268  nop
0x18003d269  mov     rcx, [rax]; this
0x18003d26c  call    ?StopMonitorIdleBackgroundTask@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::StopMonitorIdleBackgroundTask(void)
0x18003d271  nop
0x18003d272  cmp     [rbp+var_40], 0
0x18003d277  jz      short loc_18003D282
0x18003d279  lea     rcx, [rbp+var_40]
0x18003d27d  call    ?unconditional_release_ref@?$com_ptr@UPrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(void)
0x18003d282  mov     [rbp+var_30], rbx
0x18003d286  mov     [rbp+var_28], 1
0x18003d28a  mov     [rbp+var_20], 6099476Ah
0x18003d291  mov     [rbp+var_1C], 4C5D2CD5h
0x18003d298  mov     [rbp+var_18], 1BFC5C8Ch
0x18003d29f  mov     [rbp+var_14], 93240619h
0x18003d2a6  lea     rdx, [rbp+var_20]
0x18003d2aa  lea     rcx, [rbp+var_40]
0x18003d2ae  call    ??$create_instance@UIPrintWorkflowJobActivatedEventArgsPriv@PrintSupport@Printing@Internal@Graphics@Windows@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x18003d2b3  nop
0x18003d2b4  mov     rbx, [rbp+var_40]
0x18003d2b8  mov     rax, [rbx]
0x18003d2bb  mov     edx, [rsi+128h]
0x18003d2c1  mov     rcx, rbx
0x18003d2c4  mov     rax, [rax+30h]
0x18003d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2cd  mov     rcx, [rbp+38h]; this
0x18003d2d1  test    eax, eax
0x18003d2d3  js      loc_18003D475
0x18003d2d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl(void)'::`2'::impl
0x18003d2e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(void)
0x18003d2e5  lea     rdx, [rbp+var_38]
0x18003d2e9  lea     rcx, [rbp+var_40]
0x18003d2ed  test    al, al
0x18003d2ef  jz      short loc_18003D323
0x18003d2f1  call    ??$as@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@?$com_ptr@UIPrintWorkflowJobActivatedEventArgsPriv@PrintSupport@Printing@Internal@Graphics@Windows@@@winrt@@QEBA?A_PXZ
0x18003d2f6  nop
0x18003d2f7  mov     r14, [rbp+var_38]
0x18003d2fb  mov     rax, [r14]
0x18003d2fe  mov     rdi, [rax+38h]
0x18003d302  call    ?GetCurrentUserContext@PrintSupportSessionCommon@@QEAA_KXZ; PrintSupportSessionCommon::GetCurrentUserContext(void)
0x18003d307  mov     rdx, rax
0x18003d30a  mov     rcx, r14
0x18003d30d  mov     rax, rdi
0x18003d310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d315  mov     rcx, [rbp+38h]; this
0x18003d319  test    eax, eax
0x18003d31b  js      loc_18003D48A
0x18003d321  jmp     short loc_18003D353
0x18003d323  call    ??$as@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@?$com_ptr@UIPrintWorkflowJobActivatedEventArgsPriv@PrintSupport@Printing@Internal@Graphics@Windows@@@winrt@@QEBA?A_PXZ
0x18003d328  nop
0x18003d329  mov     r14, [rbp+var_38]
0x18003d32d  mov     rax, [r14]
0x18003d330  mov     rdi, [rax+38h]
0x18003d334  call    ?GetCurrentUserContextToken@PrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAA_KXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::GetCurrentUserContextToken(void)
0x18003d339  mov     rdx, rax
0x18003d33c  mov     rcx, r14
0x18003d33f  mov     rax, rdi
0x18003d342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d347  mov     rcx, [rbp+38h]; this
0x18003d34b  test    eax, eax
0x18003d34d  js      loc_18003D448
0x18003d353  test    r14, r14
0x18003d356  jz      short loc_18003D361
0x18003d358  lea     rcx, [rbp+var_38]
0x18003d35c  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18003d361  lea     rdx, [rbp+var_38]
0x18003d365  lea     rcx, [rbp+var_40]
0x18003d369  call    ??$as@UIInspectable@@@?$com_ptr@VWorkflowJobActivationEventArgs@@@winrt@@QEBA?A_PXZ
0x18003d36e  lea     rcx, [rsi+18h]; this
0x18003d372  lea     r8, [rsi+50h]
0x18003d376  mov     rdx, [rax]; int
0x18003d379  call    ?LaunchAppUI@PrintSupportSessionCommon@@QEAAJPEAUIInspectable@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; PrintSupportSessionCommon::LaunchAppUI(IInspectable *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18003d37e  mov     edi, eax
0x18003d380  shr     edi, 1Fh
0x18003d383  cmp     [rbp+var_38], 0
0x18003d388  jz      short loc_18003D393
0x18003d38a  lea     rcx, [rbp+var_38]
0x18003d38e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18003d393  test    dil, dil
0x18003d396  jz      short loc_18003D3BC
0x18003d398  test    rbx, rbx
0x18003d39b  jz      short loc_18003D3A7
0x18003d39d  lea     rcx, [rbp+var_40]
0x18003d3a1  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18003d3a6  nop
0x18003d3a7  mov     [rbp+var_28], 0
0x18003d3ab  lea     rcx, [rbp+var_30]
0x18003d3af  call    ??R_lambda_16a9492b11a7a08af849db298b6a4d35_@@QEBA@XZ; _lambda_16a9492b11a7a08af849db298b6a4d35_::operator()(void)
0x18003d3b4  nop
0x18003d3b5  mov     eax, 1
0x18003d3ba  jmp     short loc_18003D42D
0x18003d3bc  lea     r8, [rsi+50h]
0x18003d3c0  mov     rdx, r12
0x18003d3c3  call    ?WaitForEventOrProcessExit@PrintSupportSessionCommon@@QEAAXAEBV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@3@@Z
0x18003d3c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18003d3cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18003d3d4  test    al, al
0x18003d3d6  jz      short loc_18003D3E6
0x18003d3d8  mov     r8b, 1; bool
0x18003d3db  mov     edx, [rsi+128h]; unsigned int
0x18003d3e1  call    ?RemoveDebugSessionData@PrintSupportSessionCommon@@IEAAXI_N@Z; PrintSupportSessionCommon::RemoveDebugSessionData(uint,bool)
0x18003d3e6  mov     rcx, [rsi+220h]
0x18003d3ed  mov     eax, [rcx]
0x18003d3ef  nop
0x18003d3f0  cmp     eax, r15d
0x18003d3f3  jz      short loc_18003D40C
0x18003d3f5  mov     eax, [rcx]
0x18003d3f7  nop
0x18003d3f8  test    eax, 600h
0x18003d3fd  jz      short loc_18003D40C
0x18003d3ff  mov     eax, [rcx+8]
0x18003d402  nop
0x18003d403  neg     eax
0x18003d405  sbb     edi, edi
0x18003d407  add     edi, 3
0x18003d40a  jmp     short loc_18003D40E
0x18003d40c  xor     edi, edi
0x18003d40e  test    rbx, rbx
0x18003d411  jz      short loc_18003D41D
0x18003d413  lea     rcx, [rbp+var_40]
0x18003d417  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18003d41c  nop
0x18003d41d  mov     [rbp+var_28], 0
0x18003d421  lea     rcx, [rbp+var_30]
0x18003d425  call    ??R_lambda_16a9492b11a7a08af849db298b6a4d35_@@QEBA@XZ; _lambda_16a9492b11a7a08af849db298b6a4d35_::operator()(void)
0x18003d42a  nop
0x18003d42b  mov     eax, edi
0x18003d42d  mov     rcx, [rbp+var_10]
0x18003d431  xor     rcx, rsp; StackCookie
0x18003d434  call    __security_check_cookie
0x18003d439  add     rsp, 60h
0x18003d43d  pop     r15
0x18003d43f  pop     r14
0x18003d441  pop     r12
0x18003d443  pop     rdi
0x18003d444  pop     rsi
0x18003d445  pop     rbx
0x18003d446  pop     rbp
0x18003d447  retn
0x18003d448  mov     r9d, eax; char *
0x18003d44b  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003d452  mov     edx, 19Ah; void *
0x18003d457  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d45d  mov     r9d, 8000000Eh; char *
0x18003d463  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003d46a  mov     edx, 18Bh; void *
0x18003d46f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d475  mov     r9d, eax; char *
0x18003d478  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003d47f  mov     edx, 190h; void *
0x18003d484  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d48a  mov     r9d, eax; char *
0x18003d48d  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003d494  mov     edx, 195h; void *
0x18003d499  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
