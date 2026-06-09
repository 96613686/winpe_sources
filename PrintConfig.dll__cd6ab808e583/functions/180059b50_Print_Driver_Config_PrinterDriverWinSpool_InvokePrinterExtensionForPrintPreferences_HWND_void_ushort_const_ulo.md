# Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences(HWND__ *,void *,ushort const *,ulong,_devicemodeW *,ulong,_devicemodeW *,ulong,ulong)

- ea: `0x180059b50`
- end: `0x18005ada8`
- name: `?InvokePrinterExtensionForPrintPreferences@PrinterDriverWinSpool@Config@Driver@Print@@UEAAJPEAUHWND__@@PEAXPEBGKPEAU_devicemodeW@@K3KK@Z`
- size: `4696`
- prototype: `int(Print::Driver::Config::PrinterDriverWinSpool *__hidden this, HWND, void *, const unsigned __int16 *, unsigned int, struct _devicemodeW *, unsigned int, struct _devicemodeW *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000d288`
- `0x18000f380`
- `0x18000f590`
- `0x18001047c`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x180031e00`
- `0x1800325a8`
- `0x180032628`
- `0x180035cdc`
- `0x180053468`
- `0x180058d98`
- `0x180059260`
- `0x180059b50`
- `0x18005b8e4`
- `0x1800976ec`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005a15d`
- `KERNEL32!GetLastError` at `0x18005a15d`
- `KERNEL32!MultiByteToWideChar` at `0x18005a145`
- `KERNEL32!MultiByteToWideChar` at `0x18005a145`
- `KERNEL32!GlobalSize` at `0x18005a0b6`
- `KERNEL32!GlobalSize` at `0x18005a0b6`
- `KERNEL32!GlobalLock` at `0x18005a124`
- `KERNEL32!GlobalLock` at `0x18005a124`
- `KERNEL32!GlobalUnlock` at `0x18005a157`
- `KERNEL32!GlobalUnlock` at `0x18005a19f`
- `KERNEL32!GlobalUnlock` at `0x18005a157`
- `KERNEL32!GlobalUnlock` at `0x18005a19f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a1fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a1fc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005a180`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005a180`
- `OLEAUT32!__imp_SysFreeString` at `0x180059eab`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a593`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a66c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a67b`
- `OLEAUT32!__imp_SysFreeString` at `0x180059eab`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a593`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a5ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a66c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a67b`
- `OLEAUT32!__imp_SysStringLen` at `0x18005a3da`
- `OLEAUT32!__imp_SysStringLen` at `0x18005a49b`
- `OLEAUT32!__imp_SysStringLen` at `0x18005a3da`
- `OLEAUT32!__imp_SysStringLen` at `0x18005a49b`
- `ole32!CoCreateInstance` at `0x18005a2db`
- `ole32!CoCreateInstance` at `0x18005a2db`
- `ole32!CreateStreamOnHGlobal` at `0x180059fcb`
- `ole32!CreateStreamOnHGlobal` at `0x180059fcb`
- `ole32!CoSetProxyBlanket` at `0x18005a318`
- `ole32!CoSetProxyBlanket` at `0x18005a318`
- `ole32!GetHGlobalFromStream` at `0x18005a09e`
- `ole32!GetHGlobalFromStream` at `0x18005a09e`
- `ole32!CoInitializeEx` at `0x180059d16`
- `ole32!CoInitializeEx` at `0x180059d16`
- `ole32!CoUninitialize` at `0x180059f28`
- `ole32!CoUninitialize` at `0x180059f28`

## string_xrefs

- `0x18005aaf8`: `IPrinterExtensionServerInternal::RaiseExtensionEvent returned 0x%x.`
- `0x180059ebf`: `Pre-condition failure for IHV extension: 0x%x`
- `0x180059e96`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x180059ec6`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005a3a3`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005a705`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005aaff`: `Print::Driver::Config::PrinterDriverWinSpool::InvokePrinterExtensionForPrintPreferences`
- `0x18005a6fe`: `Extension returned: 0x%x %ws.`
- `0x18005a39c`: `IHV extension returned 0x%x.`

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
  int v13; // edx
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
  __int64 v31; // rdi
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
  unsigned int v48; // r8d
  OLECHAR *v49; // rdi
  int v50; // eax
  int v51; // r14d
  HRESULT Instance; // eax
  int v53; // r14d
  HRESULT v54; // eax
  int v55; // r14d
  int v56; // eax
  unsigned int v57; // r14d
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
  __int64 v87; // [rsp+B8h] [rbp-650h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-648h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-640h]
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids);
    v12 = WPP_GLOBAL_Control;
    a4 = psz;
    LODWORD(a2) = (_DWORD)v82;
    v11 = (struct _devicemodeW *)Destination;
  }
  if ( !a3 )
  {
    if ( v12 == (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control || (*((_DWORD *)v12 + 17) & 0x100) == 0 )
      return 2147942487LL;
    v13 = 11;
LABEL_12:
    WPP_SF_sd(
      *((_QWORD *)v12 + 7),
      v13,
      (unsigned int)&WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
      (unsigned int)"POINTER",
      87);
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
      WPP_SF_sd(
        *((_QWORD *)v12 + 7),
        13,
        (unsigned int)&WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        (unsigned int)"POINTER",
        122);
    return 2147942522LL;
  }
  v76 = 0;
  if ( v12 != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_qqSDqDqDD(
      *((_QWORD *)v12 + 7),
      (_DWORD)a2,
      (_DWORD)v11,
      (_DWORD)a2,
      (char)a3,
      (__int64)a4,
      a5,
      (char)a6,
      DestinationSize,
      (char)v11,
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        15,
        &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        (unsigned int)v17);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v18);
    throw (hr_error *)pExceptionObject;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&v86.Data1 + 32LL))(*(_QWORD *)&v86.Data1) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, 2147746793LL);
    }
    hr_error::hr_error((hr_error *)v102, -2147220503);
    throw (hr_error *)v102;
  }
  v19 = PrintConfig::CPrinterQueue::Create(psz);
  v20 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        17,
        &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        (unsigned int)v19);
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
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        18,
        &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        (unsigned int)v21);
    }
    hr_error::hr_error((hr_error *)v104, v22);
    throw (hr_error *)v104;
  }
  *(_OWORD *)v125 = 0;
  v23 = (Win32Adapters::Guid *)(*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v88 + 24LL))(v88, v123);
  if ( *((_QWORD *)v23 + 3) > 7u )
    v23 = *(Win32Adapters::Guid **)v23;
  Win32Adapters::Guid::GuidFromString(v23, v125, v24);
  std::wstring::~wstring(v123);
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
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          19,
          &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
          (unsigned int)v26);
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
          20,
          &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
          (unsigned int)DefaultPrintTicketService);
      }
      hr_error::hr_error((hr_error *)v106, v30);
      throw (hr_error *)v106;
    }
    v31 = v87;
    SourceSize = 0;
    v32 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, __int64, unsigned int *))(*(_QWORD *)v87 + 32LL))(
            v87,
            psz,
            1,
            1,
            &SourceSize);
    if ( v32 >= 0 )
    {
      v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _devicemodeW *, __int64, LPSTREAM))(*(_QWORD *)v31 + 48LL))(
              v31,
              a5,
              a6,
              2,
              ppstm);
      v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
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
              22,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)HGlobalFromStream);
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
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              23,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)v37);
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
                24,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v45);
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
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              25,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)v46);
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
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              26,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)v50);
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
              27,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)Instance);
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
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              28,
              &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
              (unsigned int)v54);
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids, v57);
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
                30,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v81);
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
                31,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v60);
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
                32,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v62);
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
                33,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v64);
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
                34,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v69);
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
                35,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v71);
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
          v73 = PrintConfig::WithPrintTicketServiceDo__lambda_a343ab9dd4087cf8f3958bd3266e0629___(psz, v87, &v95);
          v74 = v73;
          if ( v73 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                36,
                &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
                (unsigned int)v73);
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
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
        if ( ppstm )
          ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
        goto LABEL_181;
      }
    }
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        21,
        &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
        (unsigned int)v32);
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
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      37,
      &WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids,
      (unsigned int)v76);
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
0x180059b50  push    rbx
0x180059b52  push    rsi
0x180059b53  push    rdi
0x180059b54  push    r12
0x180059b56  push    r13
0x180059b58  push    r14
0x180059b5a  push    r15
0x180059b5c  sub     rsp, 6D0h
0x180059b63  mov     [rsp+708h+var_5C0], 0FFFFFFFFFFFFFFFEh
0x180059b6f  mov     rax, cs:__security_cookie
0x180059b76  xor     rax, rsp
0x180059b79  mov     [rsp+708h+var_48], rax
0x180059b81  mov     [rsp+708h+psz], r9
0x180059b89  mov     rdi, r8
0x180059b8c  mov     [rsp+708h+var_688], rdx
0x180059b94  mov     qword ptr [rsp+708h+var_628], rdx
0x180059b9c  mov     qword ptr [rsp+708h+Source], r8
0x180059ba4  mov     [rsp+708h+var_638], r9
0x180059bac  mov     r14, [rsp+708h+arg_28]
0x180059bb4  mov     [rsp+708h+var_5D8], r14
0x180059bbc  mov     r8, [rsp+708h+arg_38]
0x180059bc4  mov     [rsp+708h+Destination], r8
0x180059bcc  lea     r12, WPP_GLOBAL_Control
0x180059bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bda  lea     r13, WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids
0x180059be1  cmp     rcx, r12
0x180059be4  jz      short loc_180059C1F
0x180059be6  test    dword ptr [rcx+44h], 100h
0x180059bed  jz      short loc_180059C1F
0x180059bef  mov     edx, 0Ah
0x180059bf4  mov     r8, r13
0x180059bf7  mov     rcx, [rcx+38h]
0x180059bfb  call    WPP_SF_
0x180059c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c07  mov     r9, [rsp+708h+psz]
0x180059c0f  mov     rdx, [rsp+708h+var_688]
0x180059c17  mov     r8, [rsp+708h+Destination]
0x180059c1f  xor     r15d, r15d
0x180059c22  test    rdi, rdi
0x180059c25  jnz     short loc_180059C3A
0x180059c27  cmp     rcx, r12
0x180059c2a  jz      short loc_180059C6C
0x180059c2c  test    dword ptr [rcx+44h], 100h
0x180059c33  jz      short loc_180059C6C
0x180059c35  lea     edx, [rdi+0Bh]
0x180059c38  jmp     short loc_180059C51
0x180059c3a  test    r9, r9
0x180059c3d  jnz     short loc_180059C76
0x180059c3f  cmp     rcx, r12
0x180059c42  jz      short loc_180059C6C
0x180059c44  test    dword ptr [rcx+44h], 100h
0x180059c4b  jz      short loc_180059C6C
0x180059c4d  lea     edx, [r9+0Ch]
0x180059c51  mov     dword ptr [rsp+708h+lpWideCharStr], 80070057h
0x180059c59  lea     r9, aPointer; "POINTER"
0x180059c60  mov     r8, r13
0x180059c63  mov     rcx, [rcx+38h]
0x180059c67  call    WPP_SF_sd
0x180059c6c  mov     eax, 80070057h
0x180059c71  jmp     loc_180059F32
0x180059c76  test    r8, r8
0x180059c79  jnz     short loc_180059CB2
0x180059c7b  cmp     rcx, r12
0x180059c7e  jz      short loc_180059CA8
0x180059c80  test    dword ptr [rcx+44h], 100h
0x180059c87  jz      short loc_180059CA8
0x180059c89  lea     edx, [r8+0Dh]
0x180059c8d  mov     dword ptr [rsp+708h+lpWideCharStr], 8007007Ah
0x180059c95  lea     r9, aPointer; "POINTER"
0x180059c9c  mov     r8, r13
0x180059c9f  mov     rcx, [rcx+38h]
0x180059ca3  call    WPP_SF_sd
0x180059ca8  mov     eax, 8007007Ah
0x180059cad  jmp     loc_180059F32
0x180059cb2  mov     [rsp+708h+var_6A8], r15d
0x180059cb7  cmp     rcx, r12
0x180059cba  jz      short loc_180059D12
0x180059cbc  test    dword ptr [rcx+44h], 100h
0x180059cc3  jz      short loc_180059D12
0x180059cc5  mov     eax, [rsp+708h+dwProcessId]
0x180059ccc  mov     [rsp+708h+var_6B0], eax
0x180059cd0  mov     eax, [rsp+708h+arg_40]
0x180059cd7  mov     [rsp+708h+var_6B8], eax
0x180059cdb  mov     [rsp+708h+var_6C0], r8
0x180059ce0  mov     eax, dword ptr [rsp+708h+DestinationSize]
0x180059ce7  mov     [rsp+708h+var_6C8], eax
0x180059ceb  mov     qword ptr [rsp+708h+dwCapabilities], r14
0x180059cf0  mov     eax, [rsp+708h+arg_20]
0x180059cf7  mov     dword ptr [rsp+708h+pAuthInfo], eax
0x180059cfb  mov     qword ptr [rsp+708h+cchWideChar], r9
0x180059d00  mov     [rsp+708h+lpWideCharStr], rdi
0x180059d05  mov     r9, rdx
0x180059d08  mov     rcx, [rcx+38h]
0x180059d0c  call    WPP_SF_qqSDqDqDD
0x180059d11  nop
0x180059d12  xor     edx, edx; dwCoInit
0x180059d14  xor     ecx, ecx; pvReserved
0x180059d16  call    cs:__imp_CoInitializeEx
0x180059d1c  movzx   ecx, r15b
0x180059d20  mov     esi, 1
0x180059d25  test    eax, eax
0x180059d27  cmovns  ecx, esi; this
0x180059d2a  mov     [rsp+708h+var_6A4], cl
0x180059d2e  mov     qword ptr [rsp+708h+var_660.Data1], r15
0x180059d36  mov     [rsp+708h+var_640], r15
0x180059d3e  mov     [rsp+708h+var_648], r15
0x180059d46  lea     r8, [rsp+708h+var_660]; struct _GUID *
0x180059d4e  lea     rdx, _GUID_4f27786b_13a2_4df5_857c_3eea48d4839b; struct IUnknown *
0x180059d55  call    ?CreateInstanceInternal@Driver@Print@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; Print::Driver::CreateInstanceInternal(IUnknown *,_GUID const &,void * *)
0x180059d5a  mov     ebx, eax
0x180059d5c  test    eax, eax
0x180059d5e  js      loc_18005A720
0x180059d64  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x180059d6c  mov     rax, [rcx]
0x180059d6f  mov     rax, [rax+20h]
0x180059d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d78  test    eax, eax
0x180059d7a  jz      loc_18005A767
0x180059d80  lea     rdx, [rsp+708h+var_640]
0x180059d88  mov     rcx, [rsp+708h+psz]; unsigned __int16 *
0x180059d90  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x180059d95  mov     ebx, eax
0x180059d97  test    eax, eax
0x180059d99  js      loc_18005A7B4
0x180059d9f  mov     rcx, [rsp+708h+var_640]
0x180059da7  mov     rax, [rcx]
0x180059daa  lea     r8, [rsp+708h+var_648]
0x180059db2  lea     rdx, _GUID_132737be_6991_4586_a599_7b8629364f61
0x180059db9  mov     rax, [rax]
0x180059dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059dc1  mov     ebx, eax
0x180059dc3  test    eax, eax
0x180059dc5  js      loc_18005A7FD
0x180059dcb  xorps   xmm0, xmm0
0x180059dce  movups  xmmword ptr [rsp+708h+var_2B8], xmm0
0x180059dd6  mov     rcx, [rsp+708h+var_648]
0x180059dde  mov     rax, [rcx]
0x180059de1  lea     rdx, [rsp+708h+var_2E8]
0x180059de9  mov     rax, [rax+18h]
0x180059ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059df2  nop
0x180059df3  cmp     qword ptr [rax+18h], 7
0x180059df8  jbe     short loc_180059DFD
0x180059dfa  mov     rax, [rax]
0x180059dfd  lea     rdx, [rsp+708h+var_2B8]; unsigned __int16 *
0x180059e05  mov     rcx, rax; this
0x180059e08  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180059e0d  nop
0x180059e0e  lea     rcx, [rsp+708h+var_2E8]
0x180059e16  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180059e1b  xorps   xmm0, xmm0
0x180059e1e  movups  [rsp+708h+var_2C8], xmm0
0x180059e26  mov     [rsp+708h+bstrString], r15
0x180059e2e  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x180059e36  movups  xmm0, cs:PRINTER_EXTENSION_REASON_PRINT_PREFERENCES
0x180059e3d  movdqu  xmmword ptr [rsp+708h+var_2E8], xmm0
0x180059e46  movaps  xmm0, xmmword ptr [rsp+708h+var_2B8]
0x180059e4e  movdqa  [rsp+708h+var_5F8], xmm0
0x180059e57  mov     rax, [rcx]
0x180059e5a  lea     rdx, [rsp+708h+bstrString]
0x180059e62  mov     [rsp+708h+lpWideCharStr], rdx
0x180059e67  lea     r9, [rsp+708h+var_2C8]
0x180059e6f  lea     r8, [rsp+708h+var_2E8]
0x180059e77  lea     rdx, [rsp+708h+var_5F8]
0x180059e7f  mov     rax, [rax+18h]
0x180059e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e88  test    eax, eax
0x180059e8a  jns     short loc_180059EA3
0x180059e8c  mov     r8d, eax
0x180059e8f  lea     rdx, aPreConditionFa_0; "Pre-condition failure of PRINT_DRIVER_E"...
0x180059e96  lea     rcx, aPrintDriverCon; "Print::Driver::Config::PrinterDriverWin"...
0x180059e9d  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180059ea2  nop
0x180059ea3  mov     rcx, [rsp+708h+bstrString]; bstrString
0x180059eab  call    cs:__imp_SysFreeString
0x180059eb1  nop
0x180059eb2  jmp     loc_180059FA5
0x180059eb7  xor     r15d, r15d
0x180059eba  mov     r8d, [rsp+708h+var_6A8]
0x180059ebf  lea     rdx, aPreConditionFa; "Pre-condition failure for IHV extension"...
0x180059ec6  lea     rcx, aPrintDriverCon; "Print::Driver::Config::PrinterDriverWin"...
0x180059ecd  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180059ed2  nop
0x180059ed3  mov     rcx, [rsp+708h+var_648]
0x180059edb  test    rcx, rcx
0x180059ede  jz      short loc_180059EED
0x180059ee0  mov     rax, [rcx]
0x180059ee3  mov     rax, [rax+10h]
0x180059ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059eec  nop
0x180059eed  mov     rcx, [rsp+708h+var_640]
0x180059ef5  test    rcx, rcx
0x180059ef8  jz      short loc_180059F07
0x180059efa  mov     rax, [rcx]
0x180059efd  mov     rax, [rax+10h]
0x180059f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f06  nop
0x180059f07  mov     rcx, qword ptr [rsp+708h+var_660.Data1]
0x180059f0f  test    rcx, rcx
0x180059f12  jz      short loc_180059F21
0x180059f14  mov     rax, [rcx]
0x180059f17  mov     rax, [rax+10h]
0x180059f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f20  nop
0x180059f21  cmp     [rsp+708h+var_6A4], r15b
0x180059f26  jz      short loc_180059F2E
0x180059f28  call    cs:__imp_CoUninitialize
0x180059f2e  mov     eax, [rsp+708h+var_6A8]
0x180059f32  mov     rcx, [rsp+708h+var_48]
0x180059f3a  xor     rcx, rsp; StackCookie
0x180059f3d  call    __security_check_cookie
0x180059f42  add     rsp, 6D0h
0x180059f49  pop     r15
0x180059f4b  pop     r14
0x180059f4d  pop     r13
0x180059f4f  pop     r12
0x180059f51  pop     rdi
0x180059f52  pop     rsi
0x180059f53  pop     rbx
0x180059f54  retn
0x180059f55  xor     r15d, r15d
0x180059f58  cmp     [rsp+708h+var_6A8], r15d
0x180059f5d  jl      loc_180059EBA
0x180059f63  lea     r12, WPP_GLOBAL_Control
0x180059f6a  lea     r13, WPP_97f8e2c46ac339c838c97ec98b78d5b5_Traceguids
0x180059f71  lea     esi, [r15+1]
0x180059f75  mov     r14, [rsp+708h+var_5D8]
0x180059f7d  mov     rax, qword ptr [rsp+708h+var_628]
0x180059f85  mov     [rsp+708h+var_688], rax
0x180059f8d  mov     rdi, qword ptr [rsp+708h+Source]
0x180059f95  mov     rax, [rsp+708h+var_638]
0x180059f9d  mov     [rsp+708h+psz], rax
0x180059fa5  mov     [rsp+708h+pbstr], r15
0x180059fad  mov     [rsp+708h+var_690], 8000FFFFh
0x180059fb5  mov     [rsp+708h+var_610], r15
0x180059fbd  mov     [rsp+708h+ppstm], r15
0x180059fc2  lea     r8, [rsp+708h+ppstm]; ppstm
0x180059fc7  mov     edx, esi; fDeleteOnRelease
0x180059fc9  xor     ecx, ecx; hGlobal
0x180059fcb  call    cs:__imp_CreateStreamOnHGlobal
0x180059fd1  mov     ebx, eax
0x180059fd3  test    eax, eax
0x180059fd5  js      loc_18005A847
0x180059fdb  mov     [rsp+708h+var_650], r15
0x180059fe3  lea     rdx, [rsp+708h+var_650]; void *
0x180059feb  mov     rcx, rdi; this
0x180059fee  call    ?GetDefaultPrintTicketService@PrintConfig@@YAJPEAXPEAPEAUIPrintTicketService@1@@Z; PrintConfig::GetDefaultPrintTicketService(void *,PrintConfig::IPrintTicketService * *)
0x180059ff3  mov     ebx, eax
0x180059ff5  test    eax, eax
0x180059ff7  js      loc_18005A891
0x180059ffd  mov     rdi, [rsp+708h+var_650]
0x18005a005  mov     dword ptr [rsp+708h+SourceSize], r15d
0x18005a00a  mov     rax, [rdi]
0x18005a00d  lea     rcx, [rsp+708h+SourceSize]
0x18005a012  mov     [rsp+708h+lpWideCharStr], rcx
0x18005a017  mov     r9d, esi
0x18005a01a  mov     r8d, esi
0x18005a01d  mov     rdx, [rsp+708h+psz]
0x18005a025  mov     rcx, rdi
0x18005a028  mov     rax, [rax+20h]
0x18005a02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a031  mov     ebx, eax
0x18005a033  test    eax, eax
0x18005a035  js      loc_18005AD5D
0x18005a03b  mov     rcx, [rsp+708h+ppstm]
0x18005a040  mov     rax, [rdi]
0x18005a043  mov     [rsp+708h+lpWideCharStr], rcx
0x18005a048  mov     r9d, 2
0x18005a04e  mov     r8, r14
0x18005a051  mov     edx, [rsp+708h+arg_20]
0x18005a058  mov     rcx, rdi
0x18005a05b  mov     rax, [rax+30h]
0x18005a05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a064  mov     r14d, eax
0x18005a067  mov     rdx, [rdi]
0x18005a06a  mov     rcx, rdi
0x18005a06d  mov     rax, [rdx+50h]
0x18005a071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a076  mov     ebx, eax
0x18005a078  test    r14d, r14d
0x18005a07b  js      loc_18005AD5A
0x18005a081  test    eax, eax
0x18005a083  js      loc_18005AD5D
0x18005a089  mov     [rsp+708h+phglobal], r15
0x18005a091  lea     rdx, [rsp+708h+phglobal]; phglobal
0x18005a099  mov     rcx, [rsp+708h+ppstm]; pstm
0x18005a09e  call    cs:__imp_GetHGlobalFromStream
0x18005a0a4  mov     ebx, eax
0x18005a0a6  test    eax, eax
0x18005a0a8  js      loc_18005A8DA
0x18005a0ae  mov     rcx, [rsp+708h+phglobal]; hMem
0x18005a0b6  call    cs:__imp_GlobalSize
0x18005a0bc  xor     edx, edx; Val
0x18005a0be  lea     r8d, [rdx+50h]; Size
0x18005a0c2  lea     rcx, [rsp+708h+var_2A8]; void *
0x18005a0ca  call    memset_0
0x18005a0cf  mov     rcx, [rsp+708h+ppstm]
0x18005a0d4  mov     rax, [rcx]
0x18005a0d7  mov     r8d, esi
0x18005a0da  lea     rdx, [rsp+708h+var_2A8]
  ... truncated ...
```
