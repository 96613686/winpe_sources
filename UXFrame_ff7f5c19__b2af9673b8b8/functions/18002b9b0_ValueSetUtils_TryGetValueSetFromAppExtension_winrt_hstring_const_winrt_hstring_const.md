# ValueSetUtils::TryGetValueSetFromAppExtension(winrt::hstring const &,winrt::hstring const &)

- ea: `0x18002b9b0`
- end: `0x18002bd6d`
- name: `?TryGetValueSetFromAppExtension@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@6@0@Z`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023910`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043a0`
- `0x1800043f4`
- `0x1800046c8`
- `0x1800049ac`
- `0x180006698`
- `0x18000d670`
- `0x180017514`
- `0x18001eaa0`
- `0x1800225a0`
- `0x180028008`
- `0x1800280e4`
- `0x18002b9b0`
- `0x18002cc80`
- `0x18002ce04`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb58`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002bb58`

## string_xrefs

- `0x18002bce1`: `PackageFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
ValueSetUtils::details *__fastcall ValueSetUtils::TryGetValueSetFromAppExtension(
        ValueSetUtils::details *a1,
        _QWORD *a2,
        winrt::hstring *a3)
{
  unsigned int v5; // esi
  unsigned int v6; // r14d
  __int64 v7; // r15
  unsigned int v8; // eax
  struct IUnknown *v9; // rdx
  __int64 (__fastcall *v10)(__int64, _QWORD, void **); // rbx
  void **v11; // rax
  unsigned int v12; // eax
  const WCHAR *v13; // rbx
  unsigned int v14; // eax
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rax
  const struct winrt::Windows::Foundation::Collections::IPropertySet *v18; // r8
  unsigned int v19; // eax
  __int64 *v20; // rbx
  unsigned int v21; // eax
  __int64 *v22; // r14
  struct IInspectableVtbl *lpVtbl; // rbx
  struct IInspectableVtbl *v24; // rbx
  __int64 *v26; // [rsp+38h] [rbp-61h] BYREF
  int v27; // [rsp+40h] [rbp-59h] BYREF
  __int128 v28; // [rsp+48h] [rbp-51h]
  __int64 *v29; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v30[5]; // [rsp+68h] [rbp-31h] BYREF
  __int64 *v31; // [rsp+90h] [rbp-9h] BYREF
  _QWORD *v32; // [rsp+98h] [rbp-1h] BYREF
  __int64 *v33; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v34; // [rsp+A8h] [rbp+Fh] BYREF

  v30[4] = a1;
  *(_QWORD *)a1 = 0;
  v30[0] = *a2;
  v32 = v30;
  v31 = &qword_180073258;
  _InterlockedIncrement64(&qword_180073258);
  if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> )
  {
    _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(
      &v32,
      &v34,
      &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>);
    _InterlockedDecrement64(&qword_180073258);
  }
  else
  {
    _InterlockedDecrement64(&qword_180073258);
    winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::call<_lambda_57b55f0f887558b5f7921754fb17175c_ &>(
      a1,
      &v34,
      &v32);
  }
  v5 = 7;
  v6 = 0;
  LODWORD(v33) = 0;
  v7 = v34;
  v27 = 0;
  v28 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v34 + 56LL))(v34, &v33);
  winrt::check_hresult(&v29, v8, &v27);
  while ( v6 != (_DWORD)v33 )
  {
    v32 = 0;
    v27 = 0;
    v28 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v7 + 48LL);
    v11 = winrt::put_abi((winrt *)&v32, v9);
    v12 = v10(v7, v6, v11);
    winrt::check_hresult(&v29, v12, &v27);
    v13 = winrt::hstring::c_str(a3);
    v31 = 0;
    v27 = 0;
    v28 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(*v32 + 48LL))(v32, &v31);
    winrt::check_hresult(&v26, v14, &v27);
    v5 = v5 & 0xFFFFFFC7 | 0x28;
    v15 = winrt::hstring::c_str((winrt::hstring *)&v31);
    LODWORD(v13) = CompareStringOrdinal(v15, -1, v13, -1, 1);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
    if ( (_DWORD)v13 == 2 )
    {
      v31 = 0;
      v27 = 0;
      v28 = 0;
      v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(*v32 + 88LL))(v32, &v31);
      winrt::check_hresult(&v26, v16, &v27);
      v29 = v31;
      if ( v31 )
      {
        v17 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v31);
        winrt::Windows::Foundation::IUnknown::operator=(a1, v17);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v31);
        ValueSetUtils::details::InsertManifestPropertyValuesRecursive(
          a1,
          (const struct winrt::Windows::Foundation::Collections::ValueSet *)&v29,
          v18);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl'::`2'::impl) )
        {
          v31 = 0;
          v27 = 0;
          v28 = 0;
          v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(*v32 + 80LL))(v32, &v31);
          winrt::check_hresult(&v26, v19, &v27);
          v20 = v31;
          v33 = v31;
          v31 = 0;
          v27 = 0;
          v28 = 0;
          v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(*v32 + 72LL))(v32, &v31);
          winrt::check_hresult(&v26, v21, &v27);
          v22 = v31;
          v26 = v31;
          v30[0] = v20;
          lpVtbl = winrt::box_value((winrt *)&v31, (const struct winrt::param::hstring *)v30).lpVtbl;
          winrt::param::hstring::hstring((winrt::param::hstring *)&v27, L"PackageFullName");
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a1,
            &v27,
            lpVtbl);
          if ( v31 )
            winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v31);
          v30[0] = v22;
          v24 = winrt::box_value((winrt *)&v31, (const struct winrt::param::hstring *)v30).lpVtbl;
          winrt::param::hstring::hstring((winrt::param::hstring *)&v27, L"PackageFolderPath");
          winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
            a1,
            &v27,
            v24);
          if ( v31 )
            winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v31);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v26);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v33);
        }
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v29);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v32);
      break;
    }
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v32);
    ++v6;
  }
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v34);
  return a1;
}

```

## disassembly

```asm
0x18002b9b0  mov     [rsp-8+arg_8], rbx
0x18002b9b5  push    rbp
0x18002b9b6  push    rsi
0x18002b9b7  push    rdi
0x18002b9b8  push    r12
0x18002b9ba  push    r13
0x18002b9bc  push    r14
0x18002b9be  push    r15
0x18002b9c0  lea     rbp, [rsp-27h]
0x18002b9c5  sub     rsp, 0C0h
0x18002b9cc  mov     rax, cs:__security_cookie
0x18002b9d3  xor     rax, rsp
0x18002b9d6  mov     [rbp+57h+var_40], rax
0x18002b9da  mov     r12, r8
0x18002b9dd  mov     rdi, rcx
0x18002b9e0  mov     [rbp+57h+var_68], rcx
0x18002b9e4  xor     r13d, r13d
0x18002b9e7  mov     [rbp+57h+var_C0], r13d
0x18002b9eb  mov     [rcx], r13
0x18002b9ee  mov     [rbp+57h+var_C0], 1
0x18002b9f5  mov     rax, [rdx]
0x18002b9f8  mov     [rbp+57h+var_88], rax
0x18002b9fc  lea     rax, [rbp+57h+var_88]
0x18002ba00  mov     [rbp+57h+var_58], rax
0x18002ba04  lea     rax, qword_180073258
0x18002ba0b  mov     [rbp+57h+var_60], rax
0x18002ba0f  lock inc cs:qword_180073258
0x18002ba17  cmp     cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A, r13; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x18002ba1e  jz      short loc_18002BA3F
0x18002ba20  lea     r8, ??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics>
0x18002ba27  lea     rdx, [rbp+57h+var_48]
0x18002ba2b  lea     rcx, [rbp+57h+var_58]
0x18002ba2f  call    ??R_lambda_57b55f0f887558b5f7921754fb17175c_@@QEBA@AEBUIAppExtensionStatics@AppExtensions@ApplicationModel@WindowsUdk@winrt@@@Z; _lambda_57b55f0f887558b5f7921754fb17175c_::operator()(winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics const &)
0x18002ba34  nop
0x18002ba35  lock dec cs:qword_180073258
0x18002ba3d  jmp     short loc_18002BA54
0x18002ba3f  lock dec cs:qword_180073258
0x18002ba47  lea     r8, [rbp+57h+var_58]
0x18002ba4b  lea     rdx, [rbp+57h+var_48]
0x18002ba4f  call    ??$call@AEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_57b55f0f887558b5f7921754fb17175c_@@@Z
0x18002ba54  mov     esi, 7
0x18002ba59  mov     [rbp+57h+var_C0], esi
0x18002ba5c  mov     r14d, r13d
0x18002ba5f  mov     dword ptr [rbp+57h+var_50], r13d
0x18002ba63  mov     r15, [rbp+57h+var_48]
0x18002ba67  mov     [rbp+57h+var_B0], r13d
0x18002ba6b  xorps   xmm0, xmm0
0x18002ba6e  movdqu  [rbp+57h+var_A8], xmm0
0x18002ba73  mov     rax, [r15]
0x18002ba76  lea     rdx, [rbp+57h+var_50]
0x18002ba7a  mov     rcx, r15
0x18002ba7d  mov     rax, [rax+38h]
0x18002ba81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba86  lea     r8, [rbp+57h+var_B0]
0x18002ba8a  mov     edx, eax
0x18002ba8c  lea     rcx, [rbp+57h+var_90]
0x18002ba90  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002ba95  cmp     r14d, dword ptr [rbp+57h+var_50]
0x18002ba99  jz      loc_18002BD39
0x18002ba9f  mov     [rbp+57h+var_58], r13
0x18002baa3  or      esi, 10h
0x18002baa6  mov     [rbp+57h+var_C0], esi
0x18002baa9  mov     [rbp+57h+var_B0], r13d
0x18002baad  xorps   xmm0, xmm0
0x18002bab0  movdqu  [rbp+57h+var_A8], xmm0
0x18002bab5  mov     rax, [r15]
0x18002bab8  mov     rbx, [rax+30h]
0x18002babc  lea     rcx, [rbp+57h+var_58]; this
0x18002bac0  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18002bac5  mov     r8, rax
0x18002bac8  mov     edx, r14d
0x18002bacb  mov     rcx, r15
0x18002bace  mov     rax, rbx
0x18002bad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bad6  lea     r8, [rbp+57h+var_B0]
0x18002bada  mov     edx, eax
0x18002badc  lea     rcx, [rbp+57h+var_90]
0x18002bae0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bae5  and     esi, 0FFFFFFEFh
0x18002bae8  or      esi, 8
0x18002baeb  mov     [rbp+57h+var_C0], esi
0x18002baee  mov     rcx, r12; this
0x18002baf1  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18002baf6  mov     rbx, rax
0x18002baf9  mov     [rbp+57h+var_60], r13
0x18002bafd  mov     rcx, [rbp+57h+var_58]
0x18002bb01  mov     [rbp+57h+var_B0], r13d
0x18002bb05  xorps   xmm0, xmm0
0x18002bb08  movdqu  [rbp+57h+var_A8], xmm0
0x18002bb0d  mov     rax, [rcx]
0x18002bb10  lea     rdx, [rbp+57h+var_60]
0x18002bb14  mov     rax, [rax+30h]
0x18002bb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb1d  lea     r8, [rbp+57h+var_B0]
0x18002bb21  mov     edx, eax
0x18002bb23  lea     rcx, [rbp+57h+var_B8]
0x18002bb27  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bb2c  mov     rax, [rbp+57h+var_60]
0x18002bb30  mov     [rbp+57h+var_60], rax
0x18002bb34  or      esi, 20h
0x18002bb37  mov     [rbp+57h+var_C0], esi
0x18002bb3a  lea     rcx, [rbp+57h+var_60]; this
0x18002bb3e  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18002bb43  mov     rcx, rax; lpString1
0x18002bb46  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x18002bb4e  or      r9d, 0FFFFFFFFh; cchCount2
0x18002bb52  mov     r8, rbx; lpString2
0x18002bb55  or      edx, r9d; cchCount1
0x18002bb58  call    cs:__imp_CompareStringOrdinal
0x18002bb5e  mov     ebx, eax
0x18002bb60  lea     rcx, [rbp+57h+var_60]
0x18002bb64  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002bb69  cmp     ebx, 2
0x18002bb6c  jz      short loc_18002BB7F
0x18002bb6e  lea     rcx, [rbp+57h+var_58]; this
0x18002bb72  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002bb77  inc     r14d
0x18002bb7a  jmp     loc_18002BA95
0x18002bb7f  mov     [rbp+57h+var_60], r13
0x18002bb83  mov     rcx, [rbp+57h+var_58]
0x18002bb87  mov     [rbp+57h+var_B0], r13d
0x18002bb8b  xorps   xmm0, xmm0
0x18002bb8e  movdqu  [rbp+57h+var_A8], xmm0
0x18002bb93  mov     rax, [rcx]
0x18002bb96  lea     rdx, [rbp+57h+var_60]
0x18002bb9a  mov     rax, [rax+58h]
0x18002bb9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bba3  lea     r8, [rbp+57h+var_B0]
0x18002bba7  mov     edx, eax
0x18002bba9  lea     rcx, [rbp+57h+var_B8]
0x18002bbad  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bbb2  mov     rax, [rbp+57h+var_60]
0x18002bbb6  mov     [rbp+57h+var_90], rax
0x18002bbba  or      esi, 40h
0x18002bbbd  mov     [rbp+57h+var_C0], esi
0x18002bbc0  test    rax, rax
0x18002bbc3  jz      loc_18002BD25
0x18002bbc9  lea     rcx, [rbp+57h+var_60]; this
0x18002bbcd  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x18002bbd2  mov     rdx, rax
0x18002bbd5  mov     rcx, rdi
0x18002bbd8  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18002bbdd  lea     rcx, [rbp+57h+var_60]; this
0x18002bbe1  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002bbe6  lea     rdx, [rbp+57h+var_90]; struct winrt::Windows::Foundation::Collections::ValueSet *
0x18002bbea  mov     rcx, rdi; this
0x18002bbed  call    ?InsertManifestPropertyValuesRecursive@details@ValueSetUtils@@YAXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySet@4567@@Z; ValueSetUtils::details::InsertManifestPropertyValuesRecursive(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::IPropertySet const &)
0x18002bbf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior> `wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl(void)'::`2'::impl
0x18002bbf9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(void)
0x18002bbfe  test    al, al
0x18002bc00  jz      loc_18002BD25
0x18002bc06  mov     [rbp+57h+var_60], r13
0x18002bc0a  mov     rcx, [rbp+57h+var_58]
0x18002bc0e  mov     [rbp+57h+var_B0], r13d
0x18002bc12  xorps   xmm0, xmm0
0x18002bc15  movdqu  [rbp+57h+var_A8], xmm0
0x18002bc1a  mov     rax, [rcx]
0x18002bc1d  lea     rdx, [rbp+57h+var_60]
0x18002bc21  mov     rax, [rax+50h]
0x18002bc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc2a  lea     r8, [rbp+57h+var_B0]
0x18002bc2e  mov     edx, eax
0x18002bc30  lea     rcx, [rbp+57h+var_B8]
0x18002bc34  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bc39  mov     rbx, [rbp+57h+var_60]
0x18002bc3d  mov     [rbp+57h+var_50], rbx
0x18002bc41  bts     esi, 7
0x18002bc45  mov     [rbp+57h+var_C0], esi
0x18002bc48  mov     [rbp+57h+var_60], r13
0x18002bc4c  mov     rcx, [rbp+57h+var_58]
0x18002bc50  mov     [rbp+57h+var_B0], r13d
0x18002bc54  xorps   xmm0, xmm0
0x18002bc57  movdqu  [rbp+57h+var_A8], xmm0
0x18002bc5c  mov     rax, [rcx]
0x18002bc5f  lea     rdx, [rbp+57h+var_60]
0x18002bc63  mov     rax, [rax+48h]
0x18002bc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc6c  lea     r8, [rbp+57h+var_B0]
0x18002bc70  mov     edx, eax
0x18002bc72  lea     rcx, [rbp+57h+var_B8]
0x18002bc76  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bc7b  mov     r14, [rbp+57h+var_60]
0x18002bc7f  mov     [rbp+57h+var_B8], r14
0x18002bc83  bts     esi, 8
0x18002bc87  mov     [rbp+57h+var_C0], esi
0x18002bc8a  mov     [rbp+57h+var_88], rbx
0x18002bc8e  lea     rdx, [rbp+57h+var_88]; struct winrt::param::hstring *
0x18002bc92  lea     rcx, [rbp+57h+var_60]; this
0x18002bc96  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x18002bc9b  mov     rbx, rax
0x18002bc9e  lea     rdx, aPackagefullnam; "PackageFullName"
0x18002bca5  lea     rcx, [rbp+57h+var_B0]; this
0x18002bca9  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18002bcae  mov     r8, rbx
0x18002bcb1  lea     rdx, [rbp+57h+var_B0]
0x18002bcb5  mov     rcx, rdi
0x18002bcb8  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18002bcbd  nop
0x18002bcbe  cmp     [rbp+57h+var_60], r13
0x18002bcc2  jz      short loc_18002BCCD
0x18002bcc4  lea     rcx, [rbp+57h+var_60]
0x18002bcc8  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18002bccd  mov     [rbp+57h+var_88], r14
0x18002bcd1  lea     rdx, [rbp+57h+var_88]; struct winrt::param::hstring *
0x18002bcd5  lea     rcx, [rbp+57h+var_60]; this
0x18002bcd9  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x18002bcde  mov     rbx, rax
0x18002bce1  lea     rdx, aPackagefolderp; "PackageFolderPath"
0x18002bce8  lea     rcx, [rbp+57h+var_B0]; this
0x18002bcec  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18002bcf1  mov     r8, rbx
0x18002bcf4  lea     rdx, [rbp+57h+var_B0]
0x18002bcf8  mov     rcx, rdi
0x18002bcfb  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x18002bd00  nop
0x18002bd01  cmp     [rbp+57h+var_60], r13
0x18002bd05  jz      short loc_18002BD11
0x18002bd07  lea     rcx, [rbp+57h+var_60]
0x18002bd0b  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18002bd10  nop
0x18002bd11  lea     rcx, [rbp+57h+var_B8]
0x18002bd15  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002bd1a  nop
0x18002bd1b  lea     rcx, [rbp+57h+var_50]
0x18002bd1f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002bd24  nop
0x18002bd25  lea     rcx, [rbp+57h+var_90]; this
0x18002bd29  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002bd2e  nop
0x18002bd2f  lea     rcx, [rbp+57h+var_58]; this
0x18002bd33  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002bd38  nop
0x18002bd39  lea     rcx, [rbp+57h+var_48]; this
0x18002bd3d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18002bd42  mov     rax, rdi
0x18002bd45  mov     rcx, [rbp+57h+var_40]
0x18002bd49  xor     rcx, rsp; StackCookie
0x18002bd4c  call    __security_check_cookie
0x18002bd51  mov     rbx, [rsp+0F0h+arg_8]
0x18002bd59  add     rsp, 0C0h
0x18002bd60  pop     r15
0x18002bd62  pop     r14
0x18002bd64  pop     r13
0x18002bd66  pop     r12
0x18002bd68  pop     rdi
0x18002bd69  pop     rsi
0x18002bd6a  pop     rbp
0x18002bd6b  retn
```
