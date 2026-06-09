# PrintConfig::V4MxdcGetPDEVAdjustment(void *,ulong,_devicemodeW const *,ulong,void const *,ulong,PrintPropertiesCollection *)

- ea: `0x180023af4`
- end: `0x180024be2`
- name: `?V4MxdcGetPDEVAdjustment@PrintConfig@@YAXPEAXKPEBU_devicemodeW@@KPEBXKPEAUPrintPropertiesCollection@@@Z`
- size: `4334`
- prototype: `void __fastcall(PrintConfig *this, void *, struct _devicemodeW *, const struct _devicemodeW *, __int64, const void *, struct PrintPropertiesCollection *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002fa94`

## callees

- `0x180003400`
- `0x180003430`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x18000fb68`
- `0x1800109e8`
- `0x180018f00`
- `0x180018f58`
- `0x180020c8c`
- `0x180020ef8`
- `0x1800218c0`
- `0x180022484`
- `0x180022f2c`
- `0x180023184`
- `0x1800235c0`
- `0x18002378c`
- `0x180023af4`
- `0x180025050`
- `0x180055608`
- `0x1800c499c`
- `0x1800cb3a8`
- `0x1800cb5a4`
- `0x180109e0c`
- `0x180132a00`
- `0x180157cb0`
- `0x1801586d0`
- `0x180159e78`
- `0x1801b568c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023c74`
- `KERNEL32!GetLastError` at `0x180023c74`
- `KERNEL32!CreateEventExW` at `0x180023c3b`
- `KERNEL32!CreateEventExW` at `0x180023c3b`
- `OLEAUT32!__imp_SysAllocString` at `0x180024196`
- `OLEAUT32!__imp_SysAllocString` at `0x180024572`
- `OLEAUT32!__imp_SysAllocString` at `0x180024196`
- `OLEAUT32!__imp_SysAllocString` at `0x180024572`
- `OLEAUT32!__imp_SysFreeString` at `0x1800241cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800241cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800245a8`
- `OLEAUT32!__imp_VariantInit` at `0x180024288`
- `OLEAUT32!__imp_VariantInit` at `0x180024288`
- `OLEAUT32!__imp_VariantClear` at `0x180024351`
- `OLEAUT32!__imp_VariantClear` at `0x180024351`
- `ole32!CoInitializeEx` at `0x180023b93`
- `ole32!CoInitializeEx` at `0x180023b93`
- `ole32!CoUninitialize` at `0x18002485a`
- `ole32!CoUninitialize` at `0x18002485a`

## string_xrefs

- `0x180024927`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180024152`: `MxdcImageCompressionType`
- `0x180023c8c`: `Successfully created named event: %ws.`
- `0x180023c5d`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023c93`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023d18`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023d9e`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023e29`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023e74`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023eaf`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023f59`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180024705`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x18002478f`: `PrintConfig::V4MxdcGetPDEVAdjustment`
- `0x180023d97`: `Cache hit for printer %ws. Cache size %d`
- `0x180023c56`: `Failed to create named event %ws.`
- `0x180023e6d`: `Cache miss for printer %ws. Cache size %d`
- `0x180023e22`: `Retrieved from cache: DPI: %d(%ws), Landscape %d, ImageArea {L:%d, B:%d, R:%d, T:%d}, ImageType: %d, PaperSize {%d, %d}`
- `0x180023f74`: `Printer %ws supports JavaScript customization. This function call may take long to complete.`
- `0x180023ea8`: `Cache find for %ws with 0x%x. Cache size %d`
- `0x180024788`: `Inserted into cache: DPI: %d(%ws), Landscape %d, ImageArea {L:%d, B:%d, R:%d, T:%d}, ImageType: %d, PaperSize {%d, %d}`
- `0x18002472b`: `Cache insertion for printer %ws. Cache size %d`
- `0x1800247e2`: `Cache insertion for printer %ws with 0x%x. Cache size %d`
- `0x1800247ba`: `Cache insert found duplicate entry for printer %ws. Cache size %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
void __fastcall PrintConfig::V4MxdcGetPDEVAdjustment(
        PrintConfig *this,
        void *a2,
        struct _devicemodeW *a3,
        const struct _devicemodeW *a4,
        __int64 a5,
        const void *a6,
        struct PrintPropertiesCollection *a7)
{
  unsigned int v7; // r13d
  unsigned int v9; // r15d
  struct PrintPropertiesCollection *v11; // r14
  HANDLE Event; // rbx
  int v13; // edi
  HRESULT v14; // eax
  signed int v15; // eax
  _WORD *v16; // rdx
  unsigned __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r8
  int take_hevent_ownership; // eax
  wchar_t *v22; // rdx
  struct PrintConfigData *v23; // rcx
  int v24; // r9d
  char *v25; // r12
  unsigned __int16 **v26; // r8
  const wchar_t *v27; // r14
  char v28; // si
  unsigned __int16 **v29; // r8
  unsigned __int16 **v30; // r8
  unsigned __int16 *v31; // rcx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  unsigned __int16 **v36; // r8
  int v37; // r14d
  int v38; // esi
  __int64 v39; // r9
  struct PrintConfigData *v40; // rbx
  wchar_t *v41; // rax
  __int64 v42; // r8
  int PDEVAdjustment; // eax
  int v44; // eax
  struct PrintPropertiesCollection *v45; // r13
  PrintNamedProperty *propertiesCollection; // r14
  LONG v47; // eax
  int v48; // eax
  int v49; // eax
  struct IPrintSchemaTicket *v50; // rsi
  __int64 v51; // r15
  BSTR v52; // rax
  OLECHAR *v53; // rbx
  int v54; // esi
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  unsigned __int64 v60; // r8
  LONG ImageTypeFromRegistry; // eax
  _DWORD *pBuf; // rbx
  int v63; // eax
  unsigned int v64; // r9d
  unsigned int v65; // edx
  unsigned int v66; // r8d
  unsigned int v67; // ecx
  _DWORD *v68; // r15
  struct IPrintSchemaTicket *v69; // rsi
  __int64 v70; // r13
  BSTR v71; // rax
  OLECHAR *v72; // rbx
  int v73; // esi
  int v74; // eax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  int v78; // eax
  int v79; // eax
  WCHAR *v80; // rdx
  int v81; // r9d
  unsigned __int16 **v82; // r8
  const wchar_t *v83; // r9
  int v84; // [rsp+28h] [rbp-E0h]
  __int64 v85; // [rsp+28h] [rbp-E0h]
  __int64 v86; // [rsp+28h] [rbp-E0h]
  void *v87; // [rsp+30h] [rbp-D8h]
  void *v88; // [rsp+30h] [rbp-D8h]
  __int64 v89; // [rsp+38h] [rbp-D0h]
  char v90; // [rsp+68h] [rbp-A0h]
  int v91; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v92[2]; // [rsp+70h] [rbp-98h] BYREF
  struct PrintConfigData *v93; // [rsp+78h] [rbp-90h] BYREF
  struct PrintConfigData *v94[2]; // [rsp+80h] [rbp-88h] BYREF
  struct PrintPropertiesCollection *v95; // [rsp+90h] [rbp-78h]
  unsigned int v96[2]; // [rsp+98h] [rbp-70h] BYREF
  __int128 v97; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v98; // [rsp+B0h] [rbp-58h]
  __int64 v99; // [rsp+C0h] [rbp-48h]
  int v100; // [rsp+C8h] [rbp-40h] BYREF
  int v101; // [rsp+CCh] [rbp-3Ch] BYREF
  HANDLE hPrinter; // [rsp+D0h] [rbp-38h]
  struct IPrintSchemaTicket *v103; // [rsp+D8h] [rbp-30h] BYREF
  struct PrintConfigData *v104; // [rsp+E0h] [rbp-28h] BYREF
  PrintConfig *v105; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v106; // [rsp+F0h] [rbp-18h] BYREF
  struct _devicemodeW *v107; // [rsp+F8h] [rbp-10h]
  __int64 v108; // [rsp+100h] [rbp-8h] BYREF
  struct IPrinterQueue *v109; // [rsp+108h] [rbp+0h] BYREF
  int v110; // [rsp+110h] [rbp+8h]
  __int64 v111; // [rsp+118h] [rbp+10h] BYREF
  __int64 v112; // [rsp+120h] [rbp+18h] BYREF
  void *Block; // [rsp+128h] [rbp+20h] BYREF
  VARIANTARG pvarg; // [rsp+130h] [rbp+28h] BYREF
  __int128 v115; // [rsp+148h] [rbp+40h] BYREF
  __int64 v116; // [rsp+158h] [rbp+50h]
  __int64 v117; // [rsp+160h] [rbp+58h]
  char *pExceptionObject[4]; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int16 *v119[2]; // [rsp+188h] [rbp+80h] BYREF
  __int128 v120; // [rsp+198h] [rbp+90h]
  _OWORD v121[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  char v122[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  _QWORD v123[13]; // [rsp+1D0h] [rbp+C8h] BYREF
  _QWORD *v124; // [rsp+238h] [rbp+130h]
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v117 = -2;
  v7 = (unsigned int)a4;
  v107 = a3;
  v9 = (unsigned int)a2;
  hPrinter = this;
  v11 = a7;
  v95 = a7;
  *(_QWORD *)v96 = a5;
  LODWORD(Event) = 0;
  if ( !a7 || (unsigned int)a6 < 0x10 || (unsigned int)a6 < 32 * (unsigned __int64)a7->numberOfProperties + 16 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
    throw (hr_error *)pExceptionObject;
  }
  v13 = 0;
  v110 = 0;
  v14 = CoInitializeEx(0, 0);
  if ( v14 >= 0 )
  {
    v13 = 1;
    v110 = 1;
  }
  else if ( v14 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v14);
    throw (hr_error *)pExceptionObject;
  }
  v115 = 0;
  v116 = 0;
  v15 = Win32StructRAII__PRINTER_INFO_4W_::FillUsing__lambda_394aa5f26f149cae1cbff3782c40bd22___((__int64 *)&v115, this);
  if ( v15 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v15);
    throw (hr_error *)pExceptionObject;
  }
  v16 = *(_WORD **)v115;
  *(_OWORD *)v119 = 0;
  v120 = 0;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  std::wstring::_Construct<1,unsigned short const *>(v119, v16, v17);
  v18 = 1;
  if ( !_InterlockedExchange((volatile __int32 *)&g_IsWatchingFormChangedEvent, 1) )
  {
    v93 = 0;
    Event = CreateEventExW(0, L"Global_FormChanged{A587A07B-B872-48CE-8D30-522121ABD913}", 1u, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Successfully created named event: %ws.",
        L"Global_FormChanged{A587A07B-B872-48CE-8D30-522121ABD913}");
      v123[0] = off_1801CC508;
      v123[1] = L"Global_FormChanged{A587A07B-B872-48CE-8D30-522121ABD913}";
      v124 = v123;
      v93 = 0;
      take_hevent_ownership = wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
                                v19,
                                Event,
                                v20,
                                (__int64)v122);
      LODWORD(Event) = 0;
      if ( take_hevent_ownership < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          7358,
          (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)take_hevent_ownership,
          v84);
      if ( v124 )
        (*(void (__fastcall **)(_QWORD *))(*v124 + 24LL))(v124);
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Watching named event: %ws.",
        L"Global_FormChanged{A587A07B-B872-48CE-8D30-522121ABD913}");
    }
    else
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Failed to create named event %ws.",
        L"Global_FormChanged{A587A07B-B872-48CE-8D30-522121ABD913}");
      g_IsWatchingFormChangedEvent = 0;
    }
  }
  Block = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v22 = (wchar_t *)v119;
  if ( *((_QWORD *)&v120 + 1) > 7u )
    v22 = v119[0];
  v24 = DevModeLruCache<PDEVAdjustmentInfo>::Find(v18, v22, this, a3->dmDeviceName, &Block);
  v25 = (char *)Block;
  if ( v24 )
  {
    v28 = 0;
    v90 = 0;
    if ( v24 == 1 )
    {
      v29 = v119;
      if ( *((_QWORD *)&v120 + 1) > 7u )
        v29 = (unsigned __int16 **)v119[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Cache miss for printer %ws. Cache size %d",
        v29,
        (unsigned int)qword_1802A5928);
    }
    else if ( v24 < 0 )
    {
      v30 = v119;
      if ( *((_QWORD *)&v120 + 1) > 7u )
        v30 = (unsigned __int16 **)v119[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Cache find for %ws with 0x%x. Cache size %d",
        v30);
    }
  }
  else
  {
    v90 = 1;
    v26 = v119;
    if ( *((_QWORD *)&v120 + 1) > 7u )
      v26 = (unsigned __int16 **)v119[0];
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::V4MxdcGetPDEVAdjustment",
      L"Cache hit for printer %ws. Cache size %d",
      v26,
      (unsigned int)qword_1802A5928);
    v27 = L"Used";
    if ( !(unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12)) )
      v27 = L"Unused";
    LOBYTE(v87) = *((_DWORD *)v25 + 1);
    LODWORD(v85) = *(_DWORD *)v25;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::V4MxdcGetPDEVAdjustment",
      L"Retrieved from cache: DPI: %d(%ws), Landscape %d, ImageArea {L:%d, B:%d, R:%d, T:%d}, ImageType: %d, PaperSize {%d, %d}",
      (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)),
      v27,
      v85);
    v28 = 1;
    v11 = v95;
    LODWORD(Event) = 0;
  }
  v109 = 0;
  v103 = 0;
  v108 = 0;
  v91 = 0;
  if ( !v28 )
  {
    v31 = (unsigned __int16 *)v119;
    if ( *((_QWORD *)&v120 + 1) > 7u )
      v31 = v119[0];
    v32 = PrintConfig::CPrinterQueue::Create(v31, &v109);
    if ( v32 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v32);
      throw (hr_error *)pExceptionObject;
    }
    v33 = PrintConfig::CPrintTicket::Create(v109, v107, &v103);
    if ( v33 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v33);
      throw (hr_error *)pExceptionObject;
    }
    v34 = (**(__int64 (__fastcall ***)(struct IPrintSchemaTicket *, GUID *, __int64 *))v103)(
            v103,
            &GUID_cf409217_79b9_4fb3_9f9c_9c13dbcee658,
            &v108);
    if ( v34 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v34);
      throw (hr_error *)pExceptionObject;
    }
    v35 = IsDriverJScriptCapable(hPrinter, &v91);
    if ( v35 < 0 )
    {
      hr_error::hr_error((hr_error *)pExceptionObject, v35);
      throw (hr_error *)pExceptionObject;
    }
    LODWORD(Event) = v91;
    v36 = v119;
    if ( v91 )
    {
      if ( *((_QWORD *)&v120 + 1) > 7u )
        v36 = (unsigned __int16 **)v119[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Printer %ws supports JavaScript customization. This function call may take long to complete.",
        v36);
    }
    else
    {
      if ( *((_QWORD *)&v120 + 1) > 7u )
        v36 = (unsigned __int16 **)v119[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Printer %ws does not support JavaScript customization. Using non-customizable imageable area code.",
        v36);
      PrintConfig::AvoidIteratingProperties_RAII::AvoidIteratingProperties_RAII(
        (PrintConfig::AvoidIteratingProperties_RAII *)&v104,
        v11);
      v37 = 0;
      v92[0] = 0;
      v93 = 0;
      v38 = CreatePrintConfigData(hPrinter, &v93);
      v40 = v93;
      if ( v38 >= 0 )
      {
        LOBYTE(v39) = 1;
        v41 = (wchar_t *)(*(__int64 (__fastcall **)(struct PrintConfigData *, _QWORD, _QWORD, __int64))(*(_QWORD *)v93 + 8LL))(
                           v93,
                           0,
                           0,
                           v39);
        if ( v41
          || (LOBYTE(v42) = 1,
              (v41 = (wchar_t *)(*(__int64 (__fastcall **)(struct PrintConfigData *, _QWORD, __int64))(*(_QWORD *)v40 + 8LL))(
                                  v40,
                                  0,
                                  v42)) != 0) )
        {
          v38 = IsDataFileAGPD(v41, v92);
          v37 = v92[0];
        }
        else
        {
          v38 = -2147024894;
        }
      }
      if ( v40 )
        (*(void (__fastcall **)(struct PrintConfigData *, __int64))(*(_QWORD *)v40 + 32LL))(v40, 1);
      if ( v38 < 0 )
      {
        hr_error::hr_error((hr_error *)pExceptionObject, v38);
        throw (hr_error *)pExceptionObject;
      }
      LODWORD(v87) = 8;
      if ( v37 )
      {
        PDEVAdjustment = UniDrvUI::MxdcGetPDEVAdjustment(
                           (UniDrvUI *)hPrinter,
                           (void *)v9,
                           v107,
                           (const struct _devicemodeW *)v7,
                           *(__int64 *)v96,
                           v87,
                           (__int64)v95);
        if ( PDEVAdjustment < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, PDEVAdjustment);
          throw (hr_error *)pExceptionObject;
        }
      }
      else
      {
        v44 = PSUI::MxdcGetPDEVAdjustment(
                (PSUI *)hPrinter,
                (void *)v9,
                v107,
                (const struct _devicemodeW *)v7,
                *(__int64 *)v96,
                v87,
                (__int64)v95);
        if ( v44 < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, v44);
          throw (hr_error *)pExceptionObject;
        }
      }
      PrintConfig::AvoidIteratingProperties_RAII::~AvoidIteratingProperties_RAII((PrintConfig::AvoidIteratingProperties_RAII *)&v104);
      v28 = v90;
      LODWORD(Event) = v91;
    }
  }
  v45 = v95;
  propertiesCollection = v95->propertiesCollection;
  if ( propertiesCollection < &propertiesCollection[v95->numberOfProperties] )
  {
    while ( 1 )
    {
      if ( !wcscmp_0(L"MxdcDotsPerInch", propertiesCollection->propertyName) )
      {
        if ( propertiesCollection->propertyValue.ePropertyType != kPropertyTypeInt32 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
          throw (hr_error *)pExceptionObject;
        }
        if ( v28 )
        {
          if ( !v25[28] )
            goto LABEL_137;
          v47 = *((_DWORD *)v25 + 6);
          goto LABEL_75;
        }
        v92[0] = 0;
        v48 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v108 + 152LL))(v108, v92);
        if ( v48 != -2147023728 && v48 < 0 )
        {
          hr_error::hr_error((hr_error *)pExceptionObject, v48);
          throw (hr_error *)pExceptionObject;
        }
        if ( v48 < 0 )
        {
          BYTE12(v98) = 0;
          DWORD2(v98) = propertiesCollection->propertyValue.value.propertyInt32;
        }
        else
        {
          v49 = v92[0];
          propertiesCollection->propertyValue.value.propertyInt32 = v92[0];
          DWORD2(v98) = v49;
          BYTE12(v98) = 1;
        }
      }
      else
      {
        if ( !wcscmp_0(L"MxdcImageCompressionType", propertiesCollection->propertyName) )
        {
          if ( propertiesCollection->propertyValue.ePropertyType != kPropertyTypeInt32 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
            throw (hr_error *)pExceptionObject;
          }
          if ( v28 )
          {
            v47 = *((_DWORD *)v25 + 5);
LABEL_75:
            propertiesCollection->propertyValue.value.propertyInt32 = v47;
            goto LABEL_137;
          }
          v104 = 0;
          v50 = v103;
          v51 = *(_QWORD *)v103;
          v52 = SysAllocString(L"PageOutputQuality");
          v53 = v52;
          v94[0] = (struct PrintConfigData *)v52;
          if ( !v52 )
            ATL::AtlThrowImpl(-2147024882);
          v54 = (*(__int64 (__fastcall **)(struct IPrintSchemaTicket *, BSTR, struct PrintConfigData **))(v51 + 80))(
                  v50,
                  v52,
                  &v104);
          SysFreeString(v53);
          if ( v54 < 0 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, v54);
            throw (hr_error *)pExceptionObject;
          }
          propertiesCollection->propertyValue.value.propertyInt32 = 2;
          DWORD1(v98) = 2;
          if ( !v54 )
          {
            v94[0] = 0;
            v55 = (*(__int64 (__fastcall **)(struct PrintConfigData *, struct PrintConfigData **))(*(_QWORD *)v104 + 88LL))(
                    v104,
                    v94);
            if ( v55 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v55);
              throw (hr_error *)pExceptionObject;
            }
            v112 = 0;
            v56 = (*(__int64 (__fastcall **)(struct PrintConfigData *, __int64 *))(*(_QWORD *)v94[0] + 56LL))(
                    v94[0],
                    &v112);
            if ( v56 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v56);
              throw (hr_error *)pExceptionObject;
            }
            v105 = 0;
            v57 = (**(__int64 (__fastcall ***)(__int64, GUID *, PrintConfig **))v112)(
                    v112,
                    &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60,
                    &v105);
            if ( v57 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v57);
              throw (hr_error *)pExceptionObject;
            }
            v111 = 0;
            v58 = (**(__int64 (__fastcall ***)(PrintConfig *, GUID *, __int64 *))v105)(
                    v105,
                    &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                    &v111);
            if ( v58 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v58);
              throw (hr_error *)pExceptionObject;
            }
            VariantInit(&pvarg);
            v59 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, VARIANTARG *))(*(_QWORD *)v111 + 352LL))(
                    v111,
                    L"name",
                    &pvarg);
            if ( v59 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v59);
              throw (hr_error *)pExceptionObject;
            }
            if ( pvarg.vt != 8 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
              throw (hr_error *)pExceptionObject;
            }
            memset(v121, 0, sizeof(v121));
            v60 = -1;
            do
              ++v60;
            while ( *(_WORD *)(pvarg.llVal + 2 * v60) );
            std::wstring::_Construct<1,unsigned short const *>(v121, pvarg.bstrVal, v60);
            if ( PrintConfig::CPrintSchemaElement::IsInKeywordsNamespace(v105, v121) )
            {
              PrintConfig::CPrintSchemaElement::GetSuffix(pExceptionObject, v121);
              ImageTypeFromRegistry = PrintConfig::GetImageTypeFromRegistry(&v109, pExceptionObject);
              propertiesCollection->propertyValue.value.propertyInt32 = ImageTypeFromRegistry;
              DWORD1(v98) = ImageTypeFromRegistry;
              std::wstring::~wstring(pExceptionObject);
            }
            std::wstring::~wstring((char **)v121);
            VariantClear(&pvarg);
            if ( v111 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
            if ( v105 )
              (*(void (__fastcall **)(PrintConfig *))(*(_QWORD *)v105 + 16LL))(v105);
            if ( v112 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
            if ( v94[0] )
              (*(void (__fastcall **)(struct PrintConfigData *))(*(_QWORD *)v94[0] + 16LL))(v94[0]);
          }
          v23 = v104;
          if ( v104 )
            (*(void (__fastcall **)(struct PrintConfigData *))(*(_QWORD *)v104 + 16LL))(v104);
LABEL_136:
          v28 = v90;
          goto LABEL_137;
        }
        if ( !wcscmp_0(L"MxdcImageableArea", propertiesCollection->propertyName) )
        {
          if ( propertiesCollection->propertyValue.ePropertyType != kPropertyTypeBuffer
            || propertiesCollection->propertyValue.value.propertyInt32 != 16 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
            throw (hr_error *)pExceptionObject;
          }
          pBuf = propertiesCollection->propertyValue.value.propertyBlob.pBuf;
          if ( v28 )
          {
            *(_OWORD *)pBuf = *(_OWORD *)(v25 + 4);
          }
          else if ( v91 )
          {
            *(_QWORD *)v96 = 0;
            v63 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v108 + 120LL))(v108, v96);
            if ( v63 < 0 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, v63);
              throw (hr_error *)pExceptionObject;
            }
            *(_OWORD *)v94 = 0;
            PrintConfig::ExtractImageableArea(v96, (int *)v94);
            v64 = (unsigned int)v94[0];
            pBuf[1] = v94[0];
            v65 = HIDWORD(v94[0]);
            *pBuf = HIDWORD(v94[0]);
            v66 = v64 + HIDWORD(v94[1]);
            pBuf[3] = v64 + HIDWORD(v94[1]);
            v67 = v65 + LODWORD(v94[1]);
            pBuf[2] = v65 + LODWORD(v94[1]);
            *(_QWORD *)((char *)&v97 + 4) = __PAIR64__(v64, v65);
            HIDWORD(v97) = v67;
            LODWORD(v98) = v66;
            v23 = *(struct PrintConfigData **)v96;
            if ( *(_QWORD *)v96 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v96 + 16LL))(*(_QWORD *)v96);
          }
          else
          {
            *(_QWORD *)((char *)&v97 + 4) = *(_QWORD *)pBuf;
            HIDWORD(v97) = pBuf[2];
            LODWORD(v98) = pBuf[3];
          }
        }
        else
        {
          if ( wcscmp_0(L"MxdcLandscapeRotation", propertiesCollection->propertyName) )
          {
            if ( wcscmp_0(L"MxdcPhysicalPaperDimensions", propertiesCollection->propertyName) )
              goto LABEL_137;
            if ( propertiesCollection->propertyValue.ePropertyType != kPropertyTypeBuffer
              || propertiesCollection->propertyValue.value.propertyInt32 != 8 )
            {
              hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
              throw (hr_error *)pExceptionObject;
            }
            v68 = propertiesCollection->propertyValue.value.propertyBlob.pBuf;
            if ( v28 )
            {
              *(_QWORD *)v68 = *((_QWORD *)v25 + 4);
              goto LABEL_137;
            }
            if ( !(_DWORD)Event )
            {
              v99 = *(_QWORD *)v68;
              goto LABEL_137;
            }
            v93 = 0;
            v69 = v103;
            v70 = *(_QWORD *)v103;
            v71 = SysAllocString(L"PageMediaSize");
            v72 = v71;
            v94[0] = (struct PrintConfigData *)v71;
            if ( !v71 )
              ATL::AtlThrowImpl(-2147024882);
            v73 = (*(__int64 (__fastcall **)(struct IPrintSchemaTicket *, BSTR, struct PrintConfigData **))(v70 + 80))(
                    v69,
                    v71,
                    &v93);
            SysFreeString(v72);
            if ( !v73 )
            {
              v94[0] = 0;
              v74 = (*(__int64 (__fastcall **)(struct PrintConfigData *, struct PrintConfigData **))(*(_QWORD *)v93 + 88LL))(
                      v93,
                      v94);
              if ( v74 < 0 )
              {
                hr_error::hr_error((hr_error *)pExceptionObject, v74);
                throw (hr_error *)pExceptionObject;
              }
              v106 = 0;
              v75 = (**(__int64 (__fastcall ***)(struct PrintConfigData **, GUID *, __int64 *))v94[0])(
                      (struct PrintConfigData **)v94[0],
                      &GUID_68746729_f493_4830_a10f_69028774605d,
                      &v106);
              if ( v75 < 0 )
              {
                hr_error::hr_error((hr_error *)pExceptionObject, v75);
                throw (hr_error *)pExceptionObject;
              }
              v100 = 0;
              v101 = 0;
              v76 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v106 + 112LL))(v106, &v100);
              if ( v76 < 0 )
              {
                hr_error::hr_error((hr_error *)pExceptionObject, v76);
                throw (hr_error *)pExceptionObject;
              }
              v77 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v106 + 120LL))(v106, &v101);
              if ( v77 < 0 )
              {
                hr_error::hr_error((hr_error *)pExceptionObject, v77);
                throw (hr_error *)pExceptionObject;
              }
              v78 = v100;
              *v68 = v100;
              LODWORD(v99) = v78;
              v79 = v101;
              v68[1] = v101;
              HIDWORD(v99) = v79;
              if ( v106 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
              if ( v94[0] )
                (*(void (__fastcall **)(struct PrintConfigData *))(*(_QWORD *)v94[0] + 16LL))(v94[0]);
            }
            v23 = v93;
            if ( v93 )
              (*(void (__fastcall **)(struct PrintConfigData *))(*(_QWORD *)v93 + 16LL))(v93);
            v45 = v95;
            goto LABEL_136;
          }
          if ( propertiesCollection->propertyValue.ePropertyType != kPropertyTypeInt32 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, -2147024809);
            throw (hr_error *)pExceptionObject;
          }
          if ( v28 )
          {
            v47 = *(_DWORD *)v25;
            goto LABEL_75;
          }
          if ( (_DWORD)Event )
          {
            propertiesCollection->propertyValue.value.propertyInt32 = 0;
            LODWORD(v97) = 0;
          }
          else
          {
            LODWORD(v97) = propertiesCollection->propertyValue.value.propertyInt32;
          }
        }
      }
LABEL_137:
      if ( ++propertiesCollection >= &v45->propertiesCollection[(unsigned __int64)v45->numberOfProperties] )
        break;
      LODWORD(Event) = v91;
    }
  }
  if ( !v28 )
  {
    v80 = (WCHAR *)v119;
    if ( *((_QWORD *)&v120 + 1) > 7u )
      v80 = v119[0];
    v81 = DevModeLruCache<PDEVAdjustmentInfo>::Insert(
            (__int64)v23,
            v80,
            hPrinter,
            v107->dmDeviceName,
            (__int64)&v97,
            (bool)v87);
    v82 = v119;
    if ( v81 )
    {
      if ( v81 == 1 )
      {
        if ( *((_QWORD *)&v120 + 1) > 7u )
          v82 = (unsigned __int16 **)v119[0];
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "PrintConfig::V4MxdcGetPDEVAdjustment",
          L"Cache insert found duplicate entry for printer %ws. Cache size %d",
          v82,
          (unsigned int)qword_1802A5928);
      }
      else
      {
        if ( *((_QWORD *)&v120 + 1) > 7u )
          v82 = (unsigned __int16 **)v119[0];
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::V4MxdcGetPDEVAdjustment",
          L"Cache insertion for printer %ws with 0x%x. Cache size %d",
          v82);
      }
    }
    else
    {
      if ( *((_QWORD *)&v120 + 1) > 7u )
        v82 = (unsigned __int16 **)v119[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Cache insertion for printer %ws. Cache size %d",
        v82,
        (unsigned int)qword_1802A5928);
      v83 = L"Used";
      if ( !BYTE12(v98) )
        v83 = L"Unused";
      LODWORD(v89) = v98;
      LODWORD(v88) = DWORD1(v97);
      LODWORD(v86) = v97;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::V4MxdcGetPDEVAdjustment",
        L"Inserted into cache: DPI: %d(%ws), Landscape %d, ImageArea {L:%d, B:%d, R:%d, T:%d}, ImageType: %d, PaperSize {%d, %d}",
        DWORD2(v98),
        v83,
        v86,
        v88,
        v89,
        HIDWORD(v97),
        DWORD2(v97),
        DWORD1(v98),
        v99,
        HIDWORD(v99));
    }
  }
  if ( v108 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
  if ( v103 )
    (*(void (__fastcall **)(struct IPrintSchemaTicket *))(*(_QWORD *)v103 + 16LL))(v103);
  if ( v109 )
    (*(void (__fastcall **)(struct IPrinterQueue *))(*(_QWORD *)v109 + 16LL))(v109);
  if ( v25 )
    operator delete(v25);
  std::wstring::~wstring((char **)v119);
  std::vector<char>::~vector<char>((char **)&v115);
  if ( v13 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180023af4  mov     rax, rsp
0x180023af7  push    rbp
0x180023af8  push    rbx
0x180023af9  push    rsi
0x180023afa  push    rdi
0x180023afb  push    r12
0x180023afd  push    r13
0x180023aff  push    r14
0x180023b01  push    r15
0x180023b03  lea     rbp, [rax-198h]
0x180023b0a  sub     rsp, 258h
0x180023b11  mov     [rbp+190h+var_138], 0FFFFFFFFFFFFFFFEh
0x180023b19  movaps  xmmword ptr [rax-58h], xmm6
0x180023b1d  mov     rax, cs:__security_cookie
0x180023b24  xor     rax, rsp
0x180023b27  mov     qword ptr [rbp+190h+var_58], rax
0x180023b2e  mov     r13d, r9d
0x180023b31  mov     r12, r8
0x180023b34  mov     [rbp+190h+var_1A0], r8
0x180023b38  mov     r15d, edx
0x180023b3b  mov     rsi, rcx
0x180023b3e  mov     [rbp+190h+hPrinter], rcx
0x180023b42  mov     r14, qword ptr [rbp+190h+arg_30]
0x180023b49  mov     [rbp+190h+var_208], r14
0x180023b4d  mov     rax, [rbp+190h+arg_20]
0x180023b54  mov     qword ptr [rbp+190h+var_200], rax
0x180023b58  xor     ebx, ebx
0x180023b5a  test    r14, r14
0x180023b5d  jz      loc_1800248E9
0x180023b63  cmp     dword ptr [rbp+190h+arg_28], 10h
0x180023b6a  jb      loc_1800248E9
0x180023b70  mov     ecx, [r14]
0x180023b73  shl     rcx, 5
0x180023b77  add     rcx, 10h
0x180023b7b  mov     eax, dword ptr [rbp+190h+arg_28]
0x180023b81  cmp     rax, rcx
0x180023b84  jb      loc_1800248E9
0x180023b8a  mov     edi, ebx
0x180023b8c  mov     [rbp+190h+var_188], ebx
0x180023b8f  xor     edx, edx; dwCoInit
0x180023b91  xor     ecx, ecx; pvReserved
0x180023b93  call    cs:__imp_CoInitializeEx
0x180023b9a  nop     dword ptr [rax+rax+00h]
0x180023b9f  test    eax, eax
0x180023ba1  jns     short loc_180023BB0
0x180023ba3  cmp     eax, 80010106h
0x180023ba8  jnz     loc_1800248B1
0x180023bae  jmp     short loc_180023BB8
0x180023bb0  mov     edi, 1
0x180023bb5  mov     [rbp+190h+var_188], edi
0x180023bb8  xorps   xmm0, xmm0
0x180023bbb  movdqu  [rbp+190h+var_150], xmm0
0x180023bc0  mov     [rbp+190h+var_140], rbx
0x180023bc4  mov     rdx, rsi
0x180023bc7  lea     rcx, [rbp+190h+var_150]
0x180023bcb  call    Win32StructRAII__PRINTER_INFO_4W___FillUsing__lambda_394aa5f26f149cae1cbff3782c40bd22___
0x180023bd0  test    eax, eax
0x180023bd2  js      loc_180024908
0x180023bd8  mov     rax, qword ptr [rbp+190h+var_150]
0x180023bdc  mov     rdx, [rax]
0x180023bdf  xorps   xmm0, xmm0
0x180023be2  movups  xmmword ptr [rbp+190h+var_110], xmm0
0x180023be9  xorps   xmm1, xmm1
0x180023bec  movdqu  [rbp+190h+var_100], xmm1
0x180023bf4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023bf8  inc     r8
0x180023bfb  cmp     [rdx+r8*2], bx
0x180023c00  jnz     short loc_180023BF8
0x180023c02  lea     rcx, [rbp+190h+var_110]
0x180023c09  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023c0e  nop
0x180023c0f  mov     ecx, 1
0x180023c14  mov     eax, ecx
0x180023c16  xchg    eax, cs:?g_IsWatchingFormChangedEvent@@3KA; ulong g_IsWatchingFormChangedEvent
0x180023c1c  test    eax, eax
0x180023c1e  jnz     loc_180023D25
0x180023c24  mov     [rsp+290h+var_220], rbx
0x180023c29  mov     r9d, 1F0003h; dwDesiredAccess
0x180023c2f  mov     r8d, ecx; dwFlags
0x180023c32  lea     rdx, Name; "Global_FormChanged{A587A07B-B872-48CE-8"...
0x180023c39  xor     ecx, ecx; lpEventAttributes
0x180023c3b  call    cs:__imp_CreateEventExW
0x180023c42  nop     dword ptr [rax+rax+00h]
0x180023c47  mov     rbx, rax
0x180023c4a  test    rax, rax
0x180023c4d  jnz     short loc_180023C74
0x180023c4f  lea     r8, Name; "Global_FormChanged{A587A07B-B872-48CE-8"...
0x180023c56  lea     rdx, aFailedToCreate_0; "Failed to create named event %ws."
0x180023c5d  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023c64  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023c69  mov     cs:?g_IsWatchingFormChangedEvent@@3KA, ebx; ulong g_IsWatchingFormChangedEvent
0x180023c6f  jmp     loc_180023D25
0x180023c74  call    cs:__imp_GetLastError
0x180023c7b  nop     dword ptr [rax+rax+00h]
0x180023c80  mov     [rsp+290h+var_220], rbx
0x180023c85  lea     r8, Name; "Global_FormChanged{A587A07B-B872-48CE-8"...
0x180023c8c  lea     rdx, aSuccessfullyCr; "Successfully created named event: %ws."
0x180023c93  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023c9a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023c9f  lea     rax, off_1801CC508
0x180023ca6  mov     [rbp+190h+var_C8], rax
0x180023cad  lea     rax, Name; "Global_FormChanged{A587A07B-B872-48CE-8"...
0x180023cb4  mov     [rbp+190h+var_C0], rax
0x180023cbb  lea     rax, [rbp+190h+var_C8]
0x180023cc2  mov     [rbp+190h+var_60], rax
0x180023cc9  mov     [rsp+290h+var_220], 0
0x180023cd2  lea     r9, [rbp+190h+var_D0]
0x180023cd9  mov     rdx, rbx
0x180023cdc  call    ?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)
0x180023ce1  mov     rcx, [rbp+198h]; this
0x180023ce8  xor     ebx, ebx
0x180023cea  test    eax, eax
0x180023cec  js      loc_180024924
0x180023cf2  mov     rcx, [rbp+190h+var_60]
0x180023cf9  test    rcx, rcx
0x180023cfc  jz      short loc_180023D0A
0x180023cfe  mov     rax, [rcx]
0x180023d01  mov     rax, [rax+18h]
0x180023d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d0a  lea     r8, Name; "Global_FormChanged{A587A07B-B872-48CE-8"...
0x180023d11  lea     rdx, aWatchingNamedE; "Watching named event: %ws."
0x180023d18  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023d1f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023d24  nop
0x180023d25  mov     [rbp+190h+Block], rbx
0x180023d29  xorps   xmm6, xmm6
0x180023d2c  xor     eax, eax
0x180023d2e  movups  [rbp+190h+var_1F8], xmm6
0x180023d32  movups  [rbp+190h+var_1E8], xmm6
0x180023d36  mov     [rbp+190h+var_1D8], rax
0x180023d3a  lea     rdx, [rbp+190h+var_110]
0x180023d41  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023d49  cmova   rdx, [rbp+190h+var_110]
0x180023d51  lea     rax, [rbp+190h+Block]
0x180023d55  mov     [rsp+290h+var_270], rax
0x180023d5a  mov     r9, r12
0x180023d5d  mov     r8, rsi
0x180023d60  call    ?Find@?$DevModeLruCache@UPDEVAdjustmentInfo@@@@QEAAJPEBGQEAXPEBU_devicemodeW@@PEAPEAUPDEVAdjustmentInfo@@@Z; DevModeLruCache<PDEVAdjustmentInfo>::Find(ushort const *,void * const,_devicemodeW const *,PDEVAdjustmentInfo * *)
0x180023d65  mov     r9d, eax
0x180023d68  mov     r12, [rbp+190h+Block]
0x180023d6c  test    eax, eax
0x180023d6e  jnz     loc_180023E42
0x180023d74  mov     byte ptr [rsp+290h+var_230], 1
0x180023d79  lea     r8, [rbp+190h+var_110]
0x180023d80  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023d88  cmova   r8, [rbp+190h+var_110]
0x180023d90  mov     r9d, dword ptr cs:qword_1802A5928
0x180023d97  lea     rdx, aCacheHitForPri; "Cache hit for printer %ws. Cache size %"...
0x180023d9e  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023da5  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023daa  mov     ecx, [r12+24h]
0x180023daf  mov     edx, [r12+20h]
0x180023db4  mov     r8d, [r12+14h]
0x180023db9  mov     r9d, [r12+8]
0x180023dbe  mov     r10d, [r12+0Ch]
0x180023dc3  mov     r11d, [r12+10h]
0x180023dc8  mov     ebx, [r12+4]
0x180023dcd  mov     esi, [r12]
0x180023dd1  lea     r14, aUsed_0; "Used"
0x180023dd8  xorps   xmm0, xmm0
0x180023ddb  psrldq  xmm0, 0Ch
0x180023de0  movd    eax, xmm0
0x180023de4  test    al, al
0x180023de6  lea     rax, aUnused; "Unused"
0x180023ded  cmovz   r14, rax
0x180023df1  mov     dword ptr [rsp+290h+var_238], ecx
0x180023df5  mov     [rsp+290h+var_240], edx
0x180023df9  mov     [rsp+290h+var_248], r8d
0x180023dfe  mov     [rsp+290h+var_250], r9d
0x180023e03  mov     dword ptr [rsp+290h+var_258], r10d
0x180023e08  mov     dword ptr [rsp+290h+var_260], r11d
0x180023e0d  mov     dword ptr [rsp+290h+var_268], ebx
0x180023e11  mov     dword ptr [rsp+290h+var_270], esi
0x180023e15  mov     r9, r14
0x180023e18  psrldq  xmm6, 8
0x180023e1d  movd    r8d, xmm6
0x180023e22  lea     rdx, aRetrievedFromC; "Retrieved from cache: DPI: %d(%ws), Lan"...
0x180023e29  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023e30  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023e35  mov     sil, byte ptr [rsp+290h+var_230]
0x180023e3a  mov     r14, [rbp+190h+var_208]
0x180023e3e  xor     ebx, ebx
0x180023e40  jmp     short loc_180023EBB
0x180023e42  mov     sil, bl
0x180023e45  mov     byte ptr [rsp+290h+var_230], bl
0x180023e49  cmp     r9d, 1
0x180023e4d  jnz     short loc_180023E82
0x180023e4f  lea     r8, [rbp+190h+var_110]
0x180023e56  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023e5e  cmova   r8, [rbp+190h+var_110]
0x180023e66  mov     r9d, dword ptr cs:qword_1802A5928
0x180023e6d  lea     rdx, aCacheMissForPr; "Cache miss for printer %ws. Cache size "...
0x180023e74  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023e7b  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023e80  jmp     short loc_180023EBB
0x180023e82  test    r9d, r9d
0x180023e85  jns     short loc_180023EBB
0x180023e87  mov     eax, dword ptr cs:qword_1802A5928
0x180023e8d  lea     r8, [rbp+190h+var_110]
0x180023e94  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023e9c  cmova   r8, [rbp+190h+var_110]
0x180023ea4  mov     dword ptr [rsp+290h+var_270], eax
0x180023ea8  lea     rdx, aCacheFindForWs; "Cache find for %ws with 0x%x. Cache siz"...
0x180023eaf  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023eb6  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180023ebb  mov     [rbp+190h+var_190], rbx
0x180023ebf  mov     [rbp+190h+var_1C0], rbx
0x180023ec3  mov     [rbp+190h+var_198], rbx
0x180023ec7  mov     [rsp+290h+var_22C], ebx
0x180023ecb  test    sil, sil
0x180023ece  jnz     loc_1800240A4
0x180023ed4  lea     rcx, [rbp+190h+var_110]
0x180023edb  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023ee3  cmova   rcx, [rbp+190h+var_110]; unsigned __int16 *
0x180023eeb  lea     rdx, [rbp+190h+var_190]
0x180023eef  call    ?Create@CPrinterQueue@PrintConfig@@SAJPEBGAEAV?$CComPtr@UIPrinterQueue@@@ATL@@@Z; PrintConfig::CPrinterQueue::Create(ushort const *,ATL::CComPtr<IPrinterQueue> &)
0x180023ef4  test    eax, eax
0x180023ef6  js      loc_180024939
0x180023efc  lea     r8, [rbp+190h+var_1C0]; struct IPrintSchemaTicket **
0x180023f00  mov     rdx, [rbp+190h+var_1A0]; struct _devicemodeW *
0x180023f04  mov     rcx, [rbp+190h+var_190]; struct IPrinterQueue *
0x180023f08  call    ?Create@CPrintTicket@PrintConfig@@SAJPEAUIPrinterQueue@@PEBU_devicemodeW@@PEAPEAUIPrintSchemaTicket@@@Z; PrintConfig::CPrintTicket::Create(IPrinterQueue *,_devicemodeW const *,IPrintSchemaTicket * *)
0x180023f0d  test    eax, eax
0x180023f0f  js      loc_180024955
0x180023f15  mov     rcx, [rbp+190h+var_1C0]
0x180023f19  mov     rax, [rcx]
0x180023f1c  lea     r8, [rbp+190h+var_198]
0x180023f20  lea     rdx, _GUID_cf409217_79b9_4fb3_9f9c_9c13dbcee658
0x180023f27  mov     rax, [rax]
0x180023f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f2f  nop
0x180023f30  test    eax, eax
0x180023f32  js      loc_180024971
0x180023f38  lea     rdx, [rsp+290h+var_22C]
0x180023f3d  mov     rcx, [rbp+190h+hPrinter]
0x180023f41  call    IsDriverJScriptCapable
0x180023f46  test    eax, eax
0x180023f48  js      loc_18002498D
0x180023f4e  mov     ebx, [rsp+290h+var_22C]
0x180023f52  lea     r8, [rbp+190h+var_110]
0x180023f59  lea     rcx, aPrintconfigV4m_0; "PrintConfig::V4MxdcGetPDEVAdjustment"
0x180023f60  test    ebx, ebx
0x180023f62  jz      short loc_180023F85
0x180023f64  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023f6c  cmova   r8, [rbp+190h+var_110]
0x180023f74  lea     rdx, aPrinterWsSuppo; "Printer %ws supports JavaScript customi"...
0x180023f7b  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023f80  jmp     loc_1800240A4
0x180023f85  cmp     qword ptr [rbp+190h+var_100+8], 7
0x180023f8d  cmova   r8, [rbp+190h+var_110]
0x180023f95  lea     rdx, aPrinterWsDoesN; "Printer %ws does not support JavaScript"...
0x180023f9c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180023fa1  mov     rdx, r14; struct PrintPropertiesCollection *
0x180023fa4  lea     rcx, [rbp+190h+var_1B8]; this
0x180023fa8  call    ??0AvoidIteratingProperties_RAII@PrintConfig@@QEAA@PEAUPrintPropertiesCollection@@@Z; PrintConfig::AvoidIteratingProperties_RAII::AvoidIteratingProperties_RAII(PrintPropertiesCollection *)
0x180023fad  nop
0x180023fae  xor     eax, eax
0x180023fb0  mov     r14d, eax
0x180023fb3  mov     [rsp+290h+var_228], eax
0x180023fb7  mov     [rsp+290h+var_220], rax
0x180023fbc  lea     rdx, [rsp+290h+var_220]; struct PrintConfigData **
0x180023fc1  mov     rcx, [rbp+190h+hPrinter]; void *
0x180023fc5  call    ?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z; CreatePrintConfigData(void *,PrintConfigData * *)
0x180023fca  mov     esi, eax
0x180023fcc  mov     rbx, [rsp+290h+var_220]
0x180023fd1  test    eax, eax
0x180023fd3  js      short loc_180024028
0x180023fd5  mov     rax, [rbx]
0x180023fd8  mov     r9b, 1
0x180023fdb  xor     r8d, r8d
0x180023fde  xor     edx, edx
0x180023fe0  mov     rcx, rbx
0x180023fe3  mov     rax, [rax+8]
0x180023fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fec  test    rax, rax
0x180023fef  jnz     short loc_180024014
0x180023ff1  mov     rax, [rbx]
0x180023ff4  mov     r9b, 1
0x180023ff7  mov     r8b, r9b
0x180023ffa  xor     edx, edx
0x180023ffc  mov     rcx, rbx
0x180023fff  mov     rax, [rax+8]
0x180024003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024008  test    rax, rax
0x18002400b  jnz     short loc_180024014
0x18002400d  mov     esi, 80070002h
0x180024012  jmp     short loc_180024028
0x180024014  lea     rdx, [rsp+290h+var_228]; int *
0x180024019  mov     rcx, rax; Str
0x18002401c  call    ?IsDataFileAGPD@@YAJPEBGPEAH@Z; IsDataFileAGPD(ushort const *,int *)
0x180024021  mov     esi, eax
0x180024023  mov     r14d, [rsp+290h+var_228]
0x180024028  test    rbx, rbx
0x18002402b  jz      short loc_180024041
0x18002402d  mov     rax, [rbx]
0x180024030  mov     edx, 1
0x180024035  mov     rcx, rbx
0x180024038  mov     rax, [rax+20h]
0x18002403c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024041  test    esi, esi
  ... truncated ...
```
