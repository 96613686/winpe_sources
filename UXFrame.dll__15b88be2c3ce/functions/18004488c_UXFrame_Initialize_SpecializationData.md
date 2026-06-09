# UXFrame::Initialize(SpecializationData *)

- ea: `0x18004488c`
- end: `0x180044b0d`
- name: `?Initialize@UXFrame@@QEAAXPEAUSpecializationData@@@Z`
- size: `641`
- prototype: `void __fastcall(UXFrame *__hidden this, struct SpecializationData *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016660`

## callees

- `0x1800041c4`
- `0x180004240`
- `0x1800042f4`
- `0x1800043f4`
- `0x1800088ac`
- `0x18000ac48`
- `0x18000d0f0`
- `0x18000d810`
- `0x18000ff48`
- `0x18001047c`
- `0x18001049c`
- `0x180017164`
- `0x18001f48c`
- `0x18003c77c`
- `0x18003c7f4`
- `0x180040620`
- `0x180040cfc`
- `0x180040dc0`
- `0x18004384c`
- `0x18004488c`
- `0x18004a43c`
- `0x18004d5a8`
- `0x18004ef80`
- `0x18005a010`

## string_xrefs

- `0x180044ae9`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x180044afb`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UXFrame::Initialize(UXFrame *this, struct SpecializationData *a2)
{
  __int64 v4; // rdx
  const char *v5; // r9
  int v6; // r15d
  bool v7; // r14
  char v8; // bl
  struct IUnknown *v9; // rdx
  winrt *DispatcherQueueController; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  std::_Ref_count_base *v17; // rcx
  unsigned int v18; // eax
  int v19; // [rsp+20h] [rbp-28h]
  _BYTE v20[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v21; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  __int64 v23; // [rsp+90h] [rbp+48h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 64) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x52,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      v5);
  }
  UpdateThreadDescription(a2, v4);
  if ( a2 )
  {
    v7 = *((_QWORD *)a2 + 4) != 0;
    winrt::hstring::hstring((winrt::hstring *)&v23, L"UseWinUI3");
    v6 = (unsigned __int8)ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
                            &v23,
                            (_QWORD *)a2 + 6,
                            0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v23);
    wil::init_once__lambda_019472cbb20ec0888b6e44961382cbad___();
    v8 = ThreadManager::EnsureCompatibleWinAppSDKLoaded(ThreadManager::s_instance, v6 + 1);
  }
  else
  {
    LOBYTE(v6) = 1;
    v7 = 1;
    wil::init_once__lambda_019472cbb20ec0888b6e44961382cbad___();
    v23 = 0;
    v8 = ThreadManager::EnsureCompatibleWinAppSDKLoaded(ThreadManager::s_instance, 2);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
  }
  if ( !v8 && v7 )
  {
    v18 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      (const char *)v18,
      v19);
  }
  DispatcherQueueController = MakeDispatcherQueueController((winrt *)&v23, v9);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 224, DispatcherQueueController);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
  v11 = winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
          (char *)this + 224,
          &v23);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 232, v11);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
  if ( (_BYTE)v6 )
  {
    v12 = winrt::Microsoft::UI::Dispatching::DispatcherQueueController::CreateOnCurrentThread();
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 240, v12);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
    v13 = winrt::Microsoft::UI::Dispatching::DispatcherQueue::GetForCurrentThread();
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 248, v13);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
  }
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + 264);
  if ( v7 )
  {
    UXFrame::CreateFrameWindow(this, a2);
    if ( (_BYTE)v6 )
      v14 = (__int64 *)std::make_shared<LiftedXamlHostBehavior,>(v20);
    else
      v14 = (__int64 *)std::make_shared<SystemXamlHostBehavior,>(v20);
    v15 = *v14;
    v16 = v14[1];
    *v14 = 0;
    v14[1] = 0;
    *((_QWORD *)this + 24) = v15;
    v17 = (std::_Ref_count_base *)*((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = v16;
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
    (***((void (__fastcall ****)(_QWORD, UXFrame *, _QWORD, char *))this + 24))(
      *((_QWORD *)this + 24),
      this,
      *((_QWORD *)this + 37),
      (char *)this + 232);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 24) + 40LL))(*((_QWORD *)this + 24));
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    *((_DWORD *)this + 64) = 1;
  if ( a2 )
    UXFrame::SpecializeForExtension((__int64)this, a2, 0);
}

```

## disassembly

```asm
0x18004488c  push    rbp
0x18004488e  push    rbx
0x18004488f  push    rsi
0x180044890  push    rdi
0x180044891  push    r14
0x180044893  push    r15
0x180044895  mov     rbp, rsp
0x180044898  sub     rsp, 48h
0x18004489c  mov     rsi, rdx
0x18004489f  mov     rdi, rcx
0x1800448a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x1800448a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x1800448ae  test    al, al
0x1800448b0  jz      short loc_1800448C3
0x1800448b2  mov     rcx, [rbp+30h]; this
0x1800448b6  cmp     dword ptr [rdi+100h], 0
0x1800448bd  jnz     loc_180044AFB
0x1800448c3  mov     rcx, rsi; struct SpecializationData *
0x1800448c6  call    ?UpdateThreadDescription@@YAXPEAUSpecializationData@@@Z; UpdateThreadDescription(SpecializationData *)
0x1800448cb  test    rsi, rsi
0x1800448ce  jnz     short loc_180044901
0x1800448d0  mov     r15b, 1
0x1800448d3  mov     r14b, r15b
0x1800448d6  xor     dl, dl
0x1800448d8  call    wil__init_once__lambda_019472cbb20ec0888b6e44961382cbad___
0x1800448dd  mov     [rbp+arg_10], rsi
0x1800448e1  lea     r8, [rbp+arg_10]
0x1800448e5  lea     edx, [rsi+2]
0x1800448e8  mov     rcx, cs:?s_instance@ThreadManager@@0PEAV1@EA; ThreadManager * ThreadManager::s_instance
0x1800448ef  call    ?EnsureCompatibleWinAppSDKLoaded@ThreadManager@@QEAA_NW4XamlFlavor@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; ThreadManager::EnsureCompatibleWinAppSDKLoaded(XamlFlavor,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800448f4  mov     bl, al
0x1800448f6  lea     rcx, [rbp+arg_10]; this
0x1800448fa  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800448ff  jmp     short loc_180044955
0x180044901  cmp     qword ptr [rsi+20h], 0
0x180044906  setnz   r14b
0x18004490a  lea     rdx, aUsewinui3; "UseWinUI3"
0x180044911  lea     rcx, [rbp+arg_10]; this
0x180044915  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18004491a  nop
0x18004491b  xor     r8d, r8d
0x18004491e  lea     rdx, [rsi+30h]
0x180044922  lea     rcx, [rbp+arg_10]
0x180044926  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x18004492b  movzx   r15d, al
0x18004492f  lea     rcx, [rbp+arg_10]
0x180044933  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180044938  xor     dl, dl
0x18004493a  call    wil__init_once__lambda_019472cbb20ec0888b6e44961382cbad___
0x18004493f  lea     edx, [r15+1]
0x180044943  lea     r8, [rsi+30h]
0x180044947  mov     rcx, cs:?s_instance@ThreadManager@@0PEAV1@EA; ThreadManager * ThreadManager::s_instance
0x18004494e  call    ?EnsureCompatibleWinAppSDKLoaded@ThreadManager@@QEAA_NW4XamlFlavor@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; ThreadManager::EnsureCompatibleWinAppSDKLoaded(XamlFlavor,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180044953  mov     bl, al
0x180044955  test    bl, bl
0x180044957  jnz     short loc_180044962
0x180044959  test    r14b, r14b
0x18004495c  jnz     loc_180044AD8
0x180044962  lea     rcx, [rbp+arg_10]
0x180044966  call    ?MakeDispatcherQueueController@@YA?AUDispatcherQueueController@System@Windows@winrt@@XZ; MakeDispatcherQueueController(void)
0x18004496b  lea     rbx, [rdi+0E0h]
0x180044972  mov     rdx, rax
0x180044975  mov     rcx, rbx
0x180044978  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004497d  lea     rcx, [rbp+arg_10]; this
0x180044981  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044986  lea     rdx, [rbp+arg_10]
0x18004498a  mov     rcx, rbx
0x18004498d  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180044992  lea     rbx, [rdi+0E8h]
0x180044999  mov     rdx, rax
0x18004499c  mov     rcx, rbx
0x18004499f  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800449a4  lea     rcx, [rbp+arg_10]; this
0x1800449a8  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800449ad  test    r15b, r15b
0x1800449b0  jz      short loc_1800449F4
0x1800449b2  lea     rcx, [rbp+arg_10]
0x1800449b6  call    ?CreateOnCurrentThread@DispatcherQueueController@Dispatching@UI@Microsoft@winrt@@SA@XZ; winrt::Microsoft::UI::Dispatching::DispatcherQueueController::CreateOnCurrentThread(void)
0x1800449bb  lea     rcx, [rdi+0F0h]
0x1800449c2  mov     rdx, rax
0x1800449c5  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800449ca  lea     rcx, [rbp+arg_10]; this
0x1800449ce  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800449d3  lea     rcx, [rbp+arg_10]
0x1800449d7  call    ?GetForCurrentThread@DispatcherQueue@Dispatching@UI@Microsoft@winrt@@SA@XZ; winrt::Microsoft::UI::Dispatching::DispatcherQueue::GetForCurrentThread(void)
0x1800449dc  lea     rcx, [rdi+0F8h]
0x1800449e3  mov     rdx, rax
0x1800449e6  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800449eb  lea     rcx, [rbp+arg_10]; this
0x1800449ef  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800449f4  lea     rcx, [rdi+108h]
0x1800449fb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180044a00  test    r14b, r14b
0x180044a03  jz      loc_180044A9E
0x180044a09  mov     rdx, rsi; struct SpecializationData *
0x180044a0c  mov     rcx, rdi; this
0x180044a0f  call    ?CreateFrameWindow@UXFrame@@AEAAXPEBUSpecializationData@@@Z; UXFrame::CreateFrameWindow(SpecializationData const *)
0x180044a14  lea     rcx, [rbp+var_18]
0x180044a18  test    r15b, r15b
0x180044a1b  jz      short loc_180044A24
0x180044a1d  call    ??$make_shared@VLiftedXamlHostBehavior@@$$V@std@@YA?AV?$shared_ptr@VLiftedXamlHostBehavior@@@0@XZ; std::make_shared<LiftedXamlHostBehavior,>(void)
0x180044a22  jmp     short loc_180044A29
0x180044a24  call    ??$make_shared@VSystemXamlHostBehavior@@$$V@std@@YA?AV?$shared_ptr@VSystemXamlHostBehavior@@@0@XZ; std::make_shared<SystemXamlHostBehavior,>(void)
0x180044a29  mov     rcx, [rax]
0x180044a2c  mov     rdx, [rax+8]
0x180044a30  mov     qword ptr [rax], 0
0x180044a37  mov     qword ptr [rax+8], 0
0x180044a3f  mov     [rdi+0C0h], rcx
0x180044a46  mov     rcx, [rdi+0C8h]; this
0x180044a4d  test    rcx, rcx
0x180044a50  mov     [rdi+0C8h], rdx
0x180044a57  jz      short loc_180044A5E
0x180044a59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180044a5e  mov     rcx, [rbp+var_10]; this
0x180044a62  test    rcx, rcx
0x180044a65  jz      short loc_180044A6C
0x180044a67  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180044a6c  mov     rcx, [rdi+0C0h]
0x180044a73  mov     rax, [rcx]
0x180044a76  mov     r9, rbx
0x180044a79  mov     r8, [rdi+128h]
0x180044a80  mov     rdx, rdi
0x180044a83  mov     rax, [rax]
0x180044a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a8b  mov     rcx, [rdi+0C0h]
0x180044a92  mov     rax, [rcx]
0x180044a95  mov     rax, [rax+28h]
0x180044a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a9e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x180044aa5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x180044aaa  test    al, al
0x180044aac  jz      short loc_180044AB8
0x180044aae  mov     dword ptr [rdi+100h], 1
0x180044ab8  test    rsi, rsi
0x180044abb  jz      short loc_180044ACB
0x180044abd  xor     r8d, r8d
0x180044ac0  mov     rdx, rsi
0x180044ac3  mov     rcx, rdi
0x180044ac6  call    ?SpecializeForExtension@UXFrame@@AEAAXAEAUSpecializationData@@W4SpecializationType@1@@Z; UXFrame::SpecializeForExtension(SpecializationData &,UXFrame::SpecializationType)
0x180044acb  add     rsp, 48h
0x180044acf  pop     r15
0x180044ad1  pop     r14
0x180044ad3  pop     rdi
0x180044ad4  pop     rsi
0x180044ad5  pop     rbx
0x180044ad6  pop     rbp
0x180044ad7  retn
0x180044ad8  mov     ecx, 80070057h
0x180044add  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180044ae2  mov     r9d, eax; char *
0x180044ae5  mov     rcx, [rbp+30h]; this
0x180044ae9  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x180044af0  mov     edx, 71h ; 'q'; void *
0x180044af5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180044afb  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x180044b02  mov     edx, 52h ; 'R'; void *
0x180044b07  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
