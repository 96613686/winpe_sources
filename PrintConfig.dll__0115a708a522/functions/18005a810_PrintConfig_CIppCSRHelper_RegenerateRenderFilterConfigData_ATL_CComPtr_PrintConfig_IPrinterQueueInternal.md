# PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)

- ea: `0x18005a810`
- end: `0x18005b145`
- name: `?RegenerateRenderFilterConfigData@CIppCSRHelper@PrintConfig@@SAJAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z`
- size: `2357`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bb3c`

## callees

- `0x180003400`
- `0x180004564`
- `0x180006268`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x180022268`
- `0x180027334`
- `0x18003d134`
- `0x18005a640`
- `0x18005a810`
- `0x1801b56c8`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a94e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a9d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aa64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aaef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ab7f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a94e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a9d9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aa64`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005aaef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ab7f`
- `KERNEL32!WriteFile` at `0x18005ad3e`
- `KERNEL32!WriteFile` at `0x18005ad3e`
- `KERNEL32!DeleteFileW` at `0x18005ae98`
- `KERNEL32!DeleteFileW` at `0x18005ae98`
- `KERNEL32!CreateFileW` at `0x18005acb7`
- `KERNEL32!CreateFileW` at `0x18005acb7`
- `KERNEL32!FreeLibrary` at `0x18005adab`
- `KERNEL32!FreeLibrary` at `0x18005aede`
- `KERNEL32!FreeLibrary` at `0x18005adab`
- `KERNEL32!FreeLibrary` at `0x18005aede`
- `KERNEL32!CloseHandle` at `0x18005ad71`
- `KERNEL32!CloseHandle` at `0x18005ae64`
- `KERNEL32!CloseHandle` at `0x18005ad71`
- `KERNEL32!CloseHandle` at `0x18005ae64`
- `KERNEL32!SetLastError` at `0x18005ae72`
- `KERNEL32!SetLastError` at `0x18005ae72`
- `KERNEL32!GetLastError` at `0x18005acd1`
- `KERNEL32!GetLastError` at `0x18005ae25`
- `KERNEL32!GetLastError` at `0x18005ae53`
- `KERNEL32!GetLastError` at `0x18005acd1`
- `KERNEL32!GetLastError` at `0x18005ae25`
- `KERNEL32!GetLastError` at `0x18005ae53`
- `ole32!CoInitializeEx` at `0x18005a858`
- `ole32!CoInitializeEx` at `0x18005a858`
- `ole32!CoUninitialize` at `0x18005adea`
- `ole32!CoUninitialize` at `0x18005af1d`
- `ole32!CoUninitialize` at `0x18005adea`
- `ole32!CoUninitialize` at `0x18005af1d`
- `WINSPOOL!GetPrinterDataW` at `0x18005a8e1`
- `WINSPOOL!GetPrinterDataW` at `0x18005ac2b`
- `WINSPOOL!GetPrinterDataW` at `0x18005a8e1`
- `WINSPOOL!GetPrinterDataW` at `0x18005ac2b`

## string_xrefs

- `0x18005a991`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005a9ac`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005aa1c`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005aa37`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005aa8e`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005aac2`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005abad`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005abb9`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005ace2`: `CreateFile failed: error=%d`
- `0x18005ac21`: `V4_RenderFilterConfig`
- `0x18005ae36`: `WriteFile failed: error=%d`
- `0x18005ace9`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`
- `0x18005ae3d`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`
- `0x18005b0dd`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(_QWORD *a1)
{
  int v2; // ebx
  HRESULT v3; // eax
  BYTE *v4; // rdi
  void *v5; // rax
  signed int PrinterDataW; // eax
  signed int v7; // edi
  LPBYTE *v8; // rdx
  __int64 v9; // r8
  size_t v10; // rdx
  _BYTE *v11; // rdi
  const char *v12; // r9
  LPBYTE *v13; // rdx
  _BYTE *v14; // rdi
  LPBYTE *v15; // rdx
  const char *v16; // rdx
  _BYTE *v17; // rdi
  LPBYTE *v18; // rdx
  LPCVOID *v19; // rdi
  LPBYTE *v20; // rdx
  __int64 v21; // r8
  BYTE *v22; // rdi
  void *v23; // rax
  signed int v24; // eax
  signed int v25; // edi
  int v26; // edi
  LPBYTE *v27; // rcx
  char *FileW; // r14
  __int64 LastError; // rdi
  bool v30; // sf
  LPCVOID *v31; // rdx
  __int64 v33; // rsi
  DWORD v34; // edi
  LPBYTE *v35; // rcx
  LPBYTE *v36; // r8
  DWORD pcbNeeded; // [rsp+44h] [rbp-194h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-190h] BYREF
  HMODULE hLibModule; // [rsp+50h] [rbp-188h] BYREF
  __int64 v40; // [rsp+58h] [rbp-180h]
  void (*v41)(void); // [rsp+60h] [rbp-178h]
  int v42[2]; // [rsp+68h] [rbp-170h] BYREF
  int v43; // [rsp+70h] [rbp-168h]
  __int64 v44; // [rsp+78h] [rbp-160h]
  _BYTE pExceptionObject[32]; // [rsp+90h] [rbp-148h] BYREF
  _BYTE v46[32]; // [rsp+B0h] [rbp-128h] BYREF
  _BYTE v47[32]; // [rsp+D0h] [rbp-108h] BYREF
  _BYTE v48[32]; // [rsp+F0h] [rbp-E8h] BYREF
  _BYTE v49[32]; // [rsp+110h] [rbp-C8h] BYREF
  _BYTE v50[32]; // [rsp+130h] [rbp-A8h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+150h] [rbp-88h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+160h] [rbp-78h]
  unsigned __int64 v53; // [rsp+168h] [rbp-70h]
  LPBYTE pData[3]; // [rsp+170h] [rbp-68h] BYREF
  unsigned __int64 v55; // [rsp+188h] [rbp-50h]
  LPBYTE v56[3]; // [rsp+190h] [rbp-48h] BYREF
  unsigned __int64 v57; // [rsp+1A8h] [rbp-30h]

  v44 = -2;
  v2 = 0;
  v43 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    v2 = 1;
    v43 = 1;
  }
  else if ( v3 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v3);
    throw (hr_error *)pExceptionObject;
  }
  std::wstring::wstring((__int64)pData, 0x100u);
  pcbNeeded = 0;
  v4 = (BYTE *)pData;
  if ( v55 > 7 )
    v4 = pData[0];
  v5 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 40LL))(*a1);
  PrinterDataW = GetPrinterDataW(v5, (LPWSTR)L"V4_DocumentFormat", 0, v4, 0x200u, &pcbNeeded);
  v7 = PrinterDataW;
  if ( PrinterDataW > 0 )
    v7 = (unsigned __int16)PrinterDataW | 0x80070000;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x12u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v7);
    }
    hr_error::hr_error((hr_error *)v46, v7);
    throw (hr_error *)v46;
  }
  *(_OWORD *)lpBuffer = 0;
  *(_QWORD *)nNumberOfBytesToWrite = 0;
  v53 = 15;
  LOBYTE(lpBuffer[0]) = 0;
  v8 = pData;
  if ( v55 > 7 )
    v8 = (LPBYTE *)pData[0];
  if ( !(unsigned int)_o__wcsicmp(L"application/pdf", v8) )
  {
    v10 = 383;
    if ( v53 >= 0x17F )
    {
      v11 = lpBuffer[0];
      *(_QWORD *)nNumberOfBytesToWrite = 383;
      memmove_0(
        (void *)lpBuffer[0],
        "<Filters><Filter dll = \"PDFRenderFilter.dll\" clsid = \"{CD087E95-A362-4A50-B233-20DC89DED268}\" name = \"Micro"
        "soft XPS to PDF\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProvider\""
        " /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" comment = \"IID_IPrintWriteStream\" /></Filter><Fil"
        "terServiceProvider dll = \"XpsRasterService.dll\" /></Filters>",
        0x17Fu);
      v11[383] = 0;
      goto LABEL_44;
    }
    v12 = "<Filters><Filter dll = \"PDFRenderFilter.dll\" clsid = \"{CD087E95-A362-4A50-B233-20DC89DED268}\" name = \"Mic"
          "rosoft XPS to PDF\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProvi"
          "der\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" comment = \"IID_IPrintWriteStream\" /></Filt"
          "er><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
    goto LABEL_37;
  }
  v13 = pData;
  if ( v55 > 7 )
    v13 = (LPBYTE *)pData[0];
  if ( !(unsigned int)_o__wcsicmp(L"image/pwg-raster", v13) )
  {
    v10 = 388;
    if ( v53 >= 0x184 )
    {
      v14 = lpBuffer[0];
      *(_QWORD *)nNumberOfBytesToWrite = 388;
      memmove_0(
        (void *)lpBuffer[0],
        "<Filters><Filter dll = \"PWGRRenderFilter.dll\" clsid = \"{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}\" name = \"PWG "
        "Raster Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProv"
        "ider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /></Filte"
        "r><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>",
        0x184u);
      v14[388] = 0;
      goto LABEL_44;
    }
    v12 = "<Filters><Filter dll = \"PWGRRenderFilter.dll\" clsid = \"{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}\" name = \"PW"
          "G Raster Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocument"
          "Provider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /><"
          "/Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
    goto LABEL_37;
  }
  v15 = pData;
  if ( v55 > 7 )
    v15 = (LPBYTE *)pData[0];
  if ( !(unsigned int)_o__wcsicmp(L"application/PCLm", v15) )
  {
    v10 = 382;
    if ( v53 >= 0x17E )
    {
      *(_QWORD *)nNumberOfBytesToWrite = 382;
      v16 = "<Filters><Filter dll = \"PCLmRenderFilter.dll\" clsid = \"{39E2F832-C9AD-4D89-A777-79ED49AC0274}\" name = \""
            "PCLm Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentPr"
            "ovider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /><"
            "/Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
LABEL_27:
      v17 = lpBuffer[0];
      memmove_0((void *)lpBuffer[0], v16, 0x17Eu);
      v17[382] = 0;
      goto LABEL_44;
    }
    v12 = "<Filters><Filter dll = \"PCLmRenderFilter.dll\" clsid = \"{39E2F832-C9AD-4D89-A777-79ED49AC0274}\" name = \"PC"
          "Lm Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProvid"
          "er\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /></Filte"
          "r><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
LABEL_37:
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      (char **)lpBuffer,
      v10,
      v9,
      v12);
    goto LABEL_44;
  }
  v18 = pData;
  if ( v55 > 7 )
    v18 = (LPBYTE *)pData[0];
  if ( (unsigned int)_o__wcsicmp(L"application/oxps", v18) )
  {
    v20 = pData;
    if ( v55 > 7 )
      v20 = (LPBYTE *)pData[0];
    if ( (unsigned int)_o__wcsicmp(L"image/tiff", v20) )
    {
      v36 = pData;
      if ( v55 > 7 )
        v36 = (LPBYTE *)pData[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData",
        L"GetPrinterData query for document format returned un-supported document format %ws.",
        v36);
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x13u,
          (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
          -2147418113);
      }
      hr_error::hr_error((hr_error *)v50, -2147418113);
      throw (hr_error *)v50;
    }
    if ( v53 >= 0x17E )
    {
      *(_QWORD *)nNumberOfBytesToWrite = 382;
      v16 = "<Filters><Filter dll = \"TiffRenderFilter.dll\" clsid = \"{42A38C2A-038A-4595-A4E2-00803F9FAEC0}\" name = \""
            "Tiff Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentPr"
            "ovider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /><"
            "/Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
      goto LABEL_27;
    }
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      (char **)lpBuffer,
      0x17Eu,
      v21,
      "<Filters><Filter dll = \"TiffRenderFilter.dll\" clsid = \"{42A38C2A-038A-4595-A4E2-00803F9FAEC0}\" name = \"Tiff R"
      "ender Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProvider\" /><"
      "Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /></Filter><FilterSer"
      "viceProvider dll = \"XpsRasterService.dll\" /></Filters>");
  }
  else
  {
    v10 = 10;
    if ( v53 < 0xA )
    {
      v12 = "<Filters/>";
      goto LABEL_37;
    }
    v19 = lpBuffer;
    if ( v53 > 0xF )
      v19 = (LPCVOID *)lpBuffer[0];
    *(_QWORD *)nNumberOfBytesToWrite = 10;
    memmove_0(v19, "<Filters/>", 0xAu);
    *((_BYTE *)v19 + 10) = 0;
  }
LABEL_44:
  std::wstring::wstring((__int64)v56, 0x104u);
  v22 = (BYTE *)v56;
  if ( v57 > 7 )
    v22 = v56[0];
  v23 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 40LL))(*a1);
  v24 = GetPrinterDataW(v23, (LPWSTR)L"V4_RenderFilterConfig", 0, v22, 0x208u, &pcbNeeded);
  v25 = v24;
  if ( v24 > 0 )
    v25 = (unsigned __int16)v24 | 0x80070000;
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x14u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v25);
    }
    hr_error::hr_error((hr_error *)v47, v25);
    throw (hr_error *)v47;
  }
  v42[0] = 0;
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)&hLibModule, v42);
  v26 = v42[0];
  if ( v42[0] < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x15u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v42[0]);
    }
    hr_error::hr_error((hr_error *)v48, v26);
    throw (hr_error *)v48;
  }
  PrintConfig::CIppCSRHelper::EnsureFolderExists((const WCHAR *)v56);
  v27 = v56;
  if ( v57 > 7 )
    v27 = (LPBYTE *)v56[0];
  FileW = (char *)CreateFileW((LPCWSTR)v27, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
  *(_QWORD *)v42 = FileW;
  if ( FileW == (char *)-1LL )
  {
    LastError = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData",
      L"CreateFile failed: error=%d",
      LastError);
    v30 = (int)LastError < 0;
    if ( (int)LastError > 0 )
    {
      LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      v30 = (int)LastError < 0;
    }
    if ( v30 )
    {
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x16u,
          (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
          LastError);
      }
      hr_error::hr_error((hr_error *)v49, LastError);
      throw (hr_error *)v49;
    }
  }
  NumberOfBytesWritten = 0;
  v31 = lpBuffer;
  if ( v53 > 0xF )
    v31 = (LPCVOID *)lpBuffer[0];
  if ( WriteFile(FileW, v31, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0)
    && NumberOfBytesWritten == *(_QWORD *)nNumberOfBytesToWrite )
  {
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    if ( v41 && v40 )
    {
      v41();
      v41 = 0;
      v40 = 0;
    }
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    std::wstring::~wstring((char **)v56);
    std::string::~string((char **)lpBuffer);
    std::wstring::~wstring((char **)pData);
    if ( v2 )
      CoUninitialize();
    return 0;
  }
  else
  {
    v33 = GetLastError();
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData",
      L"WriteFile failed: error=%d",
      v33);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v34 = GetLastError();
      CloseHandle(FileW);
      SetLastError(v34);
    }
    v35 = v56;
    if ( v57 > 7 )
      v35 = (LPBYTE *)v56[0];
    DeleteFileW((LPCWSTR)v35);
    if ( (int)v33 > 0 )
      LODWORD(v33) = (unsigned __int16)v33 | 0x80070000;
    if ( v41 && v40 )
    {
      v41();
      v41 = 0;
      v40 = 0;
    }
    if ( hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    std::wstring::~wstring((char **)v56);
    std::string::~string((char **)lpBuffer);
    std::wstring::~wstring((char **)pData);
    if ( v2 )
      CoUninitialize();
    return (unsigned int)v33;
  }
}

```

## disassembly

```asm
0x18005a810  mov     rax, rsp
0x18005a813  push    rdi
0x18005a814  push    r12
0x18005a816  push    r14
0x18005a818  sub     rsp, 1C0h
0x18005a81f  mov     [rsp+1D8h+var_160], 0FFFFFFFFFFFFFFFEh
0x18005a828  mov     [rax+10h], rbx
0x18005a82c  mov     [rax+18h], rsi
0x18005a830  mov     rax, cs:__security_cookie
0x18005a837  xor     rax, rsp
0x18005a83a  mov     [rsp+1D8h+var_28], rax
0x18005a842  mov     rsi, rcx
0x18005a845  xor     r12d, r12d
0x18005a848  mov     [rsp+1D8h+var_198], r12d
0x18005a84d  mov     ebx, r12d
0x18005a850  mov     [rsp+1D8h+var_168], ebx
0x18005a854  xor     edx, edx; dwCoInit
0x18005a856  xor     ecx, ecx; pvReserved
0x18005a858  call    cs:__imp_CoInitializeEx
0x18005a85f  nop     dword ptr [rax+rax+00h]
0x18005a864  test    eax, eax
0x18005a866  jns     short loc_18005A875
0x18005a868  cmp     eax, 80010106h
0x18005a86d  jnz     loc_18005AF44
0x18005a873  jmp     short loc_18005A87E
0x18005a875  mov     ebx, 1
0x18005a87a  mov     [rsp+1D8h+var_168], ebx
0x18005a87e  mov     edx, 100h
0x18005a883  lea     rcx, [rsp+1D8h+pData]
0x18005a88b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005a890  nop
0x18005a891  mov     [rsp+1D8h+var_194], r12d
0x18005a896  lea     rdi, [rsp+1D8h+pData]
0x18005a89e  cmp     [rsp+1D8h+var_50], 7
0x18005a8a7  cmova   rdi, [rsp+1D8h+pData]
0x18005a8b0  mov     rcx, [rsi]
0x18005a8b3  mov     rax, [rcx]
0x18005a8b6  mov     rax, [rax+28h]
0x18005a8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8bf  lea     rcx, [rsp+1D8h+var_194]
0x18005a8c4  mov     [rsp+1D8h+pcbNeeded], rcx; pcbNeeded
0x18005a8c9  mov     [rsp+1D8h+nSize], 200h; nSize
0x18005a8d1  mov     r9, rdi; pData
0x18005a8d4  xor     r8d, r8d; pType
0x18005a8d7  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x18005a8de  mov     rcx, rax; hPrinter
0x18005a8e1  call    cs:__imp_GetPrinterDataW
0x18005a8e8  nop     dword ptr [rax+rax+00h]
0x18005a8ed  mov     edi, eax
0x18005a8ef  test    eax, eax
0x18005a8f1  jle     short loc_18005A8FC
0x18005a8f3  movzx   edi, ax
0x18005a8f6  or      edi, 80070000h
0x18005a8fc  test    edi, edi
0x18005a8fe  js      loc_18005AF68
0x18005a904  xorps   xmm0, xmm0
0x18005a907  movups  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18005a90f  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], r12
0x18005a917  mov     r14d, 0Fh
0x18005a91d  mov     [rsp+1D8h+var_70], r14
0x18005a925  mov     byte ptr [rsp+1D8h+lpBuffer], r12b
0x18005a92d  lea     rdx, [rsp+1D8h+pData]
0x18005a935  cmp     [rsp+1D8h+var_50], 7
0x18005a93e  cmova   rdx, [rsp+1D8h+pData]
0x18005a947  lea     rcx, aApplicationPdf; "application/pdf"
0x18005a94e  call    cs:__imp__o__wcsicmp
0x18005a955  nop     dword ptr [rax+rax+00h]
0x18005a95a  test    eax, eax
0x18005a95c  jnz     short loc_18005A9B8
0x18005a95e  mov     edx, 17Fh
0x18005a963  cmp     [rsp+1D8h+var_70], rdx
0x18005a96b  jb      short loc_18005A9AC
0x18005a96d  lea     rdi, [rsp+1D8h+lpBuffer]
0x18005a975  cmp     [rsp+1D8h+var_70], r14
0x18005a97d  cmova   rdi, [rsp+1D8h+lpBuffer]
0x18005a986  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005a98e  mov     r8d, edx; Size
0x18005a991  lea     rdx, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x18005a998  mov     rcx, rdi; void *
0x18005a99b  call    memmove_0
0x18005a9a0  mov     [rdi+17Fh], r12b
0x18005a9a7  jmp     loc_18005ABCD
0x18005a9ac  lea     r9, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x18005a9b3  jmp     loc_18005AB4F
0x18005a9b8  lea     rdx, [rsp+1D8h+pData]
0x18005a9c0  cmp     [rsp+1D8h+var_50], 7
0x18005a9c9  cmova   rdx, [rsp+1D8h+pData]
0x18005a9d2  lea     rcx, aImagePwgRaster; "image/pwg-raster"
0x18005a9d9  call    cs:__imp__o__wcsicmp
0x18005a9e0  nop     dword ptr [rax+rax+00h]
0x18005a9e5  test    eax, eax
0x18005a9e7  jnz     short loc_18005AA43
0x18005a9e9  mov     edx, 184h
0x18005a9ee  cmp     [rsp+1D8h+var_70], rdx
0x18005a9f6  jb      short loc_18005AA37
0x18005a9f8  lea     rdi, [rsp+1D8h+lpBuffer]
0x18005aa00  cmp     [rsp+1D8h+var_70], r14
0x18005aa08  cmova   rdi, [rsp+1D8h+lpBuffer]
0x18005aa11  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005aa19  mov     r8d, edx; Size
0x18005aa1c  lea     rdx, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x18005aa23  mov     rcx, rdi; void *
0x18005aa26  call    memmove_0
0x18005aa2b  mov     [rdi+184h], r12b
0x18005aa32  jmp     loc_18005ABCD
0x18005aa37  lea     r9, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x18005aa3e  jmp     loc_18005AB4F
0x18005aa43  lea     rdx, [rsp+1D8h+pData]
0x18005aa4b  cmp     [rsp+1D8h+var_50], 7
0x18005aa54  cmova   rdx, [rsp+1D8h+pData]
0x18005aa5d  lea     rcx, aApplicationPcl; "application/PCLm"
0x18005aa64  call    cs:__imp__o__wcsicmp
0x18005aa6b  nop     dword ptr [rax+rax+00h]
0x18005aa70  test    eax, eax
0x18005aa72  jnz     short loc_18005AACE
0x18005aa74  mov     edx, 17Eh
0x18005aa79  cmp     [rsp+1D8h+var_70], rdx
0x18005aa81  jb      short loc_18005AAC2
0x18005aa83  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005aa8b  mov     r8d, edx; Size
0x18005aa8e  lea     rdx, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x18005aa95  lea     rdi, [rsp+1D8h+lpBuffer]
0x18005aa9d  cmp     [rsp+1D8h+var_70], r14
0x18005aaa5  cmova   rdi, [rsp+1D8h+lpBuffer]
0x18005aaae  mov     rcx, rdi; void *
0x18005aab1  call    memmove_0
0x18005aab6  mov     [rdi+17Eh], r12b
0x18005aabd  jmp     loc_18005ABCD
0x18005aac2  lea     r9, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x18005aac9  jmp     loc_18005AB4F
0x18005aace  lea     rdx, [rsp+1D8h+pData]
0x18005aad6  cmp     [rsp+1D8h+var_50], 7
0x18005aadf  cmova   rdx, [rsp+1D8h+pData]
0x18005aae8  lea     rcx, aApplicationOxp; "application/oxps"
0x18005aaef  call    cs:__imp__o__wcsicmp
0x18005aaf6  nop     dword ptr [rax+rax+00h]
0x18005aafb  test    eax, eax
0x18005aafd  jnz     short loc_18005AB5E
0x18005aaff  lea     edx, [rax+0Ah]
0x18005ab02  cmp     [rsp+1D8h+var_70], rdx
0x18005ab0a  jb      short loc_18005AB48
0x18005ab0c  lea     rdi, [rsp+1D8h+lpBuffer]
0x18005ab14  cmp     [rsp+1D8h+var_70], r14
0x18005ab1c  cmova   rdi, [rsp+1D8h+lpBuffer]
0x18005ab25  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005ab2d  mov     r8d, edx; Size
0x18005ab30  lea     rdx, aFilters; "<Filters/>"
0x18005ab37  mov     rcx, rdi; void *
0x18005ab3a  call    memmove_0
0x18005ab3f  mov     [rdi+0Ah], r12b
0x18005ab43  jmp     loc_18005ABCD
0x18005ab48  lea     r9, aFilters; "<Filters/>"
0x18005ab4f  lea     rcx, [rsp+1D8h+lpBuffer]
0x18005ab57  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18005ab5c  jmp     short loc_18005ABCD
0x18005ab5e  lea     rdx, [rsp+1D8h+pData]
0x18005ab66  cmp     [rsp+1D8h+var_50], 7
0x18005ab6f  cmova   rdx, [rsp+1D8h+pData]
0x18005ab78  lea     rcx, aImageTiff; "image/tiff"
0x18005ab7f  call    cs:__imp__o__wcsicmp
0x18005ab86  nop     dword ptr [rax+rax+00h]
0x18005ab8b  test    eax, eax
0x18005ab8d  jnz     loc_18005B0BC
0x18005ab93  mov     edx, 17Eh
0x18005ab98  cmp     [rsp+1D8h+var_70], rdx
0x18005aba0  jb      short loc_18005ABB9
0x18005aba2  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005abaa  mov     r8d, edx
0x18005abad  lea     rdx, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x18005abb4  jmp     loc_18005AA95
0x18005abb9  lea     r9, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x18005abc0  lea     rcx, [rsp+1D8h+lpBuffer]
0x18005abc8  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18005abcd  mov     edx, 104h
0x18005abd2  lea     rcx, [rsp+1D8h+var_48]
0x18005abda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005abdf  nop
0x18005abe0  lea     rdi, [rsp+1D8h+var_48]
0x18005abe8  cmp     [rsp+1D8h+var_30], 7
0x18005abf1  cmova   rdi, [rsp+1D8h+var_48]
0x18005abfa  mov     rcx, [rsi]
0x18005abfd  mov     rax, [rcx]
0x18005ac00  mov     rax, [rax+28h]
0x18005ac04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac09  lea     rcx, [rsp+1D8h+var_194]
0x18005ac0e  mov     [rsp+1D8h+pcbNeeded], rcx; pcbNeeded
0x18005ac13  mov     [rsp+1D8h+nSize], 208h; nSize
0x18005ac1b  mov     r9, rdi; pData
0x18005ac1e  xor     r8d, r8d; pType
0x18005ac21  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x18005ac28  mov     rcx, rax; hPrinter
0x18005ac2b  call    cs:__imp_GetPrinterDataW
0x18005ac32  nop     dword ptr [rax+rax+00h]
0x18005ac37  mov     edi, eax
0x18005ac39  test    eax, eax
0x18005ac3b  jle     short loc_18005AC46
0x18005ac3d  movzx   edi, ax
0x18005ac40  or      edi, 80070000h
0x18005ac46  test    edi, edi
0x18005ac48  js      loc_18005AFBD
0x18005ac4e  mov     [rsp+1D8h+var_170], r12d
0x18005ac53  lea     rdx, [rsp+1D8h+var_170]; int *
0x18005ac58  lea     rcx, [rsp+1D8h+hLibModule]; this
0x18005ac5d  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18005ac62  nop
0x18005ac63  mov     edi, [rsp+1D8h+var_170]
0x18005ac67  test    edi, edi
0x18005ac69  js      loc_18005B012
0x18005ac6f  lea     rcx, [rsp+1D8h+var_48]
0x18005ac77  call    ?EnsureFolderExists@CIppCSRHelper@PrintConfig@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CIppCSRHelper::EnsureFolderExists(std::wstring const &)
0x18005ac7c  nop
0x18005ac7d  lea     rcx, [rsp+1D8h+var_48]
0x18005ac85  cmp     [rsp+1D8h+var_30], 7
0x18005ac8e  cmova   rcx, [rsp+1D8h+var_48]; lpFileName
0x18005ac97  mov     [rsp+1D8h+hTemplateFile], r12; hTemplateFile
0x18005ac9c  mov     dword ptr [rsp+1D8h+pcbNeeded], 8100080h; dwFlagsAndAttributes
0x18005aca4  mov     [rsp+1D8h+nSize], 2; dwCreationDisposition
0x18005acac  xor     r9d, r9d; lpSecurityAttributes
0x18005acaf  xor     r8d, r8d; dwShareMode
0x18005acb2  mov     edx, 40000000h; dwDesiredAccess
0x18005acb7  call    cs:__imp_CreateFileW
0x18005acbe  nop     dword ptr [rax+rax+00h]
0x18005acc3  mov     r14, rax
0x18005acc6  mov     qword ptr [rsp+1D8h+var_170], rax
0x18005accb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005accf  jnz     short loc_18005AD0A
0x18005acd1  call    cs:__imp_GetLastError
0x18005acd8  nop     dword ptr [rax+rax+00h]
0x18005acdd  mov     edi, eax
0x18005acdf  mov     r8d, eax
0x18005ace2  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x18005ace9  lea     rcx, aPrintconfigCip; "PrintConfig::CIppCSRHelper::RegenerateR"...
0x18005acf0  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005acf5  test    edi, edi
0x18005acf7  jle     short loc_18005AD04
0x18005acf9  movzx   edi, di
0x18005acfc  or      edi, 80070000h
0x18005ad02  test    edi, edi
0x18005ad04  js      loc_18005B067
0x18005ad0a  mov     [rsp+1D8h+NumberOfBytesWritten], r12d
0x18005ad0f  lea     rdx, [rsp+1D8h+lpBuffer]
0x18005ad17  cmp     [rsp+1D8h+var_70], 0Fh
0x18005ad20  cmova   rdx, [rsp+1D8h+lpBuffer]; lpBuffer
0x18005ad29  mov     qword ptr [rsp+1D8h+nSize], r12; lpOverlapped
0x18005ad2e  lea     r9, [rsp+1D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005ad33  mov     r8d, [rsp+1D8h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18005ad3b  mov     rcx, r14; hFile
0x18005ad3e  call    cs:__imp_WriteFile
0x18005ad45  nop     dword ptr [rax+rax+00h]
0x18005ad4a  test    eax, eax
0x18005ad4c  jz      loc_18005AE25
0x18005ad52  mov     eax, [rsp+1D8h+NumberOfBytesWritten]
0x18005ad56  cmp     rax, qword ptr [rsp+1D8h+nNumberOfBytesToWrite]
0x18005ad5e  jnz     loc_18005AE25
0x18005ad64  lea     rax, [r14-1]
0x18005ad68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005ad6c  ja      short loc_18005AD7E
0x18005ad6e  mov     rcx, r14; hObject
0x18005ad71  call    cs:__imp_CloseHandle
0x18005ad78  nop     dword ptr [rax+rax+00h]
0x18005ad7d  nop
0x18005ad7e  mov     rax, [rsp+1D8h+var_178]
0x18005ad83  test    rax, rax
0x18005ad86  jz      short loc_18005ADA1
0x18005ad88  mov     rcx, [rsp+1D8h+var_180]
0x18005ad8d  test    rcx, rcx
0x18005ad90  jz      short loc_18005ADA1
0x18005ad92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad97  mov     [rsp+1D8h+var_178], r12
0x18005ad9c  mov     [rsp+1D8h+var_180], r12
0x18005ada1  mov     rcx, [rsp+1D8h+hLibModule]; hLibModule
0x18005ada6  test    rcx, rcx
0x18005ada9  jz      short loc_18005ADBC
0x18005adab  call    cs:__imp_FreeLibrary
0x18005adb2  nop     dword ptr [rax+rax+00h]
0x18005adb7  mov     [rsp+1D8h+hLibModule], r12
0x18005adbc  lea     rcx, [rsp+1D8h+var_48]
0x18005adc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005adc9  nop
0x18005adca  lea     rcx, [rsp+1D8h+lpBuffer]
0x18005add2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005add7  nop
0x18005add8  lea     rcx, [rsp+1D8h+pData]
0x18005ade0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005ade5  nop
0x18005ade6  test    ebx, ebx
0x18005ade8  jz      short loc_18005ADF7
0x18005adea  call    cs:__imp_CoUninitialize
0x18005adf1  nop     dword ptr [rax+rax+00h]
0x18005adf6  nop
0x18005adf7  mov     eax, [rsp+1D8h+var_198]
0x18005adfb  mov     rcx, [rsp+1D8h+var_28]
0x18005ae03  xor     rcx, rsp; StackCookie
0x18005ae06  call    __security_check_cookie
0x18005ae0b  lea     r11, [rsp+1D8h+var_18]
0x18005ae13  mov     rbx, [r11+28h]
0x18005ae17  mov     rsi, [r11+30h]
0x18005ae1b  mov     rsp, r11
0x18005ae1e  pop     r14
0x18005ae20  pop     r12
  ... truncated ...
```
