# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetFullNameAndAumidFromFamilyName(ushort const *,ushort const *)

- ea: `0x180027f60`
- end: `0x180028097`
- name: `?GetFullNameAndAumidFromFamilyName@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AV?$tuple@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@PEBG0@Z`
- size: `311`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800293fc`

## callees

- `0x180002d40`
- `0x18000f8a8`
- `0x180012498`
- `0x1800182cc`
- `0x18001cfb4`
- `0x18001d058`
- `0x1800232bc`
- `0x180027f60`
- `0x1800291d0`
- `0x180043f5c`
- `0x180044088`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028050`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028050`

## string_xrefs

- `0x180027f9d`: `ImpersonateUser failed!`
- `0x180027fac`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180028070`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180028085`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetFullNameAndAumidFromFamilyName(
        _QWORD *a1,
        const WCHAR *a2,
        __int64 a3)
{
  unsigned int v5; // eax
  unsigned __int16 **v6; // r8
  int SinglePackageFullNameFromPackageFamilyName; // eax
  CallerIdentity *v8; // rbx
  unsigned __int16 **v9; // r8
  int SinglePackageAppUserModelIDFromPackageFullName; // eax
  int v12; // [rsp+20h] [rbp-50h]
  const char *v13; // [rsp+28h] [rbp-48h]
  CallerIdentity *v14; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 v15[4]; // [rsp+38h] [rbp-38h] BYREF
  char v16; // [rsp+41h] [rbp-2Fh]
  _BYTE v17[32]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  std::wstring::wstring(v17, a3);
  v5 = PrintCore::UserImpersonationHelpers::ImpersonateUser((__int64)v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x134,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
    (const char *)v5,
    (int)"ImpersonateUser failed!",
    v13);
  std::wstring::_Tidy_deallocate(v17);
  v16 = 1;
  v14 = 0;
  *(_QWORD *)v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v14,
    0);
  SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                 a2,
                                                 (const unsigned __int16 *)&v14,
                                                 v6);
  if ( SinglePackageFullNameFromPackageFamilyName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
      v12);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v15,
    0);
  v8 = v14;
  SinglePackageAppUserModelIDFromPackageFullName = CallerIdentity::GetSinglePackageAppUserModelIDFromPackageFullName(
                                                     v14,
                                                     v15,
                                                     v9);
  if ( SinglePackageAppUserModelIDFromPackageFullName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)(unsigned int)SinglePackageAppUserModelIDFromPackageFullName,
      v12);
  *a1 = *(_QWORD *)v15;
  *(_QWORD *)v15 = 0;
  a1[1] = v8;
  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x180027f60  push    rbp
0x180027f62  push    rbx
0x180027f63  push    rdi
0x180027f64  mov     rbp, rsp
0x180027f67  sub     rsp, 70h
0x180027f6b  mov     rax, cs:__security_cookie
0x180027f72  xor     rax, rsp
0x180027f75  mov     [rbp+var_8], rax
0x180027f79  mov     rbx, rdx
0x180027f7c  mov     rdi, rcx
0x180027f7f  mov     [rbp+var_40], rcx
0x180027f83  mov     rdx, r8
0x180027f86  lea     rcx, [rbp+var_28]
0x180027f8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027f8f  nop
0x180027f90  lea     rcx, [rbp+var_28]
0x180027f94  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x180027f99  mov     rcx, [rbp+18h]; this
0x180027f9d  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180027fa4  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180027fa9  mov     r9d, eax; char *
0x180027fac  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180027fb3  mov     edx, 134h; void *
0x180027fb8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027fbd  nop
0x180027fbe  lea     rcx, [rbp+var_28]
0x180027fc2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027fc7  mov     [rbp+var_2F], 1
0x180027fcb  mov     [rbp+var_40], 0
0x180027fd3  mov     qword ptr [rbp+var_38], 0
0x180027fdb  xor     edx, edx
0x180027fdd  lea     rcx, [rbp+var_40]
0x180027fe1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180027fe6  lea     rdx, [rbp+var_40]; unsigned __int16 *
0x180027fea  mov     rcx, rbx; packageFamilyName
0x180027fed  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x180027ff2  mov     rcx, [rbp+18h]; this
0x180027ff6  test    eax, eax
0x180027ff8  js      loc_180028082
0x180027ffe  xor     edx, edx
0x180028000  lea     rcx, [rbp+var_38]
0x180028004  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180028009  lea     rdx, [rbp+var_38]; unsigned __int16 *
0x18002800d  mov     rbx, [rbp+var_40]
0x180028011  mov     rcx, rbx; this
0x180028014  call    ?GetSinglePackageAppUserModelIDFromPackageFullName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageAppUserModelIDFromPackageFullName(ushort const *,ushort * *)
0x180028019  mov     rcx, [rbp+18h]; this
0x18002801d  test    eax, eax
0x18002801f  js      short loc_18002806D
0x180028021  mov     rcx, qword ptr [rbp+var_38]
0x180028025  mov     [rdi], rcx
0x180028028  mov     qword ptr [rbp+var_38], 0
0x180028030  mov     [rdi+8], rbx
0x180028034  mov     [rbp+var_40], 0
0x18002803c  lea     rcx, [rbp+var_38]
0x180028040  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028045  nop
0x180028046  lea     rcx, [rbp+var_40]
0x18002804a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002804f  nop
0x180028050  call    cs:__imp_RevertToSelf
0x180028056  mov     rax, rdi
0x180028059  mov     rcx, [rbp+var_8]
0x18002805d  xor     rcx, rsp; StackCookie
0x180028060  call    __security_check_cookie
0x180028065  add     rsp, 70h
0x180028069  pop     rdi
0x18002806a  pop     rbx
0x18002806b  pop     rbp
0x18002806c  retn
0x18002806d  mov     r9d, eax; char *
0x180028070  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x180028077  mov     edx, 13Ch; void *
0x18002807c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028082  mov     r9d, eax; char *
0x180028085  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002808c  mov     edx, 13Bh; void *
0x180028091  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
