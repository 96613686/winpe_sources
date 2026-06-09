# PrintConfig::CConfigManager::FetchDeviceDocumentFormat(int)

- ea: `0x1800436dc`
- end: `0x180043f3f`
- name: `?FetchDeviceDocumentFormat@CConfigManager@PrintConfig@@QEAAXH@Z`
- size: `2147`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x1800032e0`
- `0x180003310`
- `0x180004424`
- `0x18000da28`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x18000fb88`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018818`
- `0x180021820`
- `0x18003bb38`
- `0x18003e0e0`
- `0x1800436dc`
- `0x180043f48`
- `0x180048514`
- `0x18004a2a4`
- `0x18005082c`
- `0x1801adb58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043905`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004398b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043a11`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043a6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043aef`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043905`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004398b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043a11`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043a6e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043aef`
- `KERNEL32!WriteFile` at `0x180043c4e`
- `KERNEL32!WriteFile` at `0x180043c4e`
- `KERNEL32!DeleteFileW` at `0x180043e36`
- `KERNEL32!DeleteFileW` at `0x180043e36`
- `KERNEL32!CreateFileW` at `0x180043be8`
- `KERNEL32!CreateFileW` at `0x180043be8`
- `KERNEL32!FreeLibrary` at `0x180043dc2`
- `KERNEL32!FreeLibrary` at `0x180043dc2`
- `KERNEL32!CloseHandle` at `0x180043e0b`
- `KERNEL32!CloseHandle` at `0x180043e4a`
- `KERNEL32!CloseHandle` at `0x180043e0b`
- `KERNEL32!CloseHandle` at `0x180043e4a`
- `KERNEL32!SetLastError` at `0x180043e13`
- `KERNEL32!SetLastError` at `0x180043e13`
- `KERNEL32!GetLastError` at `0x180043bfc`
- `KERNEL32!GetLastError` at `0x180043de3`
- `KERNEL32!GetLastError` at `0x180043e00`
- `KERNEL32!GetLastError` at `0x180043bfc`
- `KERNEL32!GetLastError` at `0x180043de3`
- `KERNEL32!GetLastError` at `0x180043e00`
- `ole32!CoInitializeEx` at `0x180043722`
- `ole32!CoInitializeEx` at `0x180043722`
- `ole32!CoUninitialize` at `0x180043e7f`
- `ole32!CoUninitialize` at `0x180043e7f`
- `ole32!CoTaskMemFree` at `0x1800438b7`
- `ole32!CoTaskMemFree` at `0x1800438b7`
- `WINSPOOL!DeletePrinterDataW` at `0x180043c79`
- `WINSPOOL!DeletePrinterDataW` at `0x180043ce1`
- `WINSPOOL!DeletePrinterDataW` at `0x180043c79`
- `WINSPOOL!DeletePrinterDataW` at `0x180043ce1`
- `WINSPOOL!SetPrinterDataW` at `0x180043cbc`
- `WINSPOOL!SetPrinterDataW` at `0x180043d24`
- `WINSPOOL!SetPrinterDataW` at `0x180043cbc`
- `WINSPOOL!SetPrinterDataW` at `0x180043d24`
- `WINSPOOL!ClosePrinter` at `0x180043dab`
- `WINSPOOL!ClosePrinter` at `0x180043dab`

## string_xrefs

- `0x180043943`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18004395e`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800439c9`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800439e4`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180043a35`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180043a41`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180043b17`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180043b49`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x18004374d`: `PrintConfig::CConfigManager::FetchDeviceDocumentFormat`
- `0x18004382b`: `\Printer.Configuration:DocumentFormat`
- `0x180043c05`: `CreateFile failed: error=%d`
- `0x180043b8f`: `device_bidi_document_format.xml`
- `0x180043cd6`: `V4_RenderFilterConfig`
- `0x180043d19`: `V4_RenderFilterConfig`
- `0x180043dec`: `WriteFile failed: error=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall PrintConfig::CConfigManager::FetchDeviceDocumentFormat(PrintConfig::CConfigManager *this, int a2)
{
  int v4; // edi
  HRESULT v5; // eax
  void *v6; // rbx
  unsigned __int64 v7; // r8
  LPBYTE *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  _BYTE *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // r9
  LPBYTE *v15; // rdx
  _BYTE *v16; // rbx
  LPBYTE *v17; // rdx
  const char *v18; // rdx
  LPBYTE *v19; // rdx
  LPCVOID *v20; // rbx
  LPBYTE *v21; // rdx
  _BYTE *v22; // rbx
  _QWORD *v23; // r9
  __int64 v24; // rcx
  const WCHAR *v25; // rcx
  char *FileW; // rax
  char *v27; // rbx
  DWORD LastError; // eax
  LPCVOID *v29; // rdx
  BYTE *v30; // r9
  signed int v31; // eax
  bool v32; // sf
  BYTE *v33; // r9
  signed int v34; // eax
  bool v35; // sf
  __int64 PrinterSupportedFormats; // rdx
  const char *v37; // r9
  HMODULE *v38; // rsi
  void *v39; // rcx
  __int64 v40; // r8
  DWORD v41; // esi
  const WCHAR *v42; // rcx
  LPBYTE *v43; // r8
  int v44; // [rsp+40h] [rbp-148h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-144h] BYREF
  unsigned int v46[2]; // [rsp+48h] [rbp-140h] BYREF
  __int64 v47; // [rsp+50h] [rbp-138h]
  _BYTE pExceptionObject[32]; // [rsp+58h] [rbp-130h] BYREF
  _BYTE v49[32]; // [rsp+78h] [rbp-110h] BYREF
  _BYTE v50[32]; // [rsp+98h] [rbp-F0h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+B8h] [rbp-D0h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+C8h] [rbp-C0h]
  unsigned __int64 v53; // [rsp+D0h] [rbp-B8h]
  LPBYTE pData[2]; // [rsp+D8h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-A0h]
  LPCWSTR lpFileName[2]; // [rsp+F8h] [rbp-90h] BYREF
  int v57; // [rsp+108h] [rbp-80h]
  unsigned __int64 v58; // [rsp+110h] [rbp-78h]
  LPVOID pv[2]; // [rsp+118h] [rbp-70h] BYREF
  __int128 v60; // [rsp+128h] [rbp-60h]
  void *Block[2]; // [rsp+138h] [rbp-50h] BYREF
  __int128 v62; // [rsp+148h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v47 = -2;
  v4 = 0;
  v44 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    v4 = 1;
    v44 = 1;
  }
  else if ( v5 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v5);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
    L"m_printerName=%ws",
    *((_QWORD *)this + 2));
  if ( !*((_BYTE *)this + 30) )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
      L"Driver did not specify 'RetrievePrintPageDescriptionLanguageFromDevice=true'. Skipping.");
    goto LABEL_86;
  }
  *(_OWORD *)pData = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(pData[0]) = 0;
  if ( a2 )
  {
    *(_OWORD *)pv = 0;
    v60 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)pv, L"application/pdf", 0xFu);
    std::wstring::operator=(pData, pv);
    std::wstring::~wstring(pv);
    goto LABEL_14;
  }
  pv[0] = &CoTaskMemRAII<unsigned char *>::`vftable';
  pv[1] = 0;
  PrintConfig::CConfigManager::RetrieveBidiData(
    this,
    L"\\Printer.Configuration:DocumentFormat",
    0,
    6u,
    (unsigned __int8 **)&pv[1],
    v46);
  v6 = pv[1];
  if ( pv[1] )
  {
    *(_OWORD *)Block = 0;
    v62 = 0;
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv[1] + v7) );
    std::wstring::_Construct<1,unsigned short const *>((char **)Block, pv[1], v7);
    std::wstring::operator=(pData, Block);
    std::wstring::~wstring(Block);
    CoTaskMemFree(v6);
LABEL_14:
    *(_OWORD *)lpBuffer = 0;
    *(_QWORD *)nNumberOfBytesToWrite = 0;
    v53 = 15;
    LOBYTE(lpBuffer[0]) = 0;
    v8 = pData;
    if ( si128.m128i_i64[1] > 7uLL )
      v8 = (LPBYTE *)pData[0];
    if ( (unsigned int)_o__wcsicmp(L"application/pdf", v8) )
    {
      v15 = pData;
      if ( si128.m128i_i64[1] > 7uLL )
        v15 = (LPBYTE *)pData[0];
      if ( (unsigned int)_o__wcsicmp(L"image/pwg-raster", v15) )
      {
        v17 = pData;
        if ( si128.m128i_i64[1] > 7uLL )
          v17 = (LPBYTE *)pData[0];
        if ( (unsigned int)_o__wcsicmp(L"application/PCLm", v17) )
        {
          v19 = pData;
          if ( si128.m128i_i64[1] > 7uLL )
            v19 = (LPBYTE *)pData[0];
          if ( !(unsigned int)_o__wcsicmp(L"application/oxps", v19) )
          {
            v10 = 10;
            if ( v53 >= 0xA )
            {
              v20 = lpBuffer;
              if ( v53 > 0xF )
                v20 = (LPCVOID *)lpBuffer[0];
              *(_QWORD *)nNumberOfBytesToWrite = 10;
              memmove_0(v20, "<Filters/>", 0xAu);
              *((_BYTE *)v20 + 10) = 0;
              goto LABEL_48;
            }
            v14 = "<Filters/>";
            goto LABEL_47;
          }
          v21 = pData;
          if ( si128.m128i_i64[1] > 7uLL )
            v21 = (LPBYTE *)pData[0];
          if ( (unsigned int)_o__wcsicmp(L"image/tiff", v21) )
          {
            v43 = pData;
            if ( si128.m128i_i64[1] > 7uLL )
              v43 = (LPBYTE *)pData[0];
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
              "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
              L"BIDI query for document format returned un-supported document format %ws.",
              v43);
            goto LABEL_84;
          }
          v10 = 382;
          if ( v53 < 0x17E )
          {
            v14 = "<Filters><Filter dll = \"TiffRenderFilter.dll\" clsid = \"{42A38C2A-038A-4595-A4E2-00803F9FAEC0}\" nam"
                  "e = \"Tiff Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IX"
                  "psDocumentProvider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrin"
                  "tWriteStream\" /></Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
            goto LABEL_47;
          }
          *(_QWORD *)nNumberOfBytesToWrite = 382;
          v18 = "<Filters><Filter dll = \"TiffRenderFilter.dll\" clsid = \"{42A38C2A-038A-4595-A4E2-00803F9FAEC0}\" name "
                "= \"Tiff Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDo"
                "cumentProvider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWrite"
                "Stream\" /></Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
        }
        else
        {
          v10 = 382;
          if ( v53 < 0x17E )
          {
            v14 = "<Filters><Filter dll = \"PCLmRenderFilter.dll\" clsid = \"{39E2F832-C9AD-4D89-A777-79ED49AC0274}\" nam"
                  "e = \"PCLm Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IX"
                  "psDocumentProvider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrin"
                  "tWriteStream\" /></Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
            goto LABEL_47;
          }
          *(_QWORD *)nNumberOfBytesToWrite = 382;
          v18 = "<Filters><Filter dll = \"PCLmRenderFilter.dll\" clsid = \"{39E2F832-C9AD-4D89-A777-79ED49AC0274}\" name "
                "= \"PCLm Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDo"
                "cumentProvider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWrite"
                "Stream\" /></Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
        }
        v22 = lpBuffer[0];
        memmove_0((void *)lpBuffer[0], v18, 0x17Eu);
        v22[382] = 0;
        goto LABEL_48;
      }
      v10 = 388;
      if ( v53 >= 0x184 )
      {
        v16 = lpBuffer[0];
        *(_QWORD *)nNumberOfBytesToWrite = 388;
        memmove_0(
          (void *)lpBuffer[0],
          "<Filters><Filter dll = \"PWGRRenderFilter.dll\" clsid = \"{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}\" name = \"PW"
          "G Raster Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocument"
          "Provider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream\" /><"
          "/Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>",
          0x184u);
        v16[388] = 0;
        goto LABEL_48;
      }
      v14 = "<Filters><Filter dll = \"PWGRRenderFilter.dll\" clsid = \"{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}\" name = \""
            "PWG Raster Render Filter\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocu"
            "mentProvider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" Comment = \"IID_IPrintWriteStream"
            "\" /></Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
    }
    else
    {
      v10 = 383;
      if ( v53 >= 0x17F )
      {
        v11 = lpBuffer[0];
        *(_QWORD *)nNumberOfBytesToWrite = 383;
        memmove_0(
          (void *)lpBuffer[0],
          "<Filters><Filter dll = \"PDFRenderFilter.dll\" clsid = \"{CD087E95-A362-4A50-B233-20DC89DED268}\" name = \"Mic"
          "rosoft XPS to PDF\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentProvi"
          "der\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" comment = \"IID_IPrintWriteStream\" /></Filt"
          "er><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>",
          0x17Fu);
        v11[383] = 0;
LABEL_48:
        v23 = (_QWORD *)((char *)this + 32);
        v24 = *((_QWORD *)this + 6);
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v24) < 0x1F )
          std::_Xlen_string();
        if ( *((_QWORD *)this + 7) > 7u )
          v23 = (_QWORD *)*v23;
        std::wstring::wstring(lpFileName, v12, v13, v23, v24, L"device_bidi_document_format.xml", 31);
        v25 = (const WCHAR *)lpFileName;
        if ( v58 > 7 )
          v25 = lpFileName[0];
        FileW = (char *)CreateFileW(v25, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
        v27 = FileW;
        *(_QWORD *)v46 = FileW;
        if ( FileW == (char *)-1LL )
        {
          LastError = GetLastError();
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
            "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
            L"CreateFile failed: error=%d",
            LastError);
        }
        else
        {
          NumberOfBytesWritten = 0;
          v29 = lpBuffer;
          if ( v53 > 0xF )
            v29 = (LPCVOID *)lpBuffer[0];
          if ( WriteFile(FileW, v29, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0)
            && NumberOfBytesWritten == *(_QWORD *)nNumberOfBytesToWrite )
          {
            DeletePrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_DocumentFormat");
            v30 = (BYTE *)pData;
            if ( si128.m128i_i64[1] > 7uLL )
              v30 = pData[0];
            v31 = SetPrinterDataW(
                    *((HANDLE *)this + 8),
                    (LPWSTR)L"V4_DocumentFormat",
                    1u,
                    v30,
                    2 * si128.m128i_i32[0] + 2);
            v32 = v31 < 0;
            if ( v31 > 0 )
            {
              v31 = (unsigned __int16)v31 | 0x80070000;
              v32 = v31 < 0;
            }
            if ( v32 )
            {
              hr_error::hr_error((hr_error *)v49, v31);
              throw (hr_error *)v49;
            }
            DeletePrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_RenderFilterConfig");
            v33 = (BYTE *)lpFileName;
            if ( v58 > 7 )
              v33 = (BYTE *)lpFileName[0];
            v34 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_RenderFilterConfig", 1u, v33, 2 * v57 + 2);
            v35 = v34 < 0;
            if ( v34 > 0 )
            {
              v34 = (unsigned __int16)v34 | 0x80070000;
              v35 = v34 < 0;
            }
            if ( v35 )
            {
              hr_error::hr_error((hr_error *)v50, v34);
              throw (hr_error *)v50;
            }
            try
            {
              PassthroughUtil::PassthroughHelper::PassthroughHelper(
                (PassthroughUtil::PassthroughHelper *)Block,
                *((const unsigned __int16 **)this + 2));
              PrinterSupportedFormats = PrintConfig::CConfigManager::FetchPrinterSupportedFormats(this, pv, pData);
              PassthroughUtil::PassthroughHelper::SetIppSupportedFormats(Block, PrinterSupportedFormats);
              std::vector<std::wstring>::_Tidy(pv);
              std::wstring::~wstring(&v62);
              v38 = (HMODULE *)Block[0];
              if ( Block[0] )
              {
                v39 = (void *)*((_QWORD *)Block[0] + 5);
                if ( v39 )
                  ClosePrinter(v39);
                std::wstring::~wstring(v38 + 1);
                if ( *v38 )
                  FreeLibrary(*v38);
                operator delete(v38);
              }
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x3AB,
                (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
                v37);
              v4 = v44;
              v27 = *(char **)v46;
            }
          }
          else
          {
            v40 = GetLastError();
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
              "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
              L"WriteFile failed: error=%d",
              v40);
            if ( v27 )
            {
              v41 = GetLastError();
              CloseHandle(v27);
              SetLastError(v41);
            }
            v27 = 0;
            v42 = (const WCHAR *)lpFileName;
            if ( v58 > 7 )
              v42 = lpFileName[0];
            DeleteFileW(v42);
          }
          if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v27);
        }
        std::wstring::~wstring(lpFileName);
LABEL_84:
        std::string::~string((char **)lpBuffer);
        goto LABEL_85;
      }
      v14 = "<Filters><Filter dll = \"PDFRenderFilter.dll\" clsid = \"{CD087E95-A362-4A50-B233-20DC89DED268}\" name = \"M"
            "icrosoft XPS to PDF\"><Input guid = \"{b8cf8530-5562-47c4-ab67-b1f69ecf961e}\" Comment = \"IID_IXpsDocumentP"
            "rovider\" /><Output guid = \"{65bb7f1b-371e-4571-8ac7-912f510c1a38}\" comment = \"IID_IPrintWriteStream\" />"
            "</Filter><FilterServiceProvider dll = \"XpsRasterService.dll\" /></Filters>";
    }
LABEL_47:
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(lpBuffer, v10, v9, v14);
    goto LABEL_48;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
    L"BIDI query for document format returned null.");
LABEL_85:
  std::wstring::~wstring(pData);
LABEL_86:
  if ( v4 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800436dc  mov     rax, rsp
0x1800436df  push    rdi
0x1800436e0  push    r13
0x1800436e2  push    r14
0x1800436e4  sub     rsp, 170h
0x1800436eb  mov     [rsp+188h+var_138], 0FFFFFFFFFFFFFFFEh
0x1800436f4  mov     [rax+10h], rbx
0x1800436f8  mov     [rax+18h], rsi
0x1800436fc  mov     rax, cs:__security_cookie
0x180043703  xor     rax, rsp
0x180043706  mov     [rsp+188h+var_20], rax
0x18004370e  mov     ebx, edx
0x180043710  mov     rsi, rcx
0x180043713  xor     r14d, r14d
0x180043716  mov     edi, r14d
0x180043719  mov     [rsp+188h+var_148], r14d
0x18004371e  xor     edx, edx; dwCoInit
0x180043720  xor     ecx, ecx; pvReserved
0x180043722  call    cs:__imp_CoInitializeEx
0x180043728  test    eax, eax
0x18004372a  jns     short loc_180043739
0x18004372c  cmp     eax, 80010106h
0x180043731  jnz     loc_180043ED9
0x180043737  jmp     short loc_180043742
0x180043739  mov     edi, 1
0x18004373e  mov     [rsp+188h+var_148], edi
0x180043742  mov     r8, [rsi+10h]
0x180043746  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x18004374d  lea     r13, aPrintconfigCco_5; "PrintConfig::CConfigManager::FetchDevic"...
0x180043754  mov     rcx, r13; char *
0x180043757  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004375c  cmp     [rsi+1Eh], r14b
0x180043760  jnz     short loc_180043776
0x180043762  lea     rdx, aDriverDidNotSp; "Driver did not specify 'RetrievePrintPa"...
0x180043769  mov     rcx, r13; char *
0x18004376c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043771  jmp     loc_180043E7B
0x180043776  xorps   xmm0, xmm0
0x180043779  movups  xmmword ptr [rsp+188h+pData], xmm0
0x180043781  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180043789  movdqu  [rsp+188h+var_A0], xmm1
0x180043792  mov     word ptr [rsp+188h+pData], r14w
0x18004379b  test    ebx, ebx
0x18004379d  jz      short loc_1800437F4
0x18004379f  movups  xmmword ptr [rsp+188h+pv], xmm0
0x1800437a7  xorps   xmm1, xmm1
0x1800437aa  movdqu  [rsp+188h+var_60], xmm1
0x1800437b3  mov     r8d, 0Fh
0x1800437b9  lea     rdx, aApplicationPdf; "application/pdf"
0x1800437c0  lea     rcx, [rsp+188h+pv]
0x1800437c8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800437cd  lea     rdx, [rsp+188h+pv]
0x1800437d5  lea     rcx, [rsp+188h+pData]
0x1800437dd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800437e2  lea     rcx, [rsp+188h+pv]
0x1800437ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800437ef  jmp     loc_1800438BD
0x1800437f4  lea     rax, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x1800437fb  mov     [rsp+188h+pv], rax
0x180043803  mov     [rsp+188h+pv+8], r14
0x18004380b  lea     rax, [rsp+188h+var_140]
0x180043810  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], rax; unsigned int *
0x180043815  lea     rax, [rsp+188h+pv+8]
0x18004381d  mov     qword ptr [rsp+188h+dwCreationDisposition], rax; unsigned __int8 **
0x180043822  mov     r9d, 6; unsigned int
0x180043828  xor     r8d, r8d; unsigned __int16 *
0x18004382b  lea     rdx, aPrinterConfigu_0; "\\Printer.Configuration:DocumentFormat"
0x180043832  mov     rcx, rsi; this
0x180043835  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18004383a  mov     rbx, [rsp+188h+pv+8]
0x180043842  test    rbx, rbx
0x180043845  jnz     short loc_18004385C
0x180043847  lea     rdx, aBidiQueryForDo; "BIDI query for document format returned"...
0x18004384e  mov     rcx, r13; char *
0x180043851  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043856  nop
0x180043857  jmp     loc_180043E6D
0x18004385c  xorps   xmm0, xmm0
0x18004385f  movups  xmmword ptr [rsp+188h+Block], xmm0
0x180043867  xorps   xmm1, xmm1
0x18004386a  movdqu  [rsp+188h+var_40], xmm1
0x180043873  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043877  inc     r8
0x18004387a  cmp     [rbx+r8*2], r14w
0x18004387f  jnz     short loc_180043877
0x180043881  mov     rdx, rbx
0x180043884  lea     rcx, [rsp+188h+Block]
0x18004388c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043891  lea     rdx, [rsp+188h+Block]
0x180043899  lea     rcx, [rsp+188h+pData]
0x1800438a1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800438a6  lea     rcx, [rsp+188h+Block]
0x1800438ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800438b3  nop
0x1800438b4  mov     rcx, rbx; pv
0x1800438b7  call    cs:__imp_CoTaskMemFree
0x1800438bd  xorps   xmm0, xmm0
0x1800438c0  movups  xmmword ptr [rsp+188h+lpBuffer], xmm0
0x1800438c8  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], r14
0x1800438d0  mov     [rsp+188h+var_B8], 0Fh
0x1800438dc  mov     byte ptr [rsp+188h+lpBuffer], r14b
0x1800438e4  lea     rdx, [rsp+188h+pData]
0x1800438ec  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x1800438f5  cmova   rdx, [rsp+188h+pData]
0x1800438fe  lea     rcx, aApplicationPdf; "application/pdf"
0x180043905  call    cs:__imp__o__wcsicmp
0x18004390b  test    eax, eax
0x18004390d  jnz     short loc_18004396A
0x18004390f  mov     edx, 17Fh
0x180043914  cmp     [rsp+188h+var_B8], rdx
0x18004391c  jb      short loc_18004395E
0x18004391e  lea     rbx, [rsp+188h+lpBuffer]
0x180043926  cmp     [rsp+188h+var_B8], 0Fh
0x18004392f  cmova   rbx, [rsp+188h+lpBuffer]
0x180043938  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180043940  mov     r8d, edx; Size
0x180043943  lea     rdx, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x18004394a  mov     rcx, rbx; void *
0x18004394d  call    memmove_0
0x180043952  mov     [rbx+17Fh], r14b
0x180043959  jmp     loc_180043B5D
0x18004395e  lea     r9, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x180043965  jmp     loc_180043B50
0x18004396a  lea     rdx, [rsp+188h+pData]
0x180043972  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x18004397b  cmova   rdx, [rsp+188h+pData]
0x180043984  lea     rcx, aImagePwgRaster; "image/pwg-raster"
0x18004398b  call    cs:__imp__o__wcsicmp
0x180043991  test    eax, eax
0x180043993  jnz     short loc_1800439F0
0x180043995  mov     edx, 184h
0x18004399a  cmp     [rsp+188h+var_B8], rdx
0x1800439a2  jb      short loc_1800439E4
0x1800439a4  lea     rbx, [rsp+188h+lpBuffer]
0x1800439ac  cmp     [rsp+188h+var_B8], 0Fh
0x1800439b5  cmova   rbx, [rsp+188h+lpBuffer]
0x1800439be  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x1800439c6  mov     r8d, edx; Size
0x1800439c9  lea     rdx, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x1800439d0  mov     rcx, rbx; void *
0x1800439d3  call    memmove_0
0x1800439d8  mov     [rbx+184h], r14b
0x1800439df  jmp     loc_180043B5D
0x1800439e4  lea     r9, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x1800439eb  jmp     loc_180043B50
0x1800439f0  lea     rdx, [rsp+188h+pData]
0x1800439f8  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180043a01  cmova   rdx, [rsp+188h+pData]
0x180043a0a  lea     rcx, aApplicationPcl; "application/PCLm"
0x180043a11  call    cs:__imp__o__wcsicmp
0x180043a17  test    eax, eax
0x180043a19  jnz     short loc_180043A4D
0x180043a1b  mov     edx, 17Eh
0x180043a20  cmp     [rsp+188h+var_B8], rdx
0x180043a28  jb      short loc_180043A41
0x180043a2a  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180043a32  mov     r8d, edx
0x180043a35  lea     rdx, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x180043a3c  jmp     loc_180043B1E
0x180043a41  lea     r9, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x180043a48  jmp     loc_180043B50
0x180043a4d  lea     rdx, [rsp+188h+pData]
0x180043a55  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180043a5e  cmova   rdx, [rsp+188h+pData]
0x180043a67  lea     rcx, aApplicationOxp; "application/oxps"
0x180043a6e  call    cs:__imp__o__wcsicmp
0x180043a74  test    eax, eax
0x180043a76  jnz     short loc_180043ACE
0x180043a78  lea     edx, [rax+0Ah]
0x180043a7b  cmp     [rsp+188h+var_B8], rdx
0x180043a83  jb      short loc_180043AC2
0x180043a85  lea     rbx, [rsp+188h+lpBuffer]
0x180043a8d  cmp     [rsp+188h+var_B8], 0Fh
0x180043a96  cmova   rbx, [rsp+188h+lpBuffer]
0x180043a9f  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180043aa7  mov     r8d, edx; Size
0x180043aaa  lea     rdx, aFilters; "<Filters/>"
0x180043ab1  mov     rcx, rbx; void *
0x180043ab4  call    memmove_0
0x180043ab9  mov     [rbx+0Ah], r14b
0x180043abd  jmp     loc_180043B5D
0x180043ac2  lea     r9, aFilters; "<Filters/>"
0x180043ac9  jmp     loc_180043B50
0x180043ace  lea     rdx, [rsp+188h+pData]
0x180043ad6  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180043adf  cmova   rdx, [rsp+188h+pData]
0x180043ae8  lea     rcx, aImageTiff; "image/tiff"
0x180043aef  call    cs:__imp__o__wcsicmp
0x180043af5  test    eax, eax
0x180043af7  jnz     loc_180043EAE
0x180043afd  mov     edx, 17Eh
0x180043b02  cmp     [rsp+188h+var_B8], rdx
0x180043b0a  jb      short loc_180043B49
0x180043b0c  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180043b14  mov     r8d, edx; Size
0x180043b17  lea     rdx, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x180043b1e  lea     rbx, [rsp+188h+lpBuffer]
0x180043b26  cmp     [rsp+188h+var_B8], 0Fh
0x180043b2f  cmova   rbx, [rsp+188h+lpBuffer]
0x180043b38  mov     rcx, rbx; void *
0x180043b3b  call    memmove_0
0x180043b40  mov     [rbx+17Eh], r14b
0x180043b47  jmp     short loc_180043B5D
0x180043b49  lea     r9, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x180043b50  lea     rcx, [rsp+188h+lpBuffer]
0x180043b58  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180043b5d  lea     r9, [rsi+20h]
0x180043b61  mov     rcx, [r9+10h]
0x180043b65  mov     rax, 7FFFFFFFFFFFFFFEh
0x180043b6f  sub     rax, rcx
0x180043b72  cmp     rax, 1Fh
0x180043b76  jb      loc_180043EF7
0x180043b7c  cmp     qword ptr [r9+18h], 7
0x180043b81  jbe     short loc_180043B86
0x180043b83  mov     r9, [r9]
0x180043b86  mov     [rsp+188h+hTemplateFile], 1Fh
0x180043b8f  lea     rax, aDeviceBidiDocu; "device_bidi_document_format.xml"
0x180043b96  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], rax
0x180043b9b  mov     qword ptr [rsp+188h+dwCreationDisposition], rcx
0x180043ba0  lea     rcx, [rsp+188h+lpFileName]
0x180043ba8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043bad  nop
0x180043bae  lea     rcx, [rsp+188h+lpFileName]
0x180043bb6  cmp     [rsp+188h+var_78], 7
0x180043bbf  cmova   rcx, [rsp+188h+lpFileName]; lpFileName
0x180043bc8  mov     [rsp+188h+hTemplateFile], r14; hTemplateFile
0x180043bcd  mov     [rsp+188h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180043bd5  mov     [rsp+188h+dwCreationDisposition], 2; dwCreationDisposition
0x180043bdd  xor     r9d, r9d; lpSecurityAttributes
0x180043be0  xor     r8d, r8d; dwShareMode
0x180043be3  mov     edx, 40000000h; dwDesiredAccess
0x180043be8  call    cs:__imp_CreateFileW
0x180043bee  mov     rbx, rax
0x180043bf1  mov     qword ptr [rsp+188h+var_140], rax
0x180043bf6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043bfa  jnz     short loc_180043C1A
0x180043bfc  call    cs:__imp_GetLastError
0x180043c02  mov     r8d, eax
0x180043c05  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x180043c0c  mov     rcx, r13; char *
0x180043c0f  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180043c14  nop
0x180043c15  jmp     loc_180043E51
0x180043c1a  mov     [rsp+188h+NumberOfBytesWritten], r14d
0x180043c1f  lea     rdx, [rsp+188h+lpBuffer]
0x180043c27  cmp     [rsp+188h+var_B8], 0Fh
0x180043c30  cmova   rdx, [rsp+188h+lpBuffer]; lpBuffer
0x180043c39  mov     qword ptr [rsp+188h+dwCreationDisposition], r14; lpOverlapped
0x180043c3e  lea     r9, [rsp+188h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180043c43  mov     r8d, [rsp+188h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180043c4b  mov     rcx, rbx; hFile
0x180043c4e  call    cs:__imp_WriteFile
0x180043c54  test    eax, eax
0x180043c56  jz      loc_180043DE3
0x180043c5c  mov     eax, [rsp+188h+NumberOfBytesWritten]
0x180043c60  cmp     rax, qword ptr [rsp+188h+nNumberOfBytesToWrite]
0x180043c68  jnz     loc_180043DE3
0x180043c6e  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x180043c75  mov     rcx, [rsi+40h]; hPrinter
0x180043c79  call    cs:__imp_DeletePrinterDataW
0x180043c7f  mov     eax, dword ptr [rsp+188h+var_A0]
0x180043c86  lea     r9, [rsp+188h+pData]
0x180043c8e  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180043c97  cmova   r9, [rsp+188h+pData]; pData
0x180043ca0  lea     eax, ds:2[rax*2]
0x180043ca7  mov     [rsp+188h+dwCreationDisposition], eax; cbData
0x180043cab  mov     r8d, 1; Type
0x180043cb1  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x180043cb8  mov     rcx, [rsi+40h]; hPrinter
0x180043cbc  call    cs:__imp_SetPrinterDataW
0x180043cc2  test    eax, eax
0x180043cc4  jle     short loc_180043CD0
0x180043cc6  movzx   eax, ax
0x180043cc9  or      eax, 80070000h
0x180043cce  test    eax, eax
0x180043cd0  js      loc_180043EFD
0x180043cd6  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x180043cdd  mov     rcx, [rsi+40h]; hPrinter
0x180043ce1  call    cs:__imp_DeletePrinterDataW
0x180043ce7  mov     eax, [rsp+188h+var_80]
0x180043cee  lea     r9, [rsp+188h+lpFileName]
0x180043cf6  cmp     [rsp+188h+var_78], 7
0x180043cff  cmova   r9, [rsp+188h+lpFileName]; pData
0x180043d08  lea     eax, ds:2[rax*2]
0x180043d0f  mov     [rsp+188h+dwCreationDisposition], eax; cbData
0x180043d13  mov     r8d, 1; Type
0x180043d19  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x180043d20  mov     rcx, [rsi+40h]; hPrinter
0x180043d24  call    cs:__imp_SetPrinterDataW
0x180043d2a  test    eax, eax
0x180043d2c  jle     short loc_180043D38
0x180043d2e  movzx   eax, ax
0x180043d31  or      eax, 80070000h
0x180043d36  test    eax, eax
0x180043d38  js      loc_180043F1B
0x180043d3e  mov     rdx, [rsi+10h]; unsigned __int16 *
0x180043d42  lea     rcx, [rsp+188h+Block]; this
0x180043d4a  call    ??0PassthroughHelper@PassthroughUtil@@QEAA@PEBG_N@Z; PassthroughUtil::PassthroughHelper::PassthroughHelper(ushort const *,bool)
0x180043d4f  nop
0x180043d50  lea     r8, [rsp+188h+pData]
  ... truncated ...
```
