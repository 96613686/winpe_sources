# ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)

- ea: `0x18001f48c`
- end: `0x18001f60f`
- name: `??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z`
- size: `387`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fbcc`
- `0x180021664`
- `0x180022958`
- `0x180026418`
- `0x1800265d0`
- `0x18002aa84`
- `0x18002da60`
- `0x18004488c`
- `0x180046790`
- `0x180046cb0`
- `0x18004d714`
- `0x18004ff8c`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x1800043f4`
- `0x1800049ac`
- `0x180013460`
- `0x180013bc0`
- `0x180017514`
- `0x18001f48c`
- `0x180020cdc`
- `0x180020e18`
- `0x18002c450`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f597`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f5c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f597`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f5c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(
        _QWORD *a1,
        _QWORD *a2,
        char a3)
{
  void (__fastcall ***v6)(_QWORD, void *, __int64 *); // rcx
  __int64 v7; // rbx
  char v8; // bl
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v14[4]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+60h] [rbp-18h] BYREF

  if ( *a2 )
  {
    v14[0] = *a1;
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                            a2,
                            v14) )
    {
      v14[0] = *a1;
      v6 = *(void (__fastcall ****)(_QWORD, void *, __int64 *))winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
                                                                 a2,
                                                                 &v13,
                                                                 v14);
      if ( v6 )
      {
        v15 = 0;
        (**v6)(v6, &winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>, &v15);
        v7 = v15;
        v12 = v15;
      }
      else
      {
        v12 = 0;
        v7 = 0;
      }
      if ( v13 )
        winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v13);
      if ( v7 )
      {
        if ( (unsigned int)_lambda_95a7ded9384efa6b54b5506927790237_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics *)&v12) == 11 )
        {
          v8 = winrt::impl::unbox_value_type<bool,winrt::Windows::Foundation::IInspectable const &>(&v12);
LABEL_16:
          winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v12);
          return v8;
        }
        if ( (unsigned int)_lambda_95a7ded9384efa6b54b5506927790237_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics *)&v12) == 12 )
        {
          winrt::unbox_value<winrt::hstring>(&v15, &v12);
          v9 = winrt::hstring::c_str((winrt::hstring *)&v15);
          v8 = 1;
          if ( CompareStringOrdinal(v9, -1, L"true", -1, 1) == 2 )
          {
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
            goto LABEL_16;
          }
          v10 = winrt::hstring::c_str((winrt::hstring *)&v15);
          if ( CompareStringOrdinal(v10, -1, L"false", -1, 1) == 2 )
          {
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
            v8 = 0;
            goto LABEL_16;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
        }
      }
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v12);
    }
  }
  return a3;
}

```

## disassembly

```asm
0x18001f48c  push    rbp
0x18001f48e  push    rbx
0x18001f48f  push    rsi
0x18001f490  push    rdi
0x18001f491  mov     rbp, rsp
0x18001f494  sub     rsp, 78h
0x18001f498  mov     rax, cs:__security_cookie
0x18001f49f  xor     rax, rsp
0x18001f4a2  mov     [rbp+var_10], rax
0x18001f4a6  mov     dil, r8b
0x18001f4a9  mov     rbx, rdx
0x18001f4ac  mov     rsi, rcx
0x18001f4af  cmp     qword ptr [rdx], 0
0x18001f4b3  jz      loc_18001F5F7
0x18001f4b9  mov     rax, [rcx]
0x18001f4bc  mov     [rbp+var_38], rax
0x18001f4c0  lea     rdx, [rbp+var_38]
0x18001f4c4  mov     rcx, rbx
0x18001f4c7  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x18001f4cc  test    al, al
0x18001f4ce  jz      loc_18001F5F7
0x18001f4d4  mov     rax, [rsi]
0x18001f4d7  mov     [rbp+var_38], rax
0x18001f4db  lea     r8, [rbp+var_38]
0x18001f4df  lea     rdx, [rbp+var_40]
0x18001f4e3  mov     rcx, rbx
0x18001f4e6  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18001f4eb  mov     rcx, [rax]
0x18001f4ee  test    rcx, rcx
0x18001f4f1  jnz     short loc_18001F4FB
0x18001f4f3  mov     [rbp+var_48], rcx
0x18001f4f7  xor     ebx, ebx
0x18001f4f9  jmp     short loc_18001F521
0x18001f4fb  mov     [rbp+var_18], 0
0x18001f503  mov     rax, [rcx]
0x18001f506  lea     r8, [rbp+var_18]
0x18001f50a  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x18001f511  mov     rax, [rax]
0x18001f514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f519  mov     rbx, [rbp+var_18]
0x18001f51d  mov     [rbp+var_48], rbx
0x18001f521  cmp     [rbp+var_40], 0
0x18001f526  jz      short loc_18001F531
0x18001f528  lea     rcx, [rbp+var_40]
0x18001f52c  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18001f531  test    rbx, rbx
0x18001f534  jz      loc_18001F5EE
0x18001f53a  lea     rcx, [rbp+var_48]; struct winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics *
0x18001f53e  call    ?_lambda_invoker_cdecl_@_lambda_95a7ded9384efa6b54b5506927790237_@@CA@AEBUISystemVisualThemeStatics@Themes@UI@WindowsUdk@winrt@@@Z; _lambda_95a7ded9384efa6b54b5506927790237_::_lambda_invoker_cdecl_(winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics const &)
0x18001f543  lea     rcx, [rbp+var_48]; struct winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics *
0x18001f547  cmp     eax, 0Bh
0x18001f54a  jnz     short loc_18001F558
0x18001f54c  call    ??$unbox_value_type@_NAEBUIInspectable@Foundation@Windows@winrt@@@impl@winrt@@YA_NAEBUIInspectable@Foundation@Windows@1@@Z; winrt::impl::unbox_value_type<bool,winrt::Windows::Foundation::IInspectable const &>(winrt::Windows::Foundation::IInspectable const &)
0x18001f551  mov     bl, al
0x18001f553  jmp     loc_18001F5DB
0x18001f558  call    ?_lambda_invoker_cdecl_@_lambda_95a7ded9384efa6b54b5506927790237_@@CA@AEBUISystemVisualThemeStatics@Themes@UI@WindowsUdk@winrt@@@Z; _lambda_95a7ded9384efa6b54b5506927790237_::_lambda_invoker_cdecl_(winrt::WindowsUdk::UI::Themes::ISystemVisualThemeStatics const &)
0x18001f55d  cmp     eax, 0Ch
0x18001f560  jnz     loc_18001F5EE
0x18001f566  lea     rdx, [rbp+var_48]
0x18001f56a  lea     rcx, [rbp+var_18]
0x18001f56e  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x18001f573  lea     rcx, [rbp+var_18]; this
0x18001f577  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001f57c  mov     rcx, rax; lpString1
0x18001f57f  mov     ebx, 1
0x18001f584  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x18001f588  or      esi, 0FFFFFFFFh
0x18001f58b  mov     r9d, esi; cchCount2
0x18001f58e  lea     r8, String2; "true"
0x18001f595  mov     edx, esi; cchCount1
0x18001f597  call    cs:__imp_CompareStringOrdinal
0x18001f59d  lea     rcx, [rbp+var_18]; this
0x18001f5a1  cmp     eax, 2
0x18001f5a4  jnz     short loc_18001F5AD
0x18001f5a6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f5ab  jmp     short loc_18001F5DB
0x18001f5ad  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001f5b2  mov     rcx, rax; lpString1
0x18001f5b5  mov     [rsp+78h+bIgnoreCase], ebx; bIgnoreCase
0x18001f5b9  mov     r9d, esi; cchCount2
0x18001f5bc  lea     r8, aFalse; "false"
0x18001f5c3  mov     edx, esi; cchCount1
0x18001f5c5  call    cs:__imp_CompareStringOrdinal
0x18001f5cb  lea     rcx, [rbp+var_18]
0x18001f5cf  cmp     eax, 2
0x18001f5d2  jnz     short loc_18001F5E8
0x18001f5d4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f5d9  xor     bl, bl
0x18001f5db  lea     rcx, [rbp+var_48]; this
0x18001f5df  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18001f5e4  mov     al, bl
0x18001f5e6  jmp     short loc_18001F5FA
0x18001f5e8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18001f5ed  nop
0x18001f5ee  lea     rcx, [rbp+var_48]; this
0x18001f5f2  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18001f5f7  mov     al, dil
0x18001f5fa  mov     rcx, [rbp+var_10]
0x18001f5fe  xor     rcx, rsp; StackCookie
0x18001f601  call    __security_check_cookie
0x18001f606  add     rsp, 78h
0x18001f60a  pop     rdi
0x18001f60b  pop     rsi
0x18001f60c  pop     rbx
0x18001f60d  pop     rbp
0x18001f60e  retn
```
