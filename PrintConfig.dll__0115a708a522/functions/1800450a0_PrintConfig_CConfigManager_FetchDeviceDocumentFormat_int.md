# PrintConfig::CConfigManager::FetchDeviceDocumentFormat(int)

- ea: `0x1800450a0`
- end: `0x180045994`
- name: `?FetchDeviceDocumentFormat@CConfigManager@PrintConfig@@QEAAXH@Z`
- size: `2292`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bb3c`

## callees

- `0x180003400`
- `0x180003430`
- `0x180004564`
- `0x18000de1c`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800100a0`
- `0x180018f00`
- `0x180018f58`
- `0x180019388`
- `0x180022268`
- `0x18003d134`
- `0x18003f724`
- `0x1800450a0`
- `0x18004599c`
- `0x18004a36c`
- `0x18004c18c`
- `0x1800527f8`
- `0x1801b56c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800452d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045361`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800453ed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800454d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800452d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045361`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800453ed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180045450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800454d7`
- `KERNEL32!WriteFile` at `0x180045648`
- `KERNEL32!WriteFile` at `0x180045648`
- `KERNEL32!DeleteFileW` at `0x180045875`
- `KERNEL32!DeleteFileW` at `0x180045875`
- `KERNEL32!CreateFileW` at `0x1800455d6`
- `KERNEL32!CreateFileW` at `0x1800455d6`
- `KERNEL32!FreeLibrary` at `0x1800457e0`
- `KERNEL32!FreeLibrary` at `0x1800457e0`
- `KERNEL32!CloseHandle` at `0x18004583e`
- `KERNEL32!CloseHandle` at `0x18004588f`
- `KERNEL32!CloseHandle` at `0x18004583e`
- `KERNEL32!CloseHandle` at `0x18004588f`
- `KERNEL32!SetLastError` at `0x18004584c`
- `KERNEL32!SetLastError` at `0x18004584c`
- `KERNEL32!GetLastError` at `0x1800455f0`
- `KERNEL32!GetLastError` at `0x18004580a`
- `KERNEL32!GetLastError` at `0x18004582d`
- `KERNEL32!GetLastError` at `0x1800455f0`
- `KERNEL32!GetLastError` at `0x18004580a`
- `KERNEL32!GetLastError` at `0x18004582d`
- `ole32!CoInitializeEx` at `0x1800450e6`
- `ole32!CoInitializeEx` at `0x1800450e6`
- `ole32!CoUninitialize` at `0x1800458ca`
- `ole32!CoUninitialize` at `0x1800458ca`
- `ole32!CoTaskMemFree` at `0x180045281`
- `ole32!CoTaskMemFree` at `0x180045281`
- `WINSPOOL!DeletePrinterDataW` at `0x180045679`
- `WINSPOOL!DeletePrinterDataW` at `0x1800456ed`
- `WINSPOOL!DeletePrinterDataW` at `0x180045679`
- `WINSPOOL!DeletePrinterDataW` at `0x1800456ed`
- `WINSPOOL!SetPrinterDataW` at `0x1800456c2`
- `WINSPOOL!SetPrinterDataW` at `0x180045736`
- `WINSPOOL!SetPrinterDataW` at `0x1800456c2`
- `WINSPOOL!SetPrinterDataW` at `0x180045736`
- `WINSPOOL!ClosePrinter` at `0x1800457c3`
- `WINSPOOL!ClosePrinter` at `0x1800457c3`

## string_xrefs

- `0x180045319`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045334`: `<Filters><Filter dll = "PDFRenderFilter.dll" clsid = "{CD087E95-A362-4A50-B233-20DC89DED268}" name = "Microsoft XPS to PDF"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800453a5`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x1800453c0`: `<Filters><Filter dll = "PWGRRenderFilter.dll" clsid = "{D6E2ECD4-16AC-4101-98D6-4A34B4D8A87B}" name = "PWG Raster Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045417`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045423`: `<Filters><Filter dll = "PCLmRenderFilter.dll" clsid = "{39E2F832-C9AD-4D89-A777-79ED49AC0274}" name = "PCLm Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045505`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045537`: `<Filters><Filter dll = "TiffRenderFilter.dll" clsid = "{42A38C2A-038A-4595-A4E2-00803F9FAEC0}" name = "Tiff Render Filter"><Input guid = "{b8cf8530-5562-47c4-ab67-b1f69ecf961e}" Comment = "IID_IXpsDocumentProvider" /><Output guid = "{65bb7f1b-371e-4571-8ac7-912f510c1a38}" Comment = "IID_IPrintWriteStream" /></Filter><FilterServiceProvider dll = "XpsRasterService.dll" /></Filters>`
- `0x180045117`: `PrintConfig::CConfigManager::FetchDeviceDocumentFormat`
- `0x1800451f5`: `\Printer.Configuration:DocumentFormat`
- `0x1800455ff`: `CreateFile failed: error=%d`
- `0x18004557d`: `device_bidi_document_format.xml`
- `0x1800456e2`: `V4_RenderFilterConfig`
- `0x18004572b`: `V4_RenderFilterConfig`
- `0x180045819`: `WriteFile failed: error=%d`

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
  size_t v10; // rdx
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
  __int64 v35; // r8
  bool v36; // sf
  unsigned __int64 *PrinterSupportedFormats; // rdx
  const char *v38; // r9
  char **v39; // rsi
  void *v40; // rcx
  __int64 v41; // r8
  DWORD v42; // esi
  const WCHAR *v43; // rcx
  LPBYTE *v44; // r8
  int v45; // [rsp+40h] [rbp-148h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-144h] BYREF
  unsigned int v47[2]; // [rsp+48h] [rbp-140h] BYREF
  __int64 v48; // [rsp+50h] [rbp-138h]
  _BYTE pExceptionObject[32]; // [rsp+58h] [rbp-130h] BYREF
  _BYTE v50[32]; // [rsp+78h] [rbp-110h] BYREF
  _BYTE v51[32]; // [rsp+98h] [rbp-F0h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+B8h] [rbp-D0h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+C8h] [rbp-C0h]
  unsigned __int64 v54; // [rsp+D0h] [rbp-B8h]
  LPBYTE pData[2]; // [rsp+D8h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-A0h]
  LPCWSTR lpFileName[2]; // [rsp+F8h] [rbp-90h] BYREF
  int v58; // [rsp+108h] [rbp-80h]
  unsigned __int64 v59; // [rsp+110h] [rbp-78h]
  LPVOID pv[2]; // [rsp+118h] [rbp-70h] BYREF
  __int128 v61; // [rsp+128h] [rbp-60h]
  void *Block[2]; // [rsp+138h] [rbp-50h] BYREF
  __int128 v63; // [rsp+148h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v48 = -2;
  v4 = 0;
  v45 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    v4 = 1;
    v45 = 1;
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
    v61 = 0;
    std::wstring::_Construct<1,unsigned short const *>(pv, L"application/pdf", 0xFu);
    std::wstring::operator=((char **)pData, (__int64)pv);
    std::wstring::~wstring((char **)pv);
    goto LABEL_14;
  }
  pv[0] = &CoTaskMemRAII<unsigned char *>::`vftable';
  pv[1] = 0;
  PrintConfig::CConfigManager::RetrieveBidiData(
    this,
    L"\\Printer.Configuration:DocumentFormat",
    0,
    6,
    (unsigned __int8 **)&pv[1],
    v47);
  v6 = pv[1];
  if ( pv[1] )
  {
    *(_OWORD *)Block = 0;
    v63 = 0;
    v7 = -1;
    do
      ++v7;
    while ( *((_WORD *)pv[1] + v7) );
    std::wstring::_Construct<1,unsigned short const *>(Block, pv[1], v7);
    std::wstring::operator=((char **)pData, (__int64)Block);
    std::wstring::~wstring((char **)Block);
    CoTaskMemFree(v6);
LABEL_14:
    *(_OWORD *)lpBuffer = 0;
    *(_QWORD *)nNumberOfBytesToWrite = 0;
    v54 = 15;
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
            if ( v54 >= 0xA )
            {
              v20 = lpBuffer;
              if ( v54 > 0xF )
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
            v44 = pData;
            if ( si128.m128i_i64[1] > 7uLL )
              v44 = (LPBYTE *)pData[0];
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
              "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
              L"BIDI query for document format returned un-supported document format %ws.",
              v44);
            goto LABEL_84;
          }
          v10 = 382;
          if ( v54 < 0x17E )
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
          if ( v54 < 0x17E )
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
      if ( v54 >= 0x184 )
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
      if ( v54 >= 0x17F )
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
        std::wstring::wstring((char *)lpFileName, v12, v13, v23, v24, L"device_bidi_document_format.xml", 31);
        v25 = (const WCHAR *)lpFileName;
        if ( v59 > 7 )
          v25 = lpFileName[0];
        FileW = (char *)CreateFileW(v25, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
        v27 = FileW;
        *(_QWORD *)v47 = FileW;
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
          if ( v54 > 0xF )
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
              hr_error::hr_error((hr_error *)v50, v31);
              throw (hr_error *)v50;
            }
            DeletePrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_RenderFilterConfig");
            v33 = (BYTE *)lpFileName;
            if ( v59 > 7 )
              v33 = (BYTE *)lpFileName[0];
            v34 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_RenderFilterConfig", 1u, v33, 2 * v58 + 2);
            v36 = v34 < 0;
            if ( v34 > 0 )
            {
              v34 = (unsigned __int16)v34 | 0x80070000;
              v36 = v34 < 0;
            }
            if ( v36 )
            {
              hr_error::hr_error((hr_error *)v51, v34);
              throw (hr_error *)v51;
            }
            try
            {
              PassthroughUtil::PassthroughHelper::PassthroughHelper(
                (PassthroughUtil::PassthroughHelper *)Block,
                *((const unsigned __int16 **)this + 2),
                v35);
              PrinterSupportedFormats = PrintConfig::CConfigManager::FetchPrinterSupportedFormats(
                                          (__int64)this,
                                          (unsigned __int64 *)pv,
                                          (const wchar_t *)pData);
              PassthroughUtil::PassthroughHelper::SetIppSupportedFormats(
                (__int64 *)Block,
                (__int64)PrinterSupportedFormats);
              std::vector<std::wstring>::_Tidy((__int64)pv);
              std::wstring::~wstring((char **)&v63);
              v39 = (char **)Block[0];
              if ( Block[0] )
              {
                v40 = (void *)*((_QWORD *)Block[0] + 5);
                if ( v40 )
                  ClosePrinter(v40);
                std::wstring::~wstring(v39 + 1);
                if ( *v39 )
                  FreeLibrary((HMODULE)*v39);
                operator delete(v39);
              }
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x3BD,
                (int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
                v38);
              v4 = v45;
              v27 = *(char **)v47;
            }
          }
          else
          {
            v41 = GetLastError();
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
              "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
              L"WriteFile failed: error=%d",
              v41);
            if ( v27 )
            {
              v42 = GetLastError();
              CloseHandle(v27);
              SetLastError(v42);
            }
            v27 = 0;
            v43 = (const WCHAR *)lpFileName;
            if ( v59 > 7 )
              v43 = lpFileName[0];
            DeleteFileW(v43);
          }
          if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v27);
        }
        std::wstring::~wstring((char **)lpFileName);
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
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      (char **)lpBuffer,
      v10,
      v9,
      v14);
    goto LABEL_48;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchDeviceDocumentFormat",
    L"BIDI query for document format returned null.");
LABEL_85:
  std::wstring::~wstring((char **)pData);
LABEL_86:
  if ( v4 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800450a0  mov     rax, rsp
0x1800450a3  push    rdi
0x1800450a4  push    r13
0x1800450a6  push    r14
0x1800450a8  sub     rsp, 170h
0x1800450af  mov     [rsp+188h+var_138], 0FFFFFFFFFFFFFFFEh
0x1800450b8  mov     [rax+10h], rbx
0x1800450bc  mov     [rax+18h], rsi
0x1800450c0  mov     rax, cs:__security_cookie
0x1800450c7  xor     rax, rsp
0x1800450ca  mov     [rsp+188h+var_20], rax
0x1800450d2  mov     ebx, edx
0x1800450d4  mov     rsi, rcx
0x1800450d7  xor     r14d, r14d
0x1800450da  mov     edi, r14d
0x1800450dd  mov     [rsp+188h+var_148], r14d
0x1800450e2  xor     edx, edx; dwCoInit
0x1800450e4  xor     ecx, ecx; pvReserved
0x1800450e6  call    cs:__imp_CoInitializeEx
0x1800450ed  nop     dword ptr [rax+rax+00h]
0x1800450f2  test    eax, eax
0x1800450f4  jns     short loc_180045103
0x1800450f6  cmp     eax, 80010106h
0x1800450fb  jnz     loc_18004592E
0x180045101  jmp     short loc_18004510C
0x180045103  mov     edi, 1
0x180045108  mov     [rsp+188h+var_148], edi
0x18004510c  mov     r8, [rsi+10h]
0x180045110  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x180045117  lea     r13, aPrintconfigCco_5; "PrintConfig::CConfigManager::FetchDevic"...
0x18004511e  mov     rcx, r13; char *
0x180045121  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180045126  cmp     [rsi+1Eh], r14b
0x18004512a  jnz     short loc_180045140
0x18004512c  lea     rdx, aDriverDidNotSp; "Driver did not specify 'RetrievePrintPa"...
0x180045133  mov     rcx, r13; char *
0x180045136  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004513b  jmp     loc_1800458C6
0x180045140  xorps   xmm0, xmm0
0x180045143  movups  xmmword ptr [rsp+188h+pData], xmm0
0x18004514b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180045153  movdqu  [rsp+188h+var_A0], xmm1
0x18004515c  mov     word ptr [rsp+188h+pData], r14w
0x180045165  test    ebx, ebx
0x180045167  jz      short loc_1800451BE
0x180045169  movups  xmmword ptr [rsp+188h+pv], xmm0
0x180045171  xorps   xmm1, xmm1
0x180045174  movdqu  [rsp+188h+var_60], xmm1
0x18004517d  mov     r8d, 0Fh
0x180045183  lea     rdx, aApplicationPdf; "application/pdf"
0x18004518a  lea     rcx, [rsp+188h+pv]
0x180045192  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180045197  lea     rdx, [rsp+188h+pv]
0x18004519f  lea     rcx, [rsp+188h+pData]
0x1800451a7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800451ac  lea     rcx, [rsp+188h+pv]
0x1800451b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800451b9  jmp     loc_18004528D
0x1800451be  lea     rax, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x1800451c5  mov     [rsp+188h+pv], rax
0x1800451cd  mov     [rsp+188h+pv+8], r14
0x1800451d5  lea     rax, [rsp+188h+var_140]
0x1800451da  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], rax; unsigned int *
0x1800451df  lea     rax, [rsp+188h+pv+8]
0x1800451e7  mov     qword ptr [rsp+188h+dwCreationDisposition], rax; unsigned __int8 **
0x1800451ec  mov     r9d, 6; unsigned int
0x1800451f2  xor     r8d, r8d; unsigned __int16 *
0x1800451f5  lea     rdx, aPrinterConfigu_0; "\\Printer.Configuration:DocumentFormat"
0x1800451fc  mov     rcx, rsi; this
0x1800451ff  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180045204  mov     rbx, [rsp+188h+pv+8]
0x18004520c  test    rbx, rbx
0x18004520f  jnz     short loc_180045226
0x180045211  lea     rdx, aBidiQueryForDo; "BIDI query for document format returned"...
0x180045218  mov     rcx, r13; char *
0x18004521b  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180045220  nop
0x180045221  jmp     loc_1800458B8
0x180045226  xorps   xmm0, xmm0
0x180045229  movups  xmmword ptr [rsp+188h+Block], xmm0
0x180045231  xorps   xmm1, xmm1
0x180045234  movdqu  [rsp+188h+var_40], xmm1
0x18004523d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180045241  inc     r8
0x180045244  cmp     [rbx+r8*2], r14w
0x180045249  jnz     short loc_180045241
0x18004524b  mov     rdx, rbx
0x18004524e  lea     rcx, [rsp+188h+Block]
0x180045256  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004525b  lea     rdx, [rsp+188h+Block]
0x180045263  lea     rcx, [rsp+188h+pData]
0x18004526b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180045270  lea     rcx, [rsp+188h+Block]
0x180045278  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004527d  nop
0x18004527e  mov     rcx, rbx; pv
0x180045281  call    cs:__imp_CoTaskMemFree
0x180045288  nop     dword ptr [rax+rax+00h]
0x18004528d  xorps   xmm0, xmm0
0x180045290  movups  xmmword ptr [rsp+188h+lpBuffer], xmm0
0x180045298  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], r14
0x1800452a0  mov     [rsp+188h+var_B8], 0Fh
0x1800452ac  mov     byte ptr [rsp+188h+lpBuffer], r14b
0x1800452b4  lea     rdx, [rsp+188h+pData]
0x1800452bc  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x1800452c5  cmova   rdx, [rsp+188h+pData]
0x1800452ce  lea     rcx, aApplicationPdf; "application/pdf"
0x1800452d5  call    cs:__imp__o__wcsicmp
0x1800452dc  nop     dword ptr [rax+rax+00h]
0x1800452e1  test    eax, eax
0x1800452e3  jnz     short loc_180045340
0x1800452e5  mov     edx, 17Fh
0x1800452ea  cmp     [rsp+188h+var_B8], rdx
0x1800452f2  jb      short loc_180045334
0x1800452f4  lea     rbx, [rsp+188h+lpBuffer]
0x1800452fc  cmp     [rsp+188h+var_B8], 0Fh
0x180045305  cmova   rbx, [rsp+188h+lpBuffer]
0x18004530e  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180045316  mov     r8d, edx; Size
0x180045319  lea     rdx, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x180045320  mov     rcx, rbx; void *
0x180045323  call    memmove_0
0x180045328  mov     [rbx+17Fh], r14b
0x18004532f  jmp     loc_18004554B
0x180045334  lea     r9, aFiltersFilterD_1; "<Filters><Filter dll = \"PDFRenderFilte"...
0x18004533b  jmp     loc_18004553E
0x180045340  lea     rdx, [rsp+188h+pData]
0x180045348  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180045351  cmova   rdx, [rsp+188h+pData]
0x18004535a  lea     rcx, aImagePwgRaster; "image/pwg-raster"
0x180045361  call    cs:__imp__o__wcsicmp
0x180045368  nop     dword ptr [rax+rax+00h]
0x18004536d  test    eax, eax
0x18004536f  jnz     short loc_1800453CC
0x180045371  mov     edx, 184h
0x180045376  cmp     [rsp+188h+var_B8], rdx
0x18004537e  jb      short loc_1800453C0
0x180045380  lea     rbx, [rsp+188h+lpBuffer]
0x180045388  cmp     [rsp+188h+var_B8], 0Fh
0x180045391  cmova   rbx, [rsp+188h+lpBuffer]
0x18004539a  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x1800453a2  mov     r8d, edx; Size
0x1800453a5  lea     rdx, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x1800453ac  mov     rcx, rbx; void *
0x1800453af  call    memmove_0
0x1800453b4  mov     [rbx+184h], r14b
0x1800453bb  jmp     loc_18004554B
0x1800453c0  lea     r9, aFiltersFilterD_0; "<Filters><Filter dll = \"PWGRRenderFilt"...
0x1800453c7  jmp     loc_18004553E
0x1800453cc  lea     rdx, [rsp+188h+pData]
0x1800453d4  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x1800453dd  cmova   rdx, [rsp+188h+pData]
0x1800453e6  lea     rcx, aApplicationPcl; "application/PCLm"
0x1800453ed  call    cs:__imp__o__wcsicmp
0x1800453f4  nop     dword ptr [rax+rax+00h]
0x1800453f9  test    eax, eax
0x1800453fb  jnz     short loc_18004542F
0x1800453fd  mov     edx, 17Eh
0x180045402  cmp     [rsp+188h+var_B8], rdx
0x18004540a  jb      short loc_180045423
0x18004540c  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180045414  mov     r8d, edx
0x180045417  lea     rdx, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x18004541e  jmp     loc_18004550C
0x180045423  lea     r9, aFiltersFilterD_2; "<Filters><Filter dll = \"PCLmRenderFilt"...
0x18004542a  jmp     loc_18004553E
0x18004542f  lea     rdx, [rsp+188h+pData]
0x180045437  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x180045440  cmova   rdx, [rsp+188h+pData]
0x180045449  lea     rcx, aApplicationOxp; "application/oxps"
0x180045450  call    cs:__imp__o__wcsicmp
0x180045457  nop     dword ptr [rax+rax+00h]
0x18004545c  test    eax, eax
0x18004545e  jnz     short loc_1800454B6
0x180045460  lea     edx, [rax+0Ah]
0x180045463  cmp     [rsp+188h+var_B8], rdx
0x18004546b  jb      short loc_1800454AA
0x18004546d  lea     rbx, [rsp+188h+lpBuffer]
0x180045475  cmp     [rsp+188h+var_B8], 0Fh
0x18004547e  cmova   rbx, [rsp+188h+lpBuffer]
0x180045487  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x18004548f  mov     r8d, edx; Size
0x180045492  lea     rdx, aFilters; "<Filters/>"
0x180045499  mov     rcx, rbx; void *
0x18004549c  call    memmove_0
0x1800454a1  mov     [rbx+0Ah], r14b
0x1800454a5  jmp     loc_18004554B
0x1800454aa  lea     r9, aFilters; "<Filters/>"
0x1800454b1  jmp     loc_18004553E
0x1800454b6  lea     rdx, [rsp+188h+pData]
0x1800454be  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x1800454c7  cmova   rdx, [rsp+188h+pData]
0x1800454d0  lea     rcx, aImageTiff; "image/tiff"
0x1800454d7  call    cs:__imp__o__wcsicmp
0x1800454de  nop     dword ptr [rax+rax+00h]
0x1800454e3  test    eax, eax
0x1800454e5  jnz     loc_180045900
0x1800454eb  mov     edx, 17Eh
0x1800454f0  cmp     [rsp+188h+var_B8], rdx
0x1800454f8  jb      short loc_180045537
0x1800454fa  mov     qword ptr [rsp+188h+nNumberOfBytesToWrite], rdx
0x180045502  mov     r8d, edx; Size
0x180045505  lea     rdx, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x18004550c  lea     rbx, [rsp+188h+lpBuffer]
0x180045514  cmp     [rsp+188h+var_B8], 0Fh
0x18004551d  cmova   rbx, [rsp+188h+lpBuffer]
0x180045526  mov     rcx, rbx; void *
0x180045529  call    memmove_0
0x18004552e  mov     [rbx+17Eh], r14b
0x180045535  jmp     short loc_18004554B
0x180045537  lea     r9, aFiltersFilterD; "<Filters><Filter dll = \"TiffRenderFilt"...
0x18004553e  lea     rcx, [rsp+188h+lpBuffer]
0x180045546  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18004554b  lea     r9, [rsi+20h]
0x18004554f  mov     rcx, [r9+10h]
0x180045553  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004555d  sub     rax, rcx
0x180045560  cmp     rax, 1Fh
0x180045564  jb      loc_18004594C
0x18004556a  cmp     qword ptr [r9+18h], 7
0x18004556f  jbe     short loc_180045574
0x180045571  mov     r9, [r9]
0x180045574  mov     [rsp+188h+hTemplateFile], 1Fh
0x18004557d  lea     rax, aDeviceBidiDocu; "device_bidi_document_format.xml"
0x180045584  mov     qword ptr [rsp+188h+dwFlagsAndAttributes], rax
0x180045589  mov     qword ptr [rsp+188h+dwCreationDisposition], rcx
0x18004558e  lea     rcx, [rsp+188h+lpFileName]
0x180045596  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004559b  nop
0x18004559c  lea     rcx, [rsp+188h+lpFileName]
0x1800455a4  cmp     [rsp+188h+var_78], 7
0x1800455ad  cmova   rcx, [rsp+188h+lpFileName]; lpFileName
0x1800455b6  mov     [rsp+188h+hTemplateFile], r14; hTemplateFile
0x1800455bb  mov     [rsp+188h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1800455c3  mov     [rsp+188h+dwCreationDisposition], 2; dwCreationDisposition
0x1800455cb  xor     r9d, r9d; lpSecurityAttributes
0x1800455ce  xor     r8d, r8d; dwShareMode
0x1800455d1  mov     edx, 40000000h; dwDesiredAccess
0x1800455d6  call    cs:__imp_CreateFileW
0x1800455dd  nop     dword ptr [rax+rax+00h]
0x1800455e2  mov     rbx, rax
0x1800455e5  mov     qword ptr [rsp+188h+var_140], rax
0x1800455ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800455ee  jnz     short loc_180045614
0x1800455f0  call    cs:__imp_GetLastError
0x1800455f7  nop     dword ptr [rax+rax+00h]
0x1800455fc  mov     r8d, eax
0x1800455ff  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x180045606  mov     rcx, r13; char *
0x180045609  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004560e  nop
0x18004560f  jmp     loc_18004589C
0x180045614  mov     [rsp+188h+NumberOfBytesWritten], r14d
0x180045619  lea     rdx, [rsp+188h+lpBuffer]
0x180045621  cmp     [rsp+188h+var_B8], 0Fh
0x18004562a  cmova   rdx, [rsp+188h+lpBuffer]; lpBuffer
0x180045633  mov     qword ptr [rsp+188h+dwCreationDisposition], r14; lpOverlapped
0x180045638  lea     r9, [rsp+188h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004563d  mov     r8d, [rsp+188h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180045645  mov     rcx, rbx; hFile
0x180045648  call    cs:__imp_WriteFile
0x18004564f  nop     dword ptr [rax+rax+00h]
0x180045654  test    eax, eax
0x180045656  jz      loc_18004580A
0x18004565c  mov     eax, [rsp+188h+NumberOfBytesWritten]
0x180045660  cmp     rax, qword ptr [rsp+188h+nNumberOfBytesToWrite]
0x180045668  jnz     loc_18004580A
0x18004566e  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x180045675  mov     rcx, [rsi+40h]; hPrinter
0x180045679  call    cs:__imp_DeletePrinterDataW
0x180045680  nop     dword ptr [rax+rax+00h]
0x180045685  mov     eax, dword ptr [rsp+188h+var_A0]
0x18004568c  lea     r9, [rsp+188h+pData]
0x180045694  cmp     qword ptr [rsp+188h+var_A0+8], 7
0x18004569d  cmova   r9, [rsp+188h+pData]; pData
0x1800456a6  lea     eax, ds:2[rax*2]
0x1800456ad  mov     [rsp+188h+dwCreationDisposition], eax; cbData
0x1800456b1  mov     r8d, 1; Type
0x1800456b7  lea     rdx, aV4Documentform; "V4_DocumentFormat"
0x1800456be  mov     rcx, [rsi+40h]; hPrinter
0x1800456c2  call    cs:__imp_SetPrinterDataW
0x1800456c9  nop     dword ptr [rax+rax+00h]
0x1800456ce  test    eax, eax
0x1800456d0  jle     short loc_1800456DC
0x1800456d2  movzx   eax, ax
0x1800456d5  or      eax, 80070000h
0x1800456da  test    eax, eax
0x1800456dc  js      loc_180045952
0x1800456e2  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x1800456e9  mov     rcx, [rsi+40h]; hPrinter
0x1800456ed  call    cs:__imp_DeletePrinterDataW
0x1800456f4  nop     dword ptr [rax+rax+00h]
0x1800456f9  mov     eax, [rsp+188h+var_80]
0x180045700  lea     r9, [rsp+188h+lpFileName]
0x180045708  cmp     [rsp+188h+var_78], 7
0x180045711  cmova   r9, [rsp+188h+lpFileName]; pData
0x18004571a  lea     eax, ds:2[rax*2]
0x180045721  mov     [rsp+188h+dwCreationDisposition], eax; cbData
0x180045725  mov     r8d, 1; Type
0x18004572b  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
  ... truncated ...
```
