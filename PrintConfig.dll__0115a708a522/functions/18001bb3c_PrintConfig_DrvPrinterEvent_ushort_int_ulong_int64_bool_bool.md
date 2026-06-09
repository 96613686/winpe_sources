# PrintConfig::DrvPrinterEvent(ushort *,int,ulong,__int64,bool *,bool *)

- ea: `0x18001bb3c`
- end: `0x18001c35b`
- name: `?DrvPrinterEvent@PrintConfig@@YAXPEAGHK_JPEA_N2@Z`
- size: `2079`
- prototype: `void __fastcall(PrintConfig *this, unsigned __int16 *, int, OLECHAR *, PrintConfig::CConfigManager *, bool *)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fb04`

## callees

- `0x180003430`
- `0x180003c20`
- `0x180004564`
- `0x18000e964`
- `0x18000ec74`
- `0x18000f830`
- `0x18000fc40`
- `0x18001153c`
- `0x180011a7c`
- `0x180015ee8`
- `0x180015fa4`
- `0x180016674`
- `0x1800177b0`
- `0x180018f00`
- `0x1800192fc`
- `0x180019410`
- `0x1800197b4`
- `0x18001bb3c`
- `0x18001d014`
- `0x18001d130`
- `0x180037124`
- `0x1800421b0`
- `0x180043ae0`
- `0x180044628`
- `0x1800446d8`
- `0x180044e04`
- `0x1800450a0`
- `0x180047360`
- `0x18004746c`
- `0x180047c18`
- `0x180047ef4`
- `0x18004b9cc`
- `0x18004ba9c`
- `0x18004cb80`
- `0x18004d3dc`
- `0x180055608`
- `0x18005a810`
- `0x18005eeec`
- `0x180159f9c`
- `0x18015a0d8`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18001bf5a`
- `KERNEL32!ReleaseMutex` at `0x18001bf5a`
- `KERNEL32!CloseHandle` at `0x18001bf74`
- `KERNEL32!CloseHandle` at `0x18001bf74`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bd22`
- `OLEAUT32!__imp_SysStringLen` at `0x18001bd22`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x18001bd7a`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x18001bd7a`

## string_xrefs

- `0x18001bd70`: `Windows.PrintSupportExtension`
- `0x18001bd91`: `printscan\print\drivers\usermode\driverui\dll\printconfig\configevent.cpp`
- `0x18001bcb0`: `PrintConfig::DrvPrinterEvent`
- `0x18001bcbf`: `PrintConfig::DrvPrinterEvent`
- `0x18001bd5c`: `PrintConfig::DrvPrinterEvent`
- `0x18001c03b`: `PrintConfig::DrvPrinterEvent`
- `0x18001be83`: `DrvPrinterEvent: PRINTER_EVENT_CACHE_DELETE`
- `0x18001bf08`: `DrvPrinterEvent: PRINTER_EVENT_CACHE_REFRESH`
- `0x18001bf8a`: `DrvPrinterEvent: PRINTER_EVENT_DELETE`
- `0x18001bd12`: `DrvPrinterEvent: PRINTER_EVENT_CONFIGURATION_UPDATE`
- `0x18001bd55`: `Failed to regenerate the rendering config file.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall PrintConfig::DrvPrinterEvent(
        PrintConfig *this,
        unsigned __int16 *a2,
        int a3,
        OLECHAR *a4,
        PrintConfig::CConfigManager *a5,
        bool *a6)
{
  int v6; // ebx
  bool *v8; // r12
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // edi
  bool v13; // si
  void *v14; // rax
  int v15; // eax
  int v16; // edi
  PrintCore *v17; // rax
  struct _DRIVER_INFO_8W **v18; // r8
  int IsIppOrMpsPrinterCommon; // eax
  int v20; // r14d
  bool v21; // di
  PrintCore *v22; // rax
  struct _DRIVER_INFO_8W **v23; // r8
  int IsVirtualPrinterCommon; // eax
  int v25; // r15d
  bool v26; // r14
  const wchar_t *v27; // rax
  const wchar_t *v28; // r9
  char v29; // r15
  const wchar_t *v30; // r8
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  int v36; // ebx
  int v37; // eax
  PrinterConnection **v38; // rax
  PrintConfig::CConfigManager *v39; // rbx
  BOOL v40; // edx
  __int64 v41; // rdx
  __int64 v42; // r8
  Win32Adapters::Version *v43; // rcx
  struct RegistryHandleRAII *v44; // rdx
  PrinterConnection **v45; // rax
  volatile signed __int32 *pServerName; // rdi
  struct _PRINTER_INFO_4W *v47; // rax
  PrinterConnection *pPrinterName; // rbx
  unsigned __int16 *v49; // rdx
  struct RegistryHandleRAII *v50; // rdx
  PrinterConnection **v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  int v54; // eax
  int v55; // esi
  struct PrintConfig::IPrinterQueueInternal *v56; // [rsp+30h] [rbp-50h] BYREF
  int v57; // [rsp+38h] [rbp-48h] BYREF
  struct _PRINTER_INFO_4W v58; // [rsp+40h] [rbp-40h] BYREF
  struct _PRINTER_INFO_4W pExceptionObject; // [rsp+58h] [rbp-28h] BYREF
  __int64 v60; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v62; // [rsp+D0h] [rbp+50h] BYREF
  BSTR pbstr; // [rsp+D8h] [rbp+58h]

  pbstr = a4;
  v62 = a3;
  v60 = -2;
  v6 = (int)a2;
  *(_BYTE *)a5 = 0;
  v8 = a6;
  *a6 = 0;
  LODWORD(a6) = 0;
  v57 = 0;
  *(_QWORD *)&v58.Attributes = 0;
  v9 = PrintConfig::CPrinterQueue::Create((unsigned __int16 *)this, &v58.Attributes);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x13u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        v9);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v10);
    throw (hr_error *)&pExceptionObject;
  }
  v56 = 0;
  v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct PrintConfig::IPrinterQueueInternal **))&v58.Attributes)(
          *(_QWORD *)&v58.Attributes,
          &GUID_132737be_6991_4586_a599_7b8629364f61,
          &v56);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x14u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        v11);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v12);
    throw (hr_error *)&pExceptionObject;
  }
  v13 = IsGUIDPrinter((const unsigned __int16 *)this);
  LOBYTE(v62) = 0;
  v14 = (void *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v56 + 40LL))(v56);
  v15 = IsDriverV4(v14, (bool *)&v62);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x15u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        v15);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v16);
    throw (hr_error *)&pExceptionObject;
  }
  v17 = (PrintCore *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v56 + 40LL))(v56);
  LODWORD(v58.pPrinterName) = 0;
  IsIppOrMpsPrinterCommon = PrintCore::IsIppOrMpsPrinterCommon(v17, &v58, v18);
  v20 = IsIppOrMpsPrinterCommon;
  v21 = LODWORD(v58.pPrinterName) != 0;
  if ( IsIppOrMpsPrinterCommon < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x16u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        IsIppOrMpsPrinterCommon);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v20);
    throw (hr_error *)&pExceptionObject;
  }
  v22 = (PrintCore *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v56 + 40LL))(v56);
  LODWORD(v58.pPrinterName) = 0;
  IsVirtualPrinterCommon = PrintCore::IsVirtualPrinterCommon(v22, &v58, v23);
  v25 = IsVirtualPrinterCommon;
  v26 = LODWORD(v58.pPrinterName) != 0;
  if ( IsVirtualPrinterCommon < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x17u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        IsVirtualPrinterCommon);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, v25);
    throw (hr_error *)&pExceptionObject;
  }
  v27 = L"using Ipp";
  if ( !v21 )
    v27 = &Filename;
  v28 = L"v4";
  v29 = v62;
  if ( !(_BYTE)v62 )
    v28 = L"v3";
  v30 = L"printer connection";
  if ( !v13 )
    v30 = L"local printer";
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::DrvPrinterEvent",
    L"Device is a %ws with a %ws driver %ws",
    v30,
    v28,
    v27);
  v31 = v6 - 1;
  if ( !v31 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_ADD_CONNECTION");
    goto LABEL_79;
  }
  v32 = v31 - 2;
  if ( !v32 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_INITIALIZE");
    if ( v13 )
    {
      PrinterConnection::PreInitializeGUIDPrinter((Win32Adapters::Version *)&v56);
      *v8 = 1;
      goto LABEL_79;
    }
    if ( !v29 )
      goto LABEL_79;
    a5 = (PrintConfig::CConfigManager *)operator new(0x80u);
    v39 = (PrintConfig::CConfigManager *)PrintConfig::CConfigManager::CConfigManager(
                                           (__int64)a5,
                                           (__int64 *)&v58.Attributes);
    a5 = v39;
    PrintConfig::CConfigManager::Initialize((BSTR *)v39);
    PrintConfig::CConfigManager::FetchDeviceDocumentFormat(v39, 0);
    PrintConfig::CConfigManager::FetchDeviceConfigData(v39, 0, (int *)&a6, &v57);
    if ( v57 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::DrvPrinterEvent",
        L"We are using the default PDC so use the default PDL");
      PrintConfig::CConfigManager::FetchDeviceDocumentFormat(v39, 1);
    }
    if ( v21 )
    {
      PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(v39);
      PrintConfig::CConfigManager::FetchAndSaveIppCompression(v39);
      PrintConfig::CConfigManager::CheckAndSetImageQualityConfig(v39);
    }
    if ( v26 )
    {
      v54 = PrintConfig::CConfigManager::FetchAndSaveVirtualPrinterInfo((HANDLE *)v39);
      v55 = v54;
      if ( v54 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x18u,
            (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
            v54);
        }
        hr_error::hr_error((hr_error *)&pExceptionObject, v55);
        throw (hr_error *)&pExceptionObject;
      }
    }
    PrintConfig::CConfigManager::InitializeLanguageDatabase(v39, v52, v53);
    PrintConfig::CConfigManager::UpdateDriverConfigAndRenderOptions(v39);
    PrintConfig::CConfigManager::UpdateMergedConfigData(v39);
    PrintConfig::CConfigManager::IncreaseConfigChangeID(v39);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl)
      && (v21 || v26) )
    {
      PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile((PCWSTR *)v39);
    }
LABEL_76:
    if ( v39 )
    {
      PrintConfig::CConfigManager::~CConfigManager(v39);
      operator delete(v39);
    }
    goto LABEL_79;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_DELETE");
    if ( !v13 )
      goto LABEL_79;
    v51 = (PrinterConnection **)PrinterConnection::CreateFromGUIDPrinter((__int64)&pExceptionObject, &v56);
    PrinterConnection::OnCacheDelete(*v51);
    goto LABEL_60;
  }
  v34 = v33 - 1;
  if ( !v34 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_CACHE_REFRESH");
    v47 = PrinterConnection::CreateFromConnection(&pExceptionObject, &v56);
    pPrinterName = (PrinterConnection *)v47->pPrinterName;
    v49 = v47->pPrinterName + 4;
    if ( *((_QWORD *)v47->pPrinterName + 4) > 7u )
      v49 = *(unsigned __int16 **)v49;
    ConnectionSynchronizationRAII::ConnectionSynchronizationRAII((ConnectionSynchronizationRAII *)&v58, v49);
    PrinterConnection::OnCacheRefreshSynchronized(pPrinterName, v50);
    if ( LOBYTE(v58.pPrinterName) && (unsigned __int64)v58.pServerName - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      ReleaseMutex(v58.pServerName);
    if ( (unsigned __int64)v58.pServerName - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v58.pServerName);
LABEL_60:
    pServerName = (volatile signed __int32 *)pExceptionObject.pServerName;
    goto LABEL_49;
  }
  v35 = v34 - 1;
  if ( !v35 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_CACHE_DELETE");
    if ( Win32Adapters::Version::IsOlderThanWin8(v43) )
      PrintConfig::CPrinterPropertyBag::DeleteUserPropertyBag(v56, v44);
    v45 = (PrinterConnection **)PrinterConnection::CreateFromConnection(&v58, &v56);
    PrinterConnection::OnCacheDelete(*v45);
    goto LABEL_48;
  }
  v36 = v35 - 2;
  if ( v36 )
  {
    if ( v36 == 1 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::DrvPrinterEvent",
        L"DrvPrinterEvent: PRINTER_EVENT_ADD_CONNECTION_NO_UI");
    else
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::DrvPrinterEvent",
        L"DrvPrinterEvent: Unhandled event.");
    goto LABEL_79;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::DrvPrinterEvent",
    L"DrvPrinterEvent: PRINTER_EVENT_CONFIGURATION_UPDATE");
  if ( !SysStringLen(pbstr) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x19u,
        (const GUID *)WPP_6963ef9f53c4324b1fc29bc7f2c707a9_Traceguids,
        -2147024809);
    }
    hr_error::hr_error((hr_error *)&pExceptionObject, -2147024809);
    throw (hr_error *)&pExceptionObject;
  }
  if ( !v13 )
  {
    if ( !v29 )
      goto LABEL_79;
    v58.pPrinterName = (LPWSTR)operator new(0x80u);
    v39 = (PrintConfig::CConfigManager *)PrintConfig::CConfigManager::CConfigManager(
                                           (__int64)v58.pPrinterName,
                                           (__int64 *)&v58.Attributes);
    v58.pPrinterName = (LPWSTR)v39;
    PrintConfig::CConfigManager::Initialize((BSTR *)v39);
    PrintConfig::CConfigManager::FetchDeviceDocumentFormat(v39, 0);
    v40 = v21 || v26;
    PrintConfig::CConfigManager::FetchDeviceConfigData(v39, v40, (int *)&a6, &v57);
    if ( v21 )
    {
      PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(v39);
      if ( !PrintConfig::CConfigManager::IsCompressionDisabled((HANDLE *)v39) )
        PrintConfig::CConfigManager::FetchAndSaveIppCompression(v39);
    }
    if ( (_DWORD)a6 )
    {
      *(_BYTE *)a5 = 1;
    }
    else if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl)
           && (v21 || v26) )
    {
      PrintConfig::CConfigManager::SavePrintCapabilitesIfFileNotPresent(v39, v41, v42);
    }
    goto LABEL_76;
  }
  if ( v21 )
  {
    if ( (int)PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(&v56) < 0 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::DrvPrinterEvent",
        L"Failed to regenerate the rendering config file.");
    LOBYTE(v62) = 0;
    v37 = IsPsaEnabledForContractAsCurrentUser(this, L"Windows.PrintSupportExtension", &v62);
    if ( v37 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x44B,
        (__int64)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\configevent.cpp",
        (const char *)(unsigned int)v37);
    if ( (_BYTE)v62 )
    {
      v38 = (PrinterConnection **)PrinterConnection::CreateFromGUIDPrinter((__int64)&v58, &v56);
      PrinterConnection::RefreshPrinterDeviceCapabilites(*v38);
LABEL_48:
      pServerName = (volatile signed __int32 *)v58.pServerName;
LABEL_49:
      if ( pServerName )
      {
        if ( _InterlockedExchangeAdd(pServerName + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))pServerName)(pServerName);
          if ( !_InterlockedDecrement(pServerName + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)pServerName + 8LL))(pServerName);
        }
      }
    }
  }
LABEL_79:
  if ( v56 )
    (*(void (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v56 + 16LL))(v56);
  if ( *(_QWORD *)&v58.Attributes )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v58.Attributes + 16LL))(*(_QWORD *)&v58.Attributes);
}

```

## disassembly

```asm
0x18001bb3c  mov     rax, rsp
0x18001bb3f  mov     [rax+20h], r9
0x18001bb43  mov     [rax+18h], r8d
0x18001bb47  push    rbp
0x18001bb48  push    rsi
0x18001bb49  push    rdi
0x18001bb4a  push    r12
0x18001bb4c  push    r13
0x18001bb4e  push    r14
0x18001bb50  push    r15
0x18001bb52  mov     rbp, rsp
0x18001bb55  sub     rsp, 80h
0x18001bb5c  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18001bb64  mov     [rax+8], rbx
0x18001bb68  mov     ebx, edx
0x18001bb6a  mov     r13, rcx
0x18001bb6d  xor     r15d, r15d
0x18001bb70  mov     rax, [rbp+arg_20]
0x18001bb74  mov     [rax], r15b
0x18001bb77  mov     r12, [rbp+arg_28]
0x18001bb7b  mov     [r12], r15b
0x18001bb7f  mov     dword ptr [rbp+arg_28], r15d
0x18001bb83  mov     [rbp+var_48], r15d
0x18001bb87  mov     [rbp+var_30], r15
0x18001bb8b  lea     rdx, [rbp+var_30]
0x18001bb8f  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x18001bb94  mov     edi, eax
0x18001bb96  test    eax, eax
0x18001bb98  js      loc_18001C186
0x18001bb9e  mov     [rbp+var_50], r15
0x18001bba2  mov     rcx, [rbp+var_30]
0x18001bba6  mov     rax, [rcx]
0x18001bba9  lea     r8, [rbp+var_50]
0x18001bbad  lea     rdx, _GUID_132737be_6991_4586_a599_7b8629364f61
0x18001bbb4  mov     rax, [rax]
0x18001bbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbbc  mov     edi, eax
0x18001bbbe  test    eax, eax
0x18001bbc0  js      loc_18001C1D3
0x18001bbc6  mov     rcx, r13; unsigned __int16 *
0x18001bbc9  call    ?IsGUIDPrinter@@YA_NPEBG@Z; IsGUIDPrinter(ushort const *)
0x18001bbce  mov     sil, al
0x18001bbd1  mov     byte ptr [rbp+arg_10], r15b
0x18001bbd5  mov     rcx, [rbp+var_50]
0x18001bbd9  mov     rdx, [rcx]
0x18001bbdc  mov     rax, [rdx+28h]
0x18001bbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbe5  mov     rcx, rax; void *
0x18001bbe8  lea     rdx, [rbp+arg_10]; bool *
0x18001bbec  call    ?IsDriverV4@@YAJPEAXPEA_N@Z; IsDriverV4(void *,bool *)
0x18001bbf1  mov     edi, eax
0x18001bbf3  test    eax, eax
0x18001bbf5  js      loc_18001C220
0x18001bbfb  mov     rcx, [rbp+var_50]
0x18001bbff  mov     rax, [rcx]
0x18001bc02  mov     rax, [rax+28h]
0x18001bc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc0b  mov     dword ptr [rbp+var_40], r15d
0x18001bc0f  lea     rdx, [rbp+var_40]; void *
0x18001bc13  mov     rcx, rax; this
0x18001bc16  call    ?IsIppOrMpsPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsPrinterCommon(void *,int *)
0x18001bc1b  mov     r14d, eax
0x18001bc1e  cmp     dword ptr [rbp+var_40], r15d
0x18001bc22  setnz   dil
0x18001bc26  test    eax, eax
0x18001bc28  js      loc_18001C26D
0x18001bc2e  mov     rcx, [rbp+var_50]
0x18001bc32  mov     rax, [rcx]
0x18001bc35  mov     rax, [rax+28h]
0x18001bc39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc3e  mov     dword ptr [rbp+var_40], r15d
0x18001bc42  lea     rdx, [rbp+var_40]; void *
0x18001bc46  mov     rcx, rax; this
0x18001bc49  call    ?IsVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsVirtualPrinterCommon(void *,int *)
0x18001bc4e  mov     r15d, eax
0x18001bc51  cmp     dword ptr [rbp+var_40], 0
0x18001bc55  setnz   r14b
0x18001bc59  test    eax, eax
0x18001bc5b  js      loc_18001C2BB
0x18001bc61  lea     rcx, Filename
0x18001bc68  lea     rax, aUsingIpp; "using Ipp"
0x18001bc6f  test    dil, dil
0x18001bc72  cmovz   rax, rcx
0x18001bc76  lea     r9, aV4; "v4"
0x18001bc7d  lea     rcx, aV3; "v3"
0x18001bc84  mov     r15b, byte ptr [rbp+arg_10]
0x18001bc88  test    r15b, r15b
0x18001bc8b  cmovz   r9, rcx
0x18001bc8f  lea     rcx, aLocalPrinter; "local printer"
0x18001bc96  lea     r8, aPrinterConnect; "printer connection"
0x18001bc9d  test    sil, sil
0x18001bca0  cmovz   r8, rcx
0x18001bca4  mov     qword ptr [rsp+80h+var_60], rax; int
0x18001bca9  lea     rdx, aDeviceIsAWsWit; "Device is a %ws with a %ws driver %ws"
0x18001bcb0  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001bcb7  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bcbc  sub     ebx, 1
0x18001bcbf  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001bcc6  jz      loc_18001C0E4
0x18001bccc  sub     ebx, 2
0x18001bccf  jz      loc_18001BFB8
0x18001bcd5  sub     ebx, 1
0x18001bcd8  jz      loc_18001BF8A
0x18001bcde  sub     ebx, 1
0x18001bce1  jz      loc_18001BF08
0x18001bce7  sub     ebx, 1
0x18001bcea  jz      loc_18001BE83
0x18001bcf0  sub     ebx, 2
0x18001bcf3  jz      short loc_18001BD12
0x18001bcf5  cmp     ebx, 1
0x18001bcf8  jz      short loc_18001BD06
0x18001bcfa  lea     rdx, aDrvprintereven_6; "DrvPrinterEvent: Unhandled event."
0x18001bd01  jmp     loc_18001C0EB
0x18001bd06  lea     rdx, aDrvprintereven_3; "DrvPrinterEvent: PRINTER_EVENT_ADD_CONN"...
0x18001bd0d  jmp     loc_18001C0EB
0x18001bd12  lea     rdx, aDrvprintereven_4; "DrvPrinterEvent: PRINTER_EVENT_CONFIGUR"...
0x18001bd19  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bd1e  mov     rcx, [rbp+pbstr]; pbstr
0x18001bd22  call    cs:__imp_SysStringLen
0x18001bd29  nop     dword ptr [rax+rax+00h]
0x18001bd2e  test    eax, eax
0x18001bd30  jz      loc_18001C309
0x18001bd36  test    sil, sil
0x18001bd39  jz      loc_18001BDC8
0x18001bd3f  test    dil, dil
0x18001bd42  jz      loc_18001C0F1
0x18001bd48  lea     rcx, [rbp+var_50]
0x18001bd4c  call    ?RegenerateRenderFilterConfigData@CIppCSRHelper@PrintConfig@@SAJAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001bd51  test    eax, eax
0x18001bd53  jns     short loc_18001BD68
0x18001bd55  lea     rdx, aFailedToRegene; "Failed to regenerate the rendering conf"...
0x18001bd5c  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001bd63  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bd68  mov     byte ptr [rbp+arg_10], 0
0x18001bd6c  lea     r8, [rbp+arg_10]
0x18001bd70  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18001bd77  mov     rcx, r13
0x18001bd7a  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x18001bd81  nop     dword ptr [rax+rax+00h]
0x18001bd86  mov     rcx, [rbp+38h]; this
0x18001bd8a  test    eax, eax
0x18001bd8c  jns     short loc_18001BDA2
0x18001bd8e  mov     r9d, eax; char *
0x18001bd91  lea     r8, aPrintscanPrint_1; "printscan\\print\\drivers\\usermode\\dr"...
0x18001bd98  mov     edx, 44Bh; void *
0x18001bd9d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bda2  cmp     byte ptr [rbp+arg_10], 0
0x18001bda6  jz      loc_18001C0F1
0x18001bdac  lea     rdx, [rbp+var_50]
0x18001bdb0  lea     rcx, [rbp+var_40]
0x18001bdb4  call    ?CreateFromGUIDPrinter@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001bdb9  nop
0x18001bdba  mov     rcx, [rax]; this
0x18001bdbd  call    ?RefreshPrinterDeviceCapabilites@PrinterConnection@@QEAAXXZ; PrinterConnection::RefreshPrinterDeviceCapabilites(void)
0x18001bdc2  nop
0x18001bdc3  jmp     loc_18001BEB8
0x18001bdc8  test    r15b, r15b
0x18001bdcb  jz      loc_18001C0F1
0x18001bdd1  mov     r15d, 80h
0x18001bdd7  mov     ecx, r15d; Size
0x18001bdda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bddf  mov     [rbp+var_40], rax
0x18001bde3  lea     rdx, [rbp+var_30]
0x18001bde7  mov     rcx, rax
0x18001bdea  call    ??0CConfigManager@PrintConfig@@QEAA@AEBV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CConfigManager::CConfigManager(ATL::CComPtr<IPrinterQueue> const &)
0x18001bdef  mov     rbx, rax
0x18001bdf2  mov     [rbp+var_40], rax
0x18001bdf6  mov     rcx, rax; this
0x18001bdf9  call    ?Initialize@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::Initialize(void)
0x18001bdfe  xor     edx, edx; int
0x18001be00  mov     rcx, rbx; this
0x18001be03  call    ?FetchDeviceDocumentFormat@CConfigManager@PrintConfig@@QEAAXH@Z; PrintConfig::CConfigManager::FetchDeviceDocumentFormat(int)
0x18001be08  test    dil, dil
0x18001be0b  jnz     short loc_18001BE16
0x18001be0d  test    r14b, r14b
0x18001be10  jnz     short loc_18001BE16
0x18001be12  xor     edx, edx
0x18001be14  jmp     short loc_18001BE1B
0x18001be16  mov     edx, 1; int
0x18001be1b  lea     r9, [rbp+var_48]; int *
0x18001be1f  lea     r8, [rbp+arg_28]; int *
0x18001be23  mov     rcx, rbx; this
0x18001be26  call    ?FetchDeviceConfigData@CConfigManager@PrintConfig@@QEAAXHPEAH0@Z; PrintConfig::CConfigManager::FetchDeviceConfigData(int,int *,int *)
0x18001be2b  test    dil, dil
0x18001be2e  jz      short loc_18001BE4C
0x18001be30  mov     rcx, rbx; this
0x18001be33  call    ?FetchDeviceConfigPrinterAttributes@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(void)
0x18001be38  mov     rcx, rbx; this
0x18001be3b  call    ?IsCompressionDisabled@CConfigManager@PrintConfig@@QEAA_NXZ; PrintConfig::CConfigManager::IsCompressionDisabled(void)
0x18001be40  test    al, al
0x18001be42  jnz     short loc_18001BE4C
0x18001be44  mov     rcx, rbx; this
0x18001be47  call    ?FetchAndSaveIppCompression@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::FetchAndSaveIppCompression(void)
0x18001be4c  cmp     dword ptr [rbp+arg_28], 0
0x18001be50  jz      short loc_18001BE5B
0x18001be52  mov     rax, [rbp+arg_20]
0x18001be56  mov     byte ptr [rax], 1
0x18001be59  jmp     short loc_18001BE7E
0x18001be5b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505> `wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl(void)'::`2'::impl
0x18001be62  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled(void)
0x18001be67  test    al, al
0x18001be69  jz      short loc_18001BE7E
0x18001be6b  test    dil, dil
0x18001be6e  jnz     short loc_18001BE75
0x18001be70  test    r14b, r14b
0x18001be73  jz      short loc_18001BE7E
0x18001be75  mov     rcx, rbx; this
0x18001be78  call    ?SavePrintCapabilitesIfFileNotPresent@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::SavePrintCapabilitesIfFileNotPresent(void)
0x18001be7d  nop
0x18001be7e  jmp     loc_18001C0CA
0x18001be83  lea     rdx, aDrvprintereven_2; "DrvPrinterEvent: PRINTER_EVENT_CACHE_DE"...
0x18001be8a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001be8f  call    ?IsOlderThanWin8@Version@Win32Adapters@@YA_NXZ; Win32Adapters::Version::IsOlderThanWin8(void)
0x18001be94  test    al, al
0x18001be96  jz      short loc_18001BEA1
0x18001be98  mov     rcx, [rbp+var_50]; struct PrintConfig::IPrinterQueueInternal *
0x18001be9c  call    ?DeleteUserPropertyBag@CPrinterPropertyBag@PrintConfig@@SAXPEAUIPrinterQueueInternal@2@@Z; PrintConfig::CPrinterPropertyBag::DeleteUserPropertyBag(PrintConfig::IPrinterQueueInternal *)
0x18001bea1  lea     rdx, [rbp+var_50]
0x18001bea5  lea     rcx, [rbp+var_40]
0x18001bea9  call    ?CreateFromConnection@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromConnection(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001beae  nop
0x18001beaf  mov     rcx, [rax]; this
0x18001beb2  call    ?OnCacheDelete@PrinterConnection@@QEAAXXZ; PrinterConnection::OnCacheDelete(void)
0x18001beb7  nop
0x18001beb8  mov     rdi, [rbp+hMutex]
0x18001bebc  test    rdi, rdi
0x18001bebf  jz      loc_18001C0F1
0x18001bec5  or      ebx, 0FFFFFFFFh
0x18001bec8  mov     eax, ebx
0x18001beca  lock xadd [rdi+8], eax
0x18001becf  add     eax, ebx
0x18001bed1  jnz     loc_18001C0F1
0x18001bed7  mov     rax, [rdi]
0x18001beda  mov     rcx, rdi
0x18001bedd  mov     rax, [rax]
0x18001bee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bee5  mov     eax, ebx
0x18001bee7  lock xadd [rdi+0Ch], eax
0x18001beec  add     eax, ebx
0x18001beee  jnz     loc_18001C0F1
0x18001bef4  mov     rax, [rdi]
0x18001bef7  mov     rcx, rdi
0x18001befa  mov     rax, [rax+8]
0x18001befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf03  jmp     loc_18001C0F1
0x18001bf08  lea     rdx, aDrvprintereven_5; "DrvPrinterEvent: PRINTER_EVENT_CACHE_RE"...
0x18001bf0f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bf14  lea     rdx, [rbp+var_50]
0x18001bf18  lea     rcx, [rbp+pExceptionObject]
0x18001bf1c  call    ?CreateFromConnection@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromConnection(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001bf21  nop
0x18001bf22  mov     rbx, [rax]
0x18001bf25  lea     rdx, [rbx+8]
0x18001bf29  cmp     qword ptr [rdx+18h], 7
0x18001bf2e  jbe     short loc_18001BF33
0x18001bf30  mov     rdx, [rdx]; unsigned __int16 *
0x18001bf33  lea     rcx, [rbp+var_40]; this
0x18001bf37  call    ??0ConnectionSynchronizationRAII@@QEAA@PEBG@Z; ConnectionSynchronizationRAII::ConnectionSynchronizationRAII(ushort const *)
0x18001bf3c  nop
0x18001bf3d  mov     rcx, rbx; this
0x18001bf40  call    ?OnCacheRefreshSynchronized@PrinterConnection@@AEAAXXZ; PrinterConnection::OnCacheRefreshSynchronized(void)
0x18001bf45  nop
0x18001bf46  cmp     byte ptr [rbp+var_40], 0
0x18001bf4a  jz      short loc_18001BF66
0x18001bf4c  mov     rcx, [rbp+hMutex]; hMutex
0x18001bf50  lea     rax, [rcx-1]
0x18001bf54  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bf58  ja      short loc_18001BF66
0x18001bf5a  call    cs:__imp_ReleaseMutex
0x18001bf61  nop     dword ptr [rax+rax+00h]
0x18001bf66  mov     rcx, [rbp+hMutex]; hObject
0x18001bf6a  lea     rax, [rcx-1]
0x18001bf6e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001bf72  ja      short loc_18001BF81
0x18001bf74  call    cs:__imp_CloseHandle
0x18001bf7b  nop     dword ptr [rax+rax+00h]
0x18001bf80  nop
0x18001bf81  mov     rdi, [rbp+var_20]
0x18001bf85  jmp     loc_18001BEBC
0x18001bf8a  lea     rdx, aDrvprintereven_1; "DrvPrinterEvent: PRINTER_EVENT_DELETE"
0x18001bf91  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bf96  test    sil, sil
0x18001bf99  jz      loc_18001C0F1
0x18001bf9f  lea     rdx, [rbp+var_50]
0x18001bfa3  lea     rcx, [rbp+pExceptionObject]
0x18001bfa7  call    ?CreateFromGUIDPrinter@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001bfac  nop
0x18001bfad  mov     rcx, [rax]; this
0x18001bfb0  call    ?OnCacheDelete@PrinterConnection@@QEAAXXZ; PrinterConnection::OnCacheDelete(void)
0x18001bfb5  nop
0x18001bfb6  jmp     short loc_18001BF81
0x18001bfb8  lea     rdx, aDrvprintereven_9; "DrvPrinterEvent: PRINTER_EVENT_INITIALI"...
0x18001bfbf  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001bfc4  test    sil, sil
0x18001bfc7  jz      short loc_18001BFDC
0x18001bfc9  lea     rcx, [rbp+var_50]
0x18001bfcd  call    ?PreInitializeGUIDPrinter@PrinterConnection@@SAXAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::PreInitializeGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001bfd2  mov     byte ptr [r12], 1
0x18001bfd7  jmp     loc_18001C0F1
0x18001bfdc  test    r15b, r15b
  ... truncated ...
```
