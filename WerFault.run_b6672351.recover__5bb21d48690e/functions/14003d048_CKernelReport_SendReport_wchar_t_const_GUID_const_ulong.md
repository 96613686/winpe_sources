# CKernelReport::SendReport(wchar_t const *,_GUID const *,ulong)

- ea: `0x14003d048`
- end: `0x14003da07`
- name: `?SendReport@CKernelReport@@AEAAJPEB_WPEBU_GUID@@K@Z`
- size: `2495`
- prototype: `int(CKernelReport *__hidden this, const wchar_t *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14003bbd4`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x14000ca20`
- `0x14000e420`
- `0x1400125ec`
- `0x1400149e8`
- `0x1400166ec`
- `0x14001e46c`
- `0x140025c44`
- `0x1400372dc`
- `0x14003768c`
- `0x140038d00`
- `0x14003aa8c`
- `0x14003d048`
- `0x14003dc9c`
- `0x140045078`
- `0x140049108`
- `0x14004986c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14003d88f`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14003d88f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003d86e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003d86e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003d854`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003d854`
- `wer!WerReportSubmit` at `0x14003d91a`
- `wer!WerReportSubmit` at `0x14003d91a`
- `wer!WerpSetCallBack` at `0x14003d4fe`
- `wer!WerpSetCallBack` at `0x14003d4fe`
- `wer!WerReportCreate` at `0x14003d2ff`
- `wer!WerReportCreate` at `0x14003d2ff`
- `wer!WerpSetIntegratorReportId` at `0x14003d337`
- `wer!WerpSetIntegratorReportId` at `0x14003d337`
- `wer!WerpAddFile` at `0x14003d58b`
- `wer!WerpAddFile` at `0x14003d667`
- `wer!WerpAddFile` at `0x14003d7b7`
- `wer!WerpAddFile` at `0x14003d8d4`
- `wer!WerpAddFile` at `0x14003d58b`
- `wer!WerpAddFile` at `0x14003d667`
- `wer!WerpAddFile` at `0x14003d7b7`
- `wer!WerpAddFile` at `0x14003d8d4`
- `wer!WerpSetTelemetryKernelParams` at `0x14003d374`
- `wer!WerpSetTelemetryKernelParams` at `0x14003d374`
- `wer!WerpSetIptEnabled` at `0x14003d3b7`
- `wer!WerpSetIptEnabled` at `0x14003d3b7`
- `wer!WerReportCloseHandle` at `0x14003d9ce`
- `wer!WerReportCloseHandle` at `0x14003d9ce`

## string_xrefs

- `0x14003d311`: `WerCreateReport failed`
- `0x14003d944`: `WerCreateReport returned a NULL report handle, failing`
- `0x14003d449`: `WerPluginsInitialize failed`
- `0x14003d4b1`: `WerPluginsInitialize failed`
- `0x14003d460`: `Failed to create the plugins`
- `0x14003d4c8`: `Failed to create the plugins`
- `0x14003d647`: `sysdata.xml`
- `0x14003d6dc`: `Failed to copy minidump path`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::SendReport(CKernelReport *this, const wchar_t *a2, const struct _GUID *a3, int a4)
{
  __int64 v8; // rbx
  __int64 v9; // r15
  WCHAR *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  WCHAR *wzFriendlyEventName; // rax
  WCHAR v14; // r8
  WCHAR *v15; // rcx
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  WCHAR *wzApplicationName; // rax
  WCHAR v19; // r8
  WCHAR *v20; // rcx
  __int64 v21; // rcx
  const wchar_t *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  wchar_t *v25; // rax
  wchar_t v26; // r10
  wchar_t *v27; // rcx
  const wchar_t *v28; // rcx
  wchar_t *v29; // rax
  wchar_t v30; // r8
  wchar_t *v31; // rcx
  HREPORT *v32; // rax
  HRESULT v33; // ebx
  const char *v34; // rax
  __int64 v35; // rdx
  unsigned int v36; // r13d
  int v37; // eax
  int v38; // eax
  int v39; // edx
  HINSTANCE v40; // r9
  int v41; // eax
  int v42; // edx
  HINSTANCE v43; // r9
  int v44; // eax
  int v45; // eax
  char IsEnabled; // al
  int SystemData; // eax
  __int64 v48; // rdx
  int v49; // edx
  __int64 v50; // r8
  const wchar_t *v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  void *v54; // rdx
  int v55; // eax
  wchar_t *v56; // rax
  wint_t v57; // ax
  int v58; // eax
  wchar_t *pdwType; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-E0h]
  LPDWORD pdwTypeb; // [rsp+20h] [rbp-E0h]
  PVOID pvData; // [rsp+28h] [rbp-D8h]
  PVOID pvDataa; // [rsp+28h] [rbp-D8h]
  PVOID pvDatab; // [rsp+28h] [rbp-D8h]
  const char *pcbData; // [rsp+30h] [rbp-D0h]
  char v67[8]; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT hReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *v69; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v70; // [rsp+58h] [rbp-A8h]
  _WORD v71[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v72; // [rsp+70h] [rbp-90h] BYREF
  void *v73; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v74; // [rsp+80h] [rbp-80h]
  _WORD v75[8]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v76[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-48h]
  _QWORD v78[44]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WER_REPORT_INFORMATION pReportInformation; // [rsp+220h] [rbp+120h] BYREF
  char v80; // [rsp+AC0h] [rbp+9C0h] BYREF
  char v81; // [rsp+B40h] [rbp+A40h] BYREF
  __int16 v82; // [rsp+BF0h] [rbp+AF0h] BYREF
  __int128 v83; // [rsp+BF2h] [rbp+AF2h]
  __int128 v84; // [rsp+C02h] [rbp+B02h]
  char v85[80]; // [rsp+C20h] [rbp+B20h] BYREF
  wchar_t Str[264]; // [rsp+C70h] [rbp+B70h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+EC8h] [rbp+DC8h]

  hReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x9C4u);
  memset(v76, 0, sizeof(v76));
  v77 = 0;
  v73 = v75;
  v74 = v75;
  v75[0] = 0;
  memset_0(v78, 0, 0x158u);
  v67[0] = 0;
  v69 = v71;
  v70 = v71;
  v71[0] = 0;
  pReportInformation.dwSize = 2504;
  if ( !a2 )
  {
    v34 = "Invalid params";
    v33 = -2147024809;
    v35 = 1735;
    goto LABEL_94;
  }
  tlx::guid_to_string_lower<wchar_t>(v85, a3);
  LODWORD(pdwType) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x6CD,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendReport",
    (wil::details *)pdwType,
    (int)"Integrator report ID: %ws",
    v85);
  v8 = 2147483646;
  v9 = 128;
  if ( (int)UtilLoadString(&v73, 5, &_ImageBase) >= 0 )
  {
    v10 = (WCHAR *)v73;
    if ( v73 != v74 )
    {
      v11 = 2147483646;
      v12 = 128;
      wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
      do
      {
        if ( !v11 )
          break;
        v14 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *wzFriendlyEventName++ = v14;
        --v11;
        --v12;
      }
      while ( v12 );
      v15 = wzFriendlyEventName - 1;
      if ( v12 )
        v15 = wzFriendlyEventName;
      *v15 = 0;
    }
  }
  if ( (int)UtilLoadString(&v73, 3, &_ImageBase) >= 0 )
  {
    v16 = (WCHAR *)v73;
    if ( v73 != v74 )
    {
      v17 = 2147483646;
      wzApplicationName = pReportInformation.wzApplicationName;
      do
      {
        if ( !v17 )
          break;
        v19 = *v16;
        if ( !*v16 )
          break;
        ++v16;
        *wzApplicationName++ = v19;
        --v17;
        --v9;
      }
      while ( v9 );
      v20 = wzApplicationName - 1;
      if ( v9 )
        v20 = wzApplicationName;
      *v20 = 0;
    }
  }
  v21 = 2147483646;
  v22 = L"windows";
  v23 = 64;
  v24 = 64;
  v25 = (wchar_t *)&v80;
  do
  {
    if ( !v21 )
      break;
    v26 = *v22;
    if ( !*v22 )
      break;
    ++v22;
    *v25++ = v26;
    --v21;
    --v24;
  }
  while ( v24 );
  v27 = v25 - 1;
  if ( v24 )
    v27 = v25;
  *v27 = 0;
  v28 = L"windows8";
  v29 = (wchar_t *)&v81;
  do
  {
    if ( !v8 )
      break;
    v30 = *v28;
    if ( !*v28 )
      break;
    ++v28;
    *v29++ = v30;
    --v8;
    --v23;
  }
  while ( v23 );
  v31 = v29 - 1;
  if ( v23 )
    v31 = v29;
  *v31 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
    (char *)this + 688,
    L"BlueScreen");
  v32 = (HREPORT *)tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long WerReportCloseHandle(void *),0>>(&hReportHandle);
  v33 = WerReportCreate(L"BlueScreen", WerReportKernel, &pReportInformation, v32);
  if ( v33 < 0 )
  {
    v34 = "WerCreateReport failed";
    v35 = 1782;
    goto LABEL_94;
  }
  if ( !hReportHandle )
  {
    v33 = -2147024890;
    v34 = "WerCreateReport returned a NULL report handle, failing";
    v35 = 1788;
    goto LABEL_94;
  }
  v33 = WerpSetIntegratorReportId(hReportHandle, v85);
  if ( v33 < 0 )
  {
    v34 = "WerpSetIntegratorReportId failed";
    v35 = 1799;
    goto LABEL_94;
  }
  v36 = a4 | 0x80000804;
  v37 = WerpSetTelemetryKernelParams(hReportHandle, *((unsigned int *)this + 182), *((unsigned int *)this + 183));
  if ( v37 < 0 )
  {
    LODWORD(pdwType) = v37;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x712,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"WerpSetTelemetryKernelParams failed",
      pcbData);
  }
  v38 = WerpSetIptEnabled(hReportHandle, *((unsigned int *)this + 184));
  if ( v38 < 0 )
  {
    LODWORD(pdwType) = v38;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x71C,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"WerpSetIptEnabled failed",
      pcbData);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl) )
  {
    if ( !UtilIsWinRE() )
    {
      v39 = WerPluginsCreate(L"BlueScreen", (char *)this + 680);
      if ( v39 < 0 )
      {
        LODWORD(pdwType) = v39;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x743,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendReport",
          (wil::details *)pdwType,
          (int)"Failed to create the plugins",
          pcbData);
      }
      else
      {
        v78[0] = L"BlueScreen";
        v41 = WerPluginsInitialize(*((void **)this + 85), (struct WER_PLUGIN_INIT_IN *)v78, v36, v40);
        if ( v41 < 0 )
        {
          LODWORD(pdwType) = v41;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x73B,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::SendReport",
            (wil::details *)pdwType,
            (int)"WerPluginsInitialize failed",
            pcbData);
        }
      }
    }
  }
  else
  {
    v42 = WerPluginsCreate(L"BlueScreen", (char *)this + 680);
    if ( v42 < 0 )
    {
      LODWORD(pdwType) = v42;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x764,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        (wil::details *)pdwType,
        (int)"Failed to create the plugins",
        pcbData);
    }
    else
    {
      v78[0] = L"BlueScreen";
      v44 = WerPluginsInitialize(*((void **)this + 85), (struct WER_PLUGIN_INIT_IN *)v78, v36, v43);
      if ( v44 < 0 )
      {
        LODWORD(pdwType) = v44;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x75C,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::SendReport",
          (wil::details *)pdwType,
          (int)"WerPluginsInitialize failed",
          pcbData);
      }
    }
  }
  WerpSetCallBack(hReportHandle, CKernelReport::Static_WerCallbackFunction, this);
  v33 = CKernelReport::ExtractBugCheckInfo(a2, (struct _BUGCHECK_INFORMATION *)v76);
  if ( v33 < 0 )
  {
    v34 = "ExtractBugCheckInfo failed";
    v35 = 1902;
    goto LABEL_94;
  }
  v45 = CKernelReport::AddBugCheckSignaturesToReport(hReportHandle, L"BlueScreen", (struct _BUGCHECK_INFORMATION *)v76);
  if ( v45 < 0 )
  {
    LODWORD(pdwType) = v45;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x77B,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"AddBugCheckSignaturesToReport failed",
      pcbData);
  }
  pvData = 0;
  pdwType = 0;
  v33 = WerpAddFile(hReportHandle, a2, 2);
  if ( v33 < 0 )
  {
    v34 = "WerAddFile failed";
    v35 = 1927;
    goto LABEL_94;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl);
  if ( !*((_WORD *)this + 64) )
  {
    if ( IsEnabled )
    {
      if ( UtilIsWinRE()
        || (SystemData = CKernelReportDataCollection::GetSystemData(
                           (CKernelReportDataCollection *)v67,
                           (wchar_t *)this + 64),
            SystemData >= 0) )
      {
LABEL_65:
        if ( !*((_WORD *)this + 64) )
          goto LABEL_68;
        goto LABEL_66;
      }
      v48 = 1940;
    }
    else
    {
      SystemData = CKernelReportDataCollection::GetSystemData((CKernelReportDataCollection *)v67, (wchar_t *)this + 64);
      if ( SystemData >= 0 )
        goto LABEL_65;
      v48 = 1952;
    }
    LODWORD(pdwType) = SystemData;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v48,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"GetSystemData failed",
      pcbData);
    goto LABEL_65;
  }
LABEL_66:
  pvData = 0;
  pdwType = L"sysdata.xml";
  v49 = WerpAddFile(hReportHandle, (char *)this + 128, 5);
  if ( v49 < 0 )
  {
    LODWORD(pdwType) = v49;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x7B5,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"WerAddFile failed",
      pcbData);
  }
LABEL_68:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl)
    && UtilIsWinRE() )
  {
    v50 = -1;
    do
      ++v50;
    while ( a2[v50] );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v69,
                             a2) )
    {
      LODWORD(pdwType) = -2147024882;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x7C9,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        (wil::details *)pdwType,
        (int)"Failed to copy minidump path",
        pcbData);
    }
    goto LABEL_82;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 4, v76, &v69, pdwType, pvData) >= 0 )
  {
LABEL_78:
    v54 = v69;
    if ( v69 == v70 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v51, v69, v52, v53);
      v54 = v69;
    }
    v55 = WerpAddFile(hReportHandle, v54, 3);
    if ( v55 < 0 )
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x843,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        (wil::details *)(unsigned int)v55,
        (int)"WerpAddFile failed",
        pcbData);
    goto LABEL_82;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 3, v76, &v69, pdwTypea, pvDataa) >= 0 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AskKernelAcceptFull>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AskKernelAcceptFull>::GetImpl'::`2'::impl);
    v51 = L"full_dump=AskFull;full_dump=AvailableFull;full_dump=Any;fulldump=AskFull;fulldump=AvailableFull;fulldump=Any";
    goto LABEL_78;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 5, v76, &v69, pdwTypeb, pvDatab) >= 0 )
    goto LABEL_78;
LABEL_82:
  v82 = 67;
  v83 = *(_OWORD *)L":\\DumpStack.log";
  v84 = *(_OWORD *)L"ack.log";
  v72 = 520;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
          L"ExistingPageFiles",
          0x20u,
          0,
          Str,
          &v72) )
  {
    v56 = wcschr(Str, 0x3Au);
    if ( v56 )
    {
      if ( v56 > Str )
      {
        v57 = towupper(*(v56 - 1));
        if ( (unsigned __int16)(v57 - 65) <= 0x19u )
          v82 = v57;
      }
    }
  }
  pdwType = L"DumpStack.log";
  v58 = WerpAddFile(hReportHandle, &v82, 5);
  if ( v58 < 0 )
  {
    LODWORD(pdwType) = v58;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x874,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      (wil::details *)pdwType,
      (int)"WerpAddFile(DumpStack.log) failed",
      pcbData);
  }
  v33 = WerReportSubmit(hReportHandle, WerConsentNotAsked, v36, 0);
  if ( v33 >= 0 )
  {
    v33 = 0;
    goto LABEL_95;
  }
  v34 = "WerSubmitReport failed";
  v35 = 2174;
LABEL_94:
  LODWORD(pdwType) = v33;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v35,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendReport",
    (wil::details *)pdwType,
    (int)v34,
    pcbData);
LABEL_95:
  if ( v69 != v71 )
    operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
  if ( v73 != v75 )
    operator delete(v73, (const struct std::nothrow_t *)&std::nothrow);
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x14003d048  mov     [rsp-8+arg_10], rbx
0x14003d04d  push    rbp
0x14003d04e  push    rsi
0x14003d04f  push    rdi
0x14003d050  push    r12
0x14003d052  push    r13
0x14003d054  push    r14
0x14003d056  push    r15
0x14003d058  lea     rbp, [rsp-0D90h]
0x14003d060  sub     rsp, 0E90h
0x14003d067  mov     rax, cs:__security_cookie
0x14003d06e  xor     rax, rsp
0x14003d071  mov     [rbp+0DC0h+var_40], rax
0x14003d078  mov     r13d, r9d
0x14003d07b  mov     rbx, r8
0x14003d07e  mov     r12, rdx
0x14003d081  mov     r14, rcx
0x14003d084  xor     r15d, r15d
0x14003d087  mov     [rsp+0EC0h+hReportHandle], r15
0x14003d08c  xor     edx, edx; Val
0x14003d08e  mov     r8d, 9C4h; Size
0x14003d094  lea     rcx, [rbp+0DC0h+pReportInformation+4]; void *
0x14003d09b  call    memset_0
0x14003d0a0  xorps   xmm0, xmm0
0x14003d0a3  xor     eax, eax
0x14003d0a5  movups  [rbp+0DC0h+var_E28], xmm0
0x14003d0a9  movups  [rbp+0DC0h+var_E18], xmm0
0x14003d0ad  mov     [rbp+0DC0h+var_E08], rax
0x14003d0b1  lea     rax, [rbp+0DC0h+var_E38]
0x14003d0b5  mov     [rsp+0EC0h+var_E48], rax
0x14003d0ba  lea     rax, [rbp+0DC0h+var_E38]
0x14003d0be  mov     [rbp+0DC0h+var_E40], rax
0x14003d0c2  mov     [rbp+0DC0h+var_E38], r15w
0x14003d0c7  xor     edx, edx; Val
0x14003d0c9  mov     r8d, 158h; Size
0x14003d0cf  lea     rcx, [rbp+0DC0h+var_E00]; void *
0x14003d0d3  call    memset_0
0x14003d0d8  mov     [rsp+0EC0h+var_E80], r15b
0x14003d0dd  lea     rax, [rsp+0EC0h+var_E60]
0x14003d0e2  mov     [rsp+0EC0h+var_E70], rax
0x14003d0e7  lea     rax, [rsp+0EC0h+var_E60]
0x14003d0ec  mov     [rsp+0EC0h+var_E68], rax
0x14003d0f1  mov     [rsp+0EC0h+var_E60], r15w
0x14003d0f7  mov     [rbp+0DC0h+pReportInformation.dwSize], 9C8h
0x14003d101  test    r12, r12
0x14003d104  jz      loc_14003D958
0x14003d10a  mov     rdx, rbx
0x14003d10d  lea     rcx, [rbp+0DC0h+var_2A0]
0x14003d114  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x14003d119  mov     rcx, [rbp+0DC8h]; this
0x14003d120  lea     rax, [rbp+0DC0h+var_2A0]
0x14003d127  mov     [rsp+0EC0h+pcbData], rax; char *
0x14003d12c  lea     rax, aIntegratorRepo; "Integrator report ID: %ws"
0x14003d133  mov     [rsp+0EC0h+pvData], rax; int
0x14003d138  mov     dword ptr [rsp+0EC0h+pdwType], 80000000h; wil::details *
0x14003d140  lea     rdi, aCkernelreportS_1; "CKernelReport::SendReport"
0x14003d147  mov     r9, rdi; char *
0x14003d14a  lea     rsi, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003d151  mov     r8, rsi; unsigned int
0x14003d154  mov     edx, 6CDh; void *
0x14003d159  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d15e  lea     r8, __ImageBase
0x14003d165  lea     edx, [r15+5]
0x14003d169  lea     rcx, [rsp+0EC0h+var_E48]
0x14003d16e  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003d173  mov     ebx, 7FFFFFFEh
0x14003d178  mov     r15d, 80h
0x14003d17e  xor     r10d, r10d
0x14003d181  test    eax, eax
0x14003d183  js      short loc_14003D1D0
0x14003d185  mov     rcx, [rsp+0EC0h+var_E48]
0x14003d18a  cmp     rcx, [rbp+0DC0h+var_E40]
0x14003d18e  jz      short loc_14003D1D0
0x14003d190  mov     r9d, ebx
0x14003d193  mov     edx, r15d
0x14003d196  lea     rax, [rbp+0DC0h+pReportInformation.wzFriendlyEventName]
0x14003d19d  test    r9, r9
0x14003d1a0  jz      short loc_14003D1C1
0x14003d1a2  movzx   r8d, word ptr [rcx]
0x14003d1a6  test    r8w, r8w
0x14003d1aa  jz      short loc_14003D1C1
0x14003d1ac  add     rcx, 2
0x14003d1b0  mov     [rax], r8w
0x14003d1b4  add     rax, 2
0x14003d1b8  dec     r9
0x14003d1bb  sub     rdx, 1
0x14003d1bf  jnz     short loc_14003D19D
0x14003d1c1  lea     rcx, [rax-2]
0x14003d1c5  test    rdx, rdx
0x14003d1c8  cmovnz  rcx, rax
0x14003d1cc  mov     [rcx], r10w
0x14003d1d0  lea     r8, __ImageBase
0x14003d1d7  mov     edx, 3
0x14003d1dc  lea     rcx, [rsp+0EC0h+var_E48]
0x14003d1e1  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003d1e6  test    eax, eax
0x14003d1e8  js      short loc_14003D237
0x14003d1ea  mov     rcx, [rsp+0EC0h+var_E48]
0x14003d1ef  cmp     rcx, [rbp+0DC0h+var_E40]
0x14003d1f3  jz      short loc_14003D237
0x14003d1f5  mov     rdx, rbx
0x14003d1f8  lea     rax, [rbp+0DC0h+pReportInformation.wzApplicationName]
0x14003d1ff  test    rdx, rdx
0x14003d202  jz      short loc_14003D223
0x14003d204  movzx   r8d, word ptr [rcx]
0x14003d208  test    r8w, r8w
0x14003d20c  jz      short loc_14003D223
0x14003d20e  add     rcx, 2
0x14003d212  mov     [rax], r8w
0x14003d216  add     rax, 2
0x14003d21a  dec     rdx
0x14003d21d  sub     r15, 1
0x14003d221  jnz     short loc_14003D1FF
0x14003d223  lea     rcx, [rax-2]
0x14003d227  test    r15, r15
0x14003d22a  cmovnz  rcx, rax
0x14003d22e  xor     r15d, r15d
0x14003d231  mov     [rcx], r15w
0x14003d235  jmp     short loc_14003D23A
0x14003d237  xor     r15d, r15d
0x14003d23a  mov     rcx, rbx
0x14003d23d  lea     r9, aWindows; "windows"
0x14003d244  mov     edx, 40h ; '@'
0x14003d249  mov     r8d, edx
0x14003d24c  lea     rax, [rbp+0DC0h+var_400]
0x14003d253  test    rcx, rcx
0x14003d256  jz      short loc_14003D277
0x14003d258  movzx   r10d, word ptr [r9]
0x14003d25c  test    r10w, r10w
0x14003d260  jz      short loc_14003D277
0x14003d262  add     r9, 2
0x14003d266  mov     [rax], r10w
0x14003d26a  add     rax, 2
0x14003d26e  dec     rcx
0x14003d271  sub     r8, 1
0x14003d275  jnz     short loc_14003D253
0x14003d277  lea     rcx, [rax-2]
0x14003d27b  test    r8, r8
0x14003d27e  cmovnz  rcx, rax
0x14003d282  mov     [rcx], r15w
0x14003d286  lea     rcx, aWindows8; "windows8"
0x14003d28d  lea     rax, [rbp+0DC0h+var_380]
0x14003d294  test    rbx, rbx
0x14003d297  jz      short loc_14003D2B8
0x14003d299  movzx   r8d, word ptr [rcx]
0x14003d29d  test    r8w, r8w
0x14003d2a1  jz      short loc_14003D2B8
0x14003d2a3  add     rcx, 2
0x14003d2a7  mov     [rax], r8w
0x14003d2ab  add     rax, 2
0x14003d2af  dec     rbx
0x14003d2b2  sub     rdx, 1
0x14003d2b6  jnz     short loc_14003D294
0x14003d2b8  lea     rcx, [rax-2]
0x14003d2bc  test    rdx, rdx
0x14003d2bf  cmovnz  rcx, rax
0x14003d2c3  mov     [rcx], r15w
0x14003d2c7  lea     rcx, [r14+2B0h]
0x14003d2ce  mov     r8d, 0Ah
0x14003d2d4  lea     rbx, aBluescreen; "BlueScreen"
0x14003d2db  mov     rdx, rbx
0x14003d2de  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003d2e3  lea     rcx, [rsp+0EC0h+hReportHandle]
0x14003d2e8  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerReportCloseHandle@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&WerReportCloseHandle(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&WerReportCloseHandle(void *),0>> &)
0x14003d2ed  mov     r9, rax; phReportHandle
0x14003d2f0  lea     r8, [rbp+0DC0h+pReportInformation]; pReportInformation
0x14003d2f7  mov     edx, 4; repType
0x14003d2fc  mov     rcx, rbx; pwzEventType
0x14003d2ff  call    cs:__imp_WerReportCreate
0x14003d306  nop     dword ptr [rax+rax+00h]
0x14003d30b  mov     ebx, eax
0x14003d30d  test    eax, eax
0x14003d30f  jns     short loc_14003D322
0x14003d311  lea     rax, aWercreaterepor; "WerCreateReport failed"
0x14003d318  mov     edx, 6F6h
0x14003d31d  jmp     loc_14003D950
0x14003d322  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003d327  test    rcx, rcx
0x14003d32a  jz      loc_14003D93F
0x14003d330  lea     rdx, [rbp+0DC0h+var_2A0]
0x14003d337  call    cs:__imp_WerpSetIntegratorReportId
0x14003d33e  nop     dword ptr [rax+rax+00h]
0x14003d343  mov     ebx, eax
0x14003d345  test    eax, eax
0x14003d347  jns     short loc_14003D35A
0x14003d349  lea     rax, aWerpsetintegra; "WerpSetIntegratorReportId failed"
0x14003d350  mov     edx, 707h
0x14003d355  jmp     loc_14003D950
0x14003d35a  or      r13d, 80000804h
0x14003d361  mov     r8d, [r14+2DCh]
0x14003d368  mov     edx, [r14+2D8h]
0x14003d36f  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003d374  call    cs:__imp_WerpSetTelemetryKernelParams
0x14003d37b  nop     dword ptr [rax+rax+00h]
0x14003d380  test    eax, eax
0x14003d382  jns     short loc_14003D3AB
0x14003d384  mov     rcx, [rbp+0DC8h]; this
0x14003d38b  lea     rdx, aWerpsettelemet; "WerpSetTelemetryKernelParams failed"
0x14003d392  mov     [rsp+0EC0h+pvData], rdx; int
0x14003d397  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003d39b  mov     r9, rdi; char *
0x14003d39e  mov     r8, rsi; unsigned int
0x14003d3a1  mov     edx, 712h; void *
0x14003d3a6  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d3ab  mov     edx, [r14+2E0h]
0x14003d3b2  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003d3b7  call    cs:__imp_WerpSetIptEnabled
0x14003d3be  nop     dword ptr [rax+rax+00h]
0x14003d3c3  test    eax, eax
0x14003d3c5  jns     short loc_14003D3EE
0x14003d3c7  mov     rcx, [rbp+0DC8h]; this
0x14003d3ce  lea     rdx, aWerpsetiptenab; "WerpSetIptEnabled failed"
0x14003d3d5  mov     [rsp+0EC0h+pvData], rdx; int
0x14003d3da  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003d3de  mov     r9, rdi; char *
0x14003d3e1  mov     r8, rsi; unsigned int
0x14003d3e4  mov     edx, 71Ch; void *
0x14003d3e9  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d3ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl(void)'::`2'::impl
0x14003d3f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(void)
0x14003d3fa  test    al, al
0x14003d3fc  jz      short loc_14003D477
0x14003d3fe  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x14003d403  test    al, al
0x14003d405  jnz     loc_14003D4EF
0x14003d40b  lea     rbx, [r14+2A8h]
0x14003d412  mov     rdx, rbx
0x14003d415  lea     rcx, aBluescreen; "BlueScreen"
0x14003d41c  call    ?WerPluginsCreate@@YAJPEB_WPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerPluginsDestroy@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; WerPluginsCreate(wchar_t const *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&WerPluginsDestroy(void *),0>> *)
0x14003d421  mov     edx, eax
0x14003d423  test    eax, eax
0x14003d425  js      short loc_14003D460
0x14003d427  lea     rax, aBluescreen; "BlueScreen"
0x14003d42e  mov     [rbp+0DC0h+var_E00], rax
0x14003d432  mov     r8d, r13d; unsigned int
0x14003d435  lea     rdx, [rbp+0DC0h+var_E00]; struct WER_PLUGIN_INIT_IN *
0x14003d439  mov     rcx, [rbx]; void *
0x14003d43c  call    ?WerPluginsInitialize@@YAJPEAXPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z; WerPluginsInitialize(void *,WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)
0x14003d441  test    eax, eax
0x14003d443  jns     loc_14003D4EF
0x14003d449  lea     rdx, aWerpluginsinit; "WerPluginsInitialize failed"
0x14003d450  mov     [rsp+0EC0h+pvData], rdx
0x14003d455  mov     dword ptr [rsp+0EC0h+pdwType], eax
0x14003d459  mov     edx, 73Bh
0x14003d45e  jmp     short loc_14003D4DD
0x14003d460  lea     rax, aFailedToCreate_2; "Failed to create the plugins"
0x14003d467  mov     [rsp+0EC0h+pvData], rax
0x14003d46c  mov     dword ptr [rsp+0EC0h+pdwType], edx
0x14003d470  mov     edx, 743h
0x14003d475  jmp     short loc_14003D4DD
0x14003d477  lea     rbx, [r14+2A8h]
0x14003d47e  mov     rdx, rbx
0x14003d481  lea     rcx, aBluescreen; "BlueScreen"
0x14003d488  call    ?WerPluginsCreate@@YAJPEB_WPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerPluginsDestroy@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; WerPluginsCreate(wchar_t const *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&WerPluginsDestroy(void *),0>> *)
0x14003d48d  mov     edx, eax
0x14003d48f  test    eax, eax
0x14003d491  js      short loc_14003D4C8
0x14003d493  lea     rax, aBluescreen; "BlueScreen"
0x14003d49a  mov     [rbp+0DC0h+var_E00], rax
0x14003d49e  mov     r8d, r13d; unsigned int
0x14003d4a1  lea     rdx, [rbp+0DC0h+var_E00]; struct WER_PLUGIN_INIT_IN *
0x14003d4a5  mov     rcx, [rbx]; void *
0x14003d4a8  call    ?WerPluginsInitialize@@YAJPEAXPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z; WerPluginsInitialize(void *,WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)
0x14003d4ad  test    eax, eax
0x14003d4af  jns     short loc_14003D4EF
0x14003d4b1  lea     rdx, aWerpluginsinit; "WerPluginsInitialize failed"
0x14003d4b8  mov     [rsp+0EC0h+pvData], rdx
0x14003d4bd  mov     dword ptr [rsp+0EC0h+pdwType], eax
0x14003d4c1  mov     edx, 75Ch
0x14003d4c6  jmp     short loc_14003D4DD
0x14003d4c8  lea     rax, aFailedToCreate_2; "Failed to create the plugins"
0x14003d4cf  mov     [rsp+0EC0h+pvData], rax; int
0x14003d4d4  mov     dword ptr [rsp+0EC0h+pdwType], edx; wil::details *
0x14003d4d8  mov     edx, 764h; void *
0x14003d4dd  mov     r9, rdi; char *
0x14003d4e0  mov     r8, rsi; unsigned int
0x14003d4e3  mov     rcx, [rbp+0DC8h]; this
0x14003d4ea  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003d4ef  mov     r8, r14
0x14003d4f2  lea     rdx, ?Static_WerCallbackFunction@CKernelReport@@CAHPEAXQEAU_WER_CALLBACK_INPUT@@@Z; CKernelReport::Static_WerCallbackFunction(void *,_WER_CALLBACK_INPUT * const)
0x14003d4f9  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003d4fe  call    cs:__imp_WerpSetCallBack
0x14003d505  nop     dword ptr [rax+rax+00h]
0x14003d50a  lea     rdx, [rbp+0DC0h+var_E28]; struct _BUGCHECK_INFORMATION *
0x14003d50e  mov     rcx, r12; lpFileName
0x14003d511  call    ?ExtractBugCheckInfo@CKernelReport@@CAJPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::ExtractBugCheckInfo(wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003d516  mov     ebx, eax
0x14003d518  test    eax, eax
0x14003d51a  jns     short loc_14003D52D
0x14003d51c  lea     rax, aExtractbugchec; "ExtractBugCheckInfo failed"
0x14003d523  mov     edx, 76Eh
0x14003d528  jmp     loc_14003D950
0x14003d52d  lea     r8, [rbp+0DC0h+var_E28]; struct _BUGCHECK_INFORMATION *
0x14003d531  lea     rdx, aBluescreen; "BlueScreen"
0x14003d538  mov     rcx, [rsp+0EC0h+hReportHandle]; void *
0x14003d53d  call    ?AddBugCheckSignaturesToReport@CKernelReport@@CAJPEAXPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::AddBugCheckSignaturesToReport(void *,wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003d542  test    eax, eax
0x14003d544  jns     short loc_14003D56D
0x14003d546  mov     rcx, [rbp+0DC8h]; this
0x14003d54d  lea     rdx, aAddbugchecksig; "AddBugCheckSignaturesToReport failed"
  ... truncated ...
```
