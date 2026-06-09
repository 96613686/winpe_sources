# winrt_get_activation_factory(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x180007fc0`
- end: `0x1800082b2`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800082b8`

## callees

- `0x180004c8c`
- `0x1800079a0`
- `0x180007e7c`
- `0x180007fc0`
- `0x18000dd40`
- `0x18000de38`
- `0x18000dfc0`
- `0x1800128e0`
- `0x1800195b8`
- `0x18001fd30`
- `0x1800259c0`
- `0x1800273ec`
- `0x180028ddc`

## string_xrefs

- `0x180007fd0`: `Windows.Internal.Accessibility.Experience.CustomCursor`
- `0x180008179`: `Windows.UI.Accessibility.ScreenReaderService`

## pseudocode

```c
_OWORD *winrt_get_activation_factory()
{
  __int64 v0; // rcx
  __int64 v1; // r10
  _QWORD *v2; // rax
  _OWORD *v3; // rbx
  __int64 v4; // r8
  void ***v5; // r8
  void **v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // r10
  _OWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  void ***v14; // r9
  void **v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r10
  _QWORD *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r10
  _OWORD *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // r10
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r10
  _OWORD *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r10
  _OWORD *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  const unsigned __int16 *v42; // [rsp+20h] [rbp-10h] BYREF
  __int64 v43; // [rsp+28h] [rbp-8h]
  __int64 v44; // [rsp+48h] [rbp+18h] BYREF

  v42 = L"Windows.Internal.Accessibility.Experience.CustomCursor";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.Internal.Accessibility.Experience.CustomCursor");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v0, v1, &v42) )
  {
    v2 = operator new(0x18u);
    *(_OWORD *)v2 = 0;
    v3 = v2 + 2;
    v2[2] = 0;
    winrt::impl::producers_base<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(v2 + 2);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v4 + 8);
    v6 = &winrt::impl::heap_implements<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor>::`vftable';
LABEL_3:
    *v5 = v6;
LABEL_4:
    v44 = 0;
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v44);
    return v3;
  }
  v42 = L"Windows.Internal.Shell.FocusSessionActiveTheme";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.Internal.Shell.FocusSessionActiveTheme");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v8, v9, &v42) )
  {
    v10 = operator new(0x20u);
    v3 = v10 + 1;
    *v10 = 0;
    v10[1] = 0;
    winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionActiveThemeFactory>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionActiveThemeFactory>>(
      v10 + 1,
      v11,
      v12,
      v10);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v13 + 8);
    v15 = &winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme>::`vftable';
LABEL_7:
    *v14 = v15;
    goto LABEL_4;
  }
  v42 = L"Windows.Internal.Shell.FocusSessionOffTheme";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.Internal.Shell.FocusSessionOffTheme");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v16, v17, &v42) )
  {
    v18 = operator new(0x18u);
    *(_OWORD *)v18 = 0;
    v3 = v18 + 2;
    v18[2] = 0;
    winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(v18 + 2);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v19 + 8);
    v6 = &winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme>::`vftable';
    goto LABEL_3;
  }
  v42 = L"Windows.Internal.Shell.FocusSessionThemeManager";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.Internal.Shell.FocusSessionThemeManager");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v20, v21, &v42) )
  {
    v22 = operator new(0x20u);
    v3 = v22 + 1;
    *v22 = 0;
    v22[1] = 0;
    winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>>(
      v22 + 1,
      v23,
      v24,
      v22);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v25 + 8);
    v15 = &winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager>::`vftable';
    goto LABEL_7;
  }
  v42 = L"Windows.UI.Accessibility.ScreenReaderService";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.UI.Accessibility.ScreenReaderService");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v26, v27, &v42) )
  {
    v28 = operator new(0x18u);
    *(_OWORD *)v28 = 0;
    v3 = v28 + 2;
    v28[2] = 0;
    winrt::impl::producers_base<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(v28 + 2);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v29 + 8);
    v6 = &winrt::impl::heap_implements<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService>::`vftable';
    goto LABEL_3;
  }
  v42 = L"Windows.UI.Shell.FocusSessionManager";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.UI.Shell.FocusSessionManager");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v30, v31, &v42) )
  {
    v32 = operator new(0x20u);
    v3 = v32 + 1;
    *v32 = 0;
    v32[1] = 0;
    winrt::impl::producers_base<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::Shell::IFocusSessionManagerStatics>>::producers_base<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::Shell::IFocusSessionManagerStatics>>(
      v32 + 1,
      v33,
      v34,
      v32);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v35 + 8);
    v15 = &winrt::impl::heap_implements<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager>::`vftable';
    goto LABEL_7;
  }
  v42 = L"Windows.UI.ViewManagement.Core.UISettingsController";
  v43 = std::_WChar_traits<unsigned short>::length(L"Windows.UI.ViewManagement.Core.UISettingsController");
  if ( (unsigned __int8)lambda_02173b63ee26a1fab1ddde65a79c3b1c_::operator()(v36, v37, &v42) )
  {
    v38 = operator new(0x20u);
    v3 = v38 + 1;
    *v38 = 0;
    v38[1] = 0;
    winrt::impl::producers_base<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>>::producers_base<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>>(
      v38 + 1,
      v39,
      v40,
      v38);
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    std::atomic<unsigned __int64>::atomic<unsigned __int64>(v41 + 8);
    v15 = &winrt::impl::heap_implements<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController>::`vftable';
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x180007fc0  mov     [rsp-8+arg_0], rbx
0x180007fc5  push    rbp
0x180007fc6  mov     rbp, rsp
0x180007fc9  sub     rsp, 30h
0x180007fcd  mov     r10, rcx
0x180007fd0  lea     rcx, aWindowsInterna_0; "Windows.Internal.Accessibility.Experien"...
0x180007fd7  mov     [rbp+var_10], rcx
0x180007fdb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180007fe0  lea     r8, [rbp+var_10]
0x180007fe4  mov     [rbp+var_8], rax
0x180007fe8  mov     rdx, r10
0x180007feb  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180007ff0  test    al, al
0x180007ff2  jz      short loc_18000804D
0x180007ff4  mov     ecx, 18h; Size
0x180007ff9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ffe  mov     r8, rax
0x180008001  xorps   xmm0, xmm0
0x180008004  xor     eax, eax
0x180008006  movups  xmmword ptr [r8], xmm0
0x18000800a  lea     rbx, [r8+10h]
0x18000800e  mov     [r8+10h], rax
0x180008012  mov     rcx, rbx
0x180008015  call    ??0?$producers_base@UCustomCursor@factory_implementation@Experience@Accessibility@Internal@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(void)
0x18000801a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008021  lea     rcx, [r8+8]
0x180008025  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18000802a  lea     rcx, ??_7?$heap_implements@UCustomCursor@factory_implementation@Experience@Accessibility@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Accessibility::Experience::factory_implementation::CustomCursor>::`vftable'
0x180008031  mov     [r8], rcx
0x180008034  lea     rcx, [rbp+arg_8]
0x180008038  mov     [rbp+arg_8], 0
0x180008040  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180008045  mov     rax, rbx
0x180008048  jmp     loc_1800082A7
0x18000804d  lea     rcx, aWindowsInterna_2; "Windows.Internal.Shell.FocusSessionActi"...
0x180008054  mov     [rbp+var_10], rcx
0x180008058  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000805d  lea     r8, [rbp+var_10]
0x180008061  mov     [rbp+var_8], rax
0x180008065  mov     rdx, r10
0x180008068  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x18000806d  test    al, al
0x18000806f  jz      short loc_1800080B0
0x180008071  mov     ecx, 20h ; ' '; Size
0x180008076  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000807b  xorps   xmm0, xmm0
0x18000807e  mov     r9, rax
0x180008081  lea     rbx, [rax+10h]
0x180008085  movups  xmmword ptr [rax], xmm0
0x180008088  mov     rcx, rbx
0x18000808b  movups  xmmword ptr [rax+10h], xmm0
0x18000808f  call    ??0?$producers_base@UFocusSessionActiveTheme@factory_implementation@Shell@Internal@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIFocusSessionActiveThemeFactory@Shell@Internal@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionActiveThemeFactory>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionActiveThemeFactory>>(void)
0x180008094  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000809b  lea     rcx, [r9+8]
0x18000809f  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1800080a4  lea     rcx, ??_7?$heap_implements@UFocusSessionActiveTheme@factory_implementation@Shell@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionActiveTheme>::`vftable'
0x1800080ab  mov     [r9], rcx
0x1800080ae  jmp     short loc_180008034
0x1800080b0  lea     rcx, aWindowsInterna_3; "Windows.Internal.Shell.FocusSessionOffT"...
0x1800080b7  mov     [rbp+var_10], rcx
0x1800080bb  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800080c0  lea     r8, [rbp+var_10]
0x1800080c4  mov     [rbp+var_8], rax
0x1800080c8  mov     rdx, r10
0x1800080cb  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800080d0  test    al, al
0x1800080d2  jz      short loc_180008116
0x1800080d4  mov     ecx, 18h; Size
0x1800080d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080de  mov     r8, rax
0x1800080e1  xorps   xmm0, xmm0
0x1800080e4  xor     eax, eax
0x1800080e6  movups  xmmword ptr [r8], xmm0
0x1800080ea  lea     rbx, [r8+10h]
0x1800080ee  mov     [r8+10h], rax
0x1800080f2  mov     rcx, rbx
0x1800080f5  call    ??0?$producers_base@UFocusSessionOffTheme@factory_implementation@Shell@Internal@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(void)
0x1800080fa  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008101  lea     rcx, [r8+8]
0x180008105  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18000810a  lea     rcx, ??_7?$heap_implements@UFocusSessionOffTheme@factory_implementation@Shell@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionOffTheme>::`vftable'
0x180008111  jmp     loc_180008031
0x180008116  lea     rcx, aWindowsInterna_1; "Windows.Internal.Shell.FocusSessionThem"...
0x18000811d  mov     [rbp+var_10], rcx
0x180008121  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180008126  lea     r8, [rbp+var_10]
0x18000812a  mov     [rbp+var_8], rax
0x18000812e  mov     rdx, r10
0x180008131  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180008136  test    al, al
0x180008138  jz      short loc_180008179
0x18000813a  mov     ecx, 20h ; ' '; Size
0x18000813f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008144  xorps   xmm0, xmm0
0x180008147  mov     r9, rax
0x18000814a  lea     rbx, [rax+10h]
0x18000814e  movups  xmmword ptr [rax], xmm0
0x180008151  mov     rcx, rbx
0x180008154  movups  xmmword ptr [rax+10h], xmm0
0x180008158  call    ??0?$producers_base@UFocusSessionThemeManager@factory_implementation@Shell@Internal@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIFocusSessionThemeManagerStatics@Shell@Internal@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>>::producers_base<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Shell::IFocusSessionThemeManagerStatics>>(void)
0x18000815d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008164  lea     rcx, [r9+8]
0x180008168  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x18000816d  lea     rcx, ??_7?$heap_implements@UFocusSessionThemeManager@factory_implementation@Shell@Internal@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::Internal::Shell::factory_implementation::FocusSessionThemeManager>::`vftable'
0x180008174  jmp     loc_1800080AB
0x180008179  lea     rcx, aWindowsUiAcces_0; "Windows.UI.Accessibility.ScreenReaderSe"...
0x180008180  mov     [rbp+var_10], rcx
0x180008184  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180008189  lea     r8, [rbp+var_10]
0x18000818d  mov     [rbp+var_8], rax
0x180008191  mov     rdx, r10
0x180008194  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180008199  test    al, al
0x18000819b  jz      short loc_1800081DF
0x18000819d  mov     ecx, 18h; Size
0x1800081a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800081a7  mov     r8, rax
0x1800081aa  xorps   xmm0, xmm0
0x1800081ad  xor     eax, eax
0x1800081af  movups  xmmword ptr [r8], xmm0
0x1800081b3  lea     rbx, [r8+10h]
0x1800081b7  mov     [r8+10h], rax
0x1800081bb  mov     rcx, rbx
0x1800081be  call    ??0?$producers_base@UScreenReaderService@factory_implementation@Accessibility@UI@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,std::tuple<winrt::Windows::Foundation::IActivationFactory>>::producers_base<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService,std::tuple<winrt::Windows::Foundation::IActivationFactory>>(void)
0x1800081c3  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800081ca  lea     rcx, [r8+8]
0x1800081ce  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1800081d3  lea     rcx, ??_7?$heap_implements@UScreenReaderService@factory_implementation@Accessibility@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::Accessibility::factory_implementation::ScreenReaderService>::`vftable'
0x1800081da  jmp     loc_180008031
0x1800081df  lea     rcx, aWindowsUiShell; "Windows.UI.Shell.FocusSessionManager"
0x1800081e6  mov     [rbp+var_10], rcx
0x1800081ea  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800081ef  lea     r8, [rbp+var_10]
0x1800081f3  mov     [rbp+var_8], rax
0x1800081f7  mov     rdx, r10
0x1800081fa  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x1800081ff  test    al, al
0x180008201  jz      short loc_180008242
0x180008203  mov     ecx, 20h ; ' '; Size
0x180008208  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000820d  xorps   xmm0, xmm0
0x180008210  mov     r9, rax
0x180008213  lea     rbx, [rax+10h]
0x180008217  movups  xmmword ptr [rax], xmm0
0x18000821a  mov     rcx, rbx
0x18000821d  movups  xmmword ptr [rax+10h], xmm0
0x180008221  call    ??0?$producers_base@UFocusSessionManager@factory_implementation@Shell@UI@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIFocusSessionManagerStatics@Shell@UI@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::Shell::IFocusSessionManagerStatics>>::producers_base<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::Shell::IFocusSessionManagerStatics>>(void)
0x180008226  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000822d  lea     rcx, [r9+8]
0x180008231  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180008236  lea     rcx, ??_7?$heap_implements@UFocusSessionManager@factory_implementation@Shell@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::Shell::factory_implementation::FocusSessionManager>::`vftable'
0x18000823d  jmp     loc_1800080AB
0x180008242  lea     rcx, aWindowsUiViewm; "Windows.UI.ViewManagement.Core.UISettin"...
0x180008249  mov     [rbp+var_10], rcx
0x18000824d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180008252  lea     r8, [rbp+var_10]
0x180008256  mov     [rbp+var_8], rax
0x18000825a  mov     rdx, r10
0x18000825d  call    _lambda_02173b63ee26a1fab1ddde65a79c3b1c___operator__
0x180008262  test    al, al
0x180008264  jz      short loc_1800082A5
0x180008266  mov     ecx, 20h ; ' '; Size
0x18000826b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008270  xorps   xmm0, xmm0
0x180008273  mov     r9, rax
0x180008276  lea     rbx, [rax+10h]
0x18000827a  movups  xmmword ptr [rax], xmm0
0x18000827d  mov     rcx, rbx
0x180008280  movups  xmmword ptr [rax+10h], xmm0
0x180008284  call    ??0?$producers_base@UUISettingsController@factory_implementation@Core@ViewManagement@UI@Windows@winrt@@V?$tuple@UIActivationFactory@Foundation@Windows@winrt@@UIUISettingsControllerStatics@Core@ViewManagement@UI@34@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>>::producers_base<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,std::tuple<winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>>(void)
0x180008289  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180008290  lea     rcx, [r9+8]
0x180008294  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180008299  lea     rcx, ??_7?$heap_implements@UUISettingsController@factory_implementation@Core@ViewManagement@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController>::`vftable'
0x1800082a0  jmp     loc_1800080AB
0x1800082a5  xor     eax, eax
0x1800082a7  mov     rbx, [rsp+30h+arg_0]
0x1800082ac  add     rsp, 30h
0x1800082b0  pop     rbp
0x1800082b1  retn
```
