# SystemXamlHostBehavior::OnContentProvided(void)

- ea: `0x1800462dc`
- end: `0x1800466df`
- name: `?OnContentProvided@SystemXamlHostBehavior@@AEAAXXZ`
- size: `1027`
- prototype: `void __fastcall(SystemXamlHostBehavior *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800407c0`

## callees

- `0x180002b20`
- `0x180002b88`
- `0x1800041c4`
- `0x180004240`
- `0x1800043a0`
- `0x1800049ac`
- `0x18001049c`
- `0x1800371d8`
- `0x18003a0b0`
- `0x18003a1d0`
- `0x18003cf98`
- `0x18003e32c`
- `0x18003e7a4`
- `0x18003e7e4`
- `0x18003e83c`
- `0x180040324`
- `0x180040620`
- `0x180041030`
- `0x180045888`
- `0x1800462dc`
- `0x1800493f0`
- `0x18005a010`

## import_xrefs

- `USER32!SetFocus` at `0x18004665e`
- `USER32!SetFocus` at `0x18004665e`
- `USER32!GetActiveWindow` at `0x18004664f`
- `USER32!GetActiveWindow` at `0x18004664f`

## string_xrefs

- `0x1800466cd`: `pcshell\shell\uxframe\dll\SystemXamlHostBehavior.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall SystemXamlHostBehavior::OnContentProvided(SystemXamlHostBehavior *this)
{
  char *v2; // r14
  const char *v3; // r9
  _QWORD *v4; // rax
  _DWORD *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  _DWORD *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  _DWORD *v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // eax
  HWND v23; // rbx
  __int64 v24; // rax
  __int64 v25; // [rsp+20h] [rbp-39h] BYREF
  __int64 v26; // [rsp+28h] [rbp-31h]
  int v27; // [rsp+30h] [rbp-29h] BYREF
  _DWORD *v28; // [rsp+38h] [rbp-21h] BYREF
  _DWORD *v29; // [rsp+40h] [rbp-19h] BYREF
  _DWORD *v30; // [rsp+48h] [rbp-11h] BYREF
  __int64 v31; // [rsp+50h] [rbp-9h]
  __int64 v32; // [rsp+58h] [rbp-1h] BYREF
  __int64 v33; // [rsp+60h] [rbp+7h]
  int v34; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v35; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = (char *)this + 72;
  if ( !*(_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                     (char *)this + 72,
                     &v25) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF0,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\SystemXamlHostBehavior.h",
      v3);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v25);
  v4 = (_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                   v2,
                   &v30);
  winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v28,
    *v4);
  v5 = operator new(0x18u);
  v5[2] = 1;
  *((_QWORD *)v5 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v5 = &winrt::impl::delegate<winrt::Windows::UI::Xaml::SizeChangedEventHandler,_lambda_0dee0df95e42a7db4234e580c1d8b383_>::`vftable';
  v29 = v5;
  v25 = 0;
  v34 = 0;
  v35 = 0;
  v6 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD *, __int64 *))(*(_QWORD *)v28 + 376LL))(v28, v5, &v25);
  winrt::check_hresult(&v27, v6, &v34);
  v7 = v25;
  winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(
    &v32,
    &v28);
  v33 = v7;
  v8 = v32;
  v32 = 0;
  v25 = v8;
  v26 = v7;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v25, (char *)this + 88);
  v9 = v26;
  v26 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = v9;
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBIA_AA_impl_winrt__QEAA_XZ(&v25);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBIA_AA_impl_winrt__QEAA_XZ(&v32);
  winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v29);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v30);
  v10 = (_QWORD *)winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(
                    v2,
                    &v29);
  winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v28,
    *v10);
  v11 = operator new(0x18u);
  v11[2] = 1;
  *((_QWORD *)v11 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v11 = &winrt::impl::delegate<winrt::Windows::UI::Xaml::RoutedEventHandler,_lambda_09feb87d5a3120f41fe80ccd86bab29d_>::`vftable';
  v30 = v11;
  v25 = 0;
  v34 = 0;
  v35 = 0;
  v12 = (*(__int64 (__fastcall **)(_DWORD *, _DWORD *, __int64 *))(*(_QWORD *)v28 + 344LL))(v28, v11, &v25);
  winrt::check_hresult(&v27, v12, &v34);
  v13 = v25;
  winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(
    &v32,
    &v28);
  v33 = v13;
  v14 = v32;
  v32 = 0;
  v25 = v14;
  v26 = v13;
  std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(&v25, (char *)this + 104);
  v15 = v26;
  v26 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v15;
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(&v25);
  __1__event_revoker_UIFrameworkElement_Xaml_UI_Windows_winrt___MP8type___abi_UIFrameworkElement_Xaml_UI_Windows_winrt__X_impl_5_EAAHUevent_token_5___E1___96785__BBGA_AA_impl_winrt__QEAA_XZ(&v32);
  winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v30);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v28);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  v16 = operator new(0x18u);
  v30 = v16;
  v16[2] = 1;
  *((_QWORD *)v16 + 2) = this;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v16 = &winrt::impl::delegate<winrt::Windows::Foundation::EventHandler<winrt::Windows::UI::Xaml::Media::RenderedEventArgs>,_lambda_b5584cad34eef3ea12bfed3ded323e91_>::`vftable';
  v28 = v16;
  v17 = (__int64 *)winrt::Windows::UI::Xaml::Media::CompositionTarget::Rendered((winrt::Windows::Foundation::IUnknown *)&v32);
  v18 = *v17;
  *v17 = 0;
  v31 = v17[1];
  v30 = 0;
  v25 = v18;
  winrt::Windows::Foundation::IUnknown::operator=(&v30, (char *)this + 144);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 144, &v25);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v25);
  v19 = v31;
  v31 = *((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = v19;
  __1__factory_event_revoker_UICompositionTargetStatics3_Media_Xaml_UI_Windows_winrt___MP8type___abi_UICompositionTargetStatics3_Media_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BDI_AA_impl_winrt__QEAA_XZ((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v30);
  __1__factory_event_revoker_UICompositionTargetStatics3_Media_Xaml_UI_Windows_winrt___MP8type___abi_UICompositionTargetStatics3_Media_Xaml_UI_Windows_winrt__X_impl_6_EAAHUevent_token_6___E1___97896__BDI_AA_impl_winrt__QEAA_XZ((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v32);
  if ( v28 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v28);
  v20 = winrt::Windows::UI::Xaml::Window::Current();
  v21 = winrt::impl::consume_Windows_UI_Xaml_IWindow3<winrt::Windows::UI::Xaml::Window>::Compositor(v20, &v30);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 192, v21);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v30);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  winrt::impl::as<winrt::Windows::UI::Composition::Internal::ICompositorInternal,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v25,
    *((_QWORD *)this + 24));
  v34 = 0;
  v35 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 184LL))(v25, 0);
  winrt::check_hresult(&v27, v22, &v34);
  *((_DWORD *)this + 47) = 5;
  v23 = (HWND)*((_QWORD *)this + 7);
  if ( GetActiveWindow() == v23 )
  {
    SetFocus(*((HWND *)this + 8));
    v27 = 1;
    v24 = winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(
            (winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest *)&v29,
            (const enum winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *)&v27);
    winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(
      v2,
      &v30,
      v24);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v30);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
  }
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v25);
}

```

## disassembly

```asm
0x1800462dc  mov     [rsp-8+arg_8], rbx
0x1800462e1  mov     [rsp-8+arg_10], rsi
0x1800462e6  push    rbp
0x1800462e7  push    rdi
0x1800462e8  push    r12
0x1800462ea  push    r14
0x1800462ec  push    r15
0x1800462ee  lea     rbp, [rsp-37h]
0x1800462f3  sub     rsp, 90h
0x1800462fa  mov     rax, cs:__security_cookie
0x180046301  xor     rax, rsp
0x180046304  mov     [rbp+57h+var_30], rax
0x180046308  mov     rsi, rcx
0x18004630b  xor     r12d, r12d
0x18004630e  lea     r14, [rcx+48h]
0x180046312  lea     rdx, [rbp+57h+var_90]
0x180046316  mov     rcx, r14
0x180046319  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x18004631e  cmp     [rax], r12
0x180046321  setz    al
0x180046324  mov     rcx, [rbp+5Fh]; this
0x180046328  test    al, al
0x18004632a  jnz     loc_1800466CD
0x180046330  lea     rcx, [rbp+57h+var_90]; this
0x180046334  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046339  lea     rdx, [rbp+57h+var_68]
0x18004633d  mov     rcx, r14
0x180046340  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x180046345  nop
0x180046346  mov     rdx, [rax]
0x180046349  lea     rcx, [rbp+57h+var_78]
0x18004634d  call    ??$as@UFrameworkElement@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180046352  nop
0x180046353  lea     r15d, [r12+18h]
0x180046358  mov     ecx, r15d; Size
0x18004635b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046360  mov     rdx, rax
0x180046363  mov     [rbp+57h+var_70], rax
0x180046367  mov     dword ptr [rax+8], 1
0x18004636e  mov     [rax+10h], rsi
0x180046372  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180046379  lea     rax, ??_7?$delegate@USizeChangedEventHandler@Xaml@UI@Windows@winrt@@V_lambda_0dee0df95e42a7db4234e580c1d8b383_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::UI::Xaml::SizeChangedEventHandler,_lambda_0dee0df95e42a7db4234e580c1d8b383_>::`vftable'
0x180046380  mov     [rdx], rax
0x180046383  mov     [rbp+57h+var_70], rdx
0x180046387  mov     [rbp+57h+var_90], r12
0x18004638b  mov     rcx, [rbp+57h+var_78]
0x18004638f  mov     [rbp+57h+var_48], r12d
0x180046393  xorps   xmm0, xmm0
0x180046396  movdqu  [rbp+57h+var_40], xmm0
0x18004639b  mov     rax, [rcx]
0x18004639e  lea     r8, [rbp+57h+var_90]
0x1800463a2  mov     rax, [rax+178h]
0x1800463a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463ae  lea     r8, [rbp+57h+var_48]
0x1800463b2  mov     edx, eax
0x1800463b4  lea     rcx, [rbp+57h+var_80]
0x1800463b8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800463bd  mov     rbx, [rbp+57h+var_90]
0x1800463c1  lea     rdx, [rbp+57h+var_78]
0x1800463c5  lea     rcx, [rbp+57h+var_58]
0x1800463c9  call    ??$?0AEBUIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@?$weak_ref@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@winrt@@QEAA@AEBUIFrameworkElement@Xaml@UI@Microsoft@1@@Z; winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(winrt::Microsoft::UI::Xaml::IFrameworkElement const &)
0x1800463ce  mov     [rbp+57h+var_50], rbx
0x1800463d2  mov     rax, [rbp+57h+var_58]
0x1800463d6  mov     [rbp+57h+var_58], r12
0x1800463da  mov     [rbp+57h+var_90], rax
0x1800463de  mov     [rbp+57h+var_88], rbx
0x1800463e2  lea     rdx, [rsi+58h]
0x1800463e6  lea     rcx, [rbp+57h+var_90]
0x1800463ea  call    ??$swap@U?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@$0A@@std@@YAXAEAU?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@0@Z; std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &,winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &)
0x1800463ef  mov     rax, [rbp+57h+var_88]
0x1800463f3  mov     rcx, [rsi+60h]
0x1800463f7  mov     [rbp+57h+var_88], rcx
0x1800463fb  mov     [rsi+60h], rax
0x1800463ff  lea     rcx, [rbp+57h+var_90]
0x180046403  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBIA@AA@impl@winrt@@QEAA@XZ
0x180046408  lea     rcx, [rbp+57h+var_58]
0x18004640c  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBIA@AA@impl@winrt@@QEAA@XZ
0x180046411  nop
0x180046412  lea     rcx, [rbp+57h+var_70]
0x180046416  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004641b  nop
0x18004641c  lea     rcx, [rbp+57h+var_78]; this
0x180046420  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046425  nop
0x180046426  lea     rcx, [rbp+57h+var_68]; this
0x18004642a  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004642f  lea     rdx, [rbp+57h+var_70]
0x180046433  mov     rcx, r14
0x180046436  call    ?Content@?$consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Microsoft::UI::Xaml::Hosting::IDesktopWindowXamlSource>::Content(void)
0x18004643b  nop
0x18004643c  mov     rdx, [rax]
0x18004643f  lea     rcx, [rbp+57h+var_78]
0x180046443  call    ??$as@UFrameworkElement@Xaml@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@5@$0A@@impl@winrt@@YA?AUFrameworkElement@Xaml@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Xaml::FrameworkElement,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180046448  nop
0x180046449  mov     ecx, r15d; Size
0x18004644c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046451  mov     rdx, rax
0x180046454  mov     [rbp+57h+var_68], rax
0x180046458  mov     dword ptr [rax+8], 1
0x18004645f  mov     [rax+10h], rsi
0x180046463  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004646a  lea     rax, ??_7?$delegate@URoutedEventHandler@Xaml@UI@Windows@winrt@@V_lambda_09feb87d5a3120f41fe80ccd86bab29d_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::UI::Xaml::RoutedEventHandler,_lambda_09feb87d5a3120f41fe80ccd86bab29d_>::`vftable'
0x180046471  mov     [rdx], rax
0x180046474  mov     [rbp+57h+var_68], rdx
0x180046478  mov     [rbp+57h+var_90], r12
0x18004647c  mov     rcx, [rbp+57h+var_78]
0x180046480  mov     [rbp+57h+var_48], r12d
0x180046484  xorps   xmm0, xmm0
0x180046487  movdqu  [rbp+57h+var_40], xmm0
0x18004648c  mov     rax, [rcx]
0x18004648f  lea     r8, [rbp+57h+var_90]
0x180046493  mov     rax, [rax+158h]
0x18004649a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004649f  lea     r8, [rbp+57h+var_48]
0x1800464a3  mov     edx, eax
0x1800464a5  lea     rcx, [rbp+57h+var_80]
0x1800464a9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800464ae  mov     rbx, [rbp+57h+var_90]
0x1800464b2  lea     rdx, [rbp+57h+var_78]
0x1800464b6  lea     rcx, [rbp+57h+var_58]
0x1800464ba  call    ??$?0AEBUIFrameworkElement@Xaml@UI@Microsoft@winrt@@X@?$weak_ref@UIFrameworkElement@Xaml@UI@Microsoft@winrt@@@winrt@@QEAA@AEBUIFrameworkElement@Xaml@UI@Microsoft@1@@Z; winrt::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>::weak_ref<winrt::Microsoft::UI::Xaml::IFrameworkElement>(winrt::Microsoft::UI::Xaml::IFrameworkElement const &)
0x1800464bf  mov     [rbp+57h+var_50], rbx
0x1800464c3  mov     rax, [rbp+57h+var_58]
0x1800464c7  mov     [rbp+57h+var_58], r12
0x1800464cb  mov     [rbp+57h+var_90], rax
0x1800464cf  mov     [rbp+57h+var_88], rbx
0x1800464d3  lea     rdx, [rsi+68h]
0x1800464d7  lea     rcx, [rbp+57h+var_90]
0x1800464db  call    ??$swap@U?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@$0A@@std@@YAXAEAU?$weak_ref@UIFrameworkElement@Xaml@UI@Windows@winrt@@@winrt@@0@Z; std::swap<winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement>,0>(winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &,winrt::weak_ref<winrt::Windows::UI::Xaml::IFrameworkElement> &)
0x1800464e0  mov     rax, [rbp+57h+var_88]
0x1800464e4  mov     rcx, [rsi+70h]
0x1800464e8  mov     [rbp+57h+var_88], rcx
0x1800464ec  mov     [rsi+70h], rax
0x1800464f0  lea     rcx, [rbp+57h+var_90]
0x1800464f4  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ
0x1800464f9  lea     rcx, [rbp+57h+var_58]
0x1800464fd  call    ??1?$event_revoker@UIFrameworkElement@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UIFrameworkElement@Xaml@UI@Windows@winrt@@X@impl@5@EAAHUevent_token@5@@_E1??_96785@$BBGA@AA@impl@winrt@@QEAA@XZ
0x180046502  nop
0x180046503  lea     rcx, [rbp+57h+var_68]
0x180046507  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004650c  nop
0x18004650d  lea     rcx, [rbp+57h+var_78]; this
0x180046511  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046516  nop
0x180046517  lea     rcx, [rbp+57h+var_70]; this
0x18004651b  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046520  mov     ecx, r15d; Size
0x180046523  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046528  mov     [rbp+57h+var_68], rax
0x18004652c  mov     dword ptr [rax+8], 1
0x180046533  mov     [rax+10h], rsi
0x180046537  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004653e  lea     rcx, ??_7?$delegate@U?$EventHandler@URenderedEventArgs@Media@Xaml@UI@Windows@winrt@@@Foundation@Windows@winrt@@V_lambda_b5584cad34eef3ea12bfed3ded323e91_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::EventHandler<winrt::Windows::UI::Xaml::Media::RenderedEventArgs>,_lambda_b5584cad34eef3ea12bfed3ded323e91_>::`vftable'
0x180046545  mov     [rax], rcx
0x180046548  mov     [rbp+57h+var_78], rax
0x18004654c  lea     r8, [rbp+57h+var_78]
0x180046550  lea     rcx, [rbp+57h+var_58]; this
0x180046554  call    ?Rendered@CompositionTarget@Media@Xaml@UI@Windows@winrt@@SA@Uauto_revoke_t@6@AEBU?$EventHandler@URenderedEventArgs@Media@Xaml@UI@Windows@winrt@@@Foundation@56@@Z; winrt::Windows::UI::Xaml::Media::CompositionTarget::Rendered(winrt::auto_revoke_t,winrt::Windows::Foundation::EventHandler<winrt::Windows::UI::Xaml::Media::RenderedEventArgs> const &)
0x180046559  lea     rbx, [rsi+90h]
0x180046560  mov     rcx, [rax]
0x180046563  mov     [rax], r12
0x180046566  mov     rax, [rax+8]
0x18004656a  mov     [rbp+57h+var_60], rax
0x18004656e  mov     [rbp+57h+var_68], r12
0x180046572  mov     [rbp+57h+var_90], rcx
0x180046576  mov     rdx, rbx
0x180046579  lea     rcx, [rbp+57h+var_68]
0x18004657d  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180046582  lea     rdx, [rbp+57h+var_90]
0x180046586  mov     rcx, rbx
0x180046589  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004658e  lea     rcx, [rbp+57h+var_90]; this
0x180046592  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046597  mov     rax, [rbp+57h+var_60]
0x18004659b  mov     rcx, [rbx+8]
0x18004659f  mov     [rbp+57h+var_60], rcx
0x1800465a3  mov     [rbx+8], rax
0x1800465a7  lea     rcx, [rbp+57h+var_68]; this
0x1800465ab  call    ??1?$factory_event_revoker@UICompositionTargetStatics3@Media@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UICompositionTargetStatics3@Media@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BDI@AA@impl@winrt@@QEAA@XZ
0x1800465b0  lea     rcx, [rbp+57h+var_58]; this
0x1800465b4  call    ??1?$factory_event_revoker@UICompositionTargetStatics3@Media@Xaml@UI@Windows@winrt@@$MP8type@?$abi@UICompositionTargetStatics3@Media@Xaml@UI@Windows@winrt@@X@impl@6@EAAHUevent_token@6@@_E1??_97896@$BDI@AA@impl@winrt@@QEAA@XZ
0x1800465b9  nop
0x1800465ba  cmp     [rbp+57h+var_78], r12
0x1800465be  jz      short loc_1800465C9
0x1800465c0  lea     rcx, [rbp+57h+var_78]
0x1800465c4  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x1800465c9  lea     rcx, [rbp+57h+var_70]
0x1800465cd  call    ?Current@Window@Xaml@UI@Windows@winrt@@SA@XZ; winrt::Windows::UI::Xaml::Window::Current(void)
0x1800465d2  nop
0x1800465d3  lea     rdx, [rbp+57h+var_68]
0x1800465d7  mov     rcx, rax
0x1800465da  call    ?Compositor@?$consume_Windows_UI_Xaml_IWindow3@UWindow@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_UI_Xaml_IWindow3<winrt::Windows::UI::Xaml::Window>::Compositor(void)
0x1800465df  lea     rbx, [rsi+0C0h]
0x1800465e6  mov     rdx, rax
0x1800465e9  mov     rcx, rbx
0x1800465ec  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800465f1  lea     rcx, [rbp+57h+var_68]; this
0x1800465f5  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800465fa  nop
0x1800465fb  lea     rcx, [rbp+57h+var_70]; this
0x1800465ff  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046604  mov     rdx, [rbx]
0x180046607  lea     rcx, [rbp+57h+var_90]
0x18004660b  call    ??$as@UICompositorInternal@Internal@Composition@UI@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@6@$0A@@impl@winrt@@YA?AUICompositorInternal@Internal@Composition@UI@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::UI::Composition::Internal::ICompositorInternal,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180046610  nop
0x180046611  mov     rcx, [rbp+57h+var_90]
0x180046615  mov     [rbp+57h+var_48], r12d
0x180046619  xorps   xmm0, xmm0
0x18004661c  movdqu  [rbp+57h+var_40], xmm0
0x180046621  mov     rax, [rcx]
0x180046624  xor     edx, edx
0x180046626  mov     rax, [rax+0B8h]
0x18004662d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046632  lea     r8, [rbp+57h+var_48]
0x180046636  mov     edx, eax
0x180046638  lea     rcx, [rbp+57h+var_80]
0x18004663c  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180046641  mov     dword ptr [rsi+0BCh], 5
0x18004664b  mov     rbx, [rsi+38h]
0x18004664f  call    cs:__imp_GetActiveWindow
0x180046655  cmp     rax, rbx
0x180046658  jnz     short loc_18004669C
0x18004665a  mov     rcx, [rsi+40h]; hWnd
0x18004665e  call    cs:__imp_SetFocus
0x180046664  mov     [rbp+57h+var_80], 1
0x18004666b  lea     rdx, [rbp+57h+var_80]; enum winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason *
0x18004666f  lea     rcx, [rbp+57h+var_70]; this
0x180046673  call    ??0XamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@winrt@@QEAA@AEBW4XamlSourceFocusNavigationReason@12345@@Z; winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest::XamlSourceFocusNavigationRequest(winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationReason const &)
0x180046678  nop
0x180046679  mov     r8, rax
0x18004667c  lea     rdx, [rbp+57h+var_68]
0x180046680  mov     rcx, r14
0x180046683  call    ?NavigateFocus@?$consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource@UIDesktopWindowXamlSource@Hosting@Xaml@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUXamlSourceFocusNavigationRequest@Hosting@Xaml@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Xaml_Hosting_IDesktopWindowXamlSource<winrt::Windows::UI::Xaml::Hosting::IDesktopWindowXamlSource>::NavigateFocus(winrt::Windows::UI::Xaml::Hosting::XamlSourceFocusNavigationRequest const &)
0x180046688  lea     rcx, [rbp+57h+var_68]; this
0x18004668c  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180046691  nop
0x180046692  lea     rcx, [rbp+57h+var_70]; this
0x180046696  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004669b  nop
0x18004669c  lea     rcx, [rbp+57h+var_90]; this
0x1800466a0  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800466a5  mov     rcx, [rbp+57h+var_30]
0x1800466a9  xor     rcx, rsp; StackCookie
0x1800466ac  call    __security_check_cookie
0x1800466b1  lea     r11, [rsp+0B0h+var_20]
0x1800466b9  mov     rbx, [r11+38h]
0x1800466bd  mov     rsi, [r11+40h]
0x1800466c1  mov     rsp, r11
0x1800466c4  pop     r15
0x1800466c6  pop     r14
0x1800466c8  pop     r12
0x1800466ca  pop     rdi
0x1800466cb  pop     rbp
0x1800466cc  retn
0x1800466cd  lea     r8, aPcshellShellUx_3; "pcshell\\shell\\uxframe\\dll\\SystemXam"...
0x1800466d4  mov     edx, 0F0h; void *
0x1800466d9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
