# UXFrame::Uninitialize_Stage2_BeforeThreadShutdown(void)

- ea: `0x18004d1ec`
- end: `0x18004d4c9`
- name: `?Uninitialize_Stage2_BeforeThreadShutdown@UXFrame@@QEAAXXZ`
- size: `733`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016660`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x1800041c4`
- `0x180004240`
- `0x1800049ac`
- `0x1800088ac`
- `0x18000eba0`
- `0x18001049c`
- `0x180017164`
- `0x18001c890`
- `0x180034cb0`
- `0x1800396a0`
- `0x1800396e4`
- `0x18003edd0`
- `0x18004a200`
- `0x18004a2c8`
- `0x18004cc24`
- `0x18004d1ec`
- `0x18005a010`

## import_xrefs

- `USER32!DestroyWindow` at `0x18004d475`
- `USER32!DestroyWindow` at `0x18004d475`
- `USER32!GetMessageW` at `0x18004d401`
- `USER32!GetMessageW` at `0x18004d401`
- `USER32!TranslateMessage` at `0x18004d3e5`
- `USER32!TranslateMessage` at `0x18004d3e5`
- `USER32!DispatchMessageW` at `0x18004d3ef`
- `USER32!DispatchMessageW` at `0x18004d3ef`

## string_xrefs

- `0x18004d4b7`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UXFrame::Uninitialize_Stage2_BeforeThreadShutdown(HWND *this)
{
  const char *v2; // r9
  HWND v3; // rcx
  winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *v4; // rcx
  HWND v5; // rcx
  HWND v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v9[2]; // [rsp+28h] [rbp-50h] BYREF
  MSG Msg; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v9[0] = (std::_Ref_count_base *)this;
  UXFrameTelemetry::Uninitialize_Stage2_BeforeThreadShutdown_Start<UXFrame *>(v9);
  if ( *((_DWORD *)this + 64) != 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF0,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      v2);
  v3 = this[24];
  if ( v3 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)v3 + 16LL))(v3);
    *(_OWORD *)v9 = 0;
    __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
      this + 24,
      v9);
    if ( v9[1] )
      std::_Ref_count_base::_Decref(v9[1]);
  }
  v4 = (winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *)this[38];
  if ( v4 )
  {
    winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::Uninitialize(v4);
    v8 = 0;
    winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(this + 38, &v8);
    if ( v8 )
      winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(&v8);
  }
  v5 = this[26];
  if ( v5 )
  {
    (*(void (__fastcall **)(HWND))(*(_QWORD *)v5 + 80LL))(v5);
    *(_OWORD *)v9 = 0;
    __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
      this + 26,
      v9);
    if ( v9[1] )
      std::_Ref_count_base::_Decref(v9[1]);
  }
  v6 = this[35];
  if ( v6 )
  {
    *((_QWORD *)v6 + 4) = 0;
    v8 = 0;
    winrt::Windows::Foundation::IUnknown::operator=(this + 35, &v8);
    if ( v8 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v8);
  }
  v8 = 0;
  winrt::Windows::Foundation::IUnknown::operator=(this + 34, &v8);
  if ( v8 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v8);
  if ( this[30] )
  {
    winrt::impl::consume_Microsoft_UI_Dispatching_IDispatcherQueueController2<winrt::Microsoft::UI::Dispatching::DispatcherQueueController>::ShutdownQueue(this + 30);
    v8 = 0;
    winrt::Windows::Foundation::IUnknown::operator=(this + 30, &v8);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v8);
    v8 = 0;
    winrt::Windows::Foundation::IUnknown::operator=(this + 31, &v8);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v8);
  }
  if ( this[28] )
  {
    winrt::impl::consume_Windows_System_IDispatcherQueueController<winrt::Windows::System::IDispatcherQueueController>::ShutdownQueueAsync(
      this + 28,
      v9);
    v7 = operator new(0x10u);
    v7[2] = 1;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *(_QWORD *)v7 = off_18005E780;
    v8 = v7;
    winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(
      v9,
      &v8);
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v8);
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    v8 = 0;
    winrt::Windows::Foundation::IUnknown::operator=(this + 28, &v8);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v8);
    v8 = 0;
    winrt::Windows::Foundation::IUnknown::operator=(this + 29, &v8);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v8);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v9);
  }
  if ( this[37] )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
      *((_DWORD *)this + 64) = 5;
    DestroyWindow(this[37]);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    *((_DWORD *)this + 64) = 6;
  v9[0] = (std::_Ref_count_base *)this;
  UXFrameTelemetry::Uninitialize_Stage2_BeforeThreadShutdown_Stop<UXFrame *>(v9);
}

```

## disassembly

```asm
0x18004d1ec  push    rbp
0x18004d1ee  push    rbx
0x18004d1ef  push    rsi
0x18004d1f0  push    rdi
0x18004d1f1  mov     rbp, rsp
0x18004d1f4  sub     rsp, 78h
0x18004d1f8  mov     rax, cs:__security_cookie
0x18004d1ff  xor     rax, rsp
0x18004d202  mov     [rbp+var_10], rax
0x18004d206  mov     rbx, rcx
0x18004d209  xor     esi, esi
0x18004d20b  mov     [rbp+var_50], rcx
0x18004d20f  lea     rcx, [rbp+var_50]
0x18004d213  call    ??$Uninitialize_Stage2_BeforeThreadShutdown_Start@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::Uninitialize_Stage2_BeforeThreadShutdown_Start<UXFrame *>(UXFrame * &&)
0x18004d218  mov     rcx, [rbp+20h]; this
0x18004d21c  cmp     dword ptr [rbx+100h], 4
0x18004d223  jnz     loc_18004D4B7
0x18004d229  lea     rdi, [rbx+0C0h]
0x18004d230  mov     rcx, [rdi]
0x18004d233  test    rcx, rcx
0x18004d236  jz      short loc_18004D266
0x18004d238  mov     rax, [rcx]
0x18004d23b  mov     rax, [rax+10h]
0x18004d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d244  xorps   xmm0, xmm0
0x18004d247  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18004d24c  lea     rdx, [rbp+var_50]
0x18004d250  mov     rcx, rdi
0x18004d253  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004d258  mov     rcx, [rbp+var_50+8]; this
0x18004d25c  test    rcx, rcx
0x18004d25f  jz      short loc_18004D266
0x18004d261  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d266  lea     rdi, [rbx+130h]
0x18004d26d  mov     rcx, [rdi]; this
0x18004d270  test    rcx, rcx
0x18004d273  jz      short loc_18004D299
0x18004d275  call    ?Uninitialize@ShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@QEAAXXZ; winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::Uninitialize(void)
0x18004d27a  mov     [rbp+var_58], rsi
0x18004d27e  lea     rdx, [rbp+var_58]
0x18004d282  mov     rcx, rdi
0x18004d285  call    ??4?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost> &&)
0x18004d28a  cmp     [rbp+var_58], rsi
0x18004d28e  jz      short loc_18004D299
0x18004d290  lea     rcx, [rbp+var_58]
0x18004d294  call    ?unconditional_release_ref@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(void)
0x18004d299  lea     rdi, [rbx+0D0h]
0x18004d2a0  mov     rcx, [rdi]
0x18004d2a3  test    rcx, rcx
0x18004d2a6  jz      short loc_18004D2D6
0x18004d2a8  mov     rax, [rcx]
0x18004d2ab  mov     rax, [rax+50h]
0x18004d2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2b4  xorps   xmm0, xmm0
0x18004d2b7  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18004d2bc  lea     rdx, [rbp+var_50]
0x18004d2c0  mov     rcx, rdi
0x18004d2c3  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004d2c8  mov     rcx, [rbp+var_50+8]; this
0x18004d2cc  test    rcx, rcx
0x18004d2cf  jz      short loc_18004D2D6
0x18004d2d1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004d2d6  lea     rcx, [rbx+118h]
0x18004d2dd  mov     rax, [rcx]
0x18004d2e0  test    rax, rax
0x18004d2e3  jz      short loc_18004D305
0x18004d2e5  mov     [rax+20h], rsi
0x18004d2e9  mov     [rbp+var_58], rsi
0x18004d2ed  lea     rdx, [rbp+var_58]
0x18004d2f1  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d2f6  cmp     [rbp+var_58], rsi
0x18004d2fa  jz      short loc_18004D305
0x18004d2fc  lea     rcx, [rbp+var_58]
0x18004d300  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004d305  mov     [rbp+var_58], rsi
0x18004d309  lea     rcx, [rbx+110h]
0x18004d310  lea     rdx, [rbp+var_58]
0x18004d314  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d319  cmp     [rbp+var_58], rsi
0x18004d31d  jz      short loc_18004D328
0x18004d31f  lea     rcx, [rbp+var_58]
0x18004d323  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004d328  lea     rdi, [rbx+0F0h]
0x18004d32f  cmp     [rdi], rsi
0x18004d332  jz      short loc_18004D372
0x18004d334  mov     rcx, rdi
0x18004d337  call    ?ShutdownQueue@?$consume_Microsoft_UI_Dispatching_IDispatcherQueueController2@UDispatcherQueueController@Dispatching@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Dispatching_IDispatcherQueueController2<winrt::Microsoft::UI::Dispatching::DispatcherQueueController>::ShutdownQueue(void)
0x18004d33c  mov     [rbp+var_58], rsi
0x18004d340  lea     rdx, [rbp+var_58]
0x18004d344  mov     rcx, rdi
0x18004d347  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d34c  lea     rcx, [rbp+var_58]; this
0x18004d350  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d355  mov     [rbp+var_58], rsi
0x18004d359  lea     rcx, [rbx+0F8h]
0x18004d360  lea     rdx, [rbp+var_58]
0x18004d364  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d369  lea     rcx, [rbp+var_58]; this
0x18004d36d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d372  lea     rdi, [rbx+0E0h]
0x18004d379  cmp     [rdi], rsi
0x18004d37c  jz      loc_18004D44B
0x18004d382  lea     rdx, [rbp+var_50]
0x18004d386  mov     rcx, rdi
0x18004d389  call    ?ShutdownQueueAsync@?$consume_Windows_System_IDispatcherQueueController@UIDispatcherQueueController@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_IDispatcherQueueController<winrt::Windows::System::IDispatcherQueueController>::ShutdownQueueAsync(void)
0x18004d38e  nop
0x18004d38f  mov     ecx, 10h; Size
0x18004d394  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d399  mov     [rbp+var_58], rax
0x18004d39d  mov     dword ptr [rax+8], 1
0x18004d3a4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004d3ab  lea     rcx, off_18005E780
0x18004d3b2  mov     [rax], rcx
0x18004d3b5  mov     [rbp+var_58], rax
0x18004d3b9  lea     rdx, [rbp+var_58]
0x18004d3bd  lea     rcx, [rbp+var_50]
0x18004d3c1  call    ?SetHost@?$consume_WindowsUdk_UI_Shell_IShellContent@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUShellContentHost@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(winrt::WindowsUdk::UI::Shell::ShellContentHost const &)
0x18004d3c6  nop
0x18004d3c7  lea     rcx, [rbp+var_58]
0x18004d3cb  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004d3d0  xorps   xmm0, xmm0
0x18004d3d3  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18004d3d7  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18004d3db  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18004d3df  jmp     short loc_18004D3F5
0x18004d3e1  lea     rcx, [rbp+Msg]; lpMsg
0x18004d3e5  call    cs:__imp_TranslateMessage
0x18004d3eb  lea     rcx, [rbp+Msg]; lpMsg
0x18004d3ef  call    cs:__imp_DispatchMessageW
0x18004d3f5  xor     r9d, r9d; wMsgFilterMax
0x18004d3f8  xor     r8d, r8d; wMsgFilterMin
0x18004d3fb  xor     edx, edx; hWnd
0x18004d3fd  lea     rcx, [rbp+Msg]; lpMsg
0x18004d401  call    cs:__imp_GetMessageW
0x18004d407  test    eax, eax
0x18004d409  jnz     short loc_18004D3E1
0x18004d40b  mov     [rbp+var_58], rsi
0x18004d40f  lea     rdx, [rbp+var_58]
0x18004d413  mov     rcx, rdi
0x18004d416  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d41b  lea     rcx, [rbp+var_58]; this
0x18004d41f  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d424  mov     [rbp+var_58], rsi
0x18004d428  lea     rcx, [rbx+0E8h]
0x18004d42f  lea     rdx, [rbp+var_58]
0x18004d433  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d438  lea     rcx, [rbp+var_58]; this
0x18004d43c  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d441  nop
0x18004d442  lea     rcx, [rbp+var_50]; this
0x18004d446  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d44b  cmp     [rbx+128h], rsi
0x18004d452  jz      short loc_18004D47B
0x18004d454  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004d45b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004d460  test    al, al
0x18004d462  jz      short loc_18004D46E
0x18004d464  mov     dword ptr [rbx+100h], 5
0x18004d46e  mov     rcx, [rbx+128h]; hWnd
0x18004d475  call    cs:__imp_DestroyWindow
0x18004d47b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004d482  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004d487  test    al, al
0x18004d489  jz      short loc_18004D495
0x18004d48b  mov     dword ptr [rbx+100h], 6
0x18004d495  mov     [rbp+var_50], rbx
0x18004d499  lea     rcx, [rbp+var_50]
0x18004d49d  call    ??$Uninitialize_Stage2_BeforeThreadShutdown_Stop@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::Uninitialize_Stage2_BeforeThreadShutdown_Stop<UXFrame *>(UXFrame * &&)
0x18004d4a2  mov     rcx, [rbp+var_10]
0x18004d4a6  xor     rcx, rsp; StackCookie
0x18004d4a9  call    __security_check_cookie
0x18004d4ae  add     rsp, 78h
0x18004d4b2  pop     rdi
0x18004d4b3  pop     rsi
0x18004d4b4  pop     rbx
0x18004d4b5  pop     rbp
0x18004d4b6  retn
0x18004d4b7  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004d4be  mov     edx, 0F0h; void *
0x18004d4c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
