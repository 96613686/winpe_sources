# UXFrame::SpecializeForExtension(SpecializationData &,UXFrame::SpecializationType)

- ea: `0x18004a43c`
- end: `0x18004ac5c`
- name: `?SpecializeForExtension@UXFrame@@AEAAXAEAUSpecializationData@@W4SpecializationType@1@@Z`
- size: `2080`
- prototype: `void __fastcall(__int64, _QWORD *, int)`
- caller_count: `2`
- callee_count: `54`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004488c`
- `0x18004ac70`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043f4`
- `0x1800049ac`
- `0x1800068d8`
- `0x1800088ac`
- `0x18000d504`
- `0x18000d810`
- `0x18000e440`
- `0x18001049c`
- `0x180014c34`
- `0x18001600c`
- `0x180017044`
- `0x180017164`
- `0x180017514`
- `0x1800176b0`
- `0x18001c890`
- `0x18001d894`
- `0x18001ddc8`
- `0x18001e0a8`
- `0x180020c38`
- `0x180020cac`
- `0x180021e6c`
- `0x1800220c8`
- `0x1800221e4`
- `0x180026620`
- `0x18002cad8`
- `0x18002d0e4`
- `0x180034cb0`
- `0x180037414`
- `0x180037808`
- `0x180037ba0`
- `0x180037e50`
- `0x180038d94`
- `0x18003937c`
- `0x18003a140`
- `0x18003a410`
- `0x18003c5b8`
- `0x18003d8bc`
- `0x18003e3c8`
- `0x18003edd0`
- `0x18003ffc4`
- `0x1800447bc`
- `0x180048f24`
- `0x18004a43c`
- `0x18004b86c`
- `0x18004bff8`
- `0x18004d5a8`
- `0x18004d714`

## string_xrefs

- `0x18004a75c`: `CommunicationHWND`
- `0x18004ac0d`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004ac26`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004ac38`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004ac4a`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004aabb`: `DirectLaunchUriScheme`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall UXFrame::SpecializeForExtension(__int64 a1, _QWORD *a2, int a3)
{
  void *v5; // rdx
  __int64 v6; // r8
  const char *v7; // r9
  _QWORD *v8; // rsi
  __int64 v9; // rcx
  int v10; // eax
  const char *v11; // r9
  int v12; // eax
  std::_Ref_count_base *v13; // rax
  std::_Ref_count_base *v14; // rax
  std::_Ref_count_base *v15; // rax
  const char *v16; // r9
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rax
  __int64 v24; // rdx
  void *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  std::_Ref_count_base *v28; // rsi
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // r9
  std::_Ref_count_base *v33; // rbx
  void (__fastcall ****v34)(_QWORD, void *, std::_Ref_count_base **); // rsi
  __int64 v35; // rax
  void (__fastcall ***v36)(_QWORD, void *, std::_Ref_count_base **); // rcx
  std::_Ref_count_base *v37; // rax
  __int64 v38; // rax
  __int64 *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rax
  std::_Ref_count_base *v47; // rax
  __int64 v48; // rdx
  __int128 v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall **v50)(); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+48h] [rbp-B8h]
  __int64 v52; // [rsp+50h] [rbp-B0h]
  __int64 (__fastcall ***v53)(); // [rsp+78h] [rbp-88h]
  _BYTE v54[56]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h]
  _BYTE v56[240]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v57[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  std::_Ref_count_base *v58; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  LODWORD(v49) = a3;
  v57[0] = (std::_Ref_count_base *)a1;
  UXFrameTelemetry::SpecializingThread<UXFrame *>(v57);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl'::`2'::impl)
    && !UXFrame::s_VerifyLaunchPayloadIsAllowedForComponent(
          (const struct winrt::Windows::Foundation::Collections::ValueSet *)(a2 + 6),
          (const struct winrt::Windows::Foundation::Collections::ValueSet *)(a2 + 7)) )
  {
LABEL_3:
    wil::details::SetEvent(*(wil::details **)(a1 + 264), v5);
    return;
  }
  v8 = a2 + 8;
  v9 = a2[8];
  if ( v9 )
  {
    v10 = SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(v9, (__int64)(a2 + 6), v6, v7);
    if ( v10 )
    {
      v12 = v10 - 1;
      if ( v12 )
      {
        if ( v12 != 1 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x4A4,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
            v11);
        v13 = (std::_Ref_count_base *)(*v8 + 72LL);
        if ( *(_QWORD *)(*v8 + 96LL) > 7u )
          v13 = *(std::_Ref_count_base **)v13;
        v57[0] = v13;
        UXFrameTelemetry::RedirectingToOtherInstance_Failed<wchar_t const *>(v57);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(
                                a2 + 9,
                                v57)
                 + 310LL) = 1;
      }
      else
      {
        v14 = (std::_Ref_count_base *)(*v8 + 72LL);
        if ( *(_QWORD *)(*v8 + 96LL) > 7u )
          v14 = *(std::_Ref_count_base **)v14;
        v57[0] = v14;
        UXFrameTelemetry::RedirectingToOtherInstance_Succeeded<wchar_t const *>(v57);
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(
                                a2 + 9,
                                v57)
                 + 309LL) = 1;
      }
      tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(v57);
      tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(a2 + 9);
      goto LABEL_3;
    }
    v15 = (std::_Ref_count_base *)(*v8 + 72LL);
    if ( *(_QWORD *)(*v8 + 96LL) > 7u )
      v15 = *(std::_Ref_count_base **)v15;
    v57[0] = v15;
    UXFrameTelemetry::ClaimedSingleton<wchar_t const *>(v57);
    std::unique_ptr<SingletonHelpers::SingletonHelper>::operator=<std::default_delete<SingletonHelpers::SingletonHelper>,0>(
      a1 + 456,
      a2 + 8);
  }
  UpdateThreadDescription((struct SpecializationData *)a2, (__int64)v5);
  if ( *(_BYTE *)(a1 + 56) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
      v16);
  *(_BYTE *)(a1 + 56) = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
  {
    if ( *(_DWORD *)(a1 + 256) != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x4B0,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
        v18);
    *(_DWORD *)(a1 + 256) = 2;
  }
  *(_OWORD *)v57 = 0;
  winrt::hstring::operator std::wstring_view(a2 + 1, v57, v17, v18);
  std::wstring::_Assign<wchar_t>(a1 + 72, v57[0], v57[1]);
  *(_OWORD *)v57 = 0;
  winrt::hstring::operator std::wstring_view(a2 + 2, v57, v19, v20);
  std::wstring::_Assign<wchar_t>(a1 + 104, v57[0], v57[1]);
  *(_OWORD *)v57 = 0;
  winrt::hstring::operator std::wstring_view(a2 + 3, v57, v21, v22);
  std::wstring::_Assign<wchar_t>(a1 + 136, v57[0], v57[1]);
  v23 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::ensure_data(a2 + 9);
  v24 = *v23;
  v25 = *(void **)(a1 + 448);
  *(_QWORD *)(a1 + 448) = *v23;
  if ( v24 )
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 312));
  if ( v25 )
    tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(v25);
  winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)(a1 + 176));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl'::`2'::impl) )
    winrt::Windows::Foundation::IUnknown::operator=((winrt::Windows::Foundation::IUnknown *)(a1 + 168));
  v26 = std::enable_shared_from_this<UXFrame>::shared_from_this(a1 + 40, v57);
  v27 = winrt::make_self<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost,std::shared_ptr<UXFrame>,winrt::Windows::Foundation::Collections::ValueSet &>(
          &v58,
          v26,
          a1 + 176);
  winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(a1 + 304, v27);
  if ( v58 )
    winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(&v58);
  if ( v57[1] )
    std::_Ref_count_base::_Decref(v57[1]);
  winrt::hstring::hstring((winrt::hstring *)&v58, L"CommunicationHWND");
  v28 = (std::_Ref_count_base *)ValueSetUtils::try_get_value<HWND__ *,winrt::Windows::Foundation::Collections::ValueSet>(
                                  &v58,
                                  a1 + 176);
  v57[0] = v28;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v58);
  if ( !v28 || (*(_BYTE *)(a1 + 404) = 1, (unsigned __int8)FlowTargetEndpoint::Initialize(a1 + 312, a1 + 24, v29, v28)) )
  {
    v30 = std::enable_shared_from_this<UXFrame>::shared_from_this(a1 + 40, v57);
    v31 = winrt::make_self<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost,std::shared_ptr<UXFrame>,winrt::Windows::Foundation::Collections::ValueSet &>(
            &v58,
            v30,
            a1 + 176);
    winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(a1 + 304, v31);
    if ( v58 )
      winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(&v58);
    if ( v57[1] )
      std::_Ref_count_base::_Decref(v57[1]);
    if ( a2[4] )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(
                              a1 + 448,
                              v57)
               + 306LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(v57);
      UXFrame::ApplySpecializationToFrameWindow(a1, a2, (unsigned int)v49);
      v39 = (__int64 *)std::shared_ptr<WindowingBehavior>::shared_ptr<WindowingBehavior>(v57, a2 + 4);
      v40 = *v39;
      *v39 = *(_QWORD *)(a1 + 208);
      *(_QWORD *)(a1 + 208) = v40;
      v41 = v39[1];
      v39[1] = *(_QWORD *)(a1 + 216);
      *(_QWORD *)(a1 + 216) = v41;
      if ( v57[1] )
        std::_Ref_count_base::_Decref(v57[1]);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 208) + 72LL))(
        *(_QWORD *)(a1 + 208),
        a1 + 8,
        *(_QWORD *)(a1 + 296),
        a1 + 232);
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 192) + 8LL))(*(_QWORD *)(a1 + 192), a1 + 176);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 192) + 56LL))(*(_QWORD *)(a1 + 192)) == 4 )
        (**(void (__fastcall ***)(__int64))a1)(a1);
    }
    else
    {
      if ( (_DWORD)v49 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x4DA,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v32);
      winrt::param::hstring::hstring(v54, a1 + 104);
      winrt::param::hstring::hstring(&v50, a1 + 72);
      winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(
        (const struct winrt::param::hstring *)v57,
        (const struct winrt::param::hstring *)&v50,
        (__int64)v54);
      v33 = v57[0];
      if ( v57[0] )
      {
        UXFrame::WaitForDebuggerForComponentIfNecessary((UXFrame *)a1);
        winrt::impl::as<winrt::Windows::Foundation::IActivationFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
          &v49,
          v33);
        v35 = winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::IInspectable>(
                &v49,
                &v58);
        v34 = (void (__fastcall ****)(_QWORD, void *, std::_Ref_count_base **))(a1 + 272);
        winrt::Windows::Foundation::IUnknown::operator=(a1 + 272, v35);
        if ( v58 )
          winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v58);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v49);
      }
      else
      {
        v34 = (void (__fastcall ****)(_QWORD, void *, std::_Ref_count_base **))(a1 + 272);
      }
      if ( v33 )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(v57);
      v36 = *v34;
      if ( *v34 )
      {
        v57[0] = 0;
        (**v36)(v36, &winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellContent>, v57);
        v37 = v57[0];
        v58 = v57[0];
      }
      else
      {
        v58 = 0;
        v37 = 0;
      }
      if ( v37 )
      {
        v38 = winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::as<winrt::WindowsUdk::UI::Shell::ShellContentHost>(
                a1 + 304,
                v57);
        winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(
          &v58,
          v38);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v57);
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v58);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    }
    v42 = *(_QWORD *)(a1 + 456);
    if ( v42 )
    {
      v50 = off_18005E720;
      v51 = a1;
      v53 = &v50;
      SingletonHelpers::SingletonHelper::RegisterForRedirectedLaunches(v42, &v50);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_46702346>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_46702346>::GetImpl'::`2'::impl) )
      {
        winrt::hstring::hstring((winrt::hstring *)v57, L"DirectLaunchUriScheme");
        ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(
          &v58,
          v57,
          a1 + 176);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v57);
        if ( v58 )
        {
          v55 = 0;
          v43 = (__int64 *)std::enable_shared_from_this<UXFrame>::shared_from_this(a1 + 40, v57);
          v44 = *v43;
          v45 = v43[1];
          *v43 = 0;
          v43[1] = 0;
          v50 = off_18005E750;
          v51 = v44;
          v52 = v45;
          v49 = 0;
          v53 = &v50;
          v46 = DirectLaunch::DirectLaunchListener::DirectLaunchListener(v56, &v50, v54);
          std::optional<DirectLaunch::DirectLaunchListener>::operator=<DirectLaunch::DirectLaunchListener,0>(
            a1 + 464,
            v46);
          DirectLaunch::DirectLaunchListener::~DirectLaunchListener((DirectLaunch::DirectLaunchListener *)v56);
          std::_Func_class<void,>::_Tidy(&v50);
          if ( v57[1] )
            std::_Ref_count_base::_Decref(v57[1]);
          std::_Func_class<void,>::_Tidy(v54);
          v47 = (std::_Ref_count_base *)winrt::hstring::c_str((winrt::hstring *)&v58);
          v48 = -1;
          do
            ++v48;
          while ( *((_WORD *)v47 + v48) );
          v57[0] = v47;
          v57[1] = (std::_Ref_count_base *)v48;
          DirectLaunch::DirectLaunchListener::TryRegisterUriScheme(a1 + 464, v57);
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v58);
      }
    }
  }
  else
  {
    v58 = (std::_Ref_count_base *)a1;
    UXFrameTelemetry::FailedToConnectToCommunicationHwnd<UXFrame *,HWND__ * const &>(&v58, v57);
    tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(a1 + 448);
  }
}

```

## disassembly

```asm
0x18004a43c  mov     [rsp-8+arg_10], rbx
0x18004a441  push    rbp
0x18004a442  push    rsi
0x18004a443  push    rdi
0x18004a444  push    r12
0x18004a446  push    r13
0x18004a448  push    r14
0x18004a44a  push    r15
0x18004a44c  lea     rbp, [rsp-0D0h]
0x18004a454  sub     rsp, 1D0h
0x18004a45b  mov     rax, cs:__security_cookie
0x18004a462  xor     rax, rsp
0x18004a465  mov     [rbp+100h+var_38], rax
0x18004a46c  mov     dword ptr [rsp+200h+var_1D0], r8d
0x18004a471  mov     rbx, rdx
0x18004a474  mov     rdi, rcx
0x18004a477  mov     [rbp+100h+var_50], rcx
0x18004a47e  lea     rcx, [rbp+100h+var_50]
0x18004a485  call    ??$SpecializingThread@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::SpecializingThread<UXFrame *>(UXFrame * &&)
0x18004a48a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59697564@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564> `wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl(void)'::`2'::impl
0x18004a491  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(void)
0x18004a496  lea     r14, [rbx+30h]
0x18004a49a  test    al, al
0x18004a49c  jz      short loc_18004A4BF
0x18004a49e  lea     rdx, [rbx+38h]; struct winrt::Windows::Foundation::Collections::ValueSet *
0x18004a4a2  mov     rcx, r14; struct winrt::Windows::Foundation::Collections::ValueSet *
0x18004a4a5  call    ?s_VerifyLaunchPayloadIsAllowedForComponent@UXFrame@@CA_NAEBUValueSet@Collections@Foundation@Windows@winrt@@0@Z; UXFrame::s_VerifyLaunchPayloadIsAllowedForComponent(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18004a4aa  test    al, al
0x18004a4ac  jnz     short loc_18004A4BF
0x18004a4ae  mov     rcx, [rdi+108h]; this
0x18004a4b5  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18004a4ba  jmp     loc_18004ABE3
0x18004a4bf  lea     rsi, [rbx+40h]
0x18004a4c3  mov     rcx, [rsi]
0x18004a4c6  test    rcx, rcx
0x18004a4c9  jz      loc_18004A5B8
0x18004a4cf  mov     rdx, r14
0x18004a4d2  call    ?TryClaimSingletonOrRedirectLaunch@SingletonHelper@SingletonHelpers@@QEAA?AW4SingletonClaimResult@2@AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_N@Z; SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool)
0x18004a4d7  test    eax, eax
0x18004a4d9  jz      loc_18004A585
0x18004a4df  sub     eax, 1
0x18004a4e2  jz      short loc_18004A52D
0x18004a4e4  cmp     eax, 1
0x18004a4e7  jnz     loc_18004AC1F
0x18004a4ed  mov     rax, [rsi]
0x18004a4f0  add     rax, 48h ; 'H'
0x18004a4f4  cmp     qword ptr [rax+18h], 7
0x18004a4f9  jbe     short loc_18004A4FE
0x18004a4fb  mov     rax, [rax]
0x18004a4fe  mov     [rbp+100h+var_50], rax
0x18004a505  lea     rcx, [rbp+100h+var_50]
0x18004a50c  call    ??$RedirectingToOtherInstance_Failed@PEB_W@UXFrameTelemetry@@SAX$$QEAPEB_W@Z; UXFrameTelemetry::RedirectingToOtherInstance_Failed<wchar_t const *>(wchar_t const * &&)
0x18004a511  lea     rdx, [rbp+100h+var_50]
0x18004a518  lea     rcx, [rbx+48h]
0x18004a51c  call    ??C?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(void)
0x18004a521  mov     rdx, [rax]
0x18004a524  mov     byte ptr [rdx+136h], 1
0x18004a52b  jmp     short loc_18004A56B
0x18004a52d  mov     rax, [rsi]
0x18004a530  add     rax, 48h ; 'H'
0x18004a534  cmp     qword ptr [rax+18h], 7
0x18004a539  jbe     short loc_18004A53E
0x18004a53b  mov     rax, [rax]
0x18004a53e  mov     [rbp+100h+var_50], rax
0x18004a545  lea     rcx, [rbp+100h+var_50]
0x18004a54c  call    ??$RedirectingToOtherInstance_Succeeded@PEB_W@UXFrameTelemetry@@SAX$$QEAPEB_W@Z; UXFrameTelemetry::RedirectingToOtherInstance_Succeeded<wchar_t const *>(wchar_t const * &&)
0x18004a551  lea     rdx, [rbp+100h+var_50]
0x18004a558  lea     rcx, [rbx+48h]
0x18004a55c  call    ??C?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(void)
0x18004a561  mov     rdx, [rax]
0x18004a564  mov     byte ptr [rdx+135h], 1
0x18004a56b  lea     rcx, [rbp+100h+var_50]
0x18004a572  call    ??1?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(void)
0x18004a577  lea     rcx, [rbx+48h]
0x18004a57b  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x18004a580  jmp     loc_18004A4AE
0x18004a585  mov     rax, [rsi]
0x18004a588  add     rax, 48h ; 'H'
0x18004a58c  cmp     qword ptr [rax+18h], 7
0x18004a591  jbe     short loc_18004A596
0x18004a593  mov     rax, [rax]
0x18004a596  mov     [rbp+100h+var_50], rax
0x18004a59d  lea     rcx, [rbp+100h+var_50]
0x18004a5a4  call    ??$ClaimedSingleton@PEB_W@UXFrameTelemetry@@SAX$$QEAPEB_W@Z; UXFrameTelemetry::ClaimedSingleton<wchar_t const *>(wchar_t const * &&)
0x18004a5a9  lea     rcx, [rdi+1C8h]
0x18004a5b0  mov     rdx, rsi
0x18004a5b3  call    ??$?4U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@$0A@@?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<SingletonHelpers::SingletonHelper>::operator=<std::default_delete<SingletonHelpers::SingletonHelper>,0>(std::unique_ptr<SingletonHelpers::SingletonHelper> &&)
0x18004a5b8  mov     rcx, rbx; struct SpecializationData *
0x18004a5bb  call    ?UpdateThreadDescription@@YAXPEAUSpecializationData@@@Z; UpdateThreadDescription(SpecializationData *)
0x18004a5c0  mov     rcx, [rbp+108h]; this
0x18004a5c7  cmp     byte ptr [rdi+38h], 0
0x18004a5cb  jnz     loc_18004AC38
0x18004a5d1  mov     byte ptr [rdi+38h], 1
0x18004a5d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004a5dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004a5e1  test    al, al
0x18004a5e3  jz      short loc_18004A603
0x18004a5e5  mov     rcx, [rbp+108h]; this
0x18004a5ec  cmp     dword ptr [rdi+100h], 1
0x18004a5f3  jnz     loc_18004AC4A
0x18004a5f9  mov     dword ptr [rdi+100h], 2
0x18004a603  xorps   xmm0, xmm0
0x18004a606  movups  xmmword ptr [rbp+100h+var_50], xmm0
0x18004a60d  lea     rcx, [rbx+8]
0x18004a611  lea     rdx, [rbp+100h+var_50]
0x18004a618  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18004a61d  lea     rcx, [rdi+48h]
0x18004a621  mov     r8, [rbp+100h+var_50+8]
0x18004a628  mov     rdx, [rbp+100h+var_50]
0x18004a62f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18004a634  xorps   xmm0, xmm0
0x18004a637  movups  xmmword ptr [rbp+100h+var_50], xmm0
0x18004a63e  lea     rcx, [rbx+10h]
0x18004a642  lea     rdx, [rbp+100h+var_50]
0x18004a649  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18004a64e  lea     rcx, [rdi+68h]
0x18004a652  mov     r8, [rbp+100h+var_50+8]
0x18004a659  mov     rdx, [rbp+100h+var_50]
0x18004a660  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18004a665  xorps   xmm0, xmm0
0x18004a668  movups  xmmword ptr [rbp+100h+var_50], xmm0
0x18004a66f  lea     rcx, [rbx+18h]
0x18004a673  lea     rdx, [rbp+100h+var_50]
0x18004a67a  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x18004a67f  lea     rcx, [rdi+88h]
0x18004a686  mov     r8, [rbp+100h+var_50+8]
0x18004a68d  mov     rdx, [rbp+100h+var_50]
0x18004a694  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18004a699  lea     r12, [rdi+1C0h]
0x18004a6a0  lea     rcx, [rbx+48h]
0x18004a6a4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::ensure_data(void)
0x18004a6a9  mov     rdx, [rax]
0x18004a6ac  mov     rcx, [r12]; pv
0x18004a6b0  mov     [r12], rdx
0x18004a6b4  test    rdx, rdx
0x18004a6b7  jz      short loc_18004A6C0
0x18004a6b9  lock inc dword ptr [rdx+138h]
0x18004a6c0  test    rcx, rcx
0x18004a6c3  jz      short loc_18004A6CA
0x18004a6c5  call    ?Release@?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>::Release(void)
0x18004a6ca  lea     r15, [rdi+0B0h]
0x18004a6d1  mov     rdx, r14
0x18004a6d4  mov     rcx, r15; this
0x18004a6d7  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x18004a6dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59697564@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564> `wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl(void)'::`2'::impl
0x18004a6e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(void)
0x18004a6e8  test    al, al
0x18004a6ea  jz      short loc_18004A6FC
0x18004a6ec  lea     rdx, [rbx+38h]
0x18004a6f0  lea     rcx, [rdi+0A8h]; this
0x18004a6f7  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x18004a6fc  lea     r13, [rdi+28h]
0x18004a700  lea     rdx, [rbp+100h+var_50]
0x18004a707  mov     rcx, r13
0x18004a70a  call    ?shared_from_this@?$enable_shared_from_this@VUXFrame@@@std@@QEAA?AV?$shared_ptr@VUXFrame@@@2@XZ; std::enable_shared_from_this<UXFrame>::shared_from_this(void)
0x18004a70f  nop
0x18004a710  mov     r8, r15
0x18004a713  mov     rdx, rax
0x18004a716  lea     rcx, [rbp+100h+var_40]
0x18004a71d  call    ??$make_self@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@V?$shared_ptr@VUXFrame@@@std@@AEAUValueSet@Collections@Foundation@Windows@6@@winrt@@YA?AU?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@0@$$QEAV?$shared_ptr@VUXFrame@@@std@@AEAUValueSet@Collections@Foundation@Windows@0@@Z; winrt::make_self<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost,std::shared_ptr<UXFrame>,winrt::Windows::Foundation::Collections::ValueSet &>(std::shared_ptr<UXFrame> &&,winrt::Windows::Foundation::Collections::ValueSet &)
0x18004a722  lea     r14, [rdi+130h]
0x18004a729  mov     rdx, rax
0x18004a72c  mov     rcx, r14
0x18004a72f  call    ??4?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost> &&)
0x18004a734  cmp     [rbp+100h+var_40], 0
0x18004a73c  jz      short loc_18004A74B
0x18004a73e  lea     rcx, [rbp+100h+var_40]
0x18004a745  call    ?unconditional_release_ref@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(void)
0x18004a74a  nop
0x18004a74b  mov     rcx, [rbp+100h+var_50+8]; this
0x18004a752  test    rcx, rcx
0x18004a755  jz      short loc_18004A75C
0x18004a757  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004a75c  lea     rdx, aCommunicationh; "CommunicationHWND"
0x18004a763  lea     rcx, [rbp+100h+var_40]; this
0x18004a76a  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18004a76f  nop
0x18004a770  mov     rdx, r15
0x18004a773  lea     rcx, [rbp+100h+var_40]
0x18004a77a  call    ??$try_get_value@PEAUHWND__@@UValueSet@Collections@Foundation@Windows@winrt@@@ValueSetUtils@@YAPEAUHWND__@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; ValueSetUtils::try_get_value<HWND__ *,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18004a77f  mov     rsi, rax
0x18004a782  mov     [rbp+100h+var_50], rax
0x18004a789  lea     rcx, [rbp+100h+var_40]
0x18004a790  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004a795  test    rsi, rsi
0x18004a798  jz      short loc_18004A7DC
0x18004a79a  lea     rcx, [rdi+138h]
0x18004a7a1  mov     byte ptr [rcx+5Ch], 1
0x18004a7a5  lea     rdx, [rdi+18h]
0x18004a7a9  mov     r9, rsi
0x18004a7ac  call    ?Initialize@FlowTargetEndpoint@@QEAA_NPEAVFlowEndpointMessageReceiver@@KPEAUHWND__@@W4EndpointInitializationOptions@@@Z; FlowTargetEndpoint::Initialize(FlowEndpointMessageReceiver *,ulong,HWND__ *,EndpointInitializationOptions)
0x18004a7b1  test    al, al
0x18004a7b3  jnz     short loc_18004A7DC
0x18004a7b5  mov     [rbp+100h+var_40], rdi
0x18004a7bc  lea     rdx, [rbp+100h+var_50]
0x18004a7c3  lea     rcx, [rbp+100h+var_40]
0x18004a7ca  call    ??$FailedToConnectToCommunicationHwnd@PEAVUXFrame@@AEBQEAUHWND__@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@AEBQEAUHWND__@@@Z; UXFrameTelemetry::FailedToConnectToCommunicationHwnd<UXFrame *,HWND__ * const &>(UXFrame * &&,HWND__ * const &)
0x18004a7cf  mov     rcx, r12
0x18004a7d2  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x18004a7d7  jmp     loc_18004ABE3
0x18004a7dc  lea     rdx, [rbp+100h+var_50]
0x18004a7e3  mov     rcx, r13
0x18004a7e6  call    ?shared_from_this@?$enable_shared_from_this@VUXFrame@@@std@@QEAA?AV?$shared_ptr@VUXFrame@@@2@XZ; std::enable_shared_from_this<UXFrame>::shared_from_this(void)
0x18004a7eb  nop
0x18004a7ec  mov     r8, r15
0x18004a7ef  mov     rdx, rax
0x18004a7f2  lea     rcx, [rbp+100h+var_40]
0x18004a7f9  call    ??$make_self@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@V?$shared_ptr@VUXFrame@@@std@@AEAUValueSet@Collections@Foundation@Windows@6@@winrt@@YA?AU?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@0@$$QEAV?$shared_ptr@VUXFrame@@@std@@AEAUValueSet@Collections@Foundation@Windows@0@@Z; winrt::make_self<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost,std::shared_ptr<UXFrame>,winrt::Windows::Foundation::Collections::ValueSet &>(std::shared_ptr<UXFrame> &&,winrt::Windows::Foundation::Collections::ValueSet &)
0x18004a7fe  mov     rdx, rax
0x18004a801  mov     rcx, r14
0x18004a804  call    ??4?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::operator=(winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost> &&)
0x18004a809  cmp     [rbp+100h+var_40], 0
0x18004a811  jz      short loc_18004A820
0x18004a813  lea     rcx, [rbp+100h+var_40]
0x18004a81a  call    ?unconditional_release_ref@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::WindowsUdk::UI::Shell::implementation::ShellContentHost>::unconditional_release_ref(void)
0x18004a81f  nop
0x18004a820  mov     rcx, [rbp+100h+var_50+8]; this
0x18004a827  test    rcx, rcx
0x18004a82a  jz      short loc_18004A831
0x18004a82c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004a831  cmp     qword ptr [rbx+20h], 0
0x18004a836  jnz     loc_18004A98E
0x18004a83c  mov     rcx, [rbp+108h]; this
0x18004a843  xor     r12d, r12d
0x18004a846  cmp     dword ptr [rsp+200h+var_1D0], r12d
0x18004a84b  jnz     loc_18004AC0D
0x18004a851  lea     rdx, [rdi+68h]
0x18004a855  lea     rcx, [rbp+100h+var_180]
0x18004a859  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18004a85e  lea     rdx, [rdi+48h]
0x18004a862  lea     rcx, [rsp+200h+var_1C0]
0x18004a867  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18004a86c  lea     r8, [rbp+100h+var_180]
0x18004a870  lea     rdx, [rsp+200h+var_1C0]; struct winrt::param::hstring *
0x18004a875  lea     rcx, [rbp+100h+var_50]; struct winrt::param::hstring *
0x18004a87c  call    ?GetFactory@ExtensionFactory@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBUhstring@param@5@0@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::ExtensionFactory::GetFactory(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004a881  nop
0x18004a882  mov     rbx, [rbp+100h+var_50]
0x18004a889  test    rbx, rbx
0x18004a88c  jnz     short loc_18004A897
0x18004a88e  lea     rsi, [rdi+110h]
0x18004a895  jmp     short loc_18004A8F1
0x18004a897  mov     rcx, rdi; this
0x18004a89a  call    ?WaitForDebuggerForComponentIfNecessary@UXFrame@@AEAAXXZ; UXFrame::WaitForDebuggerForComponentIfNecessary(void)
0x18004a89f  mov     rdx, rbx
0x18004a8a2  lea     rcx, [rsp+200h+var_1D0]
0x18004a8a7  call    ??$as@UIActivationFactory@Foundation@Windows@winrt@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@4@$0A@@impl@winrt@@YA?AUIActivationFactory@Foundation@Windows@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<winrt::Windows::Foundation::IActivationFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x18004a8ac  nop
0x18004a8ad  lea     rdx, [rbp+100h+var_40]
0x18004a8b4  lea     rcx, [rsp+200h+var_1D0]
0x18004a8b9  call    ??$ActivateInstance@UIInspectable@Foundation@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUIInspectable@123@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Foundation::IInspectable>(void)
0x18004a8be  lea     rsi, [rdi+110h]
0x18004a8c5  mov     rdx, rax
0x18004a8c8  mov     rcx, rsi
0x18004a8cb  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004a8d0  cmp     [rbp+100h+var_40], r12
0x18004a8d7  jz      short loc_18004A8E6
0x18004a8d9  lea     rcx, [rbp+100h+var_40]
0x18004a8e0  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004a8e5  nop
0x18004a8e6  lea     rcx, [rsp+200h+var_1D0]; this
0x18004a8eb  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004a8f0  nop
0x18004a8f1  test    rbx, rbx
0x18004a8f4  jz      short loc_18004A902
0x18004a8f6  lea     rcx, [rbp+100h+var_50]
0x18004a8fd  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004a902  mov     rcx, [rsi]
0x18004a905  test    rcx, rcx
0x18004a908  jnz     short loc_18004A916
0x18004a90a  mov     [rbp+100h+var_40], r12
0x18004a911  mov     rax, r12
0x18004a914  jmp     short loc_18004A944
0x18004a916  mov     [rbp+100h+var_50], r12
0x18004a91d  mov     rax, [rcx]
0x18004a920  lea     r8, [rbp+100h+var_50]
0x18004a927  lea     rdx, ??$guid_v@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::UI::Shell::IShellContent>
0x18004a92e  mov     rax, [rax]
0x18004a931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a936  mov     rax, [rbp+100h+var_50]
0x18004a93d  mov     [rbp+100h+var_40], rax
0x18004a944  test    rax, rax
0x18004a947  jz      short loc_18004A976
0x18004a949  lea     rdx, [rbp+100h+var_50]
0x18004a950  mov     rcx, r14
0x18004a953  call    ??$as@UShellContentHost@Shell@UI@WindowsUdk@winrt@@@?$com_ptr@VShellContentHost@implementation@Shell@UI@WindowsUdk@winrt@@@winrt@@QEBA?A_PXZ
0x18004a958  nop
0x18004a959  mov     rdx, rax
0x18004a95c  lea     rcx, [rbp+100h+var_40]
0x18004a963  call    ?SetHost@?$consume_WindowsUdk_UI_Shell_IShellContent@UIShellContent@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUShellContentHost@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_IShellContent<winrt::WindowsUdk::UI::Shell::IShellContent>::SetHost(winrt::WindowsUdk::UI::Shell::ShellContentHost const &)
0x18004a968  nop
0x18004a969  lea     rcx, [rbp+100h+var_50]; this
0x18004a970  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004a975  nop
0x18004a976  lea     rcx, [rbp+100h+var_40]; this
0x18004a97d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004a982  mov     rax, [rdi]
0x18004a985  mov     rax, [rax+8]
0x18004a989  jmp     loc_18004AA6A
0x18004a98e  lea     rdx, [rbp+100h+var_50]
  ... truncated ...
```
