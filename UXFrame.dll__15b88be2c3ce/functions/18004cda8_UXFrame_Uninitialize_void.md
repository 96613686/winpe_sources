# UXFrame::Uninitialize(void)

- ea: `0x18004cda8`
- end: `0x18004d0b2`
- name: `?Uninitialize@UXFrame@@QEAAXXZ`
- size: `778`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `1`
- callee_count: `25`
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
- `0x18000ef98`
- `0x18001049c`
- `0x180017164`
- `0x18001c890`
- `0x18002c4c0`
- `0x180034cb0`
- `0x1800395d4`
- `0x18003edd0`
- `0x180041fd0`
- `0x18004a200`
- `0x18004a2c8`
- `0x18004cc24`
- `0x18004cda8`
- `0x18004d4d0`
- `0x18004e8f4`
- `0x18004fbbc`
- `0x18004fc10`
- `0x18005a010`

## import_xrefs

- `USER32!DestroyWindow` at `0x18004d082`
- `USER32!DestroyWindow` at `0x18004d082`
- `USER32!GetMessageW` at `0x18004d02c`
- `USER32!GetMessageW` at `0x18004d02c`
- `USER32!TranslateMessage` at `0x18004d010`
- `USER32!TranslateMessage` at `0x18004d010`
- `USER32!DispatchMessageW` at `0x18004d01a`
- `USER32!DispatchMessageW` at `0x18004d01a`

## string_xrefs

- `0x18004d09d`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UXFrame::Uninitialize(UXFrame *this)
{
  const char *v2; // r9
  __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // r9
  SingletonHelpers::SingletonHelper *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  _DWORD *v12; // rax
  HWND v13; // rcx
  _DWORD *v14; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+28h] [rbp-50h] BYREF
  MSG Msg; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x13E,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      v2);
  v15[0] = this;
  UXFrameTelemetry::Uninitialize<UXFrame *>(v15);
  FlowEndpointBase::FlushMessages((UXFrame *)((char *)this + 312));
  FlowEndpointBase::Uninitialize((UXFrame *)((char *)this + 312));
  v6 = (SingletonHelpers::SingletonHelper *)*((_QWORD *)this + 57);
  if ( v6 )
  {
    SingletonHelpers::SingletonHelper::UnregisterForRedirectedLaunches(v6, v3, v4, v5);
    v7 = *((_QWORD *)this + 57);
    *((_QWORD *)this + 57) = 0;
    if ( v7 )
      std::default_delete<SingletonHelpers::SingletonHelper>::operator()();
  }
  std::shared_ptr<ThreadpoolProcessWatcher>::reset((char *)this + 704);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_46702346>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_46702346>::GetImpl'::`2'::impl) )
    std::_Optional_destruct_base<DirectLaunch::DirectLaunchListener,0>::reset((char *)this + 464);
  v8 = *((_QWORD *)this + 24);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *(_OWORD *)v15 = 0;
    __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
      (char *)this + 192,
      v15);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
  }
  v9 = (winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost *)*((_QWORD *)this + 38);
  if ( v9 )
  {
    winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::Uninitialize(v9);
    v14 = 0;
    winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=((char *)this + 304, &v14);
    if ( v14 )
      winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(&v14);
  }
  v10 = *((_QWORD *)this + 26);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 80LL))(v10);
    *(_OWORD *)v15 = 0;
    __4__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__QEAAAEAV01___QEAV01__Z(
      (char *)this + 208,
      v15);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
  }
  v11 = *((_QWORD *)this + 35);
  if ( v11 )
  {
    *(_QWORD *)(v11 + 32) = 0;
    v14 = 0;
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 280, &v14);
    if ( v14 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v14);
  }
  v14 = 0;
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 272, &v14);
  if ( v14 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v14);
  if ( *((_QWORD *)this + 30) )
  {
    winrt::impl::consume_Microsoft_UI_Dispatching_IDispatcherQueueController2<winrt::Microsoft::UI::Dispatching::DispatcherQueueController>::ShutdownQueue((char *)this + 240);
    v14 = 0;
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 240, &v14);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v14);
    v14 = 0;
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 248, &v14);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v14);
  }
  if ( *((_QWORD *)this + 28) )
  {
    winrt::impl::consume_Windows_System_IDispatcherQueueController<winrt::Windows::System::IDispatcherQueueController>::ShutdownQueueAsync(
      (char *)this + 224,
      v15);
    v12 = operator new(0x10u);
    v12[2] = 1;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *(_QWORD *)v12 = off_18005E780;
    v14 = v12;
    winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(
      v15,
      &v14);
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v14);
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    v14 = 0;
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 224, &v14);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v14);
    v14 = 0;
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 232, &v14);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v14);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v15);
  }
  v13 = (HWND)*((_QWORD *)this + 37);
  if ( v13 )
    DestroyWindow(v13);
}

```

## disassembly

```asm
0x18004cda8  push    rbp
0x18004cdaa  push    rbx
0x18004cdab  push    rsi
0x18004cdac  push    rdi
0x18004cdad  mov     rbp, rsp
0x18004cdb0  sub     rsp, 78h
0x18004cdb4  mov     rax, cs:__security_cookie
0x18004cdbb  xor     rax, rsp
0x18004cdbe  mov     [rbp+var_10], rax
0x18004cdc2  mov     rdi, rcx
0x18004cdc5  xor     esi, esi
0x18004cdc7  mov     rbx, [rbp+20h]
0x18004cdcb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004cdd2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004cdd7  test    al, al
0x18004cdd9  jnz     loc_18004D09D
0x18004cddf  mov     [rbp+var_50], rdi
0x18004cde3  lea     rcx, [rbp+var_50]
0x18004cde7  call    ??$Uninitialize@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::Uninitialize<UXFrame *>(UXFrame * &&)
0x18004cdec  lea     rbx, [rdi+138h]
0x18004cdf3  mov     rcx, rbx; this
0x18004cdf6  call    ?FlushMessages@FlowEndpointBase@@QEAAXXZ; FlowEndpointBase::FlushMessages(void)
0x18004cdfb  mov     rcx, rbx; this
0x18004cdfe  call    ?Uninitialize@FlowEndpointBase@@QEAAXXZ; FlowEndpointBase::Uninitialize(void)
0x18004ce03  mov     rcx, [rdi+1C8h]; this
0x18004ce0a  test    rcx, rcx
0x18004ce0d  jz      short loc_18004CE2C
0x18004ce0f  call    ?UnregisterForRedirectedLaunches@SingletonHelper@SingletonHelpers@@QEAAXXZ; SingletonHelpers::SingletonHelper::UnregisterForRedirectedLaunches(void)
0x18004ce14  mov     rdx, [rdi+1C8h]
0x18004ce1b  mov     [rdi+1C8h], rsi
0x18004ce22  test    rdx, rdx
0x18004ce25  jz      short loc_18004CE2C
0x18004ce27  call    ??R?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@QEBAXPEAVSingletonHelper@SingletonHelpers@@@Z; std::default_delete<SingletonHelpers::SingletonHelper>::operator()(SingletonHelpers::SingletonHelper *)
0x18004ce2c  lea     rcx, [rdi+2C0h]
0x18004ce33  call    ?reset@?$shared_ptr@VThreadpoolProcessWatcher@@@std@@QEAAXXZ; std::shared_ptr<ThreadpoolProcessWatcher>::reset(void)
0x18004ce38  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_46702346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_46702346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46702346> `wil::Feature<__WilFeatureTraits_Feature_46702346>::GetImpl(void)'::`2'::impl
0x18004ce3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_46702346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46702346>::__private_IsEnabled(void)
0x18004ce44  test    al, al
0x18004ce46  jz      short loc_18004CE54
0x18004ce48  lea     rcx, [rdi+1D0h]
0x18004ce4f  call    ?reset@?$_Optional_destruct_base@VDirectLaunchListener@DirectLaunch@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<DirectLaunch::DirectLaunchListener,0>::reset(void)
0x18004ce54  lea     rbx, [rdi+0C0h]
0x18004ce5b  mov     rcx, [rbx]
0x18004ce5e  test    rcx, rcx
0x18004ce61  jz      short loc_18004CE91
0x18004ce63  mov     rax, [rcx]
0x18004ce66  mov     rax, [rax+10h]
0x18004ce6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce6f  xorps   xmm0, xmm0
0x18004ce72  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18004ce77  lea     rdx, [rbp+var_50]
0x18004ce7b  mov     rcx, rbx
0x18004ce7e  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004ce83  mov     rcx, [rbp+var_50+8]; this
0x18004ce87  test    rcx, rcx
0x18004ce8a  jz      short loc_18004CE91
0x18004ce8c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004ce91  lea     rbx, [rdi+130h]
0x18004ce98  mov     rcx, [rbx]; this
0x18004ce9b  test    rcx, rcx
0x18004ce9e  jz      short loc_18004CEC4
0x18004cea0  call    ?Uninitialize@ShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@QEAAXXZ; winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost::Uninitialize(void)
0x18004cea5  mov     [rbp+var_58], rsi
0x18004cea9  lea     rdx, [rbp+var_58]
0x18004cead  mov     rcx, rbx
0x18004ceb0  call    ??4?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost> &&)
0x18004ceb5  cmp     [rbp+var_58], rsi
0x18004ceb9  jz      short loc_18004CEC4
0x18004cebb  lea     rcx, [rbp+var_58]
0x18004cebf  call    ?unconditional_release_ref@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(void)
0x18004cec4  lea     rbx, [rdi+0D0h]
0x18004cecb  mov     rcx, [rbx]
0x18004cece  test    rcx, rcx
0x18004ced1  jz      short loc_18004CF01
0x18004ced3  mov     rax, [rcx]
0x18004ced6  mov     rax, [rax+50h]
0x18004ceda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cedf  xorps   xmm0, xmm0
0x18004cee2  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18004cee7  lea     rdx, [rbp+var_50]
0x18004ceeb  mov     rcx, rbx
0x18004ceee  call    ??4?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z
0x18004cef3  mov     rcx, [rbp+var_50+8]; this
0x18004cef7  test    rcx, rcx
0x18004cefa  jz      short loc_18004CF01
0x18004cefc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004cf01  lea     rcx, [rdi+118h]
0x18004cf08  mov     rax, [rcx]
0x18004cf0b  test    rax, rax
0x18004cf0e  jz      short loc_18004CF30
0x18004cf10  mov     [rax+20h], rsi
0x18004cf14  mov     [rbp+var_58], rsi
0x18004cf18  lea     rdx, [rbp+var_58]
0x18004cf1c  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004cf21  cmp     [rbp+var_58], rsi
0x18004cf25  jz      short loc_18004CF30
0x18004cf27  lea     rcx, [rbp+var_58]
0x18004cf2b  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004cf30  mov     [rbp+var_58], rsi
0x18004cf34  lea     rcx, [rdi+110h]
0x18004cf3b  lea     rdx, [rbp+var_58]
0x18004cf3f  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004cf44  cmp     [rbp+var_58], rsi
0x18004cf48  jz      short loc_18004CF53
0x18004cf4a  lea     rcx, [rbp+var_58]
0x18004cf4e  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004cf53  lea     rbx, [rdi+0F0h]
0x18004cf5a  cmp     [rbx], rsi
0x18004cf5d  jz      short loc_18004CF9D
0x18004cf5f  mov     rcx, rbx
0x18004cf62  call    ?ShutdownQueue@?$consume_Microsoft_UI_Dispatching_IDispatcherQueueController2@UDispatcherQueueController@Dispatching@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Dispatching_IDispatcherQueueController2<winrt::Microsoft::UI::Dispatching::DispatcherQueueController>::ShutdownQueue(void)
0x18004cf67  mov     [rbp+var_58], rsi
0x18004cf6b  lea     rdx, [rbp+var_58]
0x18004cf6f  mov     rcx, rbx
0x18004cf72  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004cf77  lea     rcx, [rbp+var_58]; this
0x18004cf7b  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004cf80  mov     [rbp+var_58], rsi
0x18004cf84  lea     rcx, [rdi+0F8h]
0x18004cf8b  lea     rdx, [rbp+var_58]
0x18004cf8f  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004cf94  lea     rcx, [rbp+var_58]; this
0x18004cf98  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004cf9d  lea     rbx, [rdi+0E0h]
0x18004cfa4  cmp     [rbx], rsi
0x18004cfa7  jz      loc_18004D076
0x18004cfad  lea     rdx, [rbp+var_50]
0x18004cfb1  mov     rcx, rbx
0x18004cfb4  call    ?ShutdownQueueAsync@?$consume_Windows_System_IDispatcherQueueController@UIDispatcherQueueController@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_IDispatcherQueueController<winrt::Windows::System::IDispatcherQueueController>::ShutdownQueueAsync(void)
0x18004cfb9  nop
0x18004cfba  mov     ecx, 10h; Size
0x18004cfbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004cfc4  mov     [rbp+var_58], rax
0x18004cfc8  mov     dword ptr [rax+8], 1
0x18004cfcf  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004cfd6  lea     rcx, off_18005E780
0x18004cfdd  mov     [rax], rcx
0x18004cfe0  mov     [rbp+var_58], rax
0x18004cfe4  lea     rdx, [rbp+var_58]
0x18004cfe8  lea     rcx, [rbp+var_50]
0x18004cfec  call    ?SetHost@?$consume_WindowsUdk_UI_Shell_IShellContent@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUShellContentHost@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(winrt::WindowsUdk::UI::Shell::ShellContentHost const &)
0x18004cff1  nop
0x18004cff2  lea     rcx, [rbp+var_58]
0x18004cff6  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004cffb  xorps   xmm0, xmm0
0x18004cffe  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18004d002  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18004d006  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18004d00a  jmp     short loc_18004D020
0x18004d00c  lea     rcx, [rbp+Msg]; lpMsg
0x18004d010  call    cs:__imp_TranslateMessage
0x18004d016  lea     rcx, [rbp+Msg]; lpMsg
0x18004d01a  call    cs:__imp_DispatchMessageW
0x18004d020  xor     r9d, r9d; wMsgFilterMax
0x18004d023  xor     r8d, r8d; wMsgFilterMin
0x18004d026  xor     edx, edx; hWnd
0x18004d028  lea     rcx, [rbp+Msg]; lpMsg
0x18004d02c  call    cs:__imp_GetMessageW
0x18004d032  test    eax, eax
0x18004d034  jnz     short loc_18004D00C
0x18004d036  mov     [rbp+var_58], rsi
0x18004d03a  lea     rdx, [rbp+var_58]
0x18004d03e  mov     rcx, rbx
0x18004d041  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d046  lea     rcx, [rbp+var_58]; this
0x18004d04a  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d04f  mov     [rbp+var_58], rsi
0x18004d053  lea     rcx, [rdi+0E8h]
0x18004d05a  lea     rdx, [rbp+var_58]
0x18004d05e  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d063  lea     rcx, [rbp+var_58]; this
0x18004d067  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d06c  nop
0x18004d06d  lea     rcx, [rbp+var_50]; this
0x18004d071  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d076  mov     rcx, [rdi+128h]; hWnd
0x18004d07d  test    rcx, rcx
0x18004d080  jz      short loc_18004D088
0x18004d082  call    cs:__imp_DestroyWindow
0x18004d088  mov     rcx, [rbp+var_10]
0x18004d08c  xor     rcx, rsp; StackCookie
0x18004d08f  call    __security_check_cookie
0x18004d094  add     rsp, 78h
0x18004d098  pop     rdi
0x18004d099  pop     rsi
0x18004d09a  pop     rbx
0x18004d09b  pop     rbp
0x18004d09c  retn
0x18004d09d  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004d0a4  mov     edx, 13Eh; void *
0x18004d0a9  mov     rcx, rbx; this
0x18004d0ac  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
