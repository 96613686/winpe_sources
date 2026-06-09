# CKernelReport::SendReport(wchar_t const *,_GUID const *,ulong)

- ea: `0x14003a8fc`
- end: `0x14003b1a3`
- name: `?SendReport@CKernelReport@@AEAAJPEB_WPEBU_GUID@@K@Z`
- size: `2215`
- prototype: `int(CKernelReport *__hidden this, const wchar_t *, const struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400353c0`
- `0x140039614`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x14000c8a0`
- `0x14000e18c`
- `0x140011db4`
- `0x140015b40`
- `0x140024414`
- `0x140034d9c`
- `0x14003510c`
- `0x140036754`
- `0x1400384dc`
- `0x14003a8fc`
- `0x14003b3dc`
- `0x140042250`
- `0x140045ef4`
- `0x140046630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14003b044`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x14003b044`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003b029`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003b029`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003b015`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003b015`
- `wer!WerReportSubmit` at `0x14003b0c3`
- `wer!WerReportSubmit` at `0x14003b0c3`
- `wer!WerpSetCallBack` at `0x14003ad21`
- `wer!WerpSetCallBack` at `0x14003ad21`
- `wer!WerReportCreate` at `0x14003abc0`
- `wer!WerReportCreate` at `0x14003abc0`
- `wer!WerpSetIntegratorReportId` at `0x14003abf2`
- `wer!WerpSetIntegratorReportId` at `0x14003abf2`
- `wer!WerpAddFile` at `0x14003ada8`
- `wer!WerpAddFile` at `0x14003ae44`
- `wer!WerpAddFile` at `0x14003af7e`
- `wer!WerpAddFile` at `0x14003b083`
- `wer!WerpAddFile` at `0x14003ada8`
- `wer!WerpAddFile` at `0x14003ae44`
- `wer!WerpAddFile` at `0x14003af7e`
- `wer!WerpAddFile` at `0x14003b083`
- `wer!WerpSetTelemetryKernelParams` at `0x14003ac29`
- `wer!WerpSetTelemetryKernelParams` at `0x14003ac29`
- `wer!WerpSetIptEnabled` at `0x14003ac66`
- `wer!WerpSetIptEnabled` at `0x14003ac66`
- `wer!WerReportCloseHandle` at `0x14003aba6`
- `wer!WerReportCloseHandle` at `0x14003b171`
- `wer!WerReportCloseHandle` at `0x14003aba6`
- `wer!WerReportCloseHandle` at `0x14003b171`

## string_xrefs

- `0x14003abcc`: `WerCreateReport failed`
- `0x14003b0e7`: `WerCreateReport returned a NULL report handle, failing`
- `0x14003acd8`: `WerPluginsInitialize failed`
- `0x14003aceb`: `Failed to create the plugins`
- `0x14003ae24`: `sysdata.xml`
- `0x14003aea3`: `Failed to copy minidump path`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::SendReport(CKernelReport *this, const wchar_t *a2, const struct _GUID *a3, int a4)
{
  __int64 v8; // rbx
  __int64 v9; // r14
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
  HREPORT v32; // rcx
  HRESULT v33; // ebx
  const char *v34; // rax
  __int64 v35; // rdx
  unsigned int v36; // r13d
  int v37; // eax
  int v38; // eax
  int v39; // eax
  HINSTANCE v40; // r9
  __int64 v41; // rdx
  int v42; // eax
  int SystemData; // eax
  int v44; // edx
  __int64 v45; // r8
  const wchar_t *v46; // rcx
  const wchar_t *v47; // rbx
  char IsEnabled; // al
  void *v49; // rdx
  int v50; // eax
  wchar_t *v51; // rax
  wint_t v52; // ax
  int v53; // eax
  wil::details *pdwType; // [rsp+20h] [rbp-E0h]
  wil::details *pdwTypea; // [rsp+20h] [rbp-E0h]
  const char *pvData; // [rsp+28h] [rbp-D8h]
  const char *pcbData; // [rsp+30h] [rbp-D0h]
  char v59[8]; // [rsp+40h] [rbp-C0h] BYREF
  HREPORT hReportHandle; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v61; // [rsp+50h] [rbp-B0h] BYREF
  void *v62; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v63; // [rsp+60h] [rbp-A0h]
  _WORD v64[8]; // [rsp+68h] [rbp-98h] BYREF
  void *v65; // [rsp+78h] [rbp-88h] BYREF
  _WORD *v66; // [rsp+80h] [rbp-80h]
  _WORD v67[8]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v68[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-48h]
  _QWORD v70[44]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WER_REPORT_INFORMATION pReportInformation; // [rsp+220h] [rbp+120h] BYREF
  char v72; // [rsp+AC0h] [rbp+9C0h] BYREF
  char v73; // [rsp+B40h] [rbp+A40h] BYREF
  __int16 v74; // [rsp+BF0h] [rbp+AF0h] BYREF
  __int128 v75; // [rsp+BF2h] [rbp+AF2h]
  __int128 v76; // [rsp+C02h] [rbp+B02h]
  char v77[80]; // [rsp+C20h] [rbp+B20h] BYREF
  wchar_t Str[264]; // [rsp+C70h] [rbp+B70h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+EC8h] [rbp+DC8h]

  hReportHandle = 0;
  memset_0(&pReportInformation.dwSize + 1, 0, 0x9C4u);
  memset(v68, 0, sizeof(v68));
  v69 = 0;
  v65 = v67;
  v66 = v67;
  v67[0] = 0;
  memset_0(v70, 0, 0x158u);
  v59[0] = 0;
  v62 = v64;
  v63 = v64;
  v64[0] = 0;
  pReportInformation.dwSize = 2504;
  if ( !a2 )
  {
    v34 = "Invalid params";
    v33 = -2147024809;
    v35 = 1747;
    goto LABEL_91;
  }
  tlx::guid_to_string_lower<wchar_t>(v77, a3);
  LODWORD(pdwType) = 0x80000000;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)0x6D9,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendReport",
    pdwType,
    (int)"Integrator report ID: %ws",
    v77);
  v8 = 2147483646;
  v9 = 128;
  if ( (int)UtilLoadString(&v65, 5, &_ImageBase) >= 0 )
  {
    v10 = (WCHAR *)v65;
    if ( v65 != v66 )
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
  if ( (int)UtilLoadString(&v65, 3, &_ImageBase) >= 0 )
  {
    v16 = (WCHAR *)v65;
    if ( v65 != v66 )
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
  v25 = (wchar_t *)&v72;
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
  v29 = (wchar_t *)&v73;
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
    L"BlueScreen",
    10);
  v32 = hReportHandle;
  hReportHandle = 0;
  if ( v32 )
    WerReportCloseHandle(v32);
  v33 = WerReportCreate(L"BlueScreen", WerReportKernel, &pReportInformation, &hReportHandle);
  if ( v33 < 0 )
  {
    v34 = "WerCreateReport failed";
    v35 = 1794;
    goto LABEL_91;
  }
  if ( !hReportHandle )
  {
    v33 = -2147024890;
    v34 = "WerCreateReport returned a NULL report handle, failing";
    v35 = 1800;
    goto LABEL_91;
  }
  v33 = WerpSetIntegratorReportId(hReportHandle, v77);
  if ( v33 < 0 )
  {
    v34 = "WerpSetIntegratorReportId failed";
    v35 = 1811;
    goto LABEL_91;
  }
  v36 = a4 | 0x80000804;
  v37 = WerpSetTelemetryKernelParams(hReportHandle, *((unsigned int *)this + 182), *((unsigned int *)this + 183));
  if ( v37 < 0 )
  {
    LODWORD(pdwType) = v37;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x71E,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      pdwType,
      (int)"WerpSetTelemetryKernelParams failed",
      pcbData);
  }
  v38 = WerpSetIptEnabled(hReportHandle, *((unsigned int *)this + 184));
  if ( v38 < 0 )
  {
    LODWORD(pdwType) = v38;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x728,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      pdwType,
      (int)"WerpSetIptEnabled failed",
      pcbData);
  }
  if ( !UtilIsWinRE() )
  {
    v39 = WerPluginsCreate(L"BlueScreen", (char *)this + 680);
    if ( v39 < 0 )
    {
      pvData = "Failed to create the plugins";
      v41 = 1868;
    }
    else
    {
      v70[0] = L"BlueScreen";
      v39 = WerPluginsInitialize(*((void **)this + 85), (struct WER_PLUGIN_INIT_IN *)v70, v36, v40);
      if ( v39 >= 0 )
        goto LABEL_49;
      pvData = "WerPluginsInitialize failed";
      v41 = 1860;
    }
    LODWORD(pdwType) = v39;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      pdwType,
      (int)pvData,
      pcbData);
  }
LABEL_49:
  WerpSetCallBack(hReportHandle, CKernelReport::Static_WerCallbackFunction, this);
  v33 = CKernelReport::ExtractBugCheckInfo(a2, (struct _BUGCHECK_INFORMATION *)v68);
  if ( v33 < 0 )
  {
    v34 = "ExtractBugCheckInfo failed";
    v35 = 1878;
    goto LABEL_91;
  }
  v42 = CKernelReport::AddBugCheckSignaturesToReport(hReportHandle, L"BlueScreen", (struct _BUGCHECK_INFORMATION *)v68);
  if ( v42 < 0 )
  {
    LODWORD(pdwType) = v42;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x763,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      pdwType,
      (int)"AddBugCheckSignaturesToReport failed",
      pcbData);
  }
  v33 = WerpAddFile(hReportHandle, a2, 2, 262146, 0, 0);
  if ( v33 < 0 )
  {
    v34 = "WerAddFile failed";
    v35 = 1903;
    goto LABEL_91;
  }
  if ( *((_WORD *)this + 64) )
    goto LABEL_60;
  if ( !UtilIsWinRE() )
  {
    SystemData = CKernelReportDataCollection::GetSystemData((CKernelReportDataCollection *)v59, (wchar_t *)this + 64);
    if ( SystemData < 0 )
    {
      LODWORD(pdwType) = SystemData;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x77A,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        pdwType,
        (int)"GetSystemData failed",
        pcbData);
    }
  }
  if ( *((_WORD *)this + 64) )
  {
LABEL_60:
    v44 = WerpAddFile(hReportHandle, (char *)this + 128, 5, 262146, L"sysdata.xml", 0);
    if ( v44 < 0 )
    {
      LODWORD(pdwType) = v44;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x78E,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        pdwType,
        (int)"WerAddFile failed",
        pcbData);
    }
  }
  if ( UtilIsWinRE() )
  {
    v45 = -1;
    do
      ++v45;
    while ( a2[v45] );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v62,
                             a2,
                             v45) )
    {
      LODWORD(pdwType) = -2147024882;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        pdwType,
        (int)"Failed to copy minidump path",
        pcbData);
    }
    goto LABEL_79;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 4, v68, &v62) >= 0 )
  {
    v47 = L"full_dump=AskKernel;full_dump=AvailableKernel;full_dump=Any;fulldump=AskKernel;fulldump=AvailableKernel;fulldump=Any";
LABEL_75:
    v49 = v62;
    if ( v62 == v63 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v46);
      v49 = v62;
    }
    v50 = WerpAddFile(hReportHandle, v49, 3, 671088640, 0, v47);
    if ( v50 < 0 )
    {
      LODWORD(pdwTypea) = v50;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x7E7,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
        "CKernelReport::SendReport",
        pdwTypea,
        (int)"WerpAddFile failed",
        pcbData);
    }
    goto LABEL_79;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 3, v68, &v62) >= 0 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AskKernelAcceptFull>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AskKernelAcceptFull>::GetImpl'::`2'::impl);
    v46 = L"full_dump=AskFull;full_dump=AvailableFull;full_dump=Any;fulldump=AskFull;fulldump=AvailableFull;fulldump=Any";
    v47 = L"full_dump=AskFull;full_dump=AskKernel;full_dump=AvailableFull;full_dump=AvailableKernel;full_dump=Any;fulldump"
           "=AskFull;fulldump=AskKernel;fulldump=AvailableFull;fulldump=AvailableKernel;fulldump=Any";
    if ( !IsEnabled )
      v47 = L"full_dump=AskFull;full_dump=AvailableFull;full_dump=Any;fulldump=AskFull;fulldump=AvailableFull;fulldump=Any";
    goto LABEL_75;
  }
  if ( (int)CKernelReport::GetMatchingDumpFile(*((unsigned int *)this + 180), 5, v68, &v62) >= 0 )
  {
    v47 = L"full_dump=Any;fulldump=Any";
    goto LABEL_75;
  }
LABEL_79:
  v74 = 67;
  v75 = *(_OWORD *)L":\\DumpStack.log";
  v76 = *(_OWORD *)L"ack.log";
  v61 = 520;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
          L"ExistingPageFiles",
          0x20u,
          0,
          Str,
          &v61) )
  {
    v51 = wcschr(Str, 0x3Au);
    if ( v51 )
    {
      if ( v51 > Str )
      {
        v52 = towupper(*(v51 - 1));
        if ( (unsigned __int16)(v52 - 65) <= 0x19u )
          v74 = v52;
      }
    }
  }
  v53 = WerpAddFile(hReportHandle, &v74, 5, 262146, L"DumpStack.log", 0);
  if ( v53 < 0 )
  {
    LODWORD(pdwType) = v53;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x818,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::SendReport",
      pdwType,
      (int)"WerpAddFile(DumpStack.log) failed",
      pcbData);
  }
  v33 = WerReportSubmit(hReportHandle, WerConsentNotAsked, v36, 0);
  if ( v33 >= 0 )
  {
    v33 = 0;
    goto LABEL_92;
  }
  v34 = "WerSubmitReport failed";
  v35 = 2082;
LABEL_91:
  LODWORD(pdwType) = v33;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v35,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::SendReport",
    pdwType,
    (int)v34,
    pcbData);
LABEL_92:
  if ( v62 != v64 )
    operator delete(v62, (const struct std::nothrow_t *)&std::nothrow);
  if ( v65 != v67 )
    operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x14003a8fc  mov     [rsp-8+arg_10], rbx
0x14003a901  push    rbp
0x14003a902  push    rsi
0x14003a903  push    rdi
0x14003a904  push    r12
0x14003a906  push    r13
0x14003a908  push    r14
0x14003a90a  push    r15
0x14003a90c  lea     rbp, [rsp-0D90h]
0x14003a914  sub     rsp, 0E90h
0x14003a91b  mov     rax, cs:__security_cookie
0x14003a922  xor     rax, rsp
0x14003a925  mov     [rbp+0DC0h+var_40], rax
0x14003a92c  mov     r13d, r9d
0x14003a92f  mov     rbx, r8
0x14003a932  mov     r12, rdx
0x14003a935  mov     r15, rcx
0x14003a938  xor     r14d, r14d
0x14003a93b  mov     [rsp+0EC0h+hReportHandle], r14
0x14003a940  xor     edx, edx; Val
0x14003a942  mov     r8d, 9C4h; Size
0x14003a948  lea     rcx, [rbp+0DC0h+pReportInformation+4]; void *
0x14003a94f  call    memset_0
0x14003a954  xorps   xmm0, xmm0
0x14003a957  xor     eax, eax
0x14003a959  movups  [rbp+0DC0h+var_E28], xmm0
0x14003a95d  movups  [rbp+0DC0h+var_E18], xmm0
0x14003a961  mov     [rbp+0DC0h+var_E08], rax
0x14003a965  lea     rax, [rbp+0DC0h+var_E38]
0x14003a969  mov     [rsp+0EC0h+var_E48], rax
0x14003a96e  lea     rax, [rbp+0DC0h+var_E38]
0x14003a972  mov     [rbp+0DC0h+var_E40], rax
0x14003a976  mov     [rbp+0DC0h+var_E38], r14w
0x14003a97b  xor     edx, edx; Val
0x14003a97d  mov     r8d, 158h; Size
0x14003a983  lea     rcx, [rbp+0DC0h+var_E00]; void *
0x14003a987  call    memset_0
0x14003a98c  mov     [rsp+0EC0h+var_E80], r14b
0x14003a991  lea     rax, [rsp+0EC0h+var_E58]
0x14003a996  mov     [rsp+0EC0h+var_E68], rax
0x14003a99b  lea     rax, [rsp+0EC0h+var_E58]
0x14003a9a0  mov     [rsp+0EC0h+var_E60], rax
0x14003a9a5  mov     [rsp+0EC0h+var_E58], r14w
0x14003a9ab  mov     [rbp+0DC0h+pReportInformation.dwSize], 9C8h
0x14003a9b5  test    r12, r12
0x14003a9b8  jz      loc_14003B0FB
0x14003a9be  mov     rdx, rbx
0x14003a9c1  lea     rcx, [rbp+0DC0h+var_2A0]
0x14003a9c8  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x14003a9cd  mov     rcx, [rbp+0DC8h]; this
0x14003a9d4  lea     rax, [rbp+0DC0h+var_2A0]
0x14003a9db  mov     [rsp+0EC0h+pcbData], rax; char *
0x14003a9e0  lea     rax, aIntegratorRepo; "Integrator report ID: %ws"
0x14003a9e7  mov     [rsp+0EC0h+pvData], rax; int
0x14003a9ec  mov     dword ptr [rsp+0EC0h+pdwType], 80000000h; wil::details *
0x14003a9f4  lea     rdi, aCkernelreportS_1; "CKernelReport::SendReport"
0x14003a9fb  mov     r9, rdi; char *
0x14003a9fe  lea     rsi, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003aa05  mov     r8, rsi; unsigned int
0x14003aa08  mov     edx, 6D9h; void *
0x14003aa0d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003aa12  lea     r8, __ImageBase
0x14003aa19  lea     edx, [r14+5]
0x14003aa1d  lea     rcx, [rsp+0EC0h+var_E48]
0x14003aa22  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003aa27  mov     ebx, 7FFFFFFEh
0x14003aa2c  mov     r14d, 80h
0x14003aa32  xor     r10d, r10d
0x14003aa35  test    eax, eax
0x14003aa37  js      short loc_14003AA84
0x14003aa39  mov     rcx, [rsp+0EC0h+var_E48]
0x14003aa3e  cmp     rcx, [rbp+0DC0h+var_E40]
0x14003aa42  jz      short loc_14003AA84
0x14003aa44  mov     r9d, ebx
0x14003aa47  mov     edx, r14d
0x14003aa4a  lea     rax, [rbp+0DC0h+pReportInformation.wzFriendlyEventName]
0x14003aa51  test    r9, r9
0x14003aa54  jz      short loc_14003AA75
0x14003aa56  movzx   r8d, word ptr [rcx]
0x14003aa5a  test    r8w, r8w
0x14003aa5e  jz      short loc_14003AA75
0x14003aa60  add     rcx, 2
0x14003aa64  mov     [rax], r8w
0x14003aa68  add     rax, 2
0x14003aa6c  dec     r9
0x14003aa6f  sub     rdx, 1
0x14003aa73  jnz     short loc_14003AA51
0x14003aa75  lea     rcx, [rax-2]
0x14003aa79  test    rdx, rdx
0x14003aa7c  cmovnz  rcx, rax
0x14003aa80  mov     [rcx], r10w
0x14003aa84  lea     r8, __ImageBase
0x14003aa8b  mov     edx, 3
0x14003aa90  lea     rcx, [rsp+0EC0h+var_E48]
0x14003aa95  call    ?UtilLoadString@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ulong,HINSTANCE__ *)
0x14003aa9a  test    eax, eax
0x14003aa9c  js      short loc_14003AAEB
0x14003aa9e  mov     rcx, [rsp+0EC0h+var_E48]
0x14003aaa3  cmp     rcx, [rbp+0DC0h+var_E40]
0x14003aaa7  jz      short loc_14003AAEB
0x14003aaa9  mov     rdx, rbx
0x14003aaac  lea     rax, [rbp+0DC0h+pReportInformation.wzApplicationName]
0x14003aab3  test    rdx, rdx
0x14003aab6  jz      short loc_14003AAD7
0x14003aab8  movzx   r8d, word ptr [rcx]
0x14003aabc  test    r8w, r8w
0x14003aac0  jz      short loc_14003AAD7
0x14003aac2  add     rcx, 2
0x14003aac6  mov     [rax], r8w
0x14003aaca  add     rax, 2
0x14003aace  dec     rdx
0x14003aad1  sub     r14, 1
0x14003aad5  jnz     short loc_14003AAB3
0x14003aad7  lea     rcx, [rax-2]
0x14003aadb  test    r14, r14
0x14003aade  cmovnz  rcx, rax
0x14003aae2  xor     r14d, r14d
0x14003aae5  mov     [rcx], r14w
0x14003aae9  jmp     short loc_14003AAEE
0x14003aaeb  xor     r14d, r14d
0x14003aaee  mov     rcx, rbx
0x14003aaf1  lea     r9, aWindows; "windows"
0x14003aaf8  mov     edx, 40h ; '@'
0x14003aafd  mov     r8d, edx
0x14003ab00  lea     rax, [rbp+0DC0h+var_400]
0x14003ab07  test    rcx, rcx
0x14003ab0a  jz      short loc_14003AB2B
0x14003ab0c  movzx   r10d, word ptr [r9]
0x14003ab10  test    r10w, r10w
0x14003ab14  jz      short loc_14003AB2B
0x14003ab16  add     r9, 2
0x14003ab1a  mov     [rax], r10w
0x14003ab1e  add     rax, 2
0x14003ab22  dec     rcx
0x14003ab25  sub     r8, 1
0x14003ab29  jnz     short loc_14003AB07
0x14003ab2b  lea     rcx, [rax-2]
0x14003ab2f  test    r8, r8
0x14003ab32  cmovnz  rcx, rax
0x14003ab36  mov     [rcx], r14w
0x14003ab3a  lea     rcx, aWindows8; "windows8"
0x14003ab41  lea     rax, [rbp+0DC0h+var_380]
0x14003ab48  test    rbx, rbx
0x14003ab4b  jz      short loc_14003AB6C
0x14003ab4d  movzx   r8d, word ptr [rcx]
0x14003ab51  test    r8w, r8w
0x14003ab55  jz      short loc_14003AB6C
0x14003ab57  add     rcx, 2
0x14003ab5b  mov     [rax], r8w
0x14003ab5f  add     rax, 2
0x14003ab63  dec     rbx
0x14003ab66  sub     rdx, 1
0x14003ab6a  jnz     short loc_14003AB48
0x14003ab6c  lea     rcx, [rax-2]
0x14003ab70  test    rdx, rdx
0x14003ab73  cmovnz  rcx, rax
0x14003ab77  mov     [rcx], r14w
0x14003ab7b  lea     rcx, [r15+2B0h]
0x14003ab82  mov     r8d, 0Ah
0x14003ab88  lea     rbx, aBluescreen; "BlueScreen"
0x14003ab8f  mov     rdx, rbx
0x14003ab92  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003ab97  mov     rcx, [rsp+0EC0h+hReportHandle]; hReportHandle
0x14003ab9c  mov     [rsp+0EC0h+hReportHandle], r14
0x14003aba1  test    rcx, rcx
0x14003aba4  jz      short loc_14003ABAC
0x14003aba6  call    cs:__imp_WerReportCloseHandle
0x14003abac  lea     r9, [rsp+0EC0h+hReportHandle]; phReportHandle
0x14003abb1  lea     r8, [rbp+0DC0h+pReportInformation]; pReportInformation
0x14003abb8  mov     edx, 4; repType
0x14003abbd  mov     rcx, rbx; pwzEventType
0x14003abc0  call    cs:__imp_WerReportCreate
0x14003abc6  mov     ebx, eax
0x14003abc8  test    eax, eax
0x14003abca  jns     short loc_14003ABDD
0x14003abcc  lea     rax, aWercreaterepor; "WerCreateReport failed"
0x14003abd3  mov     edx, 702h
0x14003abd8  jmp     loc_14003B0F3
0x14003abdd  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003abe2  test    rcx, rcx
0x14003abe5  jz      loc_14003B0E2
0x14003abeb  lea     rdx, [rbp+0DC0h+var_2A0]
0x14003abf2  call    cs:__imp_WerpSetIntegratorReportId
0x14003abf8  mov     ebx, eax
0x14003abfa  test    eax, eax
0x14003abfc  jns     short loc_14003AC0F
0x14003abfe  lea     rax, aWerpsetintegra; "WerpSetIntegratorReportId failed"
0x14003ac05  mov     edx, 713h
0x14003ac0a  jmp     loc_14003B0F3
0x14003ac0f  or      r13d, 80000804h
0x14003ac16  mov     r8d, [r15+2DCh]
0x14003ac1d  mov     edx, [r15+2D8h]
0x14003ac24  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003ac29  call    cs:__imp_WerpSetTelemetryKernelParams
0x14003ac2f  test    eax, eax
0x14003ac31  jns     short loc_14003AC5A
0x14003ac33  mov     rcx, [rbp+0DC8h]; this
0x14003ac3a  lea     rdx, aWerpsettelemet; "WerpSetTelemetryKernelParams failed"
0x14003ac41  mov     [rsp+0EC0h+pvData], rdx; int
0x14003ac46  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003ac4a  mov     r9, rdi; char *
0x14003ac4d  mov     r8, rsi; unsigned int
0x14003ac50  mov     edx, 71Eh; void *
0x14003ac55  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ac5a  mov     edx, [r15+2E0h]
0x14003ac61  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003ac66  call    cs:__imp_WerpSetIptEnabled
0x14003ac6c  test    eax, eax
0x14003ac6e  jns     short loc_14003AC97
0x14003ac70  mov     rcx, [rbp+0DC8h]; this
0x14003ac77  lea     rdx, aWerpsetiptenab; "WerpSetIptEnabled failed"
0x14003ac7e  mov     [rsp+0EC0h+pvData], rdx; int
0x14003ac83  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003ac87  mov     r9, rdi; char *
0x14003ac8a  mov     r8, rsi; unsigned int
0x14003ac8d  mov     edx, 728h; void *
0x14003ac92  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ac97  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x14003ac9c  test    al, al
0x14003ac9e  jnz     short loc_14003AD12
0x14003aca0  lea     rbx, [r15+2A8h]
0x14003aca7  mov     rdx, rbx
0x14003acaa  lea     rcx, aBluescreen; "BlueScreen"
0x14003acb1  call    ?WerPluginsCreate@@YAJPEB_WPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?WerPluginsDestroy@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; WerPluginsCreate(wchar_t const *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&WerPluginsDestroy(void *),0>> *)
0x14003acb6  test    eax, eax
0x14003acb8  js      short loc_14003ACEB
0x14003acba  lea     rax, aBluescreen; "BlueScreen"
0x14003acc1  mov     [rbp+0DC0h+var_E00], rax
0x14003acc5  mov     r8d, r13d; unsigned int
0x14003acc8  lea     rdx, [rbp+0DC0h+var_E00]; struct WER_PLUGIN_INIT_IN *
0x14003accc  mov     rcx, [rbx]; void *
0x14003accf  call    ?WerPluginsInitialize@@YAJPEAXPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z; WerPluginsInitialize(void *,WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)
0x14003acd4  test    eax, eax
0x14003acd6  jns     short loc_14003AD12
0x14003acd8  lea     rdx, aWerpluginsinit; "WerPluginsInitialize failed"
0x14003acdf  mov     [rsp+0EC0h+pvData], rdx
0x14003ace4  mov     edx, 744h
0x14003ace9  jmp     short loc_14003ACFC
0x14003aceb  lea     rdx, aFailedToCreate_2; "Failed to create the plugins"
0x14003acf2  mov     [rsp+0EC0h+pvData], rdx; int
0x14003acf7  mov     edx, 74Ch; void *
0x14003acfc  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003ad00  mov     r9, rdi; char *
0x14003ad03  mov     r8, rsi; unsigned int
0x14003ad06  mov     rcx, [rbp+0DC8h]; this
0x14003ad0d  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ad12  mov     r8, r15
0x14003ad15  lea     rdx, ?Static_WerCallbackFunction@CKernelReport@@CAHPEAXQEAU_WER_CALLBACK_INPUT@@@Z; CKernelReport::Static_WerCallbackFunction(void *,_WER_CALLBACK_INPUT * const)
0x14003ad1c  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003ad21  call    cs:__imp_WerpSetCallBack
0x14003ad27  lea     rdx, [rbp+0DC0h+var_E28]; struct _BUGCHECK_INFORMATION *
0x14003ad2b  mov     rcx, r12; lpFileName
0x14003ad2e  call    ?ExtractBugCheckInfo@CKernelReport@@CAJPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::ExtractBugCheckInfo(wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003ad33  mov     ebx, eax
0x14003ad35  test    eax, eax
0x14003ad37  jns     short loc_14003AD4A
0x14003ad39  lea     rax, aExtractbugchec; "ExtractBugCheckInfo failed"
0x14003ad40  mov     edx, 756h
0x14003ad45  jmp     loc_14003B0F3
0x14003ad4a  lea     r8, [rbp+0DC0h+var_E28]; struct _BUGCHECK_INFORMATION *
0x14003ad4e  lea     rdx, aBluescreen; "BlueScreen"
0x14003ad55  mov     rcx, [rsp+0EC0h+hReportHandle]; void *
0x14003ad5a  call    ?AddBugCheckSignaturesToReport@CKernelReport@@CAJPEAXPEB_WPEAU_BUGCHECK_INFORMATION@@@Z; CKernelReport::AddBugCheckSignaturesToReport(void *,wchar_t const *,_BUGCHECK_INFORMATION *)
0x14003ad5f  test    eax, eax
0x14003ad61  jns     short loc_14003AD8A
0x14003ad63  mov     rcx, [rbp+0DC8h]; this
0x14003ad6a  lea     rdx, aAddbugchecksig; "AddBugCheckSignaturesToReport failed"
0x14003ad71  mov     [rsp+0EC0h+pvData], rdx; int
0x14003ad76  mov     dword ptr [rsp+0EC0h+pdwType], eax; wil::details *
0x14003ad7a  mov     r9, rdi; char *
0x14003ad7d  mov     r8, rsi; unsigned int
0x14003ad80  mov     edx, 763h; void *
0x14003ad85  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ad8a  mov     [rsp+0EC0h+pvData], r14
0x14003ad8f  mov     [rsp+0EC0h+pdwType], r14
0x14003ad94  mov     r9d, 40002h
0x14003ad9a  mov     r8d, 2
0x14003ada0  mov     rdx, r12
0x14003ada3  mov     rcx, [rsp+0EC0h+hReportHandle]
0x14003ada8  call    cs:__imp_WerpAddFile
0x14003adae  mov     ebx, eax
0x14003adb0  test    eax, eax
0x14003adb2  jns     short loc_14003ADC5
0x14003adb4  lea     rax, aWeraddfileFail; "WerAddFile failed"
0x14003adbb  mov     edx, 76Fh
0x14003adc0  jmp     loc_14003B0F3
0x14003adc5  lea     rbx, [r15+80h]
0x14003adcc  cmp     [rbx], r14w
0x14003add0  jnz     short loc_14003AE1F
0x14003add2  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x14003add7  test    al, al
0x14003add9  jnz     short loc_14003AE19
0x14003addb  mov     r8d, 104h; unsigned int
0x14003ade1  mov     rdx, rbx; wchar_t *
0x14003ade4  lea     rcx, [rsp+0EC0h+var_E80]; this
0x14003ade9  call    ?GetSystemData@CKernelReportDataCollection@@QEAAJPEA_WK@Z; CKernelReportDataCollection::GetSystemData(wchar_t *,ulong)
0x14003adee  test    eax, eax
0x14003adf0  jns     short loc_14003AE19
0x14003adf2  mov     rcx, [rbp+0DC8h]; this
0x14003adf9  lea     rdx, aGetsystemdataF; "GetSystemData failed"
  ... truncated ...
```
