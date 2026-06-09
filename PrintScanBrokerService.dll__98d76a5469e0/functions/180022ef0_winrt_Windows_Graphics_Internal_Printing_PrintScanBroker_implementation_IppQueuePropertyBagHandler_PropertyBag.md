# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(void)

- ea: `0x180022ef0`
- end: `0x18002308e`
- name: `?_PropertyBagAccessCheck@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ`
- size: `414`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bad4`
- `0x18001cce4`

## callees

- `0x180002d40`
- `0x180006b48`
- `0x18000f8a8`
- `0x18000fa2c`
- `0x18001031c`
- `0x180012498`
- `0x1800182cc`
- `0x18001c5dc`
- `0x18001cfb4`
- `0x18001cfd4`
- `0x18001d1dc`
- `0x180022ef0`
- `0x1800232bc`
- `0x180035450`
- `0x1800434ac`

## import_xrefs

- `Print.PrintSupport.Source!GetAppUserModelId` at `0x180022f98`
- `Print.PrintSupport.Source!GetAppUserModelId` at `0x180022f98`

## string_xrefs

- `0x180022f61`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022fbb`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18002307c`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x18002305f`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck`

## pseudocode

```c
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_PropertyBagAccessCheck(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this)
{
  unsigned __int16 **v2; // rdx
  int CallingProcessAppId; // eax
  winrt::hstring *v4; // rdi
  const unsigned __int16 *v5; // rax
  int AppUserModelId; // eax
  char v7; // bl
  const unsigned __int16 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // [rsp+20h] [rbp-19h]
  const char *v14; // [rsp+30h] [rbp-9h] BYREF
  __int64 v15; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v16[32]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  if ( PrintScanBrokerUtilities::GetCallerIntegrityLevel(this) <= 0x3000 )
  {
    v14 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v14,
      0);
    CallingProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v14, v2);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)0x80070005LL,
      CallingProcessAppId < 0,
      (bool)"Failed to get the calling application's AUMID!",
      v14);
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v15,
      0);
    v4 = (winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)((char *)this + 24);
    v5 = winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *)((char *)this + 24));
    AppUserModelId = GetAppUserModelId(v5, &v15);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xC2,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)0x80070005LL,
      AppUserModelId < 0,
      (bool)"Failed to get the printer's package AUMID!",
      v14);
    std::wstring::wstring(v17, v15);
    std::wstring::wstring(v16, v14);
    v7 = PrintCore::StringHelpers::IEquals(v16, v17);
    std::wstring::_Tidy_deallocate(v16);
    std::wstring::_Tidy_deallocate(v17);
    if ( !v7 )
    {
      v8 = winrt::hstring::c_str(v4);
      v11 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(&v14, v9, v10, v8);
      PrintScanBrokerTelemetry::WriteDbgTraceWarning(
        "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_Prop"
        "ertyBagAccessCheck",
        L"Caller %ws is not allowed to set the IPP Queue Property Bag for printer %ws",
        v11);
      v12 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
        (const char *)v12,
        v13);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  }
}

```

## disassembly

```asm
0x180022ef0  mov     [rsp-8+arg_8], rbx
0x180022ef5  mov     [rsp-8+arg_10], rdi
0x180022efa  push    rbp
0x180022efb  lea     rbp, [rsp-57h]
0x180022f00  sub     rsp, 90h
0x180022f07  mov     rax, cs:__security_cookie
0x180022f0e  xor     rax, rsp
0x180022f11  mov     [rbp+57h+var_10], rax
0x180022f15  mov     rbx, rcx
0x180022f18  call    ?GetCallerIntegrityLevel@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerIntegrityLevel(void)
0x180022f1d  cmp     eax, 3000h
0x180022f22  ja      loc_180023020
0x180022f28  mov     [rbp+57h+var_60], 0
0x180022f30  xor     edx, edx
0x180022f32  lea     rcx, [rbp+57h+var_60]
0x180022f36  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022f3b  lea     rcx, [rbp+57h+var_60]; this
0x180022f3f  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x180022f44  shr     eax, 1Fh
0x180022f47  mov     rcx, [rbp+5Fh]; this
0x180022f4b  lea     rdx, aFailedToGetThe_4; "Failed to get the calling application's"...
0x180022f52  mov     qword ptr [rsp+90h+var_68], rdx; bool
0x180022f57  mov     [rsp+90h+var_70], al; char
0x180022f5b  mov     r9d, 80070005h; char *
0x180022f61  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022f68  mov     edx, 0BEh; void *
0x180022f6d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180022f72  mov     [rbp+57h+var_58], 0
0x180022f7a  xor     edx, edx
0x180022f7c  lea     rcx, [rbp+57h+var_58]
0x180022f80  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022f85  lea     rdi, [rbx+18h]
0x180022f89  mov     rcx, rdi; this
0x180022f8c  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180022f91  lea     rdx, [rbp+57h+var_58]
0x180022f95  mov     rcx, rax
0x180022f98  call    cs:__imp_GetAppUserModelId
0x180022f9e  shr     eax, 1Fh
0x180022fa1  mov     rcx, [rbp+5Fh]; this
0x180022fa5  lea     rdx, aFailedToGetThe_2; "Failed to get the printer's package AUM"...
0x180022fac  mov     qword ptr [rsp+90h+var_68], rdx; bool
0x180022fb1  mov     [rsp+90h+var_70], al; int
0x180022fb5  mov     r9d, 80070005h; char *
0x180022fbb  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022fc2  mov     edx, 0C2h; void *
0x180022fc7  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180022fcc  mov     rdx, [rbp+57h+var_58]
0x180022fd0  lea     rcx, [rbp+57h+var_30]
0x180022fd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022fd9  nop
0x180022fda  mov     rdx, [rbp+57h+var_60]
0x180022fde  lea     rcx, [rbp+57h+var_50]
0x180022fe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022fe7  lea     rdx, [rbp+57h+var_30]
0x180022feb  lea     rcx, [rbp+57h+var_50]
0x180022fef  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x180022ff4  mov     bl, al
0x180022ff6  lea     rcx, [rbp+57h+var_50]
0x180022ffa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022fff  nop
0x180023000  lea     rcx, [rbp+57h+var_30]
0x180023004  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023009  test    bl, bl
0x18002300b  jz      short loc_180023041
0x18002300d  lea     rcx, [rbp+57h+var_58]
0x180023011  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023016  nop
0x180023017  lea     rcx, [rbp+57h+var_60]
0x18002301b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023020  mov     rcx, [rbp+57h+var_10]
0x180023024  xor     rcx, rsp; StackCookie
0x180023027  call    __security_check_cookie
0x18002302c  lea     r11, [rsp+90h+var_s0]
0x180023034  mov     rbx, [r11+18h]
0x180023038  mov     rdi, [r11+20h]
0x18002303c  mov     rsp, r11
0x18002303f  pop     rbp
0x180023040  retn
0x180023041  mov     rcx, rdi; this
0x180023044  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180023049  mov     r9, rax
0x18002304c  lea     rcx, [rbp+57h+var_60]
0x180023050  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x180023055  mov     r8, rax
0x180023058  lea     rdx, aCallerWsIsNotA; "Caller %ws is not allowed to set the IP"...
0x18002305f  lea     rcx, aWinrtWindowsGr_1; "winrt::Windows::Graphics::Internal::Pri"...
0x180023066  call    ?WriteDbgTraceWarning@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18002306b  mov     ecx, 80070005h
0x180023070  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180023075  mov     r9d, eax; char *
0x180023078  mov     rcx, [rbp+5Fh]; this
0x18002307c  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180023083  mov     edx, 0C8h; void *
0x180023088  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
