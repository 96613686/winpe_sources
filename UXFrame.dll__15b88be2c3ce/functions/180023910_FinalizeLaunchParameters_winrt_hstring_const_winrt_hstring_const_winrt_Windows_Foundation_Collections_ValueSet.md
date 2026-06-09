# FinalizeLaunchParameters(winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>> &)

- ea: `0x180023910`
- end: `0x180023bd4`
- name: `?FinalizeLaunchParameters@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@5@0AEBU12345@AEAV?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@@Z`
- size: `708`
- prototype: `_QWORD *__fastcall(_QWORD *, winrt::hstring *, winrt::hstring *, __int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002da60`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043f4`
- `0x1800049ac`
- `0x180006698`
- `0x18000d670`
- `0x18000d810`
- `0x18000ecd8`
- `0x180016c0c`
- `0x180017514`
- `0x180020c7c`
- `0x180021e6c`
- `0x1800221e4`
- `0x180022220`
- `0x1800222a0`
- `0x180023910`
- `0x180028008`
- `0x18002b9b0`
- `0x18002bd74`
- `0x18002c5f0`
- `0x18002cdac`

## string_xrefs

- `0x1800239f7`: `PackageFolderPath`
- `0x180023a22`: `PackageFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall FinalizeLaunchParameters(_QWORD *a1, winrt::hstring *a2, winrt::hstring *a3, __int64 a4, __int64 a5)
{
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  char v13; // bl
  __int64 v14; // rbx
  __int64 v16; // [rsp+20h] [rbp-61h] BYREF
  __int64 v17; // [rsp+28h] [rbp-59h] BYREF
  int v18; // [rsp+30h] [rbp-51h]
  _BYTE v19[8]; // [rsp+38h] [rbp-49h] BYREF
  __int64 v20; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v21[5]; // [rsp+48h] [rbp-39h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v23; // [rsp+90h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+98h] [rbp+17h] BYREF

  v21[4] = a1;
  v18 = 0;
  v8 = winrt::hstring::c_str(a3);
  winrt::hstring::hstring((winrt::hstring *)&v23, v8);
  v9 = winrt::hstring::c_str(a2);
  winrt::hstring::hstring((winrt::hstring *)&v24, v9);
  ValueSetUtils::TryGetValueSetFromAppExtension((ValueSetUtils::details *)&v16, &v24, (winrt::hstring *)&v23);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v24);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v23);
  winrt::hstring::hstring((winrt::hstring *)&v24, L"ShellContentProperties");
  ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(
    a1,
    &v24,
    &v16);
  v18 = 1;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v24);
  if ( !*a1 )
  {
    v10 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v17);
    winrt::Windows::Foundation::IUnknown::operator=(a1, v10);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v17);
  }
  if ( v16 )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"PackageFolderPath");
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
      &v16,
      &v23,
      v22);
    v11 = v23;
    if ( v23 )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"PackageFolderPath");
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
        a1,
        v21,
        &v23);
      v11 = v23;
    }
    if ( v11 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v23);
    winrt::param::hstring::hstring((winrt::param::hstring *)v21, L"PackageFullName");
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
      &v16,
      &v23,
      v21);
    v12 = v23;
    if ( v23 )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"PackageFullName");
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
        a1,
        v22,
        &v23);
      v12 = v23;
    }
    if ( v12 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v23);
  }
  v23 = 0;
  v13 = winrt::Windows::Foundation::operator==(a4, &v23);
  if ( v23 )
    winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v23);
  if ( !v13 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IPropertySet,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::begin(
      a4,
      &v23);
    v17 = 0;
    while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v23, &v17) )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::operator*(
        &v23,
        &v24);
      v14 = winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Value(
              &v24,
              &v20);
      v21[0] = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<winrt::hstring>,winrt::hstring>::Value(
                            &v24,
                            v19);
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
        a1,
        v21,
        v14);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
      if ( v20 )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v20);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v24);
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::operator++(&v23);
    }
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v17);
    winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v23);
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(
                          a5,
                          v19)
           + 304LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(v19);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v16);
  return a1;
}

```

## disassembly

```asm
0x180023910  push    rbp
0x180023912  push    rbx
0x180023913  push    rsi
0x180023914  push    rdi
0x180023915  push    r14
0x180023917  lea     rbp, [rsp-2Fh]
0x18002391c  sub     rsp, 0B0h
0x180023923  mov     rax, cs:__security_cookie
0x18002392a  xor     rax, rsp
0x18002392d  mov     [rbp+4Fh+var_30], rax
0x180023931  mov     rsi, r9
0x180023934  mov     rbx, rdx
0x180023937  mov     rdi, rcx
0x18002393a  mov     [rbp+4Fh+var_68], rcx
0x18002393e  mov     r14, [rbp+4Fh+arg_20]
0x180023942  mov     [rbp+4Fh+var_A0], 0
0x180023949  mov     rcx, r8; this
0x18002394c  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180023951  mov     rdx, rax; wchar_t *
0x180023954  lea     rcx, [rbp+4Fh+var_40]; this
0x180023958  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002395d  nop
0x18002395e  mov     rcx, rbx; this
0x180023961  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180023966  mov     rdx, rax; wchar_t *
0x180023969  lea     rcx, [rbp+4Fh+var_38]; this
0x18002396d  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180023972  nop
0x180023973  lea     r8, [rbp+4Fh+var_40]
0x180023977  lea     rdx, [rbp+4Fh+var_38]
0x18002397b  lea     rcx, [rbp+4Fh+var_B0]
0x18002397f  call    ?TryGetValueSetFromAppExtension@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@6@0@Z; ValueSetUtils::TryGetValueSetFromAppExtension(winrt::hstring const &,winrt::hstring const &)
0x180023984  nop
0x180023985  lea     rcx, [rbp+4Fh+var_38]
0x180023989  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002398e  nop
0x18002398f  lea     rcx, [rbp+4Fh+var_40]
0x180023993  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180023998  lea     rdx, aShellcontentpr; "ShellContentProperties"
0x18002399f  lea     rcx, [rbp+4Fh+var_38]; this
0x1800239a3  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x1800239a8  nop
0x1800239a9  lea     r8, [rbp+4Fh+var_B0]
0x1800239ad  lea     rdx, [rbp+4Fh+var_38]
0x1800239b1  mov     rcx, rdi
0x1800239b4  call    ??$try_get_value@UValueSet@Collections@Foundation@Windows@winrt@@U12345@@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@5@AEBU12345@@Z; ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1800239b9  mov     [rbp+4Fh+var_A0], 1
0x1800239c0  lea     rcx, [rbp+4Fh+var_38]
0x1800239c4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800239c9  cmp     qword ptr [rdi], 0
0x1800239cd  jnz     short loc_1800239EC
0x1800239cf  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800239d3  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x1800239d8  mov     rdx, rax
0x1800239db  mov     rcx, rdi
0x1800239de  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800239e3  lea     rcx, [rbp+4Fh+var_A8]; this
0x1800239e7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x1800239ec  cmp     [rbp+4Fh+var_B0], 0
0x1800239f1  jz      loc_180023AB1
0x1800239f7  lea     rdx, aPackagefolderp; "PackageFolderPath"
0x1800239fe  lea     rcx, [rbp+4Fh+var_60]; this
0x180023a02  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180023a07  lea     r8, [rbp+4Fh+var_60]
0x180023a0b  lea     rdx, [rbp+4Fh+var_40]
0x180023a0f  lea     rcx, [rbp+4Fh+var_B0]
0x180023a13  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x180023a18  nop
0x180023a19  mov     rax, [rbp+4Fh+var_40]
0x180023a1d  test    rax, rax
0x180023a20  jz      short loc_180023A46
0x180023a22  lea     rdx, aPackagefolderp; "PackageFolderPath"
0x180023a29  lea     rcx, [rbp+4Fh+var_88]; this
0x180023a2d  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180023a32  lea     r8, [rbp+4Fh+var_40]
0x180023a36  lea     rdx, [rbp+4Fh+var_88]
0x180023a3a  mov     rcx, rdi
0x180023a3d  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x180023a42  mov     rax, [rbp+4Fh+var_40]
0x180023a46  test    rax, rax
0x180023a49  jz      short loc_180023A54
0x180023a4b  lea     rcx, [rbp+4Fh+var_40]
0x180023a4f  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180023a54  lea     rdx, aPackagefullnam; "PackageFullName"
0x180023a5b  lea     rcx, [rbp+4Fh+var_88]; this
0x180023a5f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180023a64  lea     r8, [rbp+4Fh+var_88]
0x180023a68  lea     rdx, [rbp+4Fh+var_40]
0x180023a6c  lea     rcx, [rbp+4Fh+var_B0]
0x180023a70  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x180023a75  nop
0x180023a76  mov     rax, [rbp+4Fh+var_40]
0x180023a7a  test    rax, rax
0x180023a7d  jz      short loc_180023AA3
0x180023a7f  lea     rdx, aPackagefullnam; "PackageFullName"
0x180023a86  lea     rcx, [rbp+4Fh+var_60]; this
0x180023a8a  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180023a8f  lea     r8, [rbp+4Fh+var_40]
0x180023a93  lea     rdx, [rbp+4Fh+var_60]
0x180023a97  mov     rcx, rdi
0x180023a9a  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x180023a9f  mov     rax, [rbp+4Fh+var_40]
0x180023aa3  test    rax, rax
0x180023aa6  jz      short loc_180023AB1
0x180023aa8  lea     rcx, [rbp+4Fh+var_40]
0x180023aac  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180023ab1  mov     [rbp+4Fh+var_40], 0
0x180023ab9  lea     rdx, [rbp+4Fh+var_40]
0x180023abd  mov     rcx, rsi
0x180023ac0  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023ac5  mov     bl, al
0x180023ac7  cmp     [rbp+4Fh+var_40], 0
0x180023acc  jz      short loc_180023AD7
0x180023ace  lea     rcx, [rbp+4Fh+var_40]
0x180023ad2  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180023ad7  test    bl, bl
0x180023ad9  jnz     loc_180023B8D
0x180023adf  lea     rdx, [rbp+4Fh+var_40]
0x180023ae3  mov     rcx, rsi
0x180023ae6  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@UIPropertySet@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IPropertySet,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::begin(void)
0x180023aeb  nop
0x180023aec  mov     [rbp+4Fh+var_A8], 0
0x180023af4  lea     rdx, [rbp+4Fh+var_A8]
0x180023af8  lea     rcx, [rbp+4Fh+var_40]
0x180023afc  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180023b01  test    al, al
0x180023b03  jnz     short loc_180023B7A
0x180023b05  lea     rdx, [rbp+4Fh+var_38]
0x180023b09  lea     rcx, [rbp+4Fh+var_40]
0x180023b0d  call    ??D?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@2345@@impl@winrt@@QEBA?AU?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@2@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::operator*(void)
0x180023b12  nop
0x180023b13  lea     rdx, [rbp+4Fh+var_90]
0x180023b17  lea     rcx, [rbp+4Fh+var_38]
0x180023b1b  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Value(void)
0x180023b20  mov     rbx, rax
0x180023b23  lea     rdx, [rbp+4Fh+var_98]
0x180023b27  lea     rcx, [rbp+4Fh+var_38]
0x180023b2b  call    ?Value@?$consume_Windows_Foundation_IReference@U?$IReference@Uhstring@winrt@@@Foundation@Windows@winrt@@Uhstring@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<winrt::hstring>,winrt::hstring>::Value(void)
0x180023b30  nop
0x180023b31  mov     rcx, [rax]
0x180023b34  mov     [rbp+4Fh+var_88], rcx
0x180023b38  mov     r8, rbx
0x180023b3b  lea     rdx, [rbp+4Fh+var_88]
0x180023b3f  mov     rcx, rdi
0x180023b42  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x180023b47  nop
0x180023b48  lea     rcx, [rbp+4Fh+var_98]
0x180023b4c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180023b51  nop
0x180023b52  cmp     [rbp+4Fh+var_90], 0
0x180023b57  jz      short loc_180023B63
0x180023b59  lea     rcx, [rbp+4Fh+var_90]
0x180023b5d  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180023b62  nop
0x180023b63  lea     rcx, [rbp+4Fh+var_38]; this
0x180023b67  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180023b6c  lea     rcx, [rbp+4Fh+var_40]
0x180023b70  call    ??E?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@2345@@impl@winrt@@QEAA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Foundation::IInspectable>>::operator++(void)
0x180023b75  jmp     loc_180023AF4
0x180023b7a  lea     rcx, [rbp+4Fh+var_A8]; this
0x180023b7e  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180023b83  nop
0x180023b84  lea     rcx, [rbp+4Fh+var_40]; this
0x180023b88  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180023b8d  lea     rdx, [rbp+4Fh+var_98]
0x180023b91  mov     rcx, r14
0x180023b94  call    ??C?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::operator->(void)
0x180023b99  mov     rcx, [rax]
0x180023b9c  mov     byte ptr [rcx+130h], 1
0x180023ba3  lea     rcx, [rbp+4Fh+var_98]
0x180023ba7  call    ??1?$test_data_control@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::~test_data_control<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>(void)
0x180023bac  nop
0x180023bad  lea     rcx, [rbp+4Fh+var_B0]; this
0x180023bb1  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180023bb6  mov     rax, rdi
0x180023bb9  mov     rcx, [rbp+4Fh+var_30]
0x180023bbd  xor     rcx, rsp; StackCookie
0x180023bc0  call    __security_check_cookie
0x180023bc5  add     rsp, 0B0h
0x180023bcc  pop     r14
0x180023bce  pop     rdi
0x180023bcf  pop     rsi
0x180023bd0  pop     rbx
0x180023bd1  pop     rbp
0x180023bd2  retn
```
