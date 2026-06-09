# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter(winrt::hstring const &)

- ea: `0x18002a148`
- end: `0x18002a6e9`
- name: `?RemoveVirtualPrinter@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@SA_KAEBUhstring@8@@Z`
- size: `1441`
- prototype: `unsigned __int64 __fastcall(const struct winrt::hstring *this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x180002d40`
- `0x180005fd8`
- `0x18000792c`
- `0x180008838`
- `0x18000f760`
- `0x18000f8a8`
- `0x18000fa2c`
- `0x18000fb60`
- `0x180012498`
- `0x18001cfb4`
- `0x180023a20`
- `0x180024314`
- `0x180026248`
- `0x180027120`
- `0x180027160`
- `0x1800278a4`
- `0x1800278ec`
- `0x18002829c`
- `0x180029108`
- `0x18002a148`
- `0x18002aff0`
- `0x18002b0e4`
- `0x18002b4d0`
- `0x180035798`
- `0x1800360f4`
- `0x180037c78`

## string_xrefs

- `0x18002a6d6`: `onecoreuap\printscan\print\printscanbroker\class\virtualprinterinstallerbroker.cpp`
- `0x18002a19c`: `Access check removing virtual printer %ws`
- `0x18002a21e`: `After access check for virtual printer %ws`
- `0x18002a1a3`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a225`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a2fc`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a4f9`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a5ba`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a603`: `winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter`
- `0x18002a2f5`: `After GetUserSidForActiveSession`

## pseudocode

```c
unsigned __int64 __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::RemoveVirtualPrinter(
        const struct winrt::hstring *this)
{
  char v2; // r14
  const unsigned __int16 *v3; // rax
  __int64 v4; // rax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  const unsigned __int16 *v7; // rax
  __m128i si128; // xmm6
  const unsigned __int16 *v9; // rax
  __int64 v10; // r8
  const unsigned __int16 *v11; // rax
  _QWORD *i; // rbx
  _QWORD *v13; // r15
  _QWORD *v14; // r8
  __int128 *v15; // rdx
  __int64 v16; // r12
  _QWORD *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rsi
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rax
  const char *v22; // r9
  unsigned __int64 result; // rax
  int v24[2]; // [rsp+20h] [rbp-3C8h] BYREF
  _BYTE v25[8]; // [rsp+28h] [rbp-3C0h] BYREF
  _BYTE v26[8]; // [rsp+30h] [rbp-3B8h] BYREF
  __int128 v27; // [rsp+38h] [rbp-3B0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-3A0h]
  _QWORD v29[3]; // [rsp+50h] [rbp-398h] BYREF
  int v30[8]; // [rsp+68h] [rbp-380h] BYREF
  _BYTE v31[40]; // [rsp+88h] [rbp-360h] BYREF
  _OWORD v32[2]; // [rsp+B0h] [rbp-338h] BYREF
  __int128 v33; // [rsp+D0h] [rbp-318h]
  __m128i v34; // [rsp+E0h] [rbp-308h]
  __int128 v35; // [rsp+F0h] [rbp-2F8h]
  __m128i v36; // [rsp+100h] [rbp-2E8h]
  __int128 v37; // [rsp+110h] [rbp-2D8h]
  __m128i v38; // [rsp+120h] [rbp-2C8h]
  __int128 v39; // [rsp+130h] [rbp-2B8h] BYREF
  __m128i v40; // [rsp+140h] [rbp-2A8h]
  _OWORD v41[2]; // [rsp+150h] [rbp-298h] BYREF
  __int128 v42; // [rsp+170h] [rbp-278h]
  __m128i v43; // [rsp+180h] [rbp-268h]
  _OWORD v44[2]; // [rsp+190h] [rbp-258h] BYREF
  __int128 v45; // [rsp+1B0h] [rbp-238h]
  __m128i v46; // [rsp+1C0h] [rbp-228h]
  __int128 v47; // [rsp+1D0h] [rbp-218h]
  __m128i v48; // [rsp+1E0h] [rbp-208h]
  __int128 v49; // [rsp+1F0h] [rbp-1F8h]
  __m128i v50; // [rsp+200h] [rbp-1E8h]
  __int128 v51; // [rsp+210h] [rbp-1D8h]
  __m128i v52; // [rsp+220h] [rbp-1C8h]
  __int128 v53; // [rsp+230h] [rbp-1B8h]
  __m128i v54; // [rsp+240h] [rbp-1A8h]
  __int128 v55; // [rsp+250h] [rbp-198h]
  __m128i v56; // [rsp+260h] [rbp-188h]
  __int128 v57; // [rsp+270h] [rbp-178h]
  __m128i v58; // [rsp+280h] [rbp-168h]
  __int128 v59; // [rsp+290h] [rbp-158h]
  __m128i v60; // [rsp+2A0h] [rbp-148h]
  _BYTE v61[16]; // [rsp+2B0h] [rbp-138h] BYREF
  _BYTE v62[32]; // [rsp+2C0h] [rbp-128h] BYREF
  _BYTE v63[32]; // [rsp+2E0h] [rbp-108h] BYREF
  _BYTE v64[160]; // [rsp+300h] [rbp-E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  v2 = 1;
  try
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage();
    v3 = winrt::hstring::c_str(this);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinter",
      L"Access check removing virtual printer %ws",
      v3);
    PrintScanBrokerUtilities::GetCallerUserSid(v25);
    v4 = winrt::operator+(v24, v25, L":");
    winrt::operator+(v26, v4, this);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v24);
    winrt::hstring::c_str((winrt::hstring *)v25);
    v5 = winrt::hstring::c_str((winrt::hstring *)v26);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(
      0x1000u,
      0,
      v5,
      v6);
    v7 = winrt::hstring::c_str(this);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinter",
      L"After access check for virtual printer %ws",
      v7);
    v32[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v32[1] = si128;
    LOWORD(v32[0]) = 0;
    v33 = 0;
    v34 = si128;
    LOWORD(v33) = 0;
    v35 = 0;
    v36 = si128;
    LOWORD(v35) = 0;
    v37 = 0;
    v38 = si128;
    LOWORD(v37) = 0;
    v39 = 0;
    v40 = si128;
    LOWORD(v39) = 0;
    v29[2] = &PrintSupportUtility::`vftable';
    v9 = winrt::hstring::c_str((winrt::hstring *)v25);
    v19 = -1;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    std::wstring::_Assign<unsigned short>(&v39, v9);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinter",
      L"After GetUserSidForActiveSession");
    v41[0] = 0;
    v41[1] = si128;
    LOWORD(v41[0]) = 0;
    v42 = 0;
    v43 = si128;
    LOWORD(v42) = 0;
    v44[0] = 0;
    v44[1] = si128;
    LOWORD(v44[0]) = 0;
    v45 = 0;
    v46 = si128;
    LOWORD(v45) = 0;
    v47 = 0;
    v48 = si128;
    LOWORD(v47) = 0;
    v49 = 0;
    v50 = si128;
    LOWORD(v49) = 0;
    v51 = 0;
    v52 = si128;
    LOWORD(v51) = 0;
    v53 = 0;
    v54 = si128;
    LOWORD(v53) = 0;
    v55 = 0;
    v56 = si128;
    LOWORD(v55) = 0;
    v57 = 0;
    v58 = si128;
    LOWORD(v57) = 0;
    v59 = 0;
    v60 = si128;
    LOWORD(v59) = 0;
    std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v61);
    winrt::hstring::operator std::basic_string_view<unsigned short>(this, v29);
    std::wstring::_Assign<unsigned short>(v44, v29[0]);
    v11 = winrt::hstring::c_str(this);
    winrt::hstring::hstring((winrt::hstring *)v24, v11);
    winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter(
      v63,
      v26,
      v24);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v24);
    std::wstring::wstring(v62, L",");
    PrintCore::StringHelpers::SplitString(&v27, v63, v62);
    std::wstring::_Tidy_deallocate(v62);
    v13 = (_QWORD *)*((_QWORD *)&v27 + 1);
    for ( i = (_QWORD *)v27; i != v13; i += 4 )
    {
      if ( i[3] <= 7u )
        v14 = i;
      else
        v14 = (_QWORD *)*i;
      PrintScanBrokerTelemetry::WriteDbgTraceInfo(
        "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Re"
        "moveVirtualPrinter",
        L"Check for %ws",
        v14);
      *(_QWORD *)v24 = v30;
      v15 = &v39;
      if ( v40.m128i_i64[1] > 7uLL )
        v15 = (__int128 *)v39;
      v16 = std::wstring::wstring(v30, v15);
      if ( i[3] <= 7u )
        v17 = i;
      else
        v17 = (_QWORD *)*i;
      v18 = std::wstring::wstring(v31, v17);
      if ( (unsigned __int8)PrintCore::StringHelpers::IContains(v18, v16) )
      {
        if ( i[3] > 7u )
          i = (_QWORD *)*i;
        do
          ++v19;
        while ( *((_WORD *)i + v19) );
        std::wstring::_Assign<unsigned short>(v41, i);
        v2 = 0;
        break;
      }
    }
    if ( v2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
        (const char *)0x80070490LL,
        v24[0]);
    v20 = winrt::hstring::c_str(this);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinter",
      L"Calling VirtualMon helper lib for %ws",
      v20);
    VirtualMon::VirtualPrinterInstaller::VirtualPrinterInstaller(
      (VirtualMon::VirtualPrinterInstaller *)v64,
      (const struct VirtualMon::VirtualPrinterAppInfo *)v32);
    VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(
      (VirtualMon::VirtualPrinterInstaller *)v64,
      (const struct VirtualMon::VirtualPrinterInfo *)v41);
    v21 = winrt::hstring::c_str(this);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::Remo"
      "veVirtualPrinter",
      L"Back from VirtualMon helper lib for %ws",
      v21);
    VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)v64);
    if ( (_QWORD)v27 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v27, *((_QWORD *)&v27 + 1));
      std::_Deallocate<16>(v27, (v28 - v27) & 0xFFFFFFFFFFFFFFE0uLL);
      v27 = 0;
      v28 = 0;
    }
    std::wstring::_Tidy_deallocate(v63);
    VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo((VirtualMon::VirtualPrinterInfo *)v41);
    VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo((VirtualMon::VirtualPrinterAppInfo *)v32);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v26);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v25);
    result = 0;
  }
  catch ( ... )
  {
    return (int)wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0xCA,
                  (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\virtualprinterinstallerbroker.cpp",
                  v22);
  }
  return result;
}

```

## disassembly

```asm
0x18002a148  mov     rax, rsp
0x18002a14b  mov     [rax+10h], rbx
0x18002a14f  mov     [rax+18h], rsi
0x18002a153  push    rdi
0x18002a154  push    r12
0x18002a156  push    r13
0x18002a158  push    r14
0x18002a15a  push    r15
0x18002a15c  sub     rsp, 3C0h
0x18002a163  movaps  xmmword ptr [rax-38h], xmm6
0x18002a167  mov     rax, cs:__security_cookie
0x18002a16e  xor     rax, rsp
0x18002a171  mov     [rsp+3E8h+var_48], rax
0x18002a179  mov     rdi, rcx
0x18002a17c  xor     r13d, r13d
0x18002a17f  mov     r14b, 1
0x18002a182  mov     dl, r14b
0x18002a185  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements> `wil::Feature<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::GetImpl(void)'::`2'::impl
0x18002a18c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VirtualPrinter_API_Enhancements>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002a191  mov     rcx, rdi; this
0x18002a194  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a199  mov     r8, rax
0x18002a19c  lea     rdx, aAccessCheckRem; "Access check removing virtual printer %"...
0x18002a1a3  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a1aa  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a1af  lea     rcx, [rsp+3E8h+var_3C0]
0x18002a1b4  call    ?GetCallerUserSid@PrintScanBrokerUtilities@@YA?AUhstring@winrt@@XZ; PrintScanBrokerUtilities::GetCallerUserSid(void)
0x18002a1b9  nop
0x18002a1ba  lea     r8, asc_18004E4AC; ":"
0x18002a1c1  lea     rdx, [rsp+3E8h+var_3C0]
0x18002a1c6  lea     rcx, [rsp+3E8h+var_3C8]
0x18002a1cb  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEBG@Z; winrt::operator+(winrt::hstring const &,ushort const *)
0x18002a1d0  nop
0x18002a1d1  mov     r8, rdi
0x18002a1d4  mov     rdx, rax
0x18002a1d7  lea     rcx, [rsp+3E8h+var_3B8]
0x18002a1dc  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x18002a1e1  nop
0x18002a1e2  lea     rcx, [rsp+3E8h+var_3C8]
0x18002a1e7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002a1ec  nop
0x18002a1ed  lea     rcx, [rsp+3E8h+var_3C0]; this
0x18002a1f2  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a1f7  mov     r9, rax
0x18002a1fa  lea     rcx, [rsp+3E8h+var_3B8]; this
0x18002a1ff  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a204  mov     r8, rax; unsigned __int16 *
0x18002a207  xor     edx, edx; unsigned __int16 *
0x18002a209  mov     ecx, 1000h; unsigned int
0x18002a20e  call    ?VirtualPrinterInstallAccessCheck@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CAXKPEBG00@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::VirtualPrinterInstallAccessCheck(ulong,ushort const *,ushort const *,ushort const *)
0x18002a213  mov     rcx, rdi; this
0x18002a216  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a21b  mov     r8, rax
0x18002a21e  lea     rdx, aAfterAccessChe; "After access check for virtual printer "...
0x18002a225  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a22c  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a231  xorps   xmm0, xmm0
0x18002a234  movups  [rsp+3E8h+var_338], xmm0
0x18002a23c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002a244  movdqa  [rsp+3E8h+var_328], xmm6
0x18002a24d  mov     word ptr [rsp+3E8h+var_338], r13w
0x18002a256  movups  [rsp+3E8h+var_318], xmm0
0x18002a25e  movdqa  [rsp+3E8h+var_308], xmm6
0x18002a267  mov     word ptr [rsp+3E8h+var_318], r13w
0x18002a270  movups  [rsp+3E8h+var_2F8], xmm0
0x18002a278  movdqa  [rsp+3E8h+var_2E8], xmm6
0x18002a281  mov     word ptr [rsp+3E8h+var_2F8], r13w
0x18002a28a  movups  [rsp+3E8h+var_2D8], xmm0
0x18002a292  movdqa  [rsp+3E8h+var_2C8], xmm6
0x18002a29b  mov     word ptr [rsp+3E8h+var_2D8], r13w
0x18002a2a4  movups  [rsp+3E8h+var_2B8], xmm0
0x18002a2ac  movdqa  [rsp+3E8h+var_2A8], xmm6
0x18002a2b5  mov     word ptr [rsp+3E8h+var_2B8], r13w
0x18002a2be  lea     rax, ??_7PrintSupportUtility@@6B@; const PrintSupportUtility::`vftable'
0x18002a2c5  mov     [rsp+3E8h+var_388], rax
0x18002a2ca  lea     rcx, [rsp+3E8h+var_3C0]; this
0x18002a2cf  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a2d4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a2d8  mov     r8, rsi
0x18002a2db  inc     r8
0x18002a2de  cmp     [rax+r8*2], r13w
0x18002a2e3  jnz     short loc_18002A2DB
0x18002a2e5  mov     rdx, rax
0x18002a2e8  lea     rcx, [rsp+3E8h+var_2B8]
0x18002a2f0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002a2f5  lea     rdx, aAfterGetusersi; "After GetUserSidForActiveSession"
0x18002a2fc  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a303  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a308  xorps   xmm0, xmm0
0x18002a30b  movups  [rsp+3E8h+var_298], xmm0
0x18002a313  movdqa  [rsp+3E8h+var_288], xmm6
0x18002a31c  mov     word ptr [rsp+3E8h+var_298], r13w
0x18002a325  movups  [rsp+3E8h+var_278], xmm0
0x18002a32d  movdqa  [rsp+3E8h+var_268], xmm6
0x18002a336  mov     word ptr [rsp+3E8h+var_278], r13w
0x18002a33f  movups  [rsp+3E8h+var_258], xmm0
0x18002a347  movdqa  [rsp+3E8h+var_248], xmm6
0x18002a350  mov     word ptr [rsp+3E8h+var_258], r13w
0x18002a359  movups  [rsp+3E8h+var_238], xmm0
0x18002a361  movdqa  [rsp+3E8h+var_228], xmm6
0x18002a36a  mov     word ptr [rsp+3E8h+var_238], r13w
0x18002a373  movups  [rsp+3E8h+var_218], xmm0
0x18002a37b  movdqa  [rsp+3E8h+var_208], xmm6
0x18002a384  mov     word ptr [rsp+3E8h+var_218], r13w
0x18002a38d  movups  [rsp+3E8h+var_1F8], xmm0
0x18002a395  movdqa  [rsp+3E8h+var_1E8], xmm6
0x18002a39e  mov     word ptr [rsp+3E8h+var_1F8], r13w
0x18002a3a7  movups  [rsp+3E8h+var_1D8], xmm0
0x18002a3af  movdqa  [rsp+3E8h+var_1C8], xmm6
0x18002a3b8  mov     word ptr [rsp+3E8h+var_1D8], r13w
0x18002a3c1  movups  [rsp+3E8h+var_1B8], xmm0
0x18002a3c9  movdqa  [rsp+3E8h+var_1A8], xmm6
0x18002a3d2  mov     word ptr [rsp+3E8h+var_1B8], r13w
0x18002a3db  movups  [rsp+3E8h+var_198], xmm0
0x18002a3e3  movdqa  [rsp+3E8h+var_188], xmm6
0x18002a3ec  mov     word ptr [rsp+3E8h+var_198], r13w
0x18002a3f5  movups  [rsp+3E8h+var_178], xmm0
0x18002a3fd  movdqa  [rsp+3E8h+var_168], xmm6
0x18002a406  mov     word ptr [rsp+3E8h+var_178], r13w
0x18002a40f  movups  [rsp+3E8h+var_158], xmm0
0x18002a417  movdqa  [rsp+3E8h+var_148], xmm6
0x18002a420  mov     word ptr [rsp+3E8h+var_158], r13w
0x18002a429  lea     rcx, [rsp+3E8h+var_138]
0x18002a431  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18002a436  nop
0x18002a437  lea     rdx, [rsp+3E8h+var_398]
0x18002a43c  mov     rcx, rdi
0x18002a43f  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x18002a444  mov     r8, [rsp+3E8h+var_390]
0x18002a449  mov     rdx, [rsp+3E8h+var_398]
0x18002a44e  lea     rcx, [rsp+3E8h+var_258]
0x18002a456  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002a45b  mov     rcx, rdi; this
0x18002a45e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a463  mov     rdx, rax; unsigned __int16 *
0x18002a466  lea     rcx, [rsp+3E8h+var_3C8]; this
0x18002a46b  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18002a470  nop
0x18002a471  lea     r8, [rsp+3E8h+var_3C8]
0x18002a476  lea     rdx, [rsp+3E8h+var_3B8]
0x18002a47b  lea     rcx, [rsp+3E8h+var_108]
0x18002a483  call    ?GetPortNameFromPrinter@VirtualPrinterInstallerBroker@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@8@0@Z; winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::VirtualPrinterInstallerBroker::GetPortNameFromPrinter(winrt::hstring const &,winrt::hstring const &)
0x18002a488  nop
0x18002a489  lea     rcx, [rsp+3E8h+var_3C8]
0x18002a48e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002a493  lea     rdx, asc_18004D314; ","
0x18002a49a  lea     rcx, [rsp+3E8h+var_128]
0x18002a4a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a4a7  nop
0x18002a4a8  lea     r8, [rsp+3E8h+var_128]
0x18002a4b0  lea     rdx, [rsp+3E8h+var_108]
0x18002a4b8  lea     rcx, [rsp+3E8h+var_3B0]
0x18002a4bd  call    ?SplitString@StringHelpers@PrintCore@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0@Z; PrintCore::StringHelpers::SplitString(std::wstring const &,std::wstring const &)
0x18002a4c2  nop
0x18002a4c3  lea     rcx, [rsp+3E8h+var_128]
0x18002a4cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a4d0  mov     rbx, qword ptr [rsp+3E8h+var_3B0]
0x18002a4d5  mov     r15, qword ptr [rsp+3E8h+var_3B0+8]
0x18002a4da  cmp     rbx, r15
0x18002a4dd  jz      loc_18002A58C
0x18002a4e3  cmp     qword ptr [rbx+18h], 7
0x18002a4e8  jbe     short loc_18002A4EF
0x18002a4ea  mov     r8, [rbx]
0x18002a4ed  jmp     short loc_18002A4F2
0x18002a4ef  mov     r8, rbx
0x18002a4f2  lea     rdx, aCheckForWs; "Check for %ws"
0x18002a4f9  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a500  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a505  lea     rax, [rsp+3E8h+var_380]
0x18002a50a  mov     qword ptr [rsp+3E8h+var_3C8], rax; int
0x18002a50f  lea     rdx, [rsp+3E8h+var_2B8]
0x18002a517  cmp     qword ptr [rsp+3E8h+var_2A8+8], 7
0x18002a520  cmova   rdx, qword ptr [rsp+3E8h+var_2B8]
0x18002a529  lea     rcx, [rsp+3E8h+var_380]
0x18002a52e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a533  mov     r12, rax
0x18002a536  cmp     qword ptr [rbx+18h], 7
0x18002a53b  jbe     short loc_18002A542
0x18002a53d  mov     rdx, [rbx]
0x18002a540  jmp     short loc_18002A545
0x18002a542  mov     rdx, rbx
0x18002a545  lea     rcx, [rsp+3E8h+var_360]
0x18002a54d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a552  nop
0x18002a553  mov     rdx, r12
0x18002a556  mov     rcx, rax
0x18002a559  call    ?IContains@StringHelpers@PrintCore@@SA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IContains(std::wstring,std::wstring)
0x18002a55e  test    al, al
0x18002a560  jz      short loc_18002A59F
0x18002a562  cmp     qword ptr [rbx+18h], 7
0x18002a567  jbe     short loc_18002A56C
0x18002a569  mov     rbx, [rbx]
0x18002a56c  inc     rsi
0x18002a56f  cmp     [rbx+rsi*2], r13w
0x18002a574  jnz     short loc_18002A56C
0x18002a576  mov     r8, rsi
0x18002a579  mov     rdx, rbx
0x18002a57c  lea     rcx, [rsp+3E8h+var_298]
0x18002a584  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002a589  mov     r14b, r13b
0x18002a58c  mov     rcx, [rsp+3E8h]; this
0x18002a594  test    r14b, r14b
0x18002a597  jnz     loc_18002A6D0
0x18002a59d  jmp     short loc_18002A5A8
0x18002a59f  add     rbx, 20h ; ' '
0x18002a5a3  jmp     loc_18002A4DA
0x18002a5a8  mov     rcx, rdi; this
0x18002a5ab  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a5b0  mov     r8, rax
0x18002a5b3  lea     rdx, aCallingVirtual; "Calling VirtualMon helper lib for %ws"
0x18002a5ba  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a5c1  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a5c6  lea     rdx, [rsp+3E8h+var_338]; struct VirtualMon::VirtualPrinterAppInfo *
0x18002a5ce  lea     rcx, [rsp+3E8h+var_E8]; this
0x18002a5d6  call    ??0VirtualPrinterInstaller@VirtualMon@@QEAA@AEBUVirtualPrinterAppInfo@1@@Z; VirtualMon::VirtualPrinterInstaller::VirtualPrinterInstaller(VirtualMon::VirtualPrinterAppInfo const &)
0x18002a5db  nop
0x18002a5dc  lea     rdx, [rsp+3E8h+var_298]; struct VirtualMon::VirtualPrinterInfo *
0x18002a5e4  lea     rcx, [rsp+3E8h+var_E8]; this
0x18002a5ec  call    ?UninstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@QEAAJAEBUVirtualPrinterInfo@2@@Z; VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(VirtualMon::VirtualPrinterInfo const &)
0x18002a5f1  mov     rcx, rdi; this
0x18002a5f4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002a5f9  mov     r8, rax
0x18002a5fc  lea     rdx, aBackFromVirtua; "Back from VirtualMon helper lib for %ws"
0x18002a603  lea     rcx, aWinrtWindowsGr_2; "winrt::Windows::Graphics::Internal::Pri"...
0x18002a60a  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002a60f  nop
0x18002a610  lea     rcx, [rsp+3E8h+var_E8]; this
0x18002a618  call    ??1VirtualPrinterAppInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo(void)
0x18002a61d  nop
0x18002a61e  mov     rcx, qword ptr [rsp+3E8h+var_3B0]
0x18002a623  test    rcx, rcx
0x18002a626  jz      short loc_18002A656
0x18002a628  mov     rdx, qword ptr [rsp+3E8h+var_3B0+8]
0x18002a62d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002a632  mov     rcx, qword ptr [rsp+3E8h+var_3B0]
0x18002a637  mov     rdx, [rsp+3E8h+var_3A0]
0x18002a63c  sub     rdx, rcx
0x18002a63f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002a643  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a648  xorps   xmm0, xmm0
0x18002a64b  movdqu  [rsp+3E8h+var_3B0], xmm0
0x18002a651  mov     [rsp+3E8h+var_3A0], r13
0x18002a656  lea     rcx, [rsp+3E8h+var_108]
0x18002a65e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a663  nop
0x18002a664  lea     rcx, [rsp+3E8h+var_298]; this
0x18002a66c  call    ??1VirtualPrinterInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterInfo::~VirtualPrinterInfo(void)
0x18002a671  nop
0x18002a672  lea     rcx, [rsp+3E8h+var_338]; this
0x18002a67a  call    ??1VirtualPrinterAppInfo@VirtualMon@@QEAA@XZ; VirtualMon::VirtualPrinterAppInfo::~VirtualPrinterAppInfo(void)
0x18002a67f  nop
0x18002a680  lea     rcx, [rsp+3E8h+var_3B8]
0x18002a685  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002a68a  nop
0x18002a68b  lea     rcx, [rsp+3E8h+var_3C0]
0x18002a690  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18002a695  xor     eax, eax
0x18002a697  jmp     short loc_18002A69E
0x18002a699  mov     rax, qword ptr [rsp+3E8h+var_3C8]
0x18002a69e  mov     rcx, [rsp+3E8h+var_48]
0x18002a6a6  xor     rcx, rsp; StackCookie
0x18002a6a9  call    __security_check_cookie
0x18002a6ae  lea     r11, [rsp+3E8h+var_28]
0x18002a6b6  mov     rbx, [r11+38h]
0x18002a6ba  mov     rsi, [r11+40h]
0x18002a6be  movaps  xmm6, xmmword ptr [r11-10h]
0x18002a6c3  mov     rsp, r11
0x18002a6c6  pop     r15
0x18002a6c8  pop     r14
0x18002a6ca  pop     r13
0x18002a6cc  pop     r12
0x18002a6ce  pop     rdi
0x18002a6cf  retn
0x18002a6d0  mov     r9d, 80070490h; char *
0x18002a6d6  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\printscan"...
0x18002a6dd  mov     edx, 0BFh; void *
0x18002a6e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
