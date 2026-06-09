# UXFrame::OnIslandReadyForContent(void)

- ea: `0x180046cb0`
- end: `0x180047048`
- name: `?OnIslandReadyForContent@UXFrame@@UEAAXXZ`
- size: `920`
- prototype: `void __fastcall(UXFrame *__hidden this)`
- caller_count: `0`
- callee_count: `31`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043f4`
- `0x1800049ac`
- `0x180006698`
- `0x1800089c0`
- `0x18000d0f0`
- `0x18000d810`
- `0x18000edc0`
- `0x18001047c`
- `0x180017164`
- `0x1800176b0`
- `0x180019f74`
- `0x18001f48c`
- `0x180021e6c`
- `0x1800220c8`
- `0x1800221e4`
- `0x180026698`
- `0x180026720`
- `0x180034cb0`
- `0x180037808`
- `0x180038544`
- `0x1800385d0`
- `0x18003a140`
- `0x18003a410`
- `0x180045554`
- `0x180046cb0`
- `0x18004d714`
- `0x18004db68`
- `0x18005a010`

## import_xrefs

- `USER32!DestroyWindow` at `0x180046fe0`
- `USER32!DestroyWindow` at `0x180046fe0`

## string_xrefs

- `0x180047036`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall UXFrame::OnIslandReadyForContent(UXFrame *this)
{
  char *v2; // rdi
  UXFrame *v3; // rax
  char *v4; // r14
  char *v5; // rax
  char *v6; // rbx
  UXFrame *v7; // rax
  char v8; // bl
  __int64 *v9; // r15
  __int64 v10; // r13
  __int64 v11; // rax
  UXFrame **v12; // rax
  UXFrame *v13; // rcx
  char v14; // r12
  UXFrame *v15; // r15
  __int64 v16; // rdx
  __int64 v17; // r8
  const char *v18; // r9
  UXFrame *v19; // rbx
  __int64 v20; // rax
  char *v21; // r14
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, UXFrame **); // rbx
  __int64 v24; // rax
  tip2 *v25; // rcx
  unsigned int v26; // eax
  int v27; // [rsp+20h] [rbp-69h] BYREF
  UXFrame *v28; // [rsp+28h] [rbp-61h] BYREF
  __int64 *v29; // [rsp+30h] [rbp-59h] BYREF
  UXFrame *v30; // [rsp+38h] [rbp-51h] BYREF
  char *v31; // [rsp+40h] [rbp-49h] BYREF
  __int64 v32[4]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v33[4]; // [rsp+68h] [rbp-21h] BYREF
  UXFrame *v34; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( *((_BYTE *)this + 56) )
  {
    v2 = (char *)this + 136;
    if ( *((_QWORD *)this + 20) <= 7u )
      v3 = (UXFrame *)((char *)this + 136);
    else
      v3 = *(UXFrame **)v2;
    v34 = v3;
    v4 = (char *)this + 104;
    if ( *((_QWORD *)this + 16) <= 7u )
      v5 = (char *)this + 104;
    else
      v5 = *(char **)v4;
    v31 = v5;
    v6 = (char *)this + 72;
    if ( *((_QWORD *)this + 12) <= 7u )
      v7 = (UXFrame *)((char *)this + 72);
    else
      v7 = *(UXFrame **)v6;
    v28 = v7;
    v29 = (__int64 *)this;
    UXFrameTelemetry::OnIslandReadyForContent_Start<UXFrame *,wchar_t const *,wchar_t const *,wchar_t const *>(
      &v29,
      &v28,
      &v31,
      &v34);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(char **)v6;
    winrt::param::hstring::hstring((winrt::param::hstring *)v32, (const wchar_t *const)v6);
    winrt::WindowsUdk::ApplicationModel::AppExtensions::XamlExtensions::GetForCategory(
      (const struct winrt::param::hstring *)&v29,
      (__int64)v32);
    winrt::hstring::hstring((winrt::hstring *)&v28, L"UseWinUI3");
    v8 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
           &v28,
           (_QWORD *)this + 22,
           0);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v28);
    v9 = (__int64 *)*((_QWORD *)this + 24);
    v10 = *v9;
    if ( v8 )
    {
      v11 = winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions4<winrt::WindowsUdk::ApplicationModel::AppExtensions::XamlExtensions>::MicrosoftUIXamlMarkupXamlMetadataProvider(
              &v29,
              &v34);
      (*(void (__fastcall **)(__int64 *, __int64))(v10 + 64))(v9, v11);
    }
    else
    {
      v12 = (UXFrame **)winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions<winrt::WindowsUdk::ApplicationModel::AppExtensions::IXamlExtensions>::XamlMetadataProvider(
                          &v29,
                          &v34);
      v13 = *v12;
      *v12 = 0;
      v28 = v13;
      (*(void (__fastcall **)(__int64 *, UXFrame **))(v10 + 64))(v9, &v28);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v34);
    }
    v14 = 0;
    LOWORD(v27) = 0;
    v15 = 0;
    v30 = 0;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(char **)v2;
    winrt::param::hstring::hstring((winrt::param::hstring *)v32, (const wchar_t *const)v2);
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(char **)v4;
    winrt::param::hstring::hstring((winrt::param::hstring *)v33, (const wchar_t *const)v4);
    winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions<winrt::WindowsUdk::ApplicationModel::AppExtensions::IXamlExtensions>::GetFactoryFromExtension(
      &v29,
      &v34,
      v33,
      v32);
    v19 = v34;
    if ( v34 )
    {
      UXFrame::WaitForDebuggerForComponentIfNecessary(this, v16, v17, v18);
      winrt::impl::as<winrt::Windows::Foundation::IActivationFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
        &v31,
        v19);
      v20 = winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::IInspectable>(
              &v31,
              &v28);
      winrt::Windows::Foundation::IUnknown::operator=(&v30, v20);
      if ( v28 )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v28);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v31);
      v15 = v30;
    }
    if ( v19 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v34);
    if ( v15 )
    {
      v14 = 1;
      BYTE1(v27) = 1;
      winrt::Windows::Foundation::IUnknown::operator=((UXFrame *)((char *)this + 272));
      v21 = (char *)this + 448;
      if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool((char *)this + 448) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(
                                (char *)this + 448,
                                &v34)
                 + 305LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(&v34);
      }
      v22 = *((_QWORD *)this + 24);
      v23 = *(void (__fastcall **)(__int64, UXFrame **))(*(_QWORD *)v22 + 24LL);
      v28 = v15;
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v28);
      v23(v22, &v28);
      v34 = 0;
      (**(void (__fastcall ***)(UXFrame *, void *, UXFrame **))v15)(
        v15,
        &winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellContent>,
        &v34);
      v28 = v34;
      if ( v34 )
      {
        LOBYTE(v27) = 1;
        v24 = winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::as<winrt::WindowsUdk::UI::Shell::ShellContentHost>(
                (char *)this + 304,
                &v34);
        winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(
          &v28,
          v24);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v34);
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
    }
    else
    {
      v21 = (char *)this + 448;
    }
    v34 = this;
    UXFrameTelemetry::OnIslandReadyForContent_Stop<UXFrame *,bool &,bool &>(&v34, (char *)&v27 + 1, &v27);
    if ( !v14 )
    {
      if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool(v21) )
        tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(v21);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
      {
        tip2::persist_cached_test_results(v25);
        v26 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1FE,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          (const char *)v26,
          v27);
      }
      DestroyWindow(*((HWND *)this + 37));
    }
    if ( v15 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v30);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  }
}

```

## disassembly

```asm
0x180046cb0  push    rbp
0x180046cb2  push    rbx
0x180046cb3  push    rsi
0x180046cb4  push    rdi
0x180046cb5  push    r12
0x180046cb7  push    r13
0x180046cb9  push    r14
0x180046cbb  push    r15
0x180046cbd  lea     rbp, [rsp-1Fh]
0x180046cc2  sub     rsp, 0A8h
0x180046cc9  mov     rax, cs:__security_cookie
0x180046cd0  xor     rax, rsp
0x180046cd3  mov     [rbp+57h+var_50], rax
0x180046cd7  mov     rsi, rcx
0x180046cda  xor     r12d, r12d
0x180046cdd  cmp     [rcx+38h], r12b
0x180046ce1  jz      loc_180046FFF
0x180046ce7  lea     rdi, [rcx+88h]
0x180046cee  cmp     qword ptr [rdi+18h], 7
0x180046cf3  jbe     short loc_180046CFA
0x180046cf5  mov     rax, [rdi]
0x180046cf8  jmp     short loc_180046CFD
0x180046cfa  mov     rax, rdi
0x180046cfd  mov     [rbp+57h+var_58], rax
0x180046d01  lea     r14, [rcx+68h]
0x180046d05  cmp     qword ptr [r14+18h], 7
0x180046d0a  jbe     short loc_180046D11
0x180046d0c  mov     rax, [r14]
0x180046d0f  jmp     short loc_180046D14
0x180046d11  mov     rax, r14
0x180046d14  mov     [rbp+57h+var_A0], rax
0x180046d18  lea     rbx, [rcx+48h]
0x180046d1c  cmp     qword ptr [rbx+18h], 7
0x180046d21  jbe     short loc_180046D28
0x180046d23  mov     rax, [rbx]
0x180046d26  jmp     short loc_180046D2B
0x180046d28  mov     rax, rbx
0x180046d2b  mov     [rbp+57h+var_B8], rax
0x180046d2f  mov     [rbp+57h+var_B0], rsi
0x180046d33  lea     r9, [rbp+57h+var_58]
0x180046d37  lea     r8, [rbp+57h+var_A0]
0x180046d3b  lea     rdx, [rbp+57h+var_B8]
0x180046d3f  lea     rcx, [rbp+57h+var_B0]
0x180046d43  call    ??$OnIslandReadyForContent_Start@PEAVUXFrame@@PEB_WPEB_WPEB_W@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@$$QEAPEB_W11@Z; UXFrameTelemetry::OnIslandReadyForContent_Start<UXFrame *,wchar_t const *,wchar_t const *,wchar_t const *>(UXFrame * &&,wchar_t const * &&,wchar_t const * &&,wchar_t const * &&)
0x180046d48  cmp     qword ptr [rbx+18h], 7
0x180046d4d  jbe     short loc_180046D52
0x180046d4f  mov     rbx, [rbx]
0x180046d52  mov     rdx, rbx; wchar_t *
0x180046d55  lea     rcx, [rbp+57h+var_98]; this
0x180046d59  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180046d5e  lea     rdx, [rbp+57h+var_98]
0x180046d62  lea     rcx, [rbp+57h+var_B0]; struct winrt::param::hstring *
0x180046d66  call    ?GetForCategory@XamlExtensions@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::XamlExtensions::GetForCategory(winrt::param::hstring const &)
0x180046d6b  nop
0x180046d6c  lea     rdx, aUsewinui3; "UseWinUI3"
0x180046d73  lea     rcx, [rbp+57h+var_B8]; this
0x180046d77  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180046d7c  nop
0x180046d7d  lea     rdx, [rsi+0B0h]
0x180046d84  xor     r8d, r8d
0x180046d87  lea     rcx, [rbp+57h+var_B8]
0x180046d8b  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x180046d90  mov     bl, al
0x180046d92  lea     rcx, [rbp+57h+var_B8]
0x180046d96  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180046d9b  mov     r15, [rsi+0C0h]
0x180046da2  mov     r13, [r15]
0x180046da5  lea     rdx, [rbp+57h+var_58]
0x180046da9  lea     rcx, [rbp+57h+var_B0]
0x180046dad  test    bl, bl
0x180046daf  jz      short loc_180046DC7
0x180046db1  call    ?MicrosoftUIXamlMarkupXamlMetadataProvider@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions4@UXamlExtensions@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions4<winrt::WindowsUdk::ApplicationModel::AppExtensions::XamlExtensions>::MicrosoftUIXamlMarkupXamlMetadataProvider(void)
0x180046db6  mov     rdx, rax
0x180046db9  mov     rcx, r15
0x180046dbc  mov     rax, [r13+40h]
0x180046dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dc5  jmp     short loc_180046DF1
0x180046dc7  call    ?XamlMetadataProvider@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions@UIXamlExtensions@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions<winrt::WindowsUdk::ApplicationModel::AppExtensions::IXamlExtensions>::XamlMetadataProvider(void)
0x180046dcc  nop
0x180046dcd  mov     rcx, [rax]
0x180046dd0  mov     [rax], r12
0x180046dd3  mov     [rbp+57h+var_B8], rcx
0x180046dd7  lea     rdx, [rbp+57h+var_B8]
0x180046ddb  mov     rcx, r15
0x180046dde  mov     rax, [r13+40h]
0x180046de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046de7  nop
0x180046de8  lea     rcx, [rbp+57h+var_58]; this
0x180046dec  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046df1  xor     r13d, r13d
0x180046df4  mov     r12b, r13b
0x180046df7  mov     [rbp+57h+var_BF], r13b
0x180046dfb  mov     [rbp+57h+var_C0], r13b
0x180046dff  mov     r15d, r13d
0x180046e02  mov     [rbp+57h+var_A8], r13
0x180046e06  cmp     qword ptr [rdi+18h], 7
0x180046e0b  jbe     short loc_180046E10
0x180046e0d  mov     rdi, [rdi]
0x180046e10  mov     rdx, rdi; wchar_t *
0x180046e13  lea     rcx, [rbp+57h+var_98]; this
0x180046e17  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180046e1c  cmp     qword ptr [r14+18h], 7
0x180046e21  jbe     short loc_180046E26
0x180046e23  mov     r14, [r14]
0x180046e26  mov     rdx, r14; wchar_t *
0x180046e29  lea     rcx, [rbp+57h+var_78]; this
0x180046e2d  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180046e32  lea     r9, [rbp+57h+var_98]
0x180046e36  lea     r8, [rbp+57h+var_78]
0x180046e3a  lea     rdx, [rbp+57h+var_58]
0x180046e3e  lea     rcx, [rbp+57h+var_B0]
0x180046e42  call    ?GetFactoryFromExtension@?$consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions@UIXamlExtensions@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_WindowsUdk_ApplicationModel_AppExtensions_IXamlExtensions<winrt::WindowsUdk::ApplicationModel::AppExtensions::IXamlExtensions>::GetFactoryFromExtension(winrt::param::hstring const &,winrt::param::hstring const &)
0x180046e47  nop
0x180046e48  mov     rbx, [rbp+57h+var_58]
0x180046e4c  test    rbx, rbx
0x180046e4f  jz      short loc_180046E9C
0x180046e51  mov     rcx, rsi; this
0x180046e54  call    ?WaitForDebuggerForComponentIfNecessary@UXFrame@@AEAAXXZ; UXFrame::WaitForDebuggerForComponentIfNecessary(void)
0x180046e59  mov     rdx, rbx
0x180046e5c  lea     rcx, [rbp+57h+var_A0]
0x180046e60  call    ??$as@UIActivationFactory@Foundation@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@4@$0A@@impl@winrt@@YA?AUIActivationFactory@Foundation@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::Foundation::IActivationFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180046e65  nop
0x180046e66  lea     rdx, [rbp+57h+var_B8]
0x180046e6a  lea     rcx, [rbp+57h+var_A0]
0x180046e6e  call    ??$ActivateInstance@UIInspectable@Foundation@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUIInspectable@123@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::IInspectable>(void)
0x180046e73  mov     rdx, rax
0x180046e76  lea     rcx, [rbp+57h+var_A8]
0x180046e7a  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180046e7f  cmp     [rbp+57h+var_B8], r13
0x180046e83  jz      short loc_180046E8F
0x180046e85  lea     rcx, [rbp+57h+var_B8]
0x180046e89  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180046e8e  nop
0x180046e8f  lea     rcx, [rbp+57h+var_A0]; this
0x180046e93  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046e98  mov     r15, [rbp+57h+var_A8]
0x180046e9c  test    rbx, rbx
0x180046e9f  jz      short loc_180046EAA
0x180046ea1  lea     rcx, [rbp+57h+var_58]
0x180046ea5  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180046eaa  test    r15, r15
0x180046ead  jnz     short loc_180046EBB
0x180046eaf  lea     r14, [rsi+1C0h]
0x180046eb6  jmp     loc_180046F9B
0x180046ebb  mov     r12b, 1
0x180046ebe  mov     [rbp+57h+var_BF], r12b
0x180046ec2  lea     rcx, [rsi+110h]; this
0x180046ec9  lea     rdx, [rbp+57h+var_A8]
0x180046ecd  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x180046ed2  lea     r14, [rsi+1C0h]
0x180046ed9  mov     rcx, r14
0x180046edc  call    ??B?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool(void)
0x180046ee1  test    al, al
0x180046ee3  jz      short loc_180046F04
0x180046ee5  lea     rdx, [rbp+57h+var_58]
0x180046ee9  mov     rcx, r14
0x180046eec  call    ??C?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(void)
0x180046ef1  mov     rcx, [rax]
0x180046ef4  mov     [rcx+131h], r12b
0x180046efb  lea     rcx, [rbp+57h+var_58]
0x180046eff  call    ??1?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(void)
0x180046f04  mov     rdi, [rsi+0C0h]
0x180046f0b  mov     rax, [rdi]
0x180046f0e  mov     rbx, [rax+18h]
0x180046f12  mov     [rbp+57h+var_B8], r15
0x180046f16  lea     rcx, [rbp+57h+var_B8]; this
0x180046f1a  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180046f1f  lea     rdx, [rbp+57h+var_B8]
0x180046f23  mov     rcx, rdi
0x180046f26  mov     rax, rbx
0x180046f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f2e  test    r15, r15
0x180046f31  jnz     short loc_180046F3C
0x180046f33  mov     [rbp+57h+var_B8], r13
0x180046f37  mov     rax, r13
0x180046f3a  jmp     short loc_180046F61
0x180046f3c  mov     [rbp+57h+var_58], r13
0x180046f40  mov     rax, [r15]
0x180046f43  lea     r8, [rbp+57h+var_58]
0x180046f47  lea     rdx, ??$guid_v@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellContent>
0x180046f4e  mov     rcx, r15
0x180046f51  mov     rax, [rax]
0x180046f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f59  mov     rax, [rbp+57h+var_58]
0x180046f5d  mov     [rbp+57h+var_B8], rax
0x180046f61  test    rax, rax
0x180046f64  jz      short loc_180046F92
0x180046f66  mov     [rbp+57h+var_C0], r12b
0x180046f6a  lea     rcx, [rsi+130h]
0x180046f71  lea     rdx, [rbp+57h+var_58]
0x180046f75  call    ??$as@UShellContentHost@Shell@UI@WindowsUdk@winrt@@@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEBA?A_PXZ
0x180046f7a  nop
0x180046f7b  mov     rdx, rax
0x180046f7e  lea     rcx, [rbp+57h+var_B8]
0x180046f82  call    ?SetHost@?$consume_WindowsUdk_UI_Shell_IShellContent@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUShellContentHost@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(winrt::WindowsUdk::UI::Shell::ShellContentHost const &)
0x180046f87  nop
0x180046f88  lea     rcx, [rbp+57h+var_58]; this
0x180046f8c  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046f91  nop
0x180046f92  lea     rcx, [rbp+57h+var_B8]; this
0x180046f96  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046f9b  mov     [rbp+57h+var_58], rsi
0x180046f9f  lea     r8, [rbp+57h+var_C0]
0x180046fa3  lea     rdx, [rbp+57h+var_BF]
0x180046fa7  lea     rcx, [rbp+57h+var_58]
0x180046fab  call    ??$OnIslandReadyForContent_Stop@PEAVUXFrame@@AEA_NAEA_N@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@AEA_N1@Z; UXFrameTelemetry::OnIslandReadyForContent_Stop<UXFrame *,bool &,bool &>(UXFrame * &&,bool &,bool &)
0x180046fb0  test    r12b, r12b
0x180046fb3  jnz     short loc_180046FE7
0x180046fb5  mov     rcx, r14
0x180046fb8  call    ??B?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEBA_NXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator bool(void)
0x180046fbd  test    al, al
0x180046fbf  jz      short loc_180046FC9
0x180046fc1  mov     rcx, r14
0x180046fc4  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x180046fc9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x180046fd0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x180046fd5  test    al, al
0x180046fd7  jnz     short loc_18004701F
0x180046fd9  mov     rcx, [rsi+128h]; hWnd
0x180046fe0  call    cs:__imp_DestroyWindow
0x180046fe6  nop
0x180046fe7  test    r15, r15
0x180046fea  jz      short loc_180046FF6
0x180046fec  lea     rcx, [rbp+57h+var_A8]
0x180046ff0  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180046ff5  nop
0x180046ff6  lea     rcx, [rbp+57h+var_B0]; this
0x180046ffa  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046fff  mov     rcx, [rbp+57h+var_50]
0x180047003  xor     rcx, rsp; StackCookie
0x180047006  call    __security_check_cookie
0x18004700b  add     rsp, 0A8h
0x180047012  pop     r15
0x180047014  pop     r14
0x180047016  pop     r13
0x180047018  pop     r12
0x18004701a  pop     rdi
0x18004701b  pop     rsi
0x18004701c  pop     rbx
0x18004701d  pop     rbp
0x18004701e  retn
0x18004701f  call    ?persist_cached_test_results@tip2@@YAXXZ; tip2::persist_cached_test_results(void)
0x180047024  nop
0x180047025  mov     ecx, 80004005h
0x18004702a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004702f  mov     r9d, eax; char *
0x180047032  mov     rcx, [rbp+5Fh]; this
0x180047036  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004703d  mov     edx, 1FEh; void *
0x180047042  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
