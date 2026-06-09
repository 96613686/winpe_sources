# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(ulong,ushort const *,ushort const *,ushort const *)

- ea: `0x18002b4d0`
- end: `0x18002b6db`
- name: `?VirtualPrinterInstallAccessCheck@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CAXKPEBG00@Z`
- size: `523`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800293fc`
- `0x1800296a0`
- `0x18002a148`
- `0x18002a6f0`

## callees

- `0x180006b48`
- `0x18000f760`
- `0x18000fa2c`
- `0x18000fb60`
- `0x18001031c`
- `0x1800182cc`
- `0x18001ca0c`
- `0x18001cfb4`
- `0x18001cfd4`
- `0x1800232bc`
- `0x1800280a0`
- `0x18002b4d0`
- `0x180035450`
- `0x180043e20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b56b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b5a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b56b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b5a4`

## string_xrefs

- `0x18002b54e`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002b618`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002b65a`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002b68d`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002b6c9`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002b6a5`: `Access denied because current level less than min level %d vs %d.`
- `0x18002b5c8`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck`
- `0x18002b5fe`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck`
- `0x18002b640`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck`
- `0x18002b673`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck`
- `0x18002b6ac`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck`
- `0x18002b5f7`: `Access denied because %ws != %ws.`
- `0x18002b639`: `Access denied because %ws != %ws`
- `0x18002b5c1`: `Access check succeeded`
- `0x18002b66c`: `Access denied because no appPkgFullName or printerName specified`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // rsi
  PrintScanBrokerUtilities *v8; // rcx
  unsigned int CallerIntegrityLevel; // eax
  unsigned __int16 **v10; // rdx
  int CallingProcessPackageFullName; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  const unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // [rsp+20h] [rbp-20h]
  int v26; // [rsp+20h] [rbp-20h]
  const char *v27; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v28[8]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v5 = a3;
  v6 = a2;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
    a2,
    a3);
  CallerIntegrityLevel = PrintScanBrokerUtilities::GetCallerIntegrityLevel(v8);
  if ( CallerIntegrityLevel < a1 )
  {
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Virt"
      "ualPrinterInstallAccessCheck",
      L"Access denied because current level less than min level %d vs %d.",
      CallerIntegrityLevel,
      a1);
    v24 = wil::verify_hresult<long>(2147942405LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)v24,
      v25);
  }
  if ( CallerIntegrityLevel <= 0x1000 )
  {
    v27 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    CallingProcessPackageFullName = CallerIdentity::GetCallingProcessPackageFullName((CallerIdentity *)&v27, v10);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
      (const char *)0x80070005LL,
      CallingProcessPackageFullName < 0,
      (bool)"Failed to get the calling application's package full name!",
      v27);
    if ( v6 )
    {
      if ( (unsigned int)_o__wcsicmp(v27, v6) )
      {
        v21 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(&v27, v12, v13, v14);
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "VirtualPrinterInstallAccessCheck",
          L"Access denied because %ws != %ws",
          v21,
          v6);
        v22 = wil::verify_hresult<long>(2147942405LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x204,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
          (const char *)v22,
          v26);
      }
    }
    else
    {
      if ( !v5 )
      {
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "VirtualPrinterInstallAccessCheck",
          L"Access denied because no appPkgFullName or printerName specified");
        v23 = wil::verify_hresult<long>(2147942405LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
          (const char *)v23,
          v26);
      }
      winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPackageFullNameForVirtualPrinter(
        v28,
        v5,
        a4);
      v15 = winrt::hstring::c_str((winrt::hstring *)v28);
      if ( (unsigned int)_o__wcsicmp(v27, v15) )
      {
        v16 = winrt::hstring::c_str((winrt::hstring *)v28);
        v19 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(&v27, v17, v18, v16);
        PrintScanBrokerTelemetry::WriteDbgTraceInfo(
          "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::"
          "VirtualPrinterInstallAccessCheck",
          L"Access denied because %ws != %ws.",
          v19);
        v20 = wil::verify_hresult<long>(2147942405LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x20E,
          (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
          (const char *)v20,
          v26);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  }
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Virtua"
    "lPrinterInstallAccessCheck",
    L"Access check succeeded");
}

```

## disassembly

```asm
0x18002b4d0  push    rbp
0x18002b4d2  push    rbx
0x18002b4d3  push    rsi
0x18002b4d4  push    r14
0x18002b4d6  push    r15
0x18002b4d8  mov     rbp, rsp
0x18002b4db  sub     rsp, 40h
0x18002b4df  mov     r15, r9
0x18002b4e2  mov     r14, r8
0x18002b4e5  mov     rsi, rdx
0x18002b4e8  mov     ebx, ecx
0x18002b4ea  mov     r8b, 3
0x18002b4ed  mov     dl, 1
0x18002b4ef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x18002b4f6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002b4fb  call    ?GetCallerIntegrityLevel@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerIntegrityLevel(void)
0x18002b500  cmp     eax, ebx
0x18002b502  jb      loc_18002B69F
0x18002b508  cmp     eax, 1000h
0x18002b50d  ja      loc_18002B5C1
0x18002b513  mov     [rbp+var_10], 0
0x18002b51b  xor     edx, edx
0x18002b51d  lea     rcx, [rbp+var_10]
0x18002b521  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b526  lea     rcx, [rbp+var_10]; this
0x18002b52a  call    ?GetCallingProcessPackageFullName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFullName(ushort * *)
0x18002b52f  shr     eax, 1Fh
0x18002b532  mov     rcx, [rbp+28h]; this
0x18002b536  lea     rdx, aFailedToGetThe_1; "Failed to get the calling application's"...
0x18002b53d  mov     qword ptr [rsp+40h+var_18], rdx; bool
0x18002b542  mov     [rsp+40h+var_20], al; int
0x18002b546  mov     ebx, 80070005h
0x18002b54b  mov     r9d, ebx; char *
0x18002b54e  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002b555  mov     edx, 1FCh; void *
0x18002b55a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002b55f  test    rsi, rsi
0x18002b562  jz      short loc_18002B57B
0x18002b564  mov     rdx, rsi
0x18002b567  mov     rcx, [rbp+var_10]
0x18002b56b  call    cs:__imp__o__wcsicmp
0x18002b571  test    eax, eax
0x18002b573  jnz     loc_18002B62A
0x18002b579  jmp     short loc_18002B5B8
0x18002b57b  test    r14, r14
0x18002b57e  jz      loc_18002B66C
0x18002b584  mov     r8, r15
0x18002b587  mov     rdx, r14
0x18002b58a  lea     rcx, [rbp+var_8]
0x18002b58e  call    ?GetPackageFullNameForVirtualPrinter@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AUhstring@8@PEBG0@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPackageFullNameForVirtualPrinter(ushort const *,ushort const *)
0x18002b593  nop
0x18002b594  lea     rcx, [rbp+var_8]; this
0x18002b598  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002b59d  mov     rdx, rax
0x18002b5a0  mov     rcx, [rbp+var_10]
0x18002b5a4  call    cs:__imp__o__wcsicmp
0x18002b5aa  test    eax, eax
0x18002b5ac  jnz     short loc_18002B5DF
0x18002b5ae  lea     rcx, [rbp+var_8]
0x18002b5b2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002b5b7  nop
0x18002b5b8  lea     rcx, [rbp+var_10]
0x18002b5bc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b5c1  lea     rdx, aAccessCheckSuc; "Access check succeeded"
0x18002b5c8  lea     rcx, aWinrtWindowsGr_4; "winrt::Windows::Graphics::Internal::Pri"...
0x18002b5cf  add     rsp, 40h
0x18002b5d3  pop     r15
0x18002b5d5  pop     r14
0x18002b5d7  pop     rsi
0x18002b5d8  pop     rbx
0x18002b5d9  pop     rbp
0x18002b5da  jmp     ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b5df  lea     rcx, [rbp+var_8]; this
0x18002b5e3  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002b5e8  mov     r9, rax
0x18002b5eb  lea     rcx, [rbp+var_10]
0x18002b5ef  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x18002b5f4  mov     r8, rax
0x18002b5f7  lea     rdx, aAccessDeniedBe_1; "Access denied because %ws != %ws."
0x18002b5fe  lea     rcx, aWinrtWindowsGr_4; "winrt::Windows::Graphics::Internal::Pri"...
0x18002b605  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b60a  mov     ecx, ebx
0x18002b60c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b611  mov     r9d, eax; char *
0x18002b614  mov     rcx, [rbp+28h]; this
0x18002b618  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002b61f  mov     edx, 20Eh; void *
0x18002b624  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b62a  lea     rcx, [rbp+var_10]
0x18002b62e  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x18002b633  mov     r8, rax
0x18002b636  mov     r9, rsi
0x18002b639  lea     rdx, aAccessDeniedBe_0; "Access denied because %ws != %ws"
0x18002b640  lea     rcx, aWinrtWindowsGr_4; "winrt::Windows::Graphics::Internal::Pri"...
0x18002b647  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b64c  mov     ecx, ebx
0x18002b64e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b653  mov     r9d, eax; char *
0x18002b656  mov     rcx, [rbp+28h]; this
0x18002b65a  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002b661  mov     edx, 204h; void *
0x18002b666  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b66c  lea     rdx, aAccessDeniedBe_2; "Access denied because no appPkgFullName"...
0x18002b673  lea     rcx, aWinrtWindowsGr_4; "winrt::Windows::Graphics::Internal::Pri"...
0x18002b67a  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b67f  mov     ecx, ebx
0x18002b681  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b686  mov     r9d, eax; char *
0x18002b689  mov     rcx, [rbp+28h]; this
0x18002b68d  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002b694  mov     edx, 214h; void *
0x18002b699  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b69f  mov     r9d, ebx
0x18002b6a2  mov     r8d, eax
0x18002b6a5  lea     rdx, aAccessDeniedBe; "Access denied because current level les"...
0x18002b6ac  lea     rcx, aWinrtWindowsGr_4; "winrt::Windows::Graphics::Internal::Pri"...
0x18002b6b3  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002b6b8  mov     ecx, 80070005h
0x18002b6bd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002b6c2  mov     r9d, eax; char *
0x18002b6c5  mov     rcx, [rbp+28h]; this
0x18002b6c9  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002b6d0  mov     edx, 1F6h; void *
0x18002b6d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
