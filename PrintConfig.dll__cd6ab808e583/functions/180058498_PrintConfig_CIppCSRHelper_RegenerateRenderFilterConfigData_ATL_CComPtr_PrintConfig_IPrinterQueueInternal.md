# PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData(ATL::CComPtr<PrintConfig::IPrinterQueueInternal> &)

- ea: `0x180058498`
- end: `0x180058d48`
- name: `?RegenerateRenderFilterConfigData@CIppCSRHelper@PrintConfig@@SAJAEAV?$CComPtr@UIPrinterQueueInternal@PrintConfig@@@ATL@@@Z`
- size: `2224`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x1800060ec`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x180021820`
- `0x18002664c`
- `0x18003bb38`
- `0x1800582e8`
- `0x180058498`
- `0x1801adb58`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800585ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005864f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800586d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058756`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800587dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800585ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005864f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800586d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180058756`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800587dd`
- `KERNEL32!WriteFile` at `0x180058984`
- `KERNEL32!WriteFile` at `0x180058984`
- `KERNEL32!DeleteFileW` at `0x180058aad`
- `KERNEL32!DeleteFileW` at `0x180058aad`
- `KERNEL32!CreateFileW` at `0x180058909`
- `KERNEL32!CreateFileW` at `0x180058909`
- `KERNEL32!FreeLibrary` at `0x1800589e5`
- `KERNEL32!FreeLibrary` at `0x180058aed`
- `KERNEL32!FreeLibrary` at `0x1800589e5`
- `KERNEL32!FreeLibrary` at `0x180058aed`
- `KERNEL32!CloseHandle` at `0x1800589b1`
- `KERNEL32!CloseHandle` at `0x180058a85`
- `KERNEL32!CloseHandle` at `0x1800589b1`
- `KERNEL32!CloseHandle` at `0x180058a85`
- `KERNEL32!SetLastError` at `0x180058a8d`
- `KERNEL32!SetLastError` at `0x180058a8d`
- `KERNEL32!GetLastError` at `0x18005891d`
- `KERNEL32!GetLastError` at `0x180058a52`
- `KERNEL32!GetLastError` at `0x180058a7a`
- `KERNEL32!GetLastError` at `0x18005891d`
- `KERNEL32!GetLastError` at `0x180058a52`
- `KERNEL32!GetLastError` at `0x180058a7a`
- `ole32!CoInitializeEx` at `0x1800584e0`
- `ole32!CoInitializeEx` at `0x1800584e0`
- `ole32!CoUninitialize` at `0x180058a1e`
- `ole32!CoUninitialize` at `0x180058b26`
- `ole32!CoUninitialize` at `0x180058a1e`
- `ole32!CoUninitialize` at `0x180058b26`
- `WINSPOOL!GetPrinterDataW` at `0x180058563`
- `WINSPOOL!GetPrinterDataW` at `0x180058883`
- `WINSPOOL!GetPrinterDataW` at `0x180058563`
- `WINSPOOL!GetPrinterDataW` at `0x180058883`

## string_xrefs

- `0x180058607`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180058622`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005868c`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800586a7`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800586f8`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18005872c`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180058805`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180058811`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180058928`: `CreateFile failed: error=%d`
- `0x180058879`: `V4_RenderFilterConfig`
- `0x180058a5d`: `WriteFile failed: error=%d`
- `0x18005892f`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`
- `0x180058a64`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`
- `0x180058ce0`: `PrintConfig::CIppCSRHelper::RegenerateRenderFilterConfigData`

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
  __int64 v10; // rdx
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
  std::wstring::wstring(pData, 256);
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
        18,
        WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        (unsigned int)v7);
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
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(lpBuffer, v10, v9, v12);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids, 2147549183LL);
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
      lpBuffer,
      382,
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
  std::wstring::wstring(v56, 260);
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
        20,
        WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        (unsigned int)v25);
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
        21,
        WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        (unsigned int)v42[0]);
    }
    hr_error::hr_error((hr_error *)v48, v26);
    throw (hr_error *)v48;
  }
  PrintConfig::CIppCSRHelper::EnsureFolderExists(v56);
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
          22,
          WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
          (unsigned int)LastError);
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
    std::wstring::~wstring(v56);
    std::string::~string((char **)lpBuffer);
    std::wstring::~wstring(pData);
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
    std::wstring::~wstring(v56);
    std::string::~string((char **)lpBuffer);
    std::wstring::~wstring(pData);
    if ( v2 )
      CoUninitialize();
    return (unsigned int)v33;
  }
}

```

## disassembly

```asm
0x180058498  mov     rax, rsp
0x18005849b  push    rdi
0x18005849c  push    r12
0x18005849e  push    r14
0x1800584a0  sub     rsp, 1C0h
0x1800584a7  mov     [rsp+1D8h+var_160], 0FFFFFFFFFFFFFFFEh
0x1800584b0  mov     [rax+10h], rbx
0x1800584b4  mov     [rax+18h], rsi
0x1800584b8  mov     rax, cs:__security_cookie
0x1800584bf  xor     rax, rsp
0x1800584c2  mov     [rsp+1D8h+var_28], rax
0x1800584ca  mov     rsi, rcx
0x1800584cd  xor     r12d, r12d
0x1800584d0  mov     [rsp+1D8h+var_198], r12d
0x1800584d5  mov     ebx, r12d
0x1800584d8  mov     [rsp+1D8h+var_168], ebx
0x1800584dc  xor     edx, edx; dwCoInit
0x1800584de  xor     ecx, ecx; pvReserved
0x1800584e0  call    cs:__imp_CoInitializeEx
0x1800584e6  test    eax, eax
0x1800584e8  jns     short loc_1800584F7
0x1800584ea  cmp     eax, 80010106h
0x1800584ef  jnz     loc_180058B47
0x1800584f5  jmp     short loc_180058500
0x1800584f7  mov     ebx, 1
0x1800584fc  mov     [rsp+1D8h+var_168], ebx
0x180058500  mov     edx, 100h
0x180058505  lea     rcx, [rsp+1D8h+pData]
0x18005850d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180058512  nop
0x180058513  mov     [rsp+1D8h+var_194], r12d
0x180058518  lea     rdi, [rsp+1D8h+pData]
0x180058520  cmp     [rsp+1D8h+var_50], 7
0x180058529  cmova   rdi, [rsp+1D8h+pData]
0x180058532  mov     rcx, [rsi]
0x180058535  mov     rax, [rcx]
0x180058538  mov     rax, [rax+28h]
0x18005853c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058541  lea     rcx, [rsp+1D8h+var_194]
0x180058546  mov     [rsp+1D8h+pcbNeeded], rcx; pcbNeeded
0x18005854b  mov     [rsp+1D8h+nSize], 200h; nSize
0x180058553  mov     r9, rdi; pData
0x180058556  xor     r8d, r8d; pType
0x180058559  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x180058560  mov     rcx, rax; hPrinter
0x180058563  call    cs:__imp_GetPrinterDataW
0x180058569  mov     edi, eax
0x18005856b  test    eax, eax
0x18005856d  jle     short loc_180058578
0x18005856f  movzx   edi, ax
0x180058572  or      edi, 80070000h
0x180058578  test    edi, edi
0x18005857a  js      loc_180058B6B
0x180058580  xorps   xmm0, xmm0
0x180058583  movups  xmmword ptr [rsp+1D8h+lpBuffer], xmm0
0x18005858b  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], r12
0x180058593  mov     r14d, 0Fh
0x180058599  mov     [rsp+1D8h+var_70], r14
0x1800585a1  mov     byte ptr [rsp+1D8h+lpBuffer], r12b
0x1800585a9  lea     rdx, [rsp+1D8h+pData]
0x1800585b1  cmp     [rsp+1D8h+var_50], 7
0x1800585ba  cmova   rdx, [rsp+1D8h+pData]
0x1800585c3  lea     rcx, aApplicationPdf; "application/pdf"
0x1800585ca  call    cs:__imp__o__wcsicmp
0x1800585d0  test    eax, eax
0x1800585d2  jnz     short loc_18005862E
0x1800585d4  mov     edx, 17Fh
0x1800585d9  cmp     [rsp+1D8h+var_70], rdx
0x1800585e1  jb      short loc_180058622
0x1800585e3  lea     rdi, [rsp+1D8h+lpBuffer]
0x1800585eb  cmp     [rsp+1D8h+var_70], r14
0x1800585f3  cmova   rdi, [rsp+1D8h+lpBuffer]
0x1800585fc  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x180058604  mov     r8d, edx; Size
0x180058607  lea     rdx, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x18005860e  mov     rcx, rdi; void *
0x180058611  call    memmove_0
0x180058616  mov     [rdi+17Fh], r12b
0x18005861d  jmp     loc_180058825
0x180058622  lea     r9, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x180058629  jmp     loc_1800587AD
0x18005862e  lea     rdx, [rsp+1D8h+pData]
0x180058636  cmp     [rsp+1D8h+var_50], 7
0x18005863f  cmova   rdx, [rsp+1D8h+pData]
0x180058648  lea     rcx, aImagePwgRaster; "image/pwg-raster"
0x18005864f  call    cs:__imp__o__wcsicmp
0x180058655  test    eax, eax
0x180058657  jnz     short loc_1800586B3
0x180058659  mov     edx, 184h
0x18005865e  cmp     [rsp+1D8h+var_70], rdx
0x180058666  jb      short loc_1800586A7
0x180058668  lea     rdi, [rsp+1D8h+lpBuffer]
0x180058670  cmp     [rsp+1D8h+var_70], r14
0x180058678  cmova   rdi, [rsp+1D8h+lpBuffer]
0x180058681  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x180058689  mov     r8d, edx; Size
0x18005868c  lea     rdx, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x180058693  mov     rcx, rdi; void *
0x180058696  call    memmove_0
0x18005869b  mov     [rdi+184h], r12b
0x1800586a2  jmp     loc_180058825
0x1800586a7  lea     r9, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x1800586ae  jmp     loc_1800587AD
0x1800586b3  lea     rdx, [rsp+1D8h+pData]
0x1800586bb  cmp     [rsp+1D8h+var_50], 7
0x1800586c4  cmova   rdx, [rsp+1D8h+pData]
0x1800586cd  lea     rcx, aApplicationPcl; "application/PCLm"
0x1800586d4  call    cs:__imp__o__wcsicmp
0x1800586da  test    eax, eax
0x1800586dc  jnz     short loc_180058735
0x1800586de  mov     edx, 17Eh
0x1800586e3  cmp     [rsp+1D8h+var_70], rdx
0x1800586eb  jb      short loc_18005872C
0x1800586ed  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x1800586f5  mov     r8d, edx; Size
0x1800586f8  lea     rdx, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x1800586ff  lea     rdi, [rsp+1D8h+lpBuffer]
0x180058707  cmp     [rsp+1D8h+var_70], r14
0x18005870f  cmova   rdi, [rsp+1D8h+lpBuffer]
0x180058718  mov     rcx, rdi; void *
0x18005871b  call    memmove_0
0x180058720  mov     [rdi+17Eh], r12b
0x180058727  jmp     loc_180058825
0x18005872c  lea     r9, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x180058733  jmp     short loc_1800587AD
0x180058735  lea     rdx, [rsp+1D8h+pData]
0x18005873d  cmp     [rsp+1D8h+var_50], 7
0x180058746  cmova   rdx, [rsp+1D8h+pData]
0x18005874f  lea     rcx, aApplicationOxp; "application/oxps"
0x180058756  call    cs:__imp__o__wcsicmp
0x18005875c  test    eax, eax
0x18005875e  jnz     short loc_1800587BC
0x180058760  lea     edx, [rax+0Ah]
0x180058763  cmp     [rsp+1D8h+var_70], rdx
0x18005876b  jb      short loc_1800587A6
0x18005876d  lea     rdi, [rsp+1D8h+lpBuffer]
0x180058775  cmp     [rsp+1D8h+var_70], r14
0x18005877d  cmova   rdi, [rsp+1D8h+lpBuffer]
0x180058786  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x18005878e  mov     r8d, edx; Size
0x180058791  lea     rdx, aFilters; "<Filters/>"
0x180058798  mov     rcx, rdi; void *
0x18005879b  call    memmove_0
0x1800587a0  mov     [rdi+0Ah], r12b
0x1800587a4  jmp     short loc_180058825
0x1800587a6  lea     r9, aFilters; "<Filters/>"
0x1800587ad  lea     rcx, [rsp+1D8h+lpBuffer]
0x1800587b5  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x1800587ba  jmp     short loc_180058825
0x1800587bc  lea     rdx, [rsp+1D8h+pData]
0x1800587c4  cmp     [rsp+1D8h+var_50], 7
0x1800587cd  cmova   rdx, [rsp+1D8h+pData]
0x1800587d6  lea     rcx, aImageTiff; "image/tiff"
0x1800587dd  call    cs:__imp__o__wcsicmp
0x1800587e3  test    eax, eax
0x1800587e5  jnz     loc_180058CBF
0x1800587eb  mov     edx, 17Eh
0x1800587f0  cmp     [rsp+1D8h+var_70], rdx
0x1800587f8  jb      short loc_180058811
0x1800587fa  mov     qword ptr [rsp+1D8h+nNumberOfBytesToWrite], rdx
0x180058802  mov     r8d, edx
0x180058805  lea     rdx, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x18005880c  jmp     loc_1800586FF
0x180058811  lea     r9, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x180058818  lea     rcx, [rsp+1D8h+lpBuffer]
0x180058820  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180058825  mov     edx, 104h
0x18005882a  lea     rcx, [rsp+1D8h+var_48]
0x180058832  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180058837  nop
0x180058838  lea     rdi, [rsp+1D8h+var_48]
0x180058840  cmp     [rsp+1D8h+var_30], 7
0x180058849  cmova   rdi, [rsp+1D8h+var_48]
0x180058852  mov     rcx, [rsi]
0x180058855  mov     rax, [rcx]
0x180058858  mov     rax, [rax+28h]
0x18005885c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058861  lea     rcx, [rsp+1D8h+var_194]
0x180058866  mov     [rsp+1D8h+pcbNeeded], rcx; pcbNeeded
0x18005886b  mov     [rsp+1D8h+nSize], 208h; nSize
0x180058873  mov     r9, rdi; pData
0x180058876  xor     r8d, r8d; pType
0x180058879  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x180058880  mov     rcx, rax; hPrinter
0x180058883  call    cs:__imp_GetPrinterDataW
0x180058889  mov     edi, eax
0x18005888b  test    eax, eax
0x18005888d  jle     short loc_180058898
0x18005888f  movzx   edi, ax
0x180058892  or      edi, 80070000h
0x180058898  test    edi, edi
0x18005889a  js      loc_180058BC0
0x1800588a0  mov     [rsp+1D8h+var_170], r12d
0x1800588a5  lea     rdx, [rsp+1D8h+var_170]; int *
0x1800588aa  lea     rcx, [rsp+1D8h+hLibModule]; this
0x1800588af  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800588b4  nop
0x1800588b5  mov     edi, [rsp+1D8h+var_170]
0x1800588b9  test    edi, edi
0x1800588bb  js      loc_180058C15
0x1800588c1  lea     rcx, [rsp+1D8h+var_48]
0x1800588c9  call    ?EnsureFolderExists@CIppCSRHelper@PrintConfig@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CIppCSRHelper::EnsureFolderExists(std::wstring const &)
0x1800588ce  nop
0x1800588cf  lea     rcx, [rsp+1D8h+var_48]
0x1800588d7  cmp     [rsp+1D8h+var_30], 7
0x1800588e0  cmova   rcx, [rsp+1D8h+var_48]; lpFileName
0x1800588e9  mov     [rsp+1D8h+hTemplateFile], r12; hTemplateFile
0x1800588ee  mov     dword ptr [rsp+1D8h+pcbNeeded], 8100080h; dwFlagsAndAttributes
0x1800588f6  mov     [rsp+1D8h+nSize], 2; dwCreationDisposition
0x1800588fe  xor     r9d, r9d; lpSecurityAttributes
0x180058901  xor     r8d, r8d; dwShareMode
0x180058904  mov     edx, 40000000h; dwDesiredAccess
0x180058909  call    cs:__imp_CreateFileW
0x18005890f  mov     r14, rax
0x180058912  mov     qword ptr [rsp+1D8h+var_170], rax
0x180058917  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005891b  jnz     short loc_180058950
0x18005891d  call    cs:__imp_GetLastError
0x180058923  mov     edi, eax
0x180058925  mov     r8d, eax
0x180058928  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x18005892f  lea     rcx, aPrintconfigCip; "PrintConfig::CIppCSRHelper::RegenerateR"...
0x180058936  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005893b  test    edi, edi
0x18005893d  jle     short loc_18005894A
0x18005893f  movzx   edi, di
0x180058942  or      edi, 80070000h
0x180058948  test    edi, edi
0x18005894a  js      loc_180058C6A
0x180058950  mov     [rsp+1D8h+NumberOfBytesWritten], r12d
0x180058955  lea     rdx, [rsp+1D8h+lpBuffer]
0x18005895d  cmp     [rsp+1D8h+var_70], 0Fh
0x180058966  cmova   rdx, [rsp+1D8h+lpBuffer]; lpBuffer
0x18005896f  mov     qword ptr [rsp+1D8h+nSize], r12; lpOverlapped
0x180058974  lea     r9, [rsp+1D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180058979  mov     r8d, [rsp+1D8h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180058981  mov     rcx, r14; hFile
0x180058984  call    cs:__imp_WriteFile
0x18005898a  test    eax, eax
0x18005898c  jz      loc_180058A52
0x180058992  mov     eax, [rsp+1D8h+NumberOfBytesWritten]
0x180058996  cmp     rax, qword ptr [rsp+1D8h+nNumberOfBytesToWrite]
0x18005899e  jnz     loc_180058A52
0x1800589a4  lea     rax, [r14-1]
0x1800589a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800589ac  ja      short loc_1800589B8
0x1800589ae  mov     rcx, r14; hObject
0x1800589b1  call    cs:__imp_CloseHandle
0x1800589b7  nop
0x1800589b8  mov     rax, [rsp+1D8h+var_178]
0x1800589bd  test    rax, rax
0x1800589c0  jz      short loc_1800589DB
0x1800589c2  mov     rcx, [rsp+1D8h+var_180]
0x1800589c7  test    rcx, rcx
0x1800589ca  jz      short loc_1800589DB
0x1800589cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589d1  mov     [rsp+1D8h+var_178], r12
0x1800589d6  mov     [rsp+1D8h+var_180], r12
0x1800589db  mov     rcx, [rsp+1D8h+hLibModule]; hLibModule
0x1800589e0  test    rcx, rcx
0x1800589e3  jz      short loc_1800589F0
0x1800589e5  call    cs:__imp_FreeLibrary
0x1800589eb  mov     [rsp+1D8h+hLibModule], r12
0x1800589f0  lea     rcx, [rsp+1D8h+var_48]
0x1800589f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800589fd  nop
0x1800589fe  lea     rcx, [rsp+1D8h+lpBuffer]
0x180058a06  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180058a0b  nop
0x180058a0c  lea     rcx, [rsp+1D8h+pData]
0x180058a14  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058a19  nop
0x180058a1a  test    ebx, ebx
0x180058a1c  jz      short loc_180058A25
0x180058a1e  call    cs:__imp_CoUninitialize
0x180058a24  nop
0x180058a25  mov     eax, [rsp+1D8h+var_198]
0x180058a29  mov     rcx, [rsp+1D8h+var_28]
0x180058a31  xor     rcx, rsp; StackCookie
0x180058a34  call    __security_check_cookie
0x180058a39  lea     r11, [rsp+1D8h+var_18]
0x180058a41  mov     rbx, [r11+28h]
0x180058a45  mov     rsi, [r11+30h]
0x180058a49  mov     rsp, r11
0x180058a4c  pop     r14
0x180058a4e  pop     r12
0x180058a50  pop     rdi
0x180058a51  retn
0x180058a52  call    cs:__imp_GetLastError
0x180058a58  mov     esi, eax
0x180058a5a  mov     r8d, eax
0x180058a5d  lea     rdx, aWritefileFaile_2; "WriteFile failed: error=%d"
0x180058a64  lea     rcx, aPrintconfigCip; "PrintConfig::CIppCSRHelper::RegenerateR"...
0x180058a6b  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180058a70  lea     rax, [r14-1]
0x180058a74  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058a78  ja      short loc_180058A93
0x180058a7a  call    cs:__imp_GetLastError
0x180058a80  mov     edi, eax
0x180058a82  mov     rcx, r14; hObject
  ... truncated ...
```
