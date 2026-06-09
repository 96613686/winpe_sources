# Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences(HWND__ *,void *,ushort const *,ulong,_devicemodeW *,ulong,_devicemodeW *,ulong,ulong)

- ea: `0x18005bfc0`
- end: `0x18005d2a7`
- name: `?InvokePrinterExtensionForPrintPreferences@PrinterDriverWinSpool@Config@Driver@Print@@UEAAJPEAUHWND__@@PEAXPEBGKPEAU_devicemodeW@@K3KK@Z`
- size: `4839`
- prototype: `__int64 __fastcall(Print::Driver::Config::PrinterDriverWinSpool *this, HWND, PrintConfig *, OLECHAR *, unsigned int, struct _devicemodeW *, unsigned int DestinationSize, struct _devicemodeW *, unsigned int, DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000d538`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800109e8`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180032da0`
- `0x180033598`
- `0x180033624`
- `0x180036f2c`
- `0x180055608`
- `0x18005b194`
- `0x18005b690`
- `0x18005bfc0`
- `0x18005de98`
- `0x18009b148`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005c608`
- `KERNEL32!GetLastError` at `0x18005c608`
- `KERNEL32!MultiByteToWideChar` at `0x18005c5e4`
- `KERNEL32!MultiByteToWideChar` at `0x18005c5e4`
- `KERNEL32!GlobalSize` at `0x18005c545`
- `KERNEL32!GlobalSize` at `0x18005c545`
- `KERNEL32!GlobalLock` at `0x18005c5bd`
- `KERNEL32!GlobalLock` at `0x18005c5bd`
- `KERNEL32!GlobalUnlock` at `0x18005c5fc`
- `KERNEL32!GlobalUnlock` at `0x18005c656`
- `KERNEL32!GlobalUnlock` at `0x18005c5fc`
- `KERNEL32!GlobalUnlock` at `0x18005c656`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c6b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18005c6b9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005c631`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005c631`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c321`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ca6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ca9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005caad`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cad7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cb74`
- `OLEAUT32!__imp_SysFreeString` at `0x18005c321`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ca6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ca9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005caad`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cad7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cb74`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c8a9`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c970`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c8a9`
- `OLEAUT32!__imp_SysStringLen` at `0x18005c970`
- `ole32!CoCreateInstance` at `0x18005c79e`
- `ole32!CoCreateInstance` at `0x18005c79e`
- `ole32!CreateStreamOnHGlobal` at `0x18005c44e`
- `ole32!CreateStreamOnHGlobal` at `0x18005c44e`
- `ole32!CoSetProxyBlanket` at `0x18005c7e1`
- `ole32!CoSetProxyBlanket` at `0x18005c7e1`
- `ole32!GetHGlobalFromStream` at `0x18005c527`
- `ole32!GetHGlobalFromStream` at `0x18005c527`
- `ole32!CoInitializeEx` at `0x18005c186`
- `ole32!CoInitializeEx` at `0x18005c186`
- `ole32!CoUninitialize` at `0x18005c3a4`
- `ole32!CoUninitialize` at `0x18005c3a4`

## string_xrefs

- `0x18005c33b`: `Pre-condition failure for IHV extension: 0x%x`
- `0x18005c30c`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005c342`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005c872`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005cc04`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005cffe`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005cbfd`: `Extension returned: 0x%x %ws.`
- `0x18005c86b`: `IHV extension returned 0x%x.`
- `0x18005cff7`: `IPrinterExtensionServerInternal::RaiseExtensionEvent returned 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=29 #try_helpers=1
__int64 __fastcall Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences(
        Print::Driver::Config::PrinterDriverWinSpool *this,
        HWND a2,
        PrintConfig *a3,
        OLECHAR *a4,
        unsigned int a5,
        struct _devicemodeW *a6,
        unsigned int DestinationSize,
        struct _devicemodeW *a8,
        unsigned int a9,
        DWORD dwProcessId)
{
  struct _devicemodeW *v11; // r8
  PrintConfig::CPageImageableSize *v12; // rcx
  USHORT v13; // dx
  _BOOL8 v15; // rcx
  void **v16; // r9
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  int v20; // ebx
  int v21; // eax
  int v22; // ebx
  Win32Adapters::Guid *v23; // rax
  struct _GUID *v24; // r8
  int v25; // eax
  HRESULT v26; // eax
  struct PrintConfig::IPrintTicketService **v27; // r8
  int v28; // ebx
  int DefaultPrintTicketService; // eax
  int v30; // ebx
  struct PrintConfig::IPrintTicketService *v31; // rdi
  int v32; // ebx
  int v33; // r14d
  int v34; // eax
  HRESULT HGlobalFromStream; // eax
  int v36; // ebx
  int v37; // eax
  int v38; // ebx
  unsigned int cchWideChar; // edi
  BSTR lpWideCharStr; // rbx
  const CHAR *v41; // rax
  signed int LastError; // eax
  Print::Driver *v43; // rcx
  void **v44; // r9
  signed int v45; // edi
  int v46; // eax
  int v47; // edi
  int v48; // r8d
  OLECHAR *v49; // rdi
  int v50; // eax
  int v51; // r14d
  HRESULT Instance; // eax
  int v53; // r14d
  HRESULT v54; // eax
  int v55; // r14d
  int v56; // eax
  int v57; // r14d
  bool v58; // zf
  int v59; // r14d
  int v60; // eax
  int v61; // r14d
  int v62; // eax
  int v63; // r14d
  int v64; // eax
  int v65; // r14d
  LPSTREAM v66; // r14
  HRESULT (__stdcall *Write)(IStream *, const void *, ULONG, ULONG *); // rsi
  UINT v68; // eax
  int v69; // eax
  int v70; // esi
  int v71; // eax
  int v72; // esi
  int v73; // eax
  int v74; // esi
  int dwCapabilities; // [rsp+38h] [rbp-6D0h]
  int v76; // [rsp+60h] [rbp-6A8h]
  bool v77; // [rsp+64h] [rbp-6A4h]
  unsigned int SourceSize; // [rsp+68h] [rbp-6A0h] BYREF
  __int16 SourceSize_4; // [rsp+6Ch] [rbp-69Ch] BYREF
  LPSTREAM ppstm; // [rsp+70h] [rbp-698h] BYREF
  int v81; // [rsp+78h] [rbp-690h] BYREF
  HWND v82; // [rsp+80h] [rbp-688h] BYREF
  OLECHAR *psz; // [rsp+88h] [rbp-680h]
  struct _GUID bstrString; // [rsp+90h] [rbp-678h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp-668h] BYREF
  struct _GUID v86; // [rsp+A8h] [rbp-660h] BYREF
  struct PrintConfig::IPrintTicketService *v87; // [rsp+B8h] [rbp-650h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-648h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-640h] BYREF
  OLECHAR *v90; // [rsp+D0h] [rbp-638h]
  GUID v91; // [rsp+E0h] [rbp-628h] BYREF
  void *Destination; // [rsp+F0h] [rbp-618h]
  BSTR v93; // [rsp+F8h] [rbp-610h] BYREF
  __int128 Source; // [rsp+100h] [rbp-608h] BYREF
  __int128 v95; // [rsp+110h] [rbp-5F8h] BYREF
  __int128 *p_Source; // [rsp+120h] [rbp-5E8h]
  GUID *v97; // [rsp+128h] [rbp-5E0h]
  struct _devicemodeW *v98; // [rsp+130h] [rbp-5D8h]
  const hr_error *v99; // [rsp+138h] [rbp-5D0h] BYREF
  const PrintCore::WindowsError *v100[4]; // [rsp+140h] [rbp-5C8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+160h] [rbp-5A8h] BYREF
  _BYTE v102[32]; // [rsp+180h] [rbp-588h] BYREF
  _BYTE v103[32]; // [rsp+1A0h] [rbp-568h] BYREF
  _BYTE v104[32]; // [rsp+1C0h] [rbp-548h] BYREF
  _BYTE v105[32]; // [rsp+1E0h] [rbp-528h] BYREF
  _BYTE v106[32]; // [rsp+200h] [rbp-508h] BYREF
  _BYTE v107[32]; // [rsp+220h] [rbp-4E8h] BYREF
  _BYTE v108[32]; // [rsp+240h] [rbp-4C8h] BYREF
  _BYTE v109[32]; // [rsp+260h] [rbp-4A8h] BYREF
  _BYTE v110[32]; // [rsp+280h] [rbp-488h] BYREF
  _BYTE v111[32]; // [rsp+2A0h] [rbp-468h] BYREF
  _BYTE v112[32]; // [rsp+2C0h] [rbp-448h] BYREF
  _BYTE v113[32]; // [rsp+2E0h] [rbp-428h] BYREF
  _BYTE v114[32]; // [rsp+300h] [rbp-408h] BYREF
  _BYTE v115[32]; // [rsp+320h] [rbp-3E8h] BYREF
  _BYTE v116[32]; // [rsp+340h] [rbp-3C8h] BYREF
  _BYTE v117[32]; // [rsp+360h] [rbp-3A8h] BYREF
  _BYTE v118[32]; // [rsp+380h] [rbp-388h] BYREF
  _BYTE v119[32]; // [rsp+3A0h] [rbp-368h] BYREF
  _BYTE v120[32]; // [rsp+3C0h] [rbp-348h] BYREF
  _BYTE v121[32]; // [rsp+3E0h] [rbp-328h] BYREF
  _BYTE v122[32]; // [rsp+400h] [rbp-308h] BYREF
  BSTR v123[4]; // [rsp+420h] [rbp-2E8h] BYREF
  __int128 v124; // [rsp+440h] [rbp-2C8h] BYREF
  unsigned __int16 v125[8]; // [rsp+450h] [rbp-2B8h] BYREF
  _BYTE v126[16]; // [rsp+460h] [rbp-2A8h] BYREF
  int cbMultiByte; // [rsp+470h] [rbp-298h]
  WCHAR Filename[264]; // [rsp+4B0h] [rbp-258h] BYREF

  v100[1] = (const PrintCore::WindowsError *)-2LL;
  psz = a4;
  v82 = a2;
  *(_QWORD *)&v91.Data1 = a2;
  *(_QWORD *)&Source = a3;
  v90 = a4;
  v98 = a6;
  v11 = a8;
  Destination = a8;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xAu, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids);
    v12 = WPP_GLOBAL_Control;
    a4 = psz;
    a2 = v82;
    v11 = (struct _devicemodeW *)Destination;
  }
  if ( !a3 )
  {
    if ( v12 == (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control || (*((_DWORD *)v12 + 17) & 0x100) == 0 )
      return 2147942487LL;
    v13 = 11;
LABEL_12:
    WPP_SF_sd(*((_QWORD *)v12 + 7), v13, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, "POINTER", -2147024809);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    if ( v12 == (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control || (*((_DWORD *)v12 + 17) & 0x100) == 0 )
      return 2147942487LL;
    v13 = 12;
    goto LABEL_12;
  }
  if ( !v11 )
  {
    if ( v12 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
      WPP_SF_sd(*((_QWORD *)v12 + 7), 0xDu, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, "POINTER", -2147024774);
    return 2147942522LL;
  }
  v76 = 0;
  if ( v12 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_qqSDqDqDD(
      *((_QWORD *)v12 + 7),
      (__int64)a2,
      (__int64)v11,
      a2,
      a3,
      a4,
      a5,
      a6,
      DestinationSize,
      v11,
      a9,
      dwProcessId);
  v15 = CoInitializeEx(0, 0) >= 0;
  v77 = v15;
  *(_QWORD *)&v86.Data1 = 0;
  v89 = 0;
  v88 = 0;
  v17 = Print::Driver::CreateInstanceInternal(
          (Print::Driver *)v15,
          (struct IUnknown *)&GUID_4f27786b_13a2_4df5_857c_3eea48d4839b,
          &v86,
          v16);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xFu, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v17);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v18);
    throw (hr_error *)pExceptionObject;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v86.Data1 + 32LL))(*(_QWORD *)&v86.Data1) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x10u,
        &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        -2147220503);
    }
    hr_error::hr_error((hr_error *)v102, -2147220503);
    throw (hr_error *)v102;
  }
  v19 = PrintConfig::CPrinterQueue::Create(psz, &v89);
  v20 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x11u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v19);
    }
    hr_error::hr_error((hr_error *)v103, v20);
    throw (hr_error *)v103;
  }
  v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v89)(
          v89,
          &GUID_132737be_6991_4586_a599_7b8629364f61,
          &v88);
  v22 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x12u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v21);
    }
    hr_error::hr_error((hr_error *)v104, v22);
    throw (hr_error *)v104;
  }
  *(_OWORD *)v125 = 0;
  v23 = (Win32Adapters::Guid *)(*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v88 + 24LL))(v88, v123);
  if ( *((_QWORD *)v23 + 3) > 7u )
    v23 = *(Win32Adapters::Guid **)v23;
  Win32Adapters::Guid::GuidFromString(v23, (UUID *)v125, v24);
  std::wstring::~wstring((char **)v123);
  v124 = 0;
  *(_QWORD *)&bstrString.Data1 = 0;
  *(_OWORD *)v123 = PRINTER_EXTENSION_REASON_PRINT_PREFERENCES;
  v95 = *(_OWORD *)v125;
  v25 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, BSTR *, __int128 *, struct _GUID *))(**(_QWORD **)&v86.Data1
                                                                                          + 24LL))(
          *(_QWORD *)&v86.Data1,
          &v95,
          v123,
          &v124,
          &bstrString);
  if ( v25 < 0 )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences",
      L"Pre-condition failure of PRINT_DRIVER_ERROR_IHV_UI_NOT_REGISTERED not set there may be pending registrations. hr=0x%x",
      (unsigned int)v25);
  SysFreeString(*(BSTR *)&bstrString.Data1);
  pbstr = 0;
  v81 = -2147418113;
  v93 = 0;
  ppstm = 0;
  v26 = CreateStreamOnHGlobal(0, 1, &ppstm);
  try
  {
    v28 = v26;
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x13u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v26);
      }
      hr_error::hr_error((hr_error *)v105, v28);
      throw (hr_error *)v105;
    }
    v87 = 0;
    DefaultPrintTicketService = PrintConfig::GetDefaultPrintTicketService(a3, &v87, v27);
    v30 = DefaultPrintTicketService;
    if ( DefaultPrintTicketService < 0 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x14u,
          &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
          DefaultPrintTicketService);
      }
      hr_error::hr_error((hr_error *)v106, v30);
      throw (hr_error *)v106;
    }
    v31 = v87;
    SourceSize = 0;
    v32 = (*(__int64 (__fastcall **)(struct PrintConfig::IPrintTicketService *, OLECHAR *, __int64, __int64, unsigned int *))(*(_QWORD *)v87 + 32LL))(
            v87,
            psz,
            1,
            1,
            &SourceSize);
    if ( v32 >= 0 )
    {
      v33 = (*(__int64 (__fastcall **)(struct PrintConfig::IPrintTicketService *, _QWORD, struct _devicemodeW *, __int64, LPSTREAM))(*(_QWORD *)v31 + 48LL))(
              v31,
              a5,
              a6,
              2,
              ppstm);
      v34 = (*(__int64 (__fastcall **)(struct PrintConfig::IPrintTicketService *))(*(_QWORD *)v31 + 80LL))(v31);
      v32 = v34;
      if ( v33 < 0 )
      {
        v32 = v33;
      }
      else if ( v34 >= 0 )
      {
        *(_QWORD *)bstrString.Data4 = 0;
        HGlobalFromStream = GetHGlobalFromStream(ppstm, (HGLOBAL *)bstrString.Data4);
        v36 = HGlobalFromStream;
        if ( HGlobalFromStream < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              0x16u,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              HGlobalFromStream);
          }
          hr_error::hr_error((hr_error *)v107, v36);
          throw (hr_error *)v107;
        }
        GlobalSize(*(HGLOBAL *)bstrString.Data4);
        memset_0(v126, 0, 0x50u);
        v37 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v126, 1);
        v38 = v37;
        if ( v37 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x17u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v37);
          }
          hr_error::hr_error((hr_error *)v108, v38);
          throw (hr_error *)v108;
        }
        cchWideChar = cbMultiByte + 1;
        if ( cbMultiByte == -1 )
        {
          lpWideCharStr = 0;
          *(_QWORD *)&v124 = 0;
        }
        else
        {
          lpWideCharStr = SysAllocStringLen(0, cchWideChar);
          *(_QWORD *)&v124 = lpWideCharStr;
          if ( !lpWideCharStr )
            ATL::AtlThrowImpl(-2147024882);
        }
        memset_0(lpWideCharStr, 0, 2LL * cchWideChar);
        v41 = (const CHAR *)GlobalLock(*(HGLOBAL *)bstrString.Data4);
        if ( MultiByteToWideChar(0xFDE9u, 0, v41, cbMultiByte, lpWideCharStr, cchWideChar) )
        {
          GlobalUnlock(*(HGLOBAL *)bstrString.Data4);
        }
        else
        {
          GlobalUnlock(*(HGLOBAL *)bstrString.Data4);
          LastError = GetLastError();
          v45 = LastError;
          if ( LastError > 0 )
            v45 = (unsigned __int16)LastError | 0x80070000;
          if ( v45 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x18u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v45);
            }
            hr_error::hr_error((hr_error *)v109, v45);
            throw (hr_error *)v109;
          }
        }
        *(_QWORD *)&bstrString.Data1 = 0;
        v46 = Print::Driver::CreateInstanceInternal(
                v43,
                (struct IUnknown *)&GUID_1837e65f_36f7_4343_a50c_d76754c31573,
                &bstrString,
                v44);
        v47 = v46;
        if ( v46 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x19u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v46);
          }
          hr_error::hr_error((hr_error *)v110, v47);
          throw (hr_error *)v110;
        }
        memset_0(Filename, 0, 0x20Au);
        Print::Driver::Config::PrinterDriverWinSpool::ConvertPidToProcessName(dwProcessId, Filename, v48);
        v49 = SysAllocString(psz);
        *(_QWORD *)v125 = v49;
        if ( !v49 )
          ATL::AtlThrowImpl(-2147024882);
        v123[0] = 0;
        v91 = GUID_NULL;
        Source = PRINTER_EXTENSION_REASON_PRINT_PREFERENCES;
        LOBYTE(dwCapabilities) = (a9 & 0x40000000) == 0;
        v50 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int128 *, BSTR, BSTR *, WCHAR *, GUID *, int, HWND))(**(_QWORD **)&bstrString.Data1 + 48LL))(
                *(_QWORD *)&bstrString.Data1,
                v49,
                &Source,
                lpWideCharStr,
                v123,
                Filename,
                &v91,
                dwCapabilities,
                v82);
        v51 = v50;
        if ( v50 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x1Au, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v50);
          }
          hr_error::hr_error((hr_error *)v111, v51);
          throw (hr_error *)v111;
        }
        *(_QWORD *)v86.Data4 = 0;
        Instance = CoCreateInstance(
                     &GUID_854a20fb_2d44_457d_992f_ef13785d2b51,
                     0,
                     4u,
                     &GUID_839bcd19_fadc_4673_9d5a_fe970b507fa3,
                     (LPVOID *)v86.Data4);
        v53 = Instance;
        if ( Instance < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              0x1Bu,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              Instance);
          }
          hr_error::hr_error((hr_error *)v112, v53);
          throw (hr_error *)v112;
        }
        v54 = CoSetProxyBlanket(
                *(IUnknown **)v86.Data4,
                0xFFFFFFFF,
                0xFFFFFFFF,
                (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                0,
                3u,
                (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                0x800u);
        v55 = v54;
        if ( v54 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x1Cu, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v54);
          }
          hr_error::hr_error((hr_error *)v113, v55);
          throw (hr_error *)v113;
        }
        v91 = (GUID)PRINTER_EXTENSION_REASON_PRINT_PREFERENCES;
        v56 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, GUID *, BSTR, BSTR *, int *, BSTR *))(**(_QWORD **)v86.Data4
                                                                                                + 40LL))(
                *(_QWORD *)v86.Data4,
                v49,
                &v91,
                v123[0],
                &pbstr,
                &v81,
                &v93);
        v57 = v56;
        if ( v56 < 0 )
        {
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences",
            L"IPrinterExtensionServerInternal::RaiseExtensionEvent returned 0x%x.",
            (unsigned int)v56);
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x1Du, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v57);
          }
          hr_error::hr_error((hr_error *)v114, v57);
          throw (hr_error *)v114;
        }
        v58 = v81 == 0;
        if ( v81 < 0 )
        {
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences",
            L"IHV extension returned 0x%x.",
            (unsigned int)v56);
          v59 = v81;
          v58 = v81 == 0;
          if ( v81 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x1Eu,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v81);
            }
            hr_error::hr_error((hr_error *)v115, v59);
            throw (hr_error *)v115;
          }
        }
        if ( v58 )
        {
          SourceSize_4 = -257;
          HIDWORD(v90) = 0;
          LODWORD(v90) = 2 * SysStringLen(pbstr) + 2;
          *(_QWORD *)&v95 = 0;
          v60 = ((__int64 (__fastcall *)(LPSTREAM, OLECHAR *))ppstm->lpVtbl->SetSize)(ppstm, v90);
          v61 = v60;
          if ( v60 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x1Fu,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v60);
            }
            hr_error::hr_error((hr_error *)v116, v61);
            throw (hr_error *)v116;
          }
          v62 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v95, 0, 0);
          v63 = v62;
          if ( v62 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x20u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v62);
            }
            hr_error::hr_error((hr_error *)v117, v63);
            throw (hr_error *)v117;
          }
          LODWORD(v82) = 0;
          v64 = ((__int64 (__fastcall *)(LPSTREAM, __int16 *, __int64, HWND *))ppstm->lpVtbl->Write)(
                  ppstm,
                  &SourceSize_4,
                  2,
                  &v82);
          v65 = v64;
          if ( v64 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x21u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v64);
            }
            hr_error::hr_error((hr_error *)v118, v65);
            throw (hr_error *)v118;
          }
          LODWORD(v82) = 0;
          v66 = ppstm;
          Write = ppstm->lpVtbl->Write;
          v68 = SysStringLen(pbstr);
          v69 = ((__int64 (__fastcall *)(LPSTREAM, BSTR, _QWORD, HWND *))Write)(v66, pbstr, 2 * v68, &v82);
          v70 = v69;
          if ( v69 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x22u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v69);
            }
            hr_error::hr_error((hr_error *)v119, v70);
            throw (hr_error *)v119;
          }
          v71 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, v95, 0, 0);
          v72 = v71;
          if ( v71 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x23u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v71);
            }
            hr_error::hr_error((hr_error *)v120, v72);
            throw (hr_error *)v120;
          }
          SourceSize = 0;
          *(_QWORD *)&Source = 0;
          *(_QWORD *)&v91.Data1 = 0;
          *(_QWORD *)&v95 = &ppstm;
          *((_QWORD *)&v95 + 1) = &SourceSize;
          p_Source = &Source;
          v97 = &v91;
          v73 = PrintConfig::WithPrintTicketServiceDo__lambda_a343ab9dd4087cf8f3958bd3266e0629___(
                  (__int64)psz,
                  (__int64 *)v87,
                  (__int64)&v95);
          v74 = v73;
          if ( v73 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                0x24u,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                v73);
            }
            hr_error::hr_error((hr_error *)v121, v74);
            throw (hr_error *)v121;
          }
          memcpy_s_0(Destination, DestinationSize, (const void *const)Source, SourceSize);
          SysFreeString(*(BSTR *)&v91.Data1);
        }
        if ( *(_QWORD *)v86.Data4 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v86.Data4 + 16LL))(*(_QWORD *)v86.Data4);
        SysFreeString(v123[0]);
        SysFreeString(v49);
        if ( *(_QWORD *)&bstrString.Data1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&bstrString.Data1 + 16LL))(*(_QWORD *)&bstrString.Data1);
        SysFreeString(lpWideCharStr);
        if ( v87 )
          (*(void (__fastcall **)(struct PrintConfig::IPrintTicketService *))(*(_QWORD *)v87 + 16LL))(v87);
        if ( ppstm )
          ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
        goto LABEL_181;
      }
    }
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x15u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v32);
    }
    hr_error::hr_error((hr_error *)v122, v32);
    throw (hr_error *)v122;
  }
  catch ( std::bad_alloc )
  {
    v76 = -2147024882;
    goto LABEL_76;
  }
  catch ( const hr_error *v99 )
  {
    v76 = *((_DWORD *)v99 + 6);
  }
  catch ( const PrintCore::WindowsError *v100 )
  {
    v76 = *((_DWORD *)v100[0] + 6);
  }
  catch ( std::exception )
  {
    v76 = -2147467259;
    goto LABEL_76;
  }
  catch ( ... )
  {
    v76 = -2147418113;
    goto LABEL_76;
  }
LABEL_181:
  if ( v76 >= 0 )
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences",
      L"Extension returned: 0x%x %ws.",
      (unsigned int)v81,
      v93);
LABEL_76:
  if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x25u, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v76);
  }
  SysFreeString(v93);
  SysFreeString(pbstr);
  if ( v88 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  if ( v89 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
  if ( *(_QWORD *)&v86.Data1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v86.Data1 + 16LL))(*(_QWORD *)&v86.Data1);
  if ( v77 )
    CoUninitialize();
  return (unsigned int)v76;
}

```

## disassembly

```asm
0x18005bfc0  push    rbx
0x18005bfc2  push    rsi
0x18005bfc3  push    rdi
0x18005bfc4  push    r12
0x18005bfc6  push    r13
0x18005bfc8  push    r14
0x18005bfca  push    r15
0x18005bfcc  sub     rsp, 6D0h
0x18005bfd3  mov     [rsp+708h+var_5C0], 0FFFFFFFFFFFFFFFEh
0x18005bfdf  mov     rax, cs:__security_cookie
0x18005bfe6  xor     rax, rsp
0x18005bfe9  mov     [rsp+708h+var_48], rax
0x18005bff1  mov     [rsp+708h+psz], r9
0x18005bff9  mov     rdi, r8
0x18005bffc  mov     [rsp+708h+var_688], rdx
0x18005c004  mov     qword ptr [rsp+708h+var_628], rdx
0x18005c00c  mov     qword ptr [rsp+708h+Source], r8
0x18005c014  mov     [rsp+708h+var_638], r9
0x18005c01c  mov     r14, [rsp+708h+arg_28]
0x18005c024  mov     [rsp+708h+var_5D8], r14
0x18005c02c  mov     r8, [rsp+708h+arg_38]
0x18005c034  mov     [rsp+708h+Destination], r8
0x18005c03c  lea     r12, WPP_GLOBAL_Control
0x18005c043  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c04a  lea     r13, WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids
0x18005c051  cmp     rcx, r12
0x18005c054  jz      short loc_18005C08F
0x18005c056  test    dword ptr [rcx+44h], 100h
0x18005c05d  jz      short loc_18005C08F
0x18005c05f  mov     edx, 0Ah
0x18005c064  mov     r8, r13
0x18005c067  mov     rcx, [rcx+38h]
0x18005c06b  call    WPP_SF_
0x18005c070  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c077  mov     r9, [rsp+708h+psz]
0x18005c07f  mov     rdx, [rsp+708h+var_688]
0x18005c087  mov     r8, [rsp+708h+Destination]
0x18005c08f  xor     r15d, r15d
0x18005c092  test    rdi, rdi
0x18005c095  jnz     short loc_18005C0AA
0x18005c097  cmp     rcx, r12
0x18005c09a  jz      short loc_18005C0DC
0x18005c09c  test    dword ptr [rcx+44h], 100h
0x18005c0a3  jz      short loc_18005C0DC
0x18005c0a5  lea     edx, [rdi+0Bh]
0x18005c0a8  jmp     short loc_18005C0C1
0x18005c0aa  test    r9, r9
0x18005c0ad  jnz     short loc_18005C0E6
0x18005c0af  cmp     rcx, r12
0x18005c0b2  jz      short loc_18005C0DC
0x18005c0b4  test    dword ptr [rcx+44h], 100h
0x18005c0bb  jz      short loc_18005C0DC
0x18005c0bd  lea     edx, [r9+0Ch]
0x18005c0c1  mov     dword ptr [rsp+708h+lpWideCharStr], 80070057h
0x18005c0c9  lea     r9, aPointer; "POINTER"
0x18005c0d0  mov     r8, r13
0x18005c0d3  mov     rcx, [rcx+38h]
0x18005c0d7  call    WPP_SF_sd
0x18005c0dc  mov     eax, 80070057h
0x18005c0e1  jmp     loc_18005C3B4
0x18005c0e6  test    r8, r8
0x18005c0e9  jnz     short loc_18005C122
0x18005c0eb  cmp     rcx, r12
0x18005c0ee  jz      short loc_18005C118
0x18005c0f0  test    dword ptr [rcx+44h], 100h
0x18005c0f7  jz      short loc_18005C118
0x18005c0f9  lea     edx, [r8+0Dh]
0x18005c0fd  mov     dword ptr [rsp+708h+lpWideCharStr], 8007007Ah
0x18005c105  lea     r9, aPointer; "POINTER"
0x18005c10c  mov     r8, r13
0x18005c10f  mov     rcx, [rcx+38h]
0x18005c113  call    WPP_SF_sd
0x18005c118  mov     eax, 8007007Ah
0x18005c11d  jmp     loc_18005C3B4
0x18005c122  mov     [rsp+708h+var_6A8], r15d
0x18005c127  cmp     rcx, r12
0x18005c12a  jz      short loc_18005C182
0x18005c12c  test    dword ptr [rcx+44h], 100h
0x18005c133  jz      short loc_18005C182
0x18005c135  mov     eax, [rsp+708h+dwProcessId]
0x18005c13c  mov     [rsp+708h+var_6B0], eax
0x18005c140  mov     eax, [rsp+708h+arg_40]
0x18005c147  mov     [rsp+708h+var_6B8], eax
0x18005c14b  mov     [rsp+708h+var_6C0], r8
0x18005c150  mov     eax, dword ptr [rsp+708h+DestinationSize]
0x18005c157  mov     [rsp+708h+var_6C8], eax
0x18005c15b  mov     qword ptr [rsp+708h+dwCapabilities], r14
0x18005c160  mov     eax, [rsp+708h+arg_20]
0x18005c167  mov     dword ptr [rsp+708h+pAuthInfo], eax
0x18005c16b  mov     qword ptr [rsp+708h+cchWideChar], r9
0x18005c170  mov     [rsp+708h+lpWideCharStr], rdi
0x18005c175  mov     r9, rdx
0x18005c178  mov     rcx, [rcx+38h]
0x18005c17c  call    WPP_SF_qqSDqDqDD
0x18005c181  nop
0x18005c182  xor     edx, edx; dwCoInit
0x18005c184  xor     ecx, ecx; pvReserved
0x18005c186  call    cs:__imp_CoInitializeEx
0x18005c18d  nop     dword ptr [rax+rax+00h]
0x18005c192  movzx   ecx, r15b
0x18005c196  mov     esi, 1
0x18005c19b  test    eax, eax
0x18005c19d  cmovns  ecx, esi; this
0x18005c1a0  mov     [rsp+708h+var_6A4], cl
0x18005c1a4  mov     qword ptr [rsp+708h+var_660.Data1], r15
0x18005c1ac  mov     [rsp+708h+var_640], r15
0x18005c1b4  mov     [rsp+708h+var_648], r15
0x18005c1bc  lea     r8, [rsp+708h+var_660]; struct _GUID *
0x18005c1c4  lea     rdx, _GUID_4f27786b_13a2_4df5_857c_3eea48d4839b; struct IUnknown *
0x18005c1cb  call    ?CreateInstanceInternal@Driver@Print@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; Print::Driver::CreateInstanceInternal(IUnknown *,_GUID const &,void * *)
0x18005c1d0  mov     ebx, eax
0x18005c1d2  test    eax, eax
0x18005c1d4  js      loc_18005CC1F
0x18005c1da  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x18005c1e2  mov     rax, [rcx]
0x18005c1e5  mov     rax, [rax+20h]
0x18005c1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1ee  test    eax, eax
0x18005c1f0  jz      loc_18005CC66
0x18005c1f6  lea     rdx, [rsp+708h+var_640]
0x18005c1fe  mov     rcx, [rsp+708h+psz]; unsigned __int16 *
0x18005c206  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x18005c20b  mov     ebx, eax
0x18005c20d  test    eax, eax
0x18005c20f  js      loc_18005CCB3
0x18005c215  mov     rcx, [rsp+708h+var_640]
0x18005c21d  mov     rax, [rcx]
0x18005c220  lea     r8, [rsp+708h+var_648]
0x18005c228  lea     rdx, _GUID_132737be_6991_4586_a599_7b8629364f61
0x18005c22f  mov     rax, [rax]
0x18005c232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c237  mov     ebx, eax
0x18005c239  test    eax, eax
0x18005c23b  js      loc_18005CCFC
0x18005c241  xorps   xmm0, xmm0
0x18005c244  movups  xmmword ptr [rsp+708h+var_2B8], xmm0
0x18005c24c  mov     rcx, [rsp+708h+var_648]
0x18005c254  mov     rax, [rcx]
0x18005c257  lea     rdx, [rsp+708h+var_2E8]
0x18005c25f  mov     rax, [rax+18h]
0x18005c263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c268  nop
0x18005c269  cmp     qword ptr [rax+18h], 7
0x18005c26e  jbe     short loc_18005C273
0x18005c270  mov     rax, [rax]
0x18005c273  lea     rdx, [rsp+708h+var_2B8]; unsigned __int16 *
0x18005c27b  mov     rcx, rax; this
0x18005c27e  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x18005c283  nop
0x18005c284  lea     rcx, [rsp+708h+var_2E8]
0x18005c28c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c291  xorps   xmm0, xmm0
0x18005c294  movups  [rsp+708h+var_2C8], xmm0
0x18005c29c  mov     [rsp+708h+bstrString], r15
0x18005c2a4  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x18005c2ac  movups  xmm0, cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES
0x18005c2b3  movdqu  xmmword ptr [rsp+708h+var_2E8], xmm0
0x18005c2bc  movaps  xmm0, xmmword ptr [rsp+708h+var_2B8]
0x18005c2c4  movdqa  [rsp+708h+var_5F8], xmm0
0x18005c2cd  mov     rax, [rcx]
0x18005c2d0  lea     rdx, [rsp+708h+bstrString]
0x18005c2d8  mov     [rsp+708h+lpWideCharStr], rdx
0x18005c2dd  lea     r9, [rsp+708h+var_2C8]
0x18005c2e5  lea     r8, [rsp+708h+var_2E8]
0x18005c2ed  lea     rdx, [rsp+708h+var_5F8]
0x18005c2f5  mov     rax, [rax+18h]
0x18005c2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2fe  test    eax, eax
0x18005c300  jns     short loc_18005C319
0x18005c302  mov     r8d, eax
0x18005c305  lea     rdx, aPreConditionFa_0; "Pre-condition failure of PRINT_DRIVER_E"...
0x18005c30c  lea     rcx, aPrintDriverCon; "Print::Driver::Config::PrinterDriverWin"...
0x18005c313  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18005c318  nop
0x18005c319  mov     rcx, [rsp+708h+bstrString]; bstrString
0x18005c321  call    cs:__imp_SysFreeString
0x18005c328  nop     dword ptr [rax+rax+00h]
0x18005c32d  nop
0x18005c32e  jmp     loc_18005C428
0x18005c333  xor     r15d, r15d
0x18005c336  mov     r8d, [rsp+708h+var_6A8]
0x18005c33b  lea     rdx, aPreConditionFa; "Pre-condition failure for IHV extension"...
0x18005c342  lea     rcx, aPrintDriverCon; "Print::Driver::Config::PrinterDriverWin"...
0x18005c349  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005c34e  nop
0x18005c34f  mov     rcx, [rsp+708h+var_648]
0x18005c357  test    rcx, rcx
0x18005c35a  jz      short loc_18005C369
0x18005c35c  mov     rax, [rcx]
0x18005c35f  mov     rax, [rax+10h]
0x18005c363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c368  nop
0x18005c369  mov     rcx, [rsp+708h+var_640]
0x18005c371  test    rcx, rcx
0x18005c374  jz      short loc_18005C383
0x18005c376  mov     rax, [rcx]
0x18005c379  mov     rax, [rax+10h]
0x18005c37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c382  nop
0x18005c383  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x18005c38b  test    rcx, rcx
0x18005c38e  jz      short loc_18005C39D
0x18005c390  mov     rax, [rcx]
0x18005c393  mov     rax, [rax+10h]
0x18005c397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c39c  nop
0x18005c39d  cmp     [rsp+708h+var_6A4], r15b
0x18005c3a2  jz      short loc_18005C3B0
0x18005c3a4  call    cs:__imp_CoUninitialize
0x18005c3ab  nop     dword ptr [rax+rax+00h]
0x18005c3b0  mov     eax, [rsp+708h+var_6A8]
0x18005c3b4  mov     rcx, [rsp+708h+var_48]
0x18005c3bc  xor     rcx, rsp; StackCookie
0x18005c3bf  call    __security_check_cookie
0x18005c3c4  add     rsp, 6D0h
0x18005c3cb  pop     r15
0x18005c3cd  pop     r14
0x18005c3cf  pop     r13
0x18005c3d1  pop     r12
0x18005c3d3  pop     rdi
0x18005c3d4  pop     rsi
0x18005c3d5  pop     rbx
0x18005c3d6  retn
0x18005c3d8  xor     r15d, r15d
0x18005c3db  cmp     [rsp+708h+var_6A8], r15d
0x18005c3e0  jl      loc_18005C336
0x18005c3e6  lea     r12, WPP_GLOBAL_Control
0x18005c3ed  lea     r13, WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids
0x18005c3f4  lea     esi, [r15+1]
0x18005c3f8  mov     r14, [rsp+708h+var_5D8]
0x18005c400  mov     rax, qword ptr [rsp+708h+var_628]
0x18005c408  mov     [rsp+708h+var_688], rax
0x18005c410  mov     rdi, qword ptr [rsp+708h+Source]
0x18005c418  mov     rax, [rsp+708h+var_638]
0x18005c420  mov     [rsp+708h+psz], rax
0x18005c428  mov     [rsp+708h+pbstr], r15
0x18005c430  mov     [rsp+708h+var_690], 8000FFFFh
0x18005c438  mov     [rsp+708h+var_610], r15
0x18005c440  mov     [rsp+708h+ppstm], r15
0x18005c445  lea     r8, [rsp+708h+ppstm]; ppstm
0x18005c44a  mov     edx, esi; fDeleteOnRelease
0x18005c44c  xor     ecx, ecx; hGlobal
0x18005c44e  call    cs:__imp_CreateStreamOnHGlobal
0x18005c455  nop     dword ptr [rax+rax+00h]
0x18005c45a  mov     ebx, eax
0x18005c45c  test    eax, eax
0x18005c45e  js      loc_18005CD46
0x18005c464  mov     [rsp+708h+var_650], r15
0x18005c46c  lea     rdx, [rsp+708h+var_650]; void *
0x18005c474  mov     rcx, rdi; this
0x18005c477  call    ?GetDefaultPrintTicketService@PrintConfig@@YAJPEAXPEAPEAUIPrintTicketService@1@@Z; PrintConfig::GetDefaultPrintTicketService(void *,PrintConfig::IPrintTicketService * *)
0x18005c47c  mov     ebx, eax
0x18005c47e  test    eax, eax
0x18005c480  js      loc_18005CD90
0x18005c486  mov     rdi, [rsp+708h+var_650]
0x18005c48e  mov     dword ptr [rsp+708h+SourceSize], r15d
0x18005c493  mov     rax, [rdi]
0x18005c496  lea     rcx, [rsp+708h+SourceSize]
0x18005c49b  mov     [rsp+708h+lpWideCharStr], rcx
0x18005c4a0  mov     r9d, esi
0x18005c4a3  mov     r8d, esi
0x18005c4a6  mov     rdx, [rsp+708h+psz]
0x18005c4ae  mov     rcx, rdi
0x18005c4b1  mov     rax, [rax+20h]
0x18005c4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4ba  mov     ebx, eax
0x18005c4bc  test    eax, eax
0x18005c4be  js      loc_18005D25C
0x18005c4c4  mov     rcx, [rsp+708h+ppstm]
0x18005c4c9  mov     rax, [rdi]
0x18005c4cc  mov     [rsp+708h+lpWideCharStr], rcx
0x18005c4d1  mov     r9d, 2
0x18005c4d7  mov     r8, r14
0x18005c4da  mov     edx, [rsp+708h+arg_20]
0x18005c4e1  mov     rcx, rdi
0x18005c4e4  mov     rax, [rax+30h]
0x18005c4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4ed  mov     r14d, eax
0x18005c4f0  mov     rdx, [rdi]
0x18005c4f3  mov     rcx, rdi
0x18005c4f6  mov     rax, [rdx+50h]
0x18005c4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4ff  mov     ebx, eax
0x18005c501  test    r14d, r14d
0x18005c504  js      loc_18005D259
0x18005c50a  test    eax, eax
0x18005c50c  js      loc_18005D25C
0x18005c512  mov     [rsp+708h+phglobal], r15
0x18005c51a  lea     rdx, [rsp+708h+phglobal]; phglobal
0x18005c522  mov     rcx, [rsp+708h+ppstm]; pstm
0x18005c527  call    cs:__imp_GetHGlobalFromStream
0x18005c52e  nop     dword ptr [rax+rax+00h]
0x18005c533  mov     ebx, eax
0x18005c535  test    eax, eax
0x18005c537  js      loc_18005CDD9
0x18005c53d  mov     rcx, [rsp+708h+phglobal]; hMem
0x18005c545  call    cs:__imp_GlobalSize
0x18005c54c  nop     dword ptr [rax+rax+00h]
0x18005c551  xor     edx, edx; Val
0x18005c553  lea     r8d, [rdx+50h]; Size
  ... truncated ...
```
