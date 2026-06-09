# PrintSupportSessionCommon::InitializeCentennialAppData(void)

- ea: `0x180033c50`
- end: `0x180033d66`
- name: `?InitializeCentennialAppData@PrintSupportSessionCommon@@IEAAXXZ`
- size: `278`
- prototype: `void __fastcall(PrintSupportSessionCommon *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033f1c`

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
- `0x18002b724`
- `0x180033c50`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033cf4`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033cf4`

## string_xrefs

- `0x180033d54`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintSupportSessionCommon::InitializeCentennialAppData(PrintSupportSessionCommon *this)
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
  PackageUtilsCommon::GetApplicationForAumidAndContract(v8, (char *)this + 88, &v6);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
  *((_BYTE *)this + 120) = winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::IsCentennial(v8);
  winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::Executable(
    v8,
    &v6);
  v2 = winrt::hstring::c_str((PrintSupportSessionCommon *)((char *)this + 96));
  PackageUtilsCommon::GetEffectiveRootPathForPackage((__int64)v9, (__int64)v2);
  ppszPathOut = 0;
  winrt::hstring::c_str((winrt::hstring *)&v6);
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
  v5 = PathAllocCombine(v3, v4, 1u, &ppszPathOut);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
      (const char *)(unsigned int)v5,
      v6);
  winrt::hstring::operator=((char *)this + 112, ppszPathOut);
  *((_BYTE *)this + 121) = 1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  std::wstring::_Tidy_deallocate(v9);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v6);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v8);
}

```

## disassembly

```asm
0x180033c50  mov     [rsp-8+arg_8], rbx
0x180033c55  push    rbp
0x180033c56  mov     rbp, rsp
0x180033c59  sub     rsp, 60h
0x180033c5d  mov     rax, cs:__security_cookie
0x180033c64  xor     rax, rsp
0x180033c67  mov     [rbp+var_8], rax
0x180033c6b  mov     rbx, rcx
0x180033c6e  lea     rdx, aWindowsPrintsu_2; "Windows.PrintSupportJobUI"
0x180033c75  lea     rcx, [rbp+var_40]; this
0x180033c79  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180033c7e  nop
0x180033c7f  lea     rdx, [rbx+58h]
0x180033c83  lea     r8, [rbp+var_40]
0x180033c87  lea     rcx, [rbp+var_30]
0x180033c8b  call    ?GetApplicationForAumidAndContract@PackageUtilsCommon@@YA?AUApplication@StateRepository@Internal@Windows@winrt@@AEBUhstring@6@0@Z; PackageUtilsCommon::GetApplicationForAumidAndContract(winrt::hstring const &,winrt::hstring const &)
0x180033c90  nop
0x180033c91  lea     rcx, [rbp+var_40]
0x180033c95  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033c9a  lea     rcx, [rbp+var_30]
0x180033c9e  call    ?IsCentennial@?$consume_Windows_Internal_StateRepository_IApplication@UIApplication@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::IsCentennial(void)
0x180033ca3  mov     [rbx+78h], al
0x180033ca6  lea     rdx, [rbp+var_40]
0x180033caa  lea     rcx, [rbp+var_30]
0x180033cae  call    ?Executable@?$consume_Windows_Internal_StateRepository_IApplication@UIApplication@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IApplication<winrt::Windows::Internal::StateRepository::IApplication>::Executable(void)
0x180033cb3  nop
0x180033cb4  lea     rcx, [rbx+60h]; this
0x180033cb8  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180033cbd  mov     rdx, rax
0x180033cc0  lea     rcx, [rbp+var_28]
0x180033cc4  call    ?GetEffectiveRootPathForPackage@PackageUtilsCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PackageUtilsCommon::GetEffectiveRootPathForPackage(ushort const *)
0x180033cc9  nop
0x180033cca  mov     [rbp+ppszPathOut], 0
0x180033cd2  lea     rcx, [rbp+var_40]; this
0x180033cd6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180033cdb  mov     rdx, rax
0x180033cde  lea     rcx, [rbp+var_28]
0x180033ce2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033ce7  mov     rcx, rax; pszPathIn
0x180033cea  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180033cee  mov     r8d, 1; dwFlags
0x180033cf4  call    cs:__imp_PathAllocCombine
0x180033cfa  mov     rcx, [rbp+8]; this
0x180033cfe  test    eax, eax
0x180033d00  js      short loc_180033D51
0x180033d02  lea     rcx, [rbx+70h]
0x180033d06  mov     rdx, [rbp+ppszPathOut]
0x180033d0a  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x180033d0f  mov     byte ptr [rbx+79h], 1
0x180033d13  lea     rcx, [rbp+ppszPathOut]
0x180033d17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180033d1c  nop
0x180033d1d  lea     rcx, [rbp+var_28]
0x180033d21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033d26  nop
0x180033d27  lea     rcx, [rbp+var_40]
0x180033d2b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033d30  nop
0x180033d31  lea     rcx, [rbp+var_30]; this
0x180033d35  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180033d3a  mov     rcx, [rbp+var_8]
0x180033d3e  xor     rcx, rsp; StackCookie
0x180033d41  call    __security_check_cookie
0x180033d46  mov     rbx, [rsp+60h+arg_8]
0x180033d4b  add     rsp, 60h
0x180033d4f  pop     rbp
0x180033d50  retn
0x180033d51  mov     r9d, eax; char *
0x180033d54  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x180033d5b  mov     edx, 1EEh; void *
0x180033d60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
