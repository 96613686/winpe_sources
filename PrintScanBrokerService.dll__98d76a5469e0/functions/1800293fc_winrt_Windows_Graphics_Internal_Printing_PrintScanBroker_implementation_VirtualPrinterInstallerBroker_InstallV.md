# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinter(winrt::Windows::Foundation::IInspectable const &,winrt::hstring const &)

- ea: `0x1800293fc`
- end: `0x180029698`
- name: `?InstallVirtualPrinter@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@SA_KAEBUIInspectable@Foundation@78@AEBUhstring@8@@Z`
- size: `668`
- prototype: `unsigned __int64 __fastcall(const struct IInspectable *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b3a0`

## callees

- `0x180002d40`
- `0x180007a58`
- `0x18000f760`
- `0x18000fa2c`
- `0x18000fb60`
- `0x18001cfb4`
- `0x180023a20`
- `0x1800256f8`
- `0x180026f64`
- `0x180027120`
- `0x180027160`
- `0x180027f60`
- `0x1800288d8`
- `0x1800293fc`
- `0x18002aff0`
- `0x18002b4d0`
- `0x180035798`
- `0x1800360f4`
- `0x180036ca0`

## string_xrefs

- `0x180029434`: `Checking access`
- `0x180029685`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x180029494`: `Converting VirtualPrinterInstallationParameters to VirtualPrinterInfo`
- `0x18002943b`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinter`
- `0x18002949b`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinter`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::InstallVirtualPrinter(
        const struct IInspectable *a1,
        const struct winrt::hstring *a2)
{
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // rax
  const unsigned __int16 *v6; // rax
  __int64 v7; // r8
  const unsigned __int16 *v8; // rax
  __int64 v9; // r8
  const unsigned __int16 *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rbx
  int v13; // eax
  const char *v14; // r9
  unsigned __int64 result; // rax
  int v16; // [rsp+20h] [rbp-2E8h] BYREF
  __int64 v17; // [rsp+28h] [rbp-2E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-2D8h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-2D0h]
  __int128 v20; // [rsp+40h] [rbp-2C8h] BYREF
  __m128i si128; // [rsp+50h] [rbp-2B8h]
  _OWORD v22[2]; // [rsp+60h] [rbp-2A8h] BYREF
  _OWORD v23[2]; // [rsp+80h] [rbp-288h] BYREF
  __int128 v24; // [rsp+A0h] [rbp-268h]
  __m128i v25; // [rsp+B0h] [rbp-258h]
  _OWORD v26[2]; // [rsp+C0h] [rbp-248h] BYREF
  _BYTE v27[160]; // [rsp+E0h] [rbp-228h] BYREF
  _BYTE v28[368]; // [rsp+180h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage();
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinter",
      L"Checking access");
    PrintScanBrokerUtilities::GetCallerUserSid(&v16);
    winrt::hstring::c_str((winrt::hstring *)&v16);
    v4 = winrt::hstring::c_str(a2);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetFullNameAndAumidFromFamilyName(
      &v18,
      v4);
    v5 = winrt::hstring::c_str((winrt::hstring *)&v16);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(
      0x1000u,
      v19,
      0,
      v5);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Inst"
      "allVirtualPrinter",
      L"Converting VirtualPrinterInstallationParameters to VirtualPrinterInfo");
    winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Devices::Printers::VirtualPrinterInstallationParameters>(
      a1,
      &v17);
    v6 = winrt::hstring::c_str((winrt::hstring *)&v16);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(
      v28,
      &v17,
      v19,
      v6);
    v20 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v20) = 0;
    v22[0] = 0;
    v22[1] = si128;
    LOWORD(v22[0]) = 0;
    v23[0] = 0;
    v23[1] = si128;
    LOWORD(v23[0]) = 0;
    v24 = 0;
    v25 = si128;
    LOWORD(v24) = 0;
    v26[0] = 0;
    v26[1] = si128;
    LOWORD(v26[0]) = 0;
    v12 = -1;
    v7 = -1;
    do
      ++v7;
    while ( v19[v7] );
    std::wstring::_Assign<unsigned short>(v23, v19);
    v8 = winrt::hstring::c_str((winrt::hstring *)&v16);
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    std::wstring::_Assign<unsigned short>(v26, v8);
    v10 = winrt::hstring::c_str(a2);
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    std::wstring::_Assign<unsigned short>(v22, v10);
    do
      ++v12;
    while ( *(_WORD *)(v18 + 2 * v12) );
    std::wstring::_Assign<unsigned short>(&v20, v18);
    VirtualMon::VirtualPrinterInstaller::VirtualPrinterInstaller(
      (VirtualMon::VirtualPrinterInstaller *)v27,
      (const struct VirtualMon::VirtualPrinterAppInfo *)&v20);
    v13 = VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(
            (VirtualMon::VirtualPrinterInstaller *)v27,
            (const struct VirtualMon::VirtualPrinterInfo *)v28);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)(unsigned int)v13,
        v16);
    VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)v27);
    VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)&v20);
    VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo((VirtualMon::VirtualPrinterInfo *)v28);
    winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v17);
    std::tuple<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~tuple<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v16);
    result = 0;
  }
  catch ( ... )
  {
    return (int)wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x4A,
                  (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
                  v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800293fc  mov     [rsp+arg_10], rbx
0x180029401  mov     [rsp+arg_18], rsi
0x180029406  push    rdi
0x180029407  sub     rsp, 300h
0x18002940e  mov     rax, cs:__security_cookie
0x180029415  xor     rax, rsp
0x180029418  mov     [rsp+308h+var_18], rax
0x180029420  mov     rdi, rdx
0x180029423  mov     rbx, rcx
0x180029426  mov     dl, 1
0x180029428  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x18002942f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180029434  lea     rdx, aCheckingAccess; "Checking access"
0x18002943b  lea     rcx, aWinrtWindowsGr_3; "winrt::Windows::Graphics::Internal::Pri"...
0x180029442  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180029447  lea     rcx, [rsp+308h+var_2E8]
0x18002944c  call    ?GetCallerUserSid@PrintScanBrokerUtilities@@YA?AUhstring@winrt@@XZ; PrintScanBrokerUtilities::GetCallerUserSid(void)
0x180029451  nop
0x180029452  lea     rcx, [rsp+308h+var_2E8]; this
0x180029457  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002945c  mov     r8, rax
0x18002945f  mov     rcx, rdi; this
0x180029462  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180029467  mov     rdx, rax
0x18002946a  lea     rcx, [rsp+308h+var_2D8]
0x18002946f  call    ?GetFullNameAndAumidFromFamilyName@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AV?$tuple@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@PEBG0@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetFullNameAndAumidFromFamilyName(ushort const *,ushort const *)
0x180029474  nop
0x180029475  lea     rcx, [rsp+308h+var_2E8]; this
0x18002947a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002947f  mov     r9, rax; unsigned __int16 *
0x180029482  xor     r8d, r8d; unsigned __int16 *
0x180029485  mov     rdx, [rsp+308h+var_2D0]; unsigned __int16 *
0x18002948a  mov     ecx, 1000h; unsigned int
0x18002948f  call    ?VirtualPrinterInstallAccessCheck@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CAXKPEBG00@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(ulong,ushort const *,ushort const *,ushort const *)
0x180029494  lea     rdx, aConvertingVirt; "Converting VirtualPrinterInstallationPa"...
0x18002949b  lea     rcx, aWinrtWindowsGr_3; "winrt::Windows::Graphics::Internal::Pri"...
0x1800294a2  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800294a7  lea     rdx, [rsp+308h+var_2E0]
0x1800294ac  mov     rcx, rbx
0x1800294af  call    ??$as@UVirtualPrinterInstallationParameters@Printers@Devices@Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x1800294b4  nop
0x1800294b5  lea     rcx, [rsp+308h+var_2E8]; this
0x1800294ba  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800294bf  mov     r9, rax
0x1800294c2  mov     r8, [rsp+308h+var_2D0]
0x1800294c7  lea     rdx, [rsp+308h+var_2E0]
0x1800294cc  lea     rcx, [rsp+308h+var_188]
0x1800294d4  call    ?GetVirtualPrinterInfo@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AUVirtualPrinterInfo@VirtualMon@@AEBUVirtualPrinterInstallationParameters@Printers@Devices@78@PEBG1@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetVirtualPrinterInfo(winrt::Windows::Devices::Printers::VirtualPrinterInstallationParameters const &,ushort const *,ushort const *)
0x1800294d9  nop
0x1800294da  xorps   xmm0, xmm0
0x1800294dd  movups  [rsp+308h+var_2C8], xmm0
0x1800294e2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800294ea  movdqa  [rsp+308h+var_2B8], xmm1
0x1800294f0  xor     esi, esi
0x1800294f2  mov     word ptr [rsp+308h+var_2C8], si
0x1800294f7  movups  [rsp+308h+var_2A8], xmm0
0x1800294fc  movdqa  [rsp+308h+var_298], xmm1
0x180029502  mov     word ptr [rsp+308h+var_2A8], si
0x180029507  movups  [rsp+308h+var_288], xmm0
0x18002950f  movdqa  [rsp+308h+var_278], xmm1
0x180029518  mov     word ptr [rsp+308h+var_288], si
0x180029520  movups  [rsp+308h+var_268], xmm0
0x180029528  movdqa  [rsp+308h+var_258], xmm1
0x180029531  mov     word ptr [rsp+308h+var_268], si
0x180029539  movups  [rsp+308h+var_248], xmm0
0x180029541  movdqa  [rsp+308h+var_238], xmm1
0x18002954a  mov     word ptr [rsp+308h+var_248], si
0x180029552  mov     rdx, [rsp+308h+var_2D0]
0x180029557  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002955b  mov     r8, rbx
0x18002955e  inc     r8
0x180029561  cmp     [rdx+r8*2], si
0x180029566  jnz     short loc_18002955E
0x180029568  lea     rcx, [rsp+308h+var_288]
0x180029570  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180029575  lea     rcx, [rsp+308h+var_2E8]; this
0x18002957a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002957f  mov     r8, rbx
0x180029582  inc     r8
0x180029585  cmp     [rax+r8*2], si
0x18002958a  jnz     short loc_180029582
0x18002958c  mov     rdx, rax
0x18002958f  lea     rcx, [rsp+308h+var_248]
0x180029597  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002959c  mov     rcx, rdi; this
0x18002959f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800295a4  mov     r8, rbx
0x1800295a7  inc     r8
0x1800295aa  cmp     [rax+r8*2], si
0x1800295af  jnz     short loc_1800295A7
0x1800295b1  mov     rdx, rax
0x1800295b4  lea     rcx, [rsp+308h+var_2A8]
0x1800295b9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800295be  mov     rdx, [rsp+308h+var_2D8]
0x1800295c3  inc     rbx
0x1800295c6  cmp     [rdx+rbx*2], si
0x1800295ca  jnz     short loc_1800295C3
0x1800295cc  mov     r8, rbx
0x1800295cf  lea     rcx, [rsp+308h+var_2C8]
0x1800295d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800295d9  lea     rdx, [rsp+308h+var_2C8]; struct VirtualMon::VirtualPrinterAppInfo *
0x1800295de  lea     rcx, [rsp+308h+var_228]; this
0x1800295e6  call    ??0VirtualPrinterInstaller@VirtualMon@@QEAA@AEBUVirtualPrinterAppInfo@1@@Z; VirtualMon::VirtualPrinterInstaller::VirtualPrinterInstaller(VirtualMon::VirtualPrinterAppInfo const &)
0x1800295eb  nop
0x1800295ec  lea     rdx, [rsp+308h+var_188]; struct VirtualMon::VirtualPrinterInfo *
0x1800295f4  lea     rcx, [rsp+308h+var_228]; this
0x1800295fc  call    ?InstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@QEAAJAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInstaller::InstallVirtualPrinter(VirtualMon::VirtualPrinterInfo const &)
0x180029601  mov     rcx, [rsp+308h]; this
0x180029609  test    eax, eax
0x18002960b  js      short loc_180029682
0x18002960d  lea     rcx, [rsp+308h+var_228]; this
0x180029615  call    ??1VirtualPrinterAppInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo(void)
0x18002961a  nop
0x18002961b  lea     rcx, [rsp+308h+var_2C8]; this
0x180029620  call    ??1VirtualPrinterAppInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo(void)
0x180029625  nop
0x180029626  lea     rcx, [rsp+308h+var_188]; this
0x18002962e  call    ??1VirtualPrinterInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo(void)
0x180029633  nop
0x180029634  lea     rcx, [rsp+308h+var_2E0]; this
0x180029639  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x18002963e  nop
0x18002963f  lea     rcx, [rsp+308h+var_2D8]
0x180029644  call    ??1?$tuple@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@QEAA@XZ; std::tuple<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~tuple<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180029649  nop
0x18002964a  lea     rcx, [rsp+308h+var_2E8]
0x18002964f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180029654  xor     eax, eax
0x180029656  jmp     short loc_18002965D
0x180029658  mov     rax, [rsp+308h+var_2E0]
0x18002965d  mov     rcx, [rsp+308h+var_18]
0x180029665  xor     rcx, rsp; StackCookie
0x180029668  call    __security_check_cookie
0x18002966d  lea     r11, [rsp+308h+var_8]
0x180029675  mov     rbx, [r11+20h]
0x180029679  mov     rsi, [r11+28h]
0x18002967d  mov     rsp, r11
0x180029680  pop     rdi
0x180029681  retn
0x180029682  mov     r9d, eax; char *
0x180029685  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002968c  mov     edx, 47h ; 'G'; void *
0x180029691  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
