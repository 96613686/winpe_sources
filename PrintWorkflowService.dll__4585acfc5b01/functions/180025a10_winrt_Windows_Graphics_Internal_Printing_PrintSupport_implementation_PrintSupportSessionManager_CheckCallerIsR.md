# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager::CheckCallerIsRegisteredPsaApp(winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportExtensionBrokerSession const &)

- ea: `0x180025a10`
- end: `0x180025ad6`
- name: `?CheckCallerIsRegisteredPsaApp@PrintSupportSessionManager@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXAEBUPrintSupportExtensionBrokerSession@345678@@Z`
- size: `198`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *__hidden this, const struct winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportExtensionBrokerSession *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800267ac`

## callees

- `0x180008610`
- `0x1800127a4`
- `0x1800129dc`
- `0x180012b10`
- `0x1800253ec`
- `0x1800257e0`
- `0x180025a10`
- `0x180026fe4`
- `0x1800275e0`
- `0x180027fd8`
- `0x180055968`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025a6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025a6b`

## string_xrefs

- `0x180025aaf`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessionmanager.cpp`
- `0x180025ac4`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessionmanager.cpp`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager::CheckCallerIsRegisteredPsaApp(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSessionManager *this,
        const struct winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportExtensionBrokerSession *a2)
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
        (void *)0xDD,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessionmanager.cpp",
        (const char *)(unsigned int)CallingProcessAppId,
        v9);
    v5 = (winrt::hstring *)winrt::impl::consume_Windows_Graphics_Internal_Printing_PrintSupport_IPrintSupportExtensionBrokerSession<winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportExtensionBrokerSession>::AppAumid(
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
        (void *)0xE0,
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
0x180025a10  mov     [rsp+arg_0], rcx
0x180025a15  push    rbx
0x180025a16  sub     rsp, 30h
0x180025a1a  mov     rbx, rdx
0x180025a1d  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x180025a22  test    al, al
0x180025a24  jz      short loc_180025A8B
0x180025a26  mov     [rsp+38h+arg_0], 0
0x180025a2f  xor     edx, edx
0x180025a31  lea     rcx, [rsp+38h+arg_0]
0x180025a36  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025a3b  lea     rcx, [rsp+38h+arg_0]; this
0x180025a40  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x180025a45  mov     rcx, [rsp+38h]; this
0x180025a4a  test    eax, eax
0x180025a4c  js      short loc_180025AC1
0x180025a4e  lea     rdx, [rsp+38h+arg_10]
0x180025a53  mov     rcx, rbx
0x180025a56  call    ?AppAumid@?$consume_Windows_Graphics_Internal_Printing_PrintSupport_IPrintSupportExtensionBrokerSession@UIPrintSupportExtensionBrokerSession@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Graphics_Internal_Printing_PrintSupport_IPrintSupportExtensionBrokerSession<winrt::Windows::Graphics::Internal::Printing::PrintSupport::IPrintSupportExtensionBrokerSession>::AppAumid(void)
0x180025a5b  mov     rcx, rax; this
0x180025a5e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180025a63  mov     rdx, rax
0x180025a66  mov     rcx, [rsp+38h+arg_0]
0x180025a6b  call    cs:__imp__o__wcsicmp
0x180025a71  mov     ebx, eax
0x180025a73  lea     rcx, [rsp+38h+arg_10]
0x180025a78  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180025a7d  test    ebx, ebx
0x180025a7f  jnz     short loc_180025A91
0x180025a81  lea     rcx, [rsp+38h+arg_0]
0x180025a86  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025a8b  add     rsp, 30h
0x180025a8f  pop     rbx
0x180025a90  retn
0x180025a91  mov     ecx, 80070005h
0x180025a96  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180025a9b  mov     r9d, eax; char *
0x180025a9e  mov     rcx, [rsp+38h]; this
0x180025aa3  lea     rax, aCallerIsNotReg; "Caller is not registered PSA app"
0x180025aaa  mov     qword ptr [rsp+38h+var_18], rax; int
0x180025aaf  lea     r8, aOnecoreuapPrin_15; "onecoreuap\\printscan\\print\\workflow"...
0x180025ab6  mov     edx, 0E0h; void *
0x180025abb  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025ac1  mov     r9d, eax; char *
0x180025ac4  lea     r8, aOnecoreuapPrin_15; "onecoreuap\\printscan\\print\\workflow"...
0x180025acb  mov     edx, 0DDh; void *
0x180025ad0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
