# PrintConfig::DrvPrinterEvent(ushort *,int,ulong,__int64,bool *,bool *)

- ea: `0x18001aecc`
- end: `0x18001b6c7`
- name: `?DrvPrinterEvent@PrintConfig@@YAXPEAGHK_JPEA_N2@Z`
- size: `2043`
- prototype: `void __usercall(wchar_t *Str@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, unsigned int@<r9d>, __int64, bool *, bool *)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e7dc`

## callees

- `0x180003310`
- `0x180003b00`
- `0x180004424`
- `0x18000e550`
- `0x18000e83c`
- `0x18000f380`
- `0x18000f770`
- `0x180010efc`
- `0x180011438`
- `0x180015554`
- `0x180015604`
- `0x180015cb0`
- `0x180016da8`
- `0x1800183a0`
- `0x18001878c`
- `0x180018bbc`
- `0x18001aecc`
- `0x18001c33c`
- `0x18001c438`
- `0x180035e18`
- `0x180040894`
- `0x1800421f4`
- `0x180042cfc`
- `0x180042dac`
- `0x18004347c`
- `0x1800436dc`
- `0x180045730`
- `0x180045828`
- `0x180045f4c`
- `0x180046210`
- `0x180049b18`
- `0x180049be0`
- `0x18004ac54`
- `0x18004b448`
- `0x180053468`
- `0x180058498`
- `0x18005c924`
- `0x180152e30`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001af65`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001af65`
- `KERNEL32!ReleaseMutex` at `0x18001b2e3`
- `KERNEL32!ReleaseMutex` at `0x18001b2e3`
- `KERNEL32!CloseHandle` at `0x18001b2f7`
- `KERNEL32!CloseHandle` at `0x18001b2f7`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b0c7`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b0c7`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x18001b119`
- `Print.PrintSupport.Source!IsPsaEnabledForContractAsCurrentUser` at `0x18001b119`

## string_xrefs

- `0x18001b10f`: `Windows.PrintSupportExtension`
- `0x18001b12a`: `printscan\print\drivers\usermode\driverui\dll\printconfig\configevent.cpp`
- `0x18001b055`: `PrintConfig::DrvPrinterEvent`
- `0x18001b064`: `PrintConfig::DrvPrinterEvent`
- `0x18001b0fb`: `PrintConfig::DrvPrinterEvent`
- `0x18001b3b8`: `PrintConfig::DrvPrinterEvent`
- `0x18001b20c`: `DrvPrinterEvent: PRINTER_EVENT_CACHE_DELETE`
- `0x18001b291`: `DrvPrinterEvent: PRINTER_EVENT_CACHE_REFRESH`
- `0x18001b307`: `DrvPrinterEvent: PRINTER_EVENT_DELETE`
- `0x18001b0b7`: `DrvPrinterEvent: PRINTER_EVENT_CONFIGURATION_UPDATE`
- `0x18001b0f4`: `Failed to regenerate the rendering config file.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall PrintConfig::DrvPrinterEvent(
        wchar_t *Str,
        unsigned __int16 *a2,
        int a3,
        OLECHAR *a4,
        PrintConfig::CConfigManager *a5,
        bool *a6)
{
  int v6; // ebx
  bool *v8; // r13
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // edi
  char v13; // si
  void *v14; // rax
  int v15; // eax
  int v16; // edi
  PrintCore *v17; // rax
  int *v18; // r8
  int IsIppOrMpsPrinterCommon; // eax
  int v20; // r15d
  bool v21; // di
  PrintCore *v22; // rax
  int *v23; // r8
  int IsVirtualPrinterCommon; // eax
  int v25; // r12d
  bool v26; // r15
  const wchar_t *v27; // rax
  const wchar_t *v28; // r9
  char v29; // r12
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
  Win32Adapters::Version *v41; // rcx
  PrinterConnection **v42; // rax
  volatile signed __int32 *v43; // rdi
  __int64 v44; // rax
  PrinterConnection *v45; // rbx
  const unsigned __int16 *v46; // rdx
  PrinterConnection **v47; // rax
  int v48; // eax
  int v49; // esi
  int v50; // [rsp+20h] [rbp-60h]
  struct PrintConfig::IPrinterQueueInternal *v51; // [rsp+30h] [rbp-50h] BYREF
  int v52; // [rsp+38h] [rbp-48h] BYREF
  PrintConfig::CConfigManager *v53; // [rsp+40h] [rbp-40h] BYREF
  HANDLE hMutex; // [rsp+48h] [rbp-38h]
  __int64 v55; // [rsp+50h] [rbp-30h] BYREF
  _BYTE pExceptionObject[8]; // [rsp+58h] [rbp-28h] BYREF
  volatile signed __int32 *v57; // [rsp+60h] [rbp-20h]
  __int64 v58; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v60; // [rsp+D0h] [rbp+50h] BYREF
  BSTR pbstr; // [rsp+D8h] [rbp+58h]

  pbstr = a4;
  v60 = a3;
  v58 = -2;
  v6 = (int)a2;
  *(_BYTE *)a5 = 0;
  v8 = a6;
  *a6 = 0;
  LODWORD(a6) = 0;
  v52 = 0;
  v55 = 0;
  v9 = PrintConfig::CPrinterQueue::Create(Str);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        19,
        WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
        (unsigned int)v9);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v10);
    throw (hr_error *)pExceptionObject;
  }
  v51 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct PrintConfig::IPrinterQueueInternal **))v55)(
          v55,
          &GUID_132737be_6991_4586_a599_7b8629364f61,
          &v51);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        20,
        WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
        (unsigned int)v11);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v12);
    throw (hr_error *)pExceptionObject;
  }
  if ( !Str || (v13 = 1, !wcsstr(Str, L"\\\\CSR|")) )
    v13 = 0;
  LOBYTE(v60) = 0;
  v14 = (void *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v51 + 40LL))(v51);
  v15 = IsDriverV4(v14, (bool *)&v60);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        21,
        WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
        (unsigned int)v15);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v16);
    throw (hr_error *)pExceptionObject;
  }
  v17 = (PrintCore *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v51 + 40LL))(v51);
  LODWORD(v53) = 0;
  IsIppOrMpsPrinterCommon = PrintCore::IsIppOrMpsPrinterCommon(v17, &v53, v18);
  v20 = IsIppOrMpsPrinterCommon;
  v21 = (_DWORD)v53 != 0;
  if ( IsIppOrMpsPrinterCommon < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        22,
        WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
        (unsigned int)IsIppOrMpsPrinterCommon);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v20);
    throw (hr_error *)pExceptionObject;
  }
  v22 = (PrintCore *)(*(__int64 (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v51 + 40LL))(v51);
  LODWORD(v53) = 0;
  IsVirtualPrinterCommon = PrintCore::IsVirtualPrinterCommon(v22, &v53, v23);
  v25 = IsVirtualPrinterCommon;
  v26 = (_DWORD)v53 != 0;
  if ( IsVirtualPrinterCommon < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        23,
        WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
        (unsigned int)IsVirtualPrinterCommon);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v25);
    throw (hr_error *)pExceptionObject;
  }
  v27 = L"using Ipp";
  if ( !v21 )
    v27 = &Filename;
  v28 = L"v4";
  v29 = v60;
  if ( !(_BYTE)v60 )
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
    goto LABEL_80;
  }
  v32 = v31 - 2;
  if ( !v32 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_INITIALIZE");
    if ( v13 )
    {
      PrinterConnection::PreInitializeGUIDPrinter(&v51);
      *v8 = 1;
      goto LABEL_80;
    }
    if ( !v29 )
      goto LABEL_80;
    a5 = (PrintConfig::CConfigManager *)operator new(0x80u);
    v39 = (PrintConfig::CConfigManager *)PrintConfig::CConfigManager::CConfigManager((__int64)a5, &v55);
    a5 = v39;
    PrintConfig::CConfigManager::Initialize(v39);
    PrintConfig::CConfigManager::FetchDeviceDocumentFormat(v39, 0);
    PrintConfig::CConfigManager::FetchDeviceConfigData(v39, 0, (int *)&a6, &v52);
    if ( v52 )
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
      v48 = PrintConfig::CConfigManager::FetchAndSaveVirtualPrinterInfo(v39);
      v49 = v48;
      if ( v48 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            24,
            WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
            (unsigned int)v48);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v49);
        throw (hr_error *)pExceptionObject;
      }
    }
    PrintConfig::CConfigManager::InitializeLanguageDatabase(v39);
    PrintConfig::CConfigManager::UpdateDriverConfigAndRenderOptions(v39);
    PrintConfig::CConfigManager::UpdateMergedConfigData(v39);
    PrintConfig::CConfigManager::IncreaseConfigChangeID(v39);
    if ( v21 || v26 )
      PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile((PCWSTR *)v39);
LABEL_77:
    if ( v39 )
    {
      PrintConfig::CConfigManager::~CConfigManager(v39);
      operator delete(v39);
    }
    goto LABEL_80;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_DELETE");
    if ( !v13 )
      goto LABEL_80;
    v47 = (PrinterConnection **)PrinterConnection::CreateFromGUIDPrinter(pExceptionObject, &v51);
    PrinterConnection::OnCacheDelete(*v47);
    goto LABEL_62;
  }
  v34 = v33 - 1;
  if ( !v34 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_CACHE_REFRESH");
    v44 = PrinterConnection::CreateFromConnection(pExceptionObject, &v51);
    v45 = *(PrinterConnection **)v44;
    v46 = (const unsigned __int16 *)(*(_QWORD *)v44 + 8LL);
    if ( *(_QWORD *)(*(_QWORD *)v44 + 32LL) > 7u )
      v46 = *(const unsigned __int16 **)v46;
    ConnectionSynchronizationRAII::ConnectionSynchronizationRAII((ConnectionSynchronizationRAII *)&v53, v46);
    PrinterConnection::OnCacheRefreshSynchronized(v45);
    if ( (_BYTE)v53 && (char *)hMutex - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      ReleaseMutex(hMutex);
    if ( (char *)hMutex - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hMutex);
LABEL_62:
    v43 = v57;
    goto LABEL_51;
  }
  v35 = v34 - 1;
  if ( !v35 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::DrvPrinterEvent",
      L"DrvPrinterEvent: PRINTER_EVENT_CACHE_DELETE");
    if ( Win32Adapters::Version::IsOlderThanWin8(v41) )
      PrintConfig::CPrinterPropertyBag::DeleteUserPropertyBag(v51);
    v42 = (PrinterConnection **)PrinterConnection::CreateFromConnection(&v53, &v51);
    PrinterConnection::OnCacheDelete(*v42);
    goto LABEL_50;
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
    goto LABEL_80;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::DrvPrinterEvent",
    L"DrvPrinterEvent: PRINTER_EVENT_CONFIGURATION_UPDATE");
  if ( !SysStringLen(pbstr) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids, 2147942487LL);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
    throw (hr_error *)pExceptionObject;
  }
  if ( !v13 )
  {
    if ( !v29 )
      goto LABEL_80;
    v53 = (PrintConfig::CConfigManager *)operator new(0x80u);
    v39 = (PrintConfig::CConfigManager *)PrintConfig::CConfigManager::CConfigManager((__int64)v53, &v55);
    v53 = v39;
    PrintConfig::CConfigManager::Initialize(v39);
    PrintConfig::CConfigManager::FetchDeviceDocumentFormat(v39, 0);
    v40 = v21 || v26;
    PrintConfig::CConfigManager::FetchDeviceConfigData(v39, v40, (int *)&a6, &v52);
    if ( v21 )
    {
      PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(v39);
      if ( !PrintConfig::CConfigManager::IsCompressionDisabled(v39) )
        PrintConfig::CConfigManager::FetchAndSaveIppCompression(v39);
    }
    if ( (_DWORD)a6 )
    {
      *(_BYTE *)a5 = 1;
    }
    else if ( v21 || v26 )
    {
      PrintConfig::CConfigManager::SavePrintCapabilitesIfFileNotPresent(v39);
    }
    goto LABEL_77;
  }
  if ( v21 )
  {
    if ( (int)PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(&v51) < 0 )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::DrvPrinterEvent",
        L"Failed to regenerate the rendering config file.");
    LOBYTE(v60) = 0;
    v37 = IsPsaEnabledForContractAsCurrentUser(Str, L"Windows.PrintSupportExtension", &v60);
    if ( v37 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x448,
        (unsigned int)"printscan\\print\\drivers\\usermode\\driverui\\dll\\printconfig\\configevent.cpp",
        (const char *)(unsigned int)v37,
        v50);
    if ( (_BYTE)v60 )
    {
      v38 = (PrinterConnection **)PrinterConnection::CreateFromGUIDPrinter(&v53, &v51);
      PrinterConnection::RefreshPrinterDeviceCapabilites(*v38);
LABEL_50:
      v43 = (volatile signed __int32 *)hMutex;
LABEL_51:
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
          if ( !_InterlockedDecrement(v43 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
        }
      }
    }
  }
LABEL_80:
  if ( v51 )
    (*(void (__fastcall **)(struct PrintConfig::IPrinterQueueInternal *))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
}

```

## disassembly

```asm
0x18001aecc  mov     rax, rsp
0x18001aecf  mov     [rax+20h], r9
0x18001aed3  mov     [rax+18h], r8d
0x18001aed7  push    rbp
0x18001aed8  push    rsi
0x18001aed9  push    rdi
0x18001aeda  push    r12
0x18001aedc  push    r13
0x18001aede  push    r14
0x18001aee0  push    r15
0x18001aee2  mov     rbp, rsp
0x18001aee5  sub     rsp, 80h
0x18001aeec  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18001aef4  mov     [rax+8], rbx
0x18001aef8  mov     ebx, edx
0x18001aefa  mov     r14, rcx
0x18001aefd  xor     r12d, r12d
0x18001af00  mov     rax, [rbp+arg_20]
0x18001af04  mov     [rax], r12b
0x18001af07  mov     r13, [rbp+arg_28]
0x18001af0b  mov     [r13+0], r12b
0x18001af0f  mov     dword ptr [rbp+arg_28], r12d
0x18001af13  mov     [rbp+var_48], r12d
0x18001af17  mov     [rbp+var_30], r12
0x18001af1b  lea     rdx, [rbp+var_30]
0x18001af1f  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x18001af24  mov     edi, eax
0x18001af26  test    eax, eax
0x18001af28  js      loc_18001B4F2
0x18001af2e  mov     [rbp+var_50], r12
0x18001af32  mov     rcx, [rbp+var_30]
0x18001af36  mov     rax, [rcx]
0x18001af39  lea     r8, [rbp+var_50]
0x18001af3d  lea     rdx, _GUID_132737be_6991_4586_a599_7b8629364f61
0x18001af44  mov     rax, [rax]
0x18001af47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af4c  mov     edi, eax
0x18001af4e  test    eax, eax
0x18001af50  js      loc_18001B53F
0x18001af56  test    r14, r14
0x18001af59  jz      short loc_18001AF73
0x18001af5b  lea     rdx, aCsr; "\\\\CSR|"
0x18001af62  mov     rcx, r14; Str
0x18001af65  call    cs:__imp_wcsstr
0x18001af6b  test    rax, rax
0x18001af6e  mov     sil, 1
0x18001af71  jnz     short loc_18001AF76
0x18001af73  mov     sil, r12b
0x18001af76  mov     byte ptr [rbp+arg_10], r12b
0x18001af7a  mov     rcx, [rbp+var_50]
0x18001af7e  mov     rax, [rcx]
0x18001af81  mov     rax, [rax+28h]
0x18001af85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af8a  mov     rcx, rax; void *
0x18001af8d  lea     rdx, [rbp+arg_10]; bool *
0x18001af91  call    ?IsDriverV4@@YAJPEAXPEA_N@Z; IsDriverV4(void *,bool *)
0x18001af96  mov     edi, eax
0x18001af98  test    eax, eax
0x18001af9a  js      loc_18001B58C
0x18001afa0  mov     rcx, [rbp+var_50]
0x18001afa4  mov     rax, [rcx]
0x18001afa7  mov     rax, [rax+28h]
0x18001afab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afb0  mov     dword ptr [rbp+var_40], r12d
0x18001afb4  lea     rdx, [rbp+var_40]; void *
0x18001afb8  mov     rcx, rax; this
0x18001afbb  call    ?IsIppOrMpsPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsIppOrMpsPrinterCommon(void *,int *)
0x18001afc0  mov     r15d, eax
0x18001afc3  cmp     dword ptr [rbp+var_40], r12d
0x18001afc7  setnz   dil
0x18001afcb  test    eax, eax
0x18001afcd  js      loc_18001B5D9
0x18001afd3  mov     rcx, [rbp+var_50]
0x18001afd7  mov     rax, [rcx]
0x18001afda  mov     rax, [rax+28h]
0x18001afde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afe3  mov     dword ptr [rbp+var_40], r12d
0x18001afe7  lea     rdx, [rbp+var_40]; void *
0x18001afeb  mov     rcx, rax; this
0x18001afee  call    ?IsVirtualPrinterCommon@PrintCore@@YAJPEAXPEAH@Z; PrintCore::IsVirtualPrinterCommon(void *,int *)
0x18001aff3  mov     r12d, eax
0x18001aff6  cmp     dword ptr [rbp+var_40], 0
0x18001affa  setnz   r15b
0x18001affe  test    eax, eax
0x18001b000  js      loc_18001B627
0x18001b006  lea     rcx, Filename
0x18001b00d  lea     rax, aUsingIpp; "using Ipp"
0x18001b014  test    dil, dil
0x18001b017  cmovz   rax, rcx
0x18001b01b  lea     r9, aV4; "v4"
0x18001b022  lea     rcx, aV3; "v3"
0x18001b029  mov     r12b, byte ptr [rbp+arg_10]
0x18001b02d  test    r12b, r12b
0x18001b030  cmovz   r9, rcx
0x18001b034  lea     rcx, aLocalPrinter; "local printer"
0x18001b03b  lea     r8, aPrinterConnect; "printer connection"
0x18001b042  test    sil, sil
0x18001b045  cmovz   r8, rcx
0x18001b049  mov     qword ptr [rsp+80h+var_60], rax; int
0x18001b04e  lea     rdx, aDeviceIsAWsWit; "Device is a %ws with a %ws driver %ws"
0x18001b055  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001b05c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b061  sub     ebx, 1
0x18001b064  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001b06b  jz      loc_18001B451
0x18001b071  sub     ebx, 2
0x18001b074  jz      loc_18001B335
0x18001b07a  sub     ebx, 1
0x18001b07d  jz      loc_18001B307
0x18001b083  sub     ebx, 1
0x18001b086  jz      loc_18001B291
0x18001b08c  sub     ebx, 1
0x18001b08f  jz      loc_18001B20C
0x18001b095  sub     ebx, 2
0x18001b098  jz      short loc_18001B0B7
0x18001b09a  cmp     ebx, 1
0x18001b09d  jz      short loc_18001B0AB
0x18001b09f  lea     rdx, aDrvprintereven_6; "DrvPrinterEvent: Unhandled event."
0x18001b0a6  jmp     loc_18001B458
0x18001b0ab  lea     rdx, aDrvprintereven_3; "DrvPrinterEvent: PRINTER_EVENT_ADD_CONN"...
0x18001b0b2  jmp     loc_18001B458
0x18001b0b7  lea     rdx, aDrvprintereven_4; "DrvPrinterEvent: PRINTER_EVENT_CONFIGUR"...
0x18001b0be  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b0c3  mov     rcx, [rbp+pbstr]; pbstr
0x18001b0c7  call    cs:__imp_SysStringLen
0x18001b0cd  test    eax, eax
0x18001b0cf  jz      loc_18001B675
0x18001b0d5  test    sil, sil
0x18001b0d8  jz      loc_18001B161
0x18001b0de  test    dil, dil
0x18001b0e1  jz      loc_18001B45E
0x18001b0e7  lea     rcx, [rbp+var_50]
0x18001b0eb  call    ?RegenerateRenderFilterConfigData@CIppCSRHelper@PrintConfig@@SAJAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b0f0  test    eax, eax
0x18001b0f2  jns     short loc_18001B107
0x18001b0f4  lea     rdx, aFailedToRegene; "Failed to regenerate the rendering conf"...
0x18001b0fb  lea     rcx, aPrintconfigDrv_14; "PrintConfig::DrvPrinterEvent"
0x18001b102  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b107  mov     byte ptr [rbp+arg_10], 0
0x18001b10b  lea     r8, [rbp+arg_10]
0x18001b10f  lea     rdx, aWindowsPrintsu_1; "Windows.PrintSupportExtension"
0x18001b116  mov     rcx, r14
0x18001b119  call    cs:__imp_IsPsaEnabledForContractAsCurrentUser
0x18001b11f  mov     rcx, [rbp+38h]; this
0x18001b123  test    eax, eax
0x18001b125  jns     short loc_18001B13B
0x18001b127  mov     r9d, eax; char *
0x18001b12a  lea     r8, aPrintscanPrint_1; "printscan\\print\\drivers\\usermode\\dr"...
0x18001b131  mov     edx, 448h; void *
0x18001b136  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b13b  cmp     byte ptr [rbp+arg_10], 0
0x18001b13f  jz      loc_18001B45E
0x18001b145  lea     rdx, [rbp+var_50]
0x18001b149  lea     rcx, [rbp+var_40]
0x18001b14d  call    ?CreateFromGUIDPrinter@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b152  nop
0x18001b153  mov     rcx, [rax]; this
0x18001b156  call    ?RefreshPrinterDeviceCapabilites@PrinterConnection@@QEAAXXZ; PrinterConnection::RefreshPrinterDeviceCapabilites(void)
0x18001b15b  nop
0x18001b15c  jmp     loc_18001B241
0x18001b161  test    r12b, r12b
0x18001b164  jz      loc_18001B45E
0x18001b16a  mov     r14d, 80h
0x18001b170  mov     ecx, r14d; Size
0x18001b173  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b178  mov     [rbp+var_40], rax
0x18001b17c  lea     rdx, [rbp+var_30]
0x18001b180  mov     rcx, rax
0x18001b183  call    ??0CConfigManager@PrintConfig@@QEAA@AEBV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CConfigManager::CConfigManager(ATL::CComPtr<IPrinterQueue> const &)
0x18001b188  mov     rbx, rax
0x18001b18b  mov     [rbp+var_40], rax
0x18001b18f  mov     rcx, rax; this
0x18001b192  call    ?Initialize@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::Initialize(void)
0x18001b197  xor     edx, edx; int
0x18001b199  mov     rcx, rbx; this
0x18001b19c  call    ?FetchDeviceDocumentFormat@CConfigManager@PrintConfig@@QEAAXH@Z; PrintConfig::CConfigManager::FetchDeviceDocumentFormat(int)
0x18001b1a1  test    dil, dil
0x18001b1a4  jnz     short loc_18001B1AF
0x18001b1a6  test    r15b, r15b
0x18001b1a9  jnz     short loc_18001B1AF
0x18001b1ab  xor     edx, edx
0x18001b1ad  jmp     short loc_18001B1B4
0x18001b1af  mov     edx, 1; int
0x18001b1b4  lea     r9, [rbp+var_48]; int *
0x18001b1b8  lea     r8, [rbp+arg_28]; int *
0x18001b1bc  mov     rcx, rbx; this
0x18001b1bf  call    ?FetchDeviceConfigData@CConfigManager@PrintConfig@@QEAAXHPEAH0@Z; PrintConfig::CConfigManager::FetchDeviceConfigData(int,int *,int *)
0x18001b1c4  test    dil, dil
0x18001b1c7  jz      short loc_18001B1E5
0x18001b1c9  mov     rcx, rbx; this
0x18001b1cc  call    ?FetchDeviceConfigPrinterAttributes@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(void)
0x18001b1d1  mov     rcx, rbx; this
0x18001b1d4  call    ?IsCompressionDisabled@CConfigManager@PrintConfig@@QEAA_NXZ; PrintConfig::CConfigManager::IsCompressionDisabled(void)
0x18001b1d9  test    al, al
0x18001b1db  jnz     short loc_18001B1E5
0x18001b1dd  mov     rcx, rbx; this
0x18001b1e0  call    ?FetchAndSaveIppCompression@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::FetchAndSaveIppCompression(void)
0x18001b1e5  cmp     dword ptr [rbp+arg_28], 0
0x18001b1e9  jz      short loc_18001B1F4
0x18001b1eb  mov     rax, [rbp+arg_20]
0x18001b1ef  mov     byte ptr [rax], 1
0x18001b1f2  jmp     short loc_18001B207
0x18001b1f4  test    dil, dil
0x18001b1f7  jnz     short loc_18001B1FE
0x18001b1f9  test    r15b, r15b
0x18001b1fc  jz      short loc_18001B207
0x18001b1fe  mov     rcx, rbx; this
0x18001b201  call    ?SavePrintCapabilitesIfFileNotPresent@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::SavePrintCapabilitesIfFileNotPresent(void)
0x18001b206  nop
0x18001b207  jmp     loc_18001B437
0x18001b20c  lea     rdx, aDrvprintereven_2; "DrvPrinterEvent: PRINTER_EVENT_CACHE_DE"...
0x18001b213  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b218  call    ?IsOlderThanWin8@Version@Win32Adapters@@YA_NXZ; Win32Adapters::Version::IsOlderThanWin8(void)
0x18001b21d  test    al, al
0x18001b21f  jz      short loc_18001B22A
0x18001b221  mov     rcx, [rbp+var_50]; struct PrintConfig::IPrinterQueueInternal *
0x18001b225  call    ?DeleteUserPropertyBag@CPrinterPropertyBag@PrintConfig@@SAXPEAUIPrinterQueueInternal@2@@Z; PrintConfig::CPrinterPropertyBag::DeleteUserPropertyBag(PrintConfig::IPrinterQueueInternal *)
0x18001b22a  lea     rdx, [rbp+var_50]
0x18001b22e  lea     rcx, [rbp+var_40]
0x18001b232  call    ?CreateFromConnection@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromConnection(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b237  nop
0x18001b238  mov     rcx, [rax]; this
0x18001b23b  call    ?OnCacheDelete@PrinterConnection@@QEAAXXZ; PrinterConnection::OnCacheDelete(void)
0x18001b240  nop
0x18001b241  mov     rdi, [rbp+hMutex]
0x18001b245  test    rdi, rdi
0x18001b248  jz      loc_18001B45E
0x18001b24e  or      ebx, 0FFFFFFFFh
0x18001b251  mov     eax, ebx
0x18001b253  lock xadd [rdi+8], eax
0x18001b258  add     eax, ebx
0x18001b25a  jnz     loc_18001B45E
0x18001b260  mov     rax, [rdi]
0x18001b263  mov     rcx, rdi
0x18001b266  mov     rax, [rax]
0x18001b269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b26e  mov     eax, ebx
0x18001b270  lock xadd [rdi+0Ch], eax
0x18001b275  add     eax, ebx
0x18001b277  jnz     loc_18001B45E
0x18001b27d  mov     rax, [rdi]
0x18001b280  mov     rcx, rdi
0x18001b283  mov     rax, [rax+8]
0x18001b287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28c  jmp     loc_18001B45E
0x18001b291  lea     rdx, aDrvprintereven_5; "DrvPrinterEvent: PRINTER_EVENT_CACHE_RE"...
0x18001b298  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b29d  lea     rdx, [rbp+var_50]
0x18001b2a1  lea     rcx, [rbp+pExceptionObject]
0x18001b2a5  call    ?CreateFromConnection@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromConnection(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b2aa  nop
0x18001b2ab  mov     rbx, [rax]
0x18001b2ae  lea     rdx, [rbx+8]
0x18001b2b2  cmp     qword ptr [rdx+18h], 7
0x18001b2b7  jbe     short loc_18001B2BC
0x18001b2b9  mov     rdx, [rdx]; unsigned __int16 *
0x18001b2bc  lea     rcx, [rbp+var_40]; this
0x18001b2c0  call    ??0ConnectionSynchronizationRAII@@QEAA@PEBG@Z; ConnectionSynchronizationRAII::ConnectionSynchronizationRAII(ushort const *)
0x18001b2c5  nop
0x18001b2c6  mov     rcx, rbx; this
0x18001b2c9  call    ?OnCacheRefreshSynchronized@PrinterConnection@@AEAAXXZ; PrinterConnection::OnCacheRefreshSynchronized(void)
0x18001b2ce  nop
0x18001b2cf  cmp     byte ptr [rbp+var_40], 0
0x18001b2d3  jz      short loc_18001B2E9
0x18001b2d5  mov     rcx, [rbp+hMutex]; hMutex
0x18001b2d9  lea     rax, [rcx-1]
0x18001b2dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b2e1  ja      short loc_18001B2E9
0x18001b2e3  call    cs:__imp_ReleaseMutex
0x18001b2e9  mov     rcx, [rbp+hMutex]; hObject
0x18001b2ed  lea     rax, [rcx-1]
0x18001b2f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b2f5  ja      short loc_18001B2FE
0x18001b2f7  call    cs:__imp_CloseHandle
0x18001b2fd  nop
0x18001b2fe  mov     rdi, [rbp+var_20]
0x18001b302  jmp     loc_18001B245
0x18001b307  lea     rdx, aDrvprintereven_1; "DrvPrinterEvent: PRINTER_EVENT_DELETE"
0x18001b30e  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b313  test    sil, sil
0x18001b316  jz      loc_18001B45E
0x18001b31c  lea     rdx, [rbp+var_50]
0x18001b320  lea     rcx, [rbp+pExceptionObject]
0x18001b324  call    ?CreateFromGUIDPrinter@PrinterConnection@@SA?AV?$shared_ptr@VPrinterConnection@@@std@@AEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::CreateFromGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b329  nop
0x18001b32a  mov     rcx, [rax]; this
0x18001b32d  call    ?OnCacheDelete@PrinterConnection@@QEAAXXZ; PrinterConnection::OnCacheDelete(void)
0x18001b332  nop
0x18001b333  jmp     short loc_18001B2FE
0x18001b335  lea     rdx, aDrvprintereven_9; "DrvPrinterEvent: PRINTER_EVENT_INITIALI"...
0x18001b33c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b341  test    sil, sil
0x18001b344  jz      short loc_18001B359
0x18001b346  lea     rcx, [rbp+var_50]
0x18001b34a  call    ?PreInitializeGUIDPrinter@PrinterConnection@@SAXAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z; PrinterConnection::PreInitializeGUIDPrinter(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)
0x18001b34f  mov     byte ptr [r13+0], 1
0x18001b354  jmp     loc_18001B45E
0x18001b359  test    r12b, r12b
0x18001b35c  jz      loc_18001B45E
0x18001b362  mov     r14d, 80h
  ... truncated ...
```
