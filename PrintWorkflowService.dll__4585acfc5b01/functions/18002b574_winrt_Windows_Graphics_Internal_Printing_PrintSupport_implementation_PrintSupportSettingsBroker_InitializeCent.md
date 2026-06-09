# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::InitializeCentennialAppData(void)

- ea: `0x18002b574`
- end: `0x18002b6a7`
- name: `?InitializeCentennialAppData@PrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ`
- size: `307`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800297b4`

## callees

- `0x180003ca0`
- `0x180009718`
- `0x1800097ec`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x1800129dc`
- `0x180012b10`
- `0x1800213cc`
- `0x180029f38`
- `0x18002a500`
- `0x18002a91c`
- `0x18002ac2c`
- `0x18002b574`
- `0x18002b724`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002b628`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002b628`

## string_xrefs

- `0x18002b695`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsettingsbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker::InitializeCentennialAppData(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *this)
{
  const unsigned __int16 *v2; // rax
  const WCHAR *v3; // rax
  PCWSTR v4; // rdx
  HRESULT v5; // eax
  int v6; // [rsp+20h] [rbp-40h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[8]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  winrt::hstring::hstring((winrt::hstring *)&v6, L"Windows.PrintSupportJobUI");
  PackageUtilsCommon::GetApplicationForAumidAndContract(v8, (char *)this + 168, &v6);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
  *((_BYTE *)this + 200) = winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::IsCentennial(v8);
  winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::Executable(
    v8,
    &v6);
  v2 = winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *)((char *)this + 176));
  PackageUtilsCommon::GetEffectiveRootPathForPackage(v9, v2);
  ppszPathOut = 0;
  winrt::hstring::c_str((winrt::hstring *)&v6);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
  v5 = PathAllocCombine(v3, v4, 1u, &ppszPathOut);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsettingsbroker.cpp",
      (const char *)(unsigned int)v5,
      v6);
  winrt::hstring::operator=((char *)this + 192, ppszPathOut);
  *((_BYTE *)this + 201) = 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  std::wstring::_Tidy_deallocate(v9);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v8);
}

```

## disassembly

```asm
0x18002b574  mov     [rsp-8+arg_8], rbx
0x18002b579  mov     [rsp-8+arg_10], rdi
0x18002b57e  push    rbp
0x18002b57f  mov     rbp, rsp
0x18002b582  sub     rsp, 60h
0x18002b586  mov     rax, cs:__security_cookie
0x18002b58d  xor     rax, rsp
0x18002b590  mov     [rbp+var_8], rax
0x18002b594  mov     rbx, rcx
0x18002b597  lea     rdx, aWindowsPrintsu_2; "Windows.PrintSupportJobUI"
0x18002b59e  lea     rcx, [rbp+var_40]; this
0x18002b5a2  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18002b5a7  nop
0x18002b5a8  lea     rdx, [rbx+0A8h]
0x18002b5af  lea     r8, [rbp+var_40]
0x18002b5b3  lea     rcx, [rbp+var_30]
0x18002b5b7  call    ?GetApplicationForAumidAndContract@PackageUtilsCommon@@YA?AUApplication@StateRepository@Internal@Windows@winrt@@AEBUhstring@6@0@Z; PackageUtilsCommon::GetApplicationForAumidAndContract(winrt::hstring const &,winrt::hstring const &)
0x18002b5bc  nop
0x18002b5bd  lea     rcx, [rbp+var_40]
0x18002b5c1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002b5c6  lea     rcx, [rbp+var_30]
0x18002b5ca  call    ?IsCentennial@?$consume_Windows_Internal_StateRepository_IApplication@UIApplication@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::IsCentennial(void)
0x18002b5cf  mov     [rbx+0C8h], al
0x18002b5d5  lea     rdx, [rbp+var_40]
0x18002b5d9  lea     rcx, [rbp+var_30]
0x18002b5dd  call    ?Executable@?$consume_Windows_Internal_StateRepository_IApplication@UIApplication@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::Executable(void)
0x18002b5e2  nop
0x18002b5e3  lea     rcx, [rbx+0B0h]; this
0x18002b5ea  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002b5ef  mov     rdx, rax
0x18002b5f2  lea     rcx, [rbp+var_28]
0x18002b5f6  call    ?GetEffectiveRootPathForPackage@PackageUtilsCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PackageUtilsCommon::GetEffectiveRootPathForPackage(ushort const *)
0x18002b5fb  nop
0x18002b5fc  mov     [rbp+ppszPathOut], 0
0x18002b604  lea     rcx, [rbp+var_40]; this
0x18002b608  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002b60d  mov     rdx, rax
0x18002b610  lea     rcx, [rbp+var_28]
0x18002b614  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b619  mov     rcx, rax; pszPathIn
0x18002b61c  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18002b620  mov     edi, 1
0x18002b625  mov     r8d, edi; dwFlags
0x18002b628  call    cs:__imp_PathAllocCombine
0x18002b62e  mov     rcx, [rbp+8]; this
0x18002b632  test    eax, eax
0x18002b634  js      short loc_18002B692
0x18002b636  lea     rcx, [rbx+0C0h]
0x18002b63d  mov     rdx, [rbp+ppszPathOut]
0x18002b641  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x18002b646  xchg    dil, [rbx+0C9h]
0x18002b64d  lea     rcx, [rbp+ppszPathOut]
0x18002b651  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b656  nop
0x18002b657  lea     rcx, [rbp+var_28]
0x18002b65b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b660  nop
0x18002b661  lea     rcx, [rbp+var_40]
0x18002b665  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002b66a  nop
0x18002b66b  lea     rcx, [rbp+var_30]; this
0x18002b66f  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18002b674  mov     rcx, [rbp+var_8]
0x18002b678  xor     rcx, rsp; StackCookie
0x18002b67b  call    __security_check_cookie
0x18002b680  lea     r11, [rsp+60h+var_s0]
0x18002b685  mov     rbx, [r11+18h]
0x18002b689  mov     rdi, [r11+20h]
0x18002b68d  mov     rsp, r11
0x18002b690  pop     rbp
0x18002b691  retn
0x18002b692  mov     r9d, eax; char *
0x18002b695  lea     r8, aOnecoreuapPrin_25; "onecoreuap\\printscan\\print\\workflow"...
0x18002b69c  mov     edx, 254h; void *
0x18002b6a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
