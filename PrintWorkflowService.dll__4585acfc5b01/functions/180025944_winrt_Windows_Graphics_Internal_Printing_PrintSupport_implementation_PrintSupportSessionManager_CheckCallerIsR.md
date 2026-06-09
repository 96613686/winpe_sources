# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager::CheckCallerIsRegisteredPsaApp(winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportAppSessionCommon const &)

- ea: `0x180025944`
- end: `0x180025a0a`
- name: `?CheckCallerIsRegisteredPsaApp@PrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEBUIPrintSupportAppSessionCommon@345678@@Z`
- size: `198`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *__hidden this, const struct winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportAppSessionCommon *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026590`

## callees

- `0x180008610`
- `0x1800127a4`
- `0x1800129dc`
- `0x180012b10`
- `0x1800253ec`
- `0x180025780`
- `0x180025944`
- `0x180026fe4`
- `0x1800275e0`
- `0x180027fd8`
- `0x180055968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002599f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002599f`

## string_xrefs

- `0x1800259e3`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessionmanager.cpp`
- `0x1800259f8`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager::CheckCallerIsRegisteredPsaApp(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *this,
        const struct winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportAppSessionCommon *a2)
{
  unsigned __int16 **v3; // rdx
  int CallingProcessAppId; // eax
  winrt::hstring *v5; // rax
  const unsigned __int16 *v6; // rax
  int v7; // ebx
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-18h]
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v12; // [rsp+40h] [rbp+8h] BYREF
  char v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = this;
  if ( ProcessUtils::IsCurrentProcess(this, (const unsigned __int16 *)a2) )
  {
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v12, v3);
    if ( CallingProcessAppId < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessionmanager.cpp",
        (const char *)(unsigned int)CallingProcessAppId,
        v9);
    v5 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_StateRepository_IPackage<winrt::Windows::Internal::StateRepository::IPackage>::PackageFullName(
                             a2,
                             &v13);
    v6 = winrt::hstring::c_str(v5);
    v7 = _o__wcsicmp(v12, v6);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
    if ( v7 )
    {
      v8 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessionmanager.cpp",
        (const char *)v8,
        (int)"Caller is not registered PSA app",
        v10);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180025944  mov     [rsp+arg_0], rcx
0x180025949  push    rbx
0x18002594a  sub     rsp, 30h
0x18002594e  mov     rbx, rdx
0x180025951  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x180025956  test    al, al
0x180025958  jz      short loc_1800259BF
0x18002595a  mov     [rsp+38h+arg_0], 0
0x180025963  xor     edx, edx
0x180025965  lea     rcx, [rsp+38h+arg_0]
0x18002596a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002596f  lea     rcx, [rsp+38h+arg_0]; this
0x180025974  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x180025979  mov     rcx, [rsp+38h]; this
0x18002597e  test    eax, eax
0x180025980  js      short loc_1800259F5
0x180025982  lea     rdx, [rsp+38h+arg_10]
0x180025987  mov     rcx, rbx
0x18002598a  call    ?PackageFullName@?$consume_Windows_Internal_StateRepository_IPackage@UIPackage@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IPackage<winrt::Windows::Internal::StateRepository::IPackage>::PackageFullName(void)
0x18002598f  mov     rcx, rax; this
0x180025992  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180025997  mov     rdx, rax
0x18002599a  mov     rcx, [rsp+38h+arg_0]
0x18002599f  call    cs:__imp__o__wcsicmp
0x1800259a5  mov     ebx, eax
0x1800259a7  lea     rcx, [rsp+38h+arg_10]
0x1800259ac  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800259b1  test    ebx, ebx
0x1800259b3  jnz     short loc_1800259C5
0x1800259b5  lea     rcx, [rsp+38h+arg_0]
0x1800259ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800259bf  add     rsp, 30h
0x1800259c3  pop     rbx
0x1800259c4  retn
0x1800259c5  mov     ecx, 80070005h
0x1800259ca  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800259cf  mov     r9d, eax; char *
0x1800259d2  mov     rcx, [rsp+38h]; this
0x1800259d7  lea     rax, aCallerIsNotReg; "Caller is not registered PSA app"
0x1800259de  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800259e3  lea     r8, aOnecoreuapPrin_15; "onecoreuap\\printscan\\print\\workflow"...
0x1800259ea  mov     edx, 0D1h; void *
0x1800259ef  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800259f5  mov     r9d, eax; char *
0x1800259f8  lea     r8, aOnecoreuapPrin_15; "onecoreuap\\printscan\\print\\workflow"...
0x1800259ff  mov     edx, 0CEh; void *
0x180025a04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
