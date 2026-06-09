# PrintConfig::CConfigManager::FetchDeviceConfigData(int,int *,int *)

- ea: `0x1800446d8`
- end: `0x180044dfc`
- name: `?FetchDeviceConfigData@CConfigManager@PrintConfig@@QEAAXHPEAH0@Z`
- size: `1828`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this, int, int *, int *)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bb3c`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000ded0`
- `0x18000e444`
- `0x18000e82c`
- `0x18000f830`
- `0x18000fa4c`
- `0x18000fb68`
- `0x18001535c`
- `0x180018f00`
- `0x180018f58`
- `0x180019410`
- `0x180022268`
- `0x18002dbc8`
- `0x180039584`
- `0x18003a260`
- `0x18003a5d0`
- `0x18003b388`
- `0x18004240c`
- `0x180042838`
- `0x180042980`
- `0x180042e4c`
- `0x1800446d8`
- `0x18004a080`
- `0x18004a36c`
- `0x18004b124`
- `0x18004b844`
- `0x18004dcd8`
- `0x180052cac`
- `0x180059c78`
- `0x1801b56c8`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180044c9d`
- `KERNEL32!WideCharToMultiByte` at `0x180044c9d`
- `KERNEL32!SetLastError` at `0x180044966`
- `KERNEL32!SetLastError` at `0x180044966`
- `KERNEL32!GetLastError` at `0x180044947`
- `KERNEL32!GetLastError` at `0x180044d00`
- `KERNEL32!GetLastError` at `0x180044947`
- `KERNEL32!GetLastError` at `0x180044d00`
- `ole32!CoInitializeEx` at `0x180044722`
- `ole32!CoInitializeEx` at `0x180044722`
- `ole32!CoUninitialize` at `0x180044a2c`
- `ole32!CoUninitialize` at `0x180044a2c`
- `ole32!CoTaskMemFree` at `0x180044958`
- `ole32!CoTaskMemFree` at `0x180044c49`
- `ole32!CoTaskMemFree` at `0x180044cef`
- `ole32!CoTaskMemFree` at `0x180044958`
- `ole32!CoTaskMemFree` at `0x180044c49`
- `ole32!CoTaskMemFree` at `0x180044cef`
- `WINSPOOL!GetPrinterDataW` at `0x1800447ac`
- `WINSPOOL!GetPrinterDataW` at `0x1800447f9`
- `WINSPOOL!GetPrinterDataW` at `0x1800447ac`
- `WINSPOOL!GetPrinterDataW` at `0x1800447f9`

## string_xrefs

- `0x180044d26`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004475a`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x18004488e`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x180044c2a`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x180044d16`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x1800449b9`: `No cached Bidi PrintDeviceCapabilities changeid found`
- `0x180044887`: `Cached Bidi PrintDeviceCapabilities changeid: %ws`
- `0x1800449ea`: `\Printer.Configuration.DriverConfigFiles:PPDFile`
- `0x1800449f1`: `\Printer.Configuration.DriverConfigFiles:GPDFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PrintConfig::CConfigManager::FetchDeviceConfigData(
        PrintConfig::CConfigManager *this,
        int a2,
        int *a3,
        int *a4)
{
  int *v5; // r12
  int v7; // edi
  HRESULT v8; // eax
  signed int PrinterDataW; // eax
  __int64 v10; // r8
  signed int v11; // eax
  __int64 v12; // r8
  bool v13; // sf
  LPBYTE v14; // r15
  unsigned __int64 v15; // rdx
  char *v16; // r12
  __int64 v17; // rbx
  int v18; // eax
  void *v19; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v21; // r8
  bool v22; // sf
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  DWORD v29; // r14d
  __int128 *p_pExceptionObject; // rcx
  int v31; // eax
  void *v32; // rbx
  LPSTR v33; // r15
  _DWORD *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  LPBYTE *v37; // r8
  int v38; // eax
  __int64 v39; // r8
  const char *v40; // r9
  int cbMultiByte; // [rsp+40h] [rbp-79h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+44h] [rbp-75h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-71h] BYREF
  int v44; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v45; // [rsp+58h] [rbp-61h] BYREF
  int v46; // [rsp+60h] [rbp-59h] BYREF
  int v47; // [rsp+64h] [rbp-55h]
  LPSTR lpMultiByteStr[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v49; // [rsp+78h] [rbp-41h]
  __int64 v50; // [rsp+80h] [rbp-39h]
  __int128 pExceptionObject; // [rsp+88h] [rbp-31h] BYREF
  __m128i si128; // [rsp+98h] [rbp-21h]
  LPBYTE pData[2]; // [rsp+A8h] [rbp-11h] BYREF
  __m128i v54; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v56; // [rsp+128h] [rbp+6Fh] BYREF

  v56 = a2;
  v50 = -2;
  v5 = a3;
  v45 = a3;
  v7 = 0;
  v47 = 0;
  v8 = CoInitializeEx(0, 0);
  if ( v8 >= 0 )
  {
    v7 = 1;
    v47 = 1;
  }
  else if ( v8 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v8);
    throw (hr_error *)&pExceptionObject;
  }
  *v5 = 0;
  *a4 = 0;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchDeviceConfigData",
    L"m_printerName=%ws",
    *((_QWORD *)this + 2));
  if ( *((_BYTE *)this + 28) )
  {
    if ( !*((_BYTE *)this + 29) )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::FetchDeviceConfigData",
        L"Driver is PrintDeviceCapabilities-based, but did not specify 'RetrievePrintDeviceCapabilitiesFromDevice=true'. Skipping.");
      goto LABEL_44;
    }
    nNumberOfBytesToWrite = 0;
    PrinterDataW = GetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_PDC_ChangeID", 0, 0, 0, &nNumberOfBytesToWrite);
    if ( PrinterDataW == 234 )
    {
      std::vector<unsigned char>::vector<unsigned char>((__int64 *)pData, nNumberOfBytesToWrite + 2LL, v10);
      v11 = GetPrinterDataW(
              *((HANDLE *)this + 8),
              (LPWSTR)L"V4_PDC_ChangeID",
              0,
              pData[0],
              LODWORD(pData[1]) - LODWORD(pData[0]),
              &nNumberOfBytesToWrite);
      v13 = v11 < 0;
      if ( v11 > 0 )
      {
        v11 = (unsigned __int16)v11 | 0x80070000;
        v13 = v11 < 0;
      }
      if ( v13 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v11);
        throw (hr_error *)&pExceptionObject;
      }
      v14 = pData[0];
      *(_WORD *)&pData[0][2 * ((unsigned __int64)(pData[1] - pData[0]) >> 1) - 2] = 0;
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
      if ( v15 > *((_QWORD *)this + 14) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)this + 11,
          v15,
          v12,
          v14);
      }
      else
      {
        if ( *((_QWORD *)this + 14) <= 7u )
          v16 = (char *)this + 88;
        else
          v16 = (char *)*((_QWORD *)this + 11);
        *((_QWORD *)this + 13) = v15;
        v17 = 2 * v15;
        memmove_0(v16, v14, 2 * v15);
        *(_WORD *)&v16[v17] = 0;
        v5 = (int *)v45;
      }
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::FetchDeviceConfigData",
        L"Cached Bidi PrintDeviceCapabilities changeid: %ws",
        v14);
      if ( std::operator==<unsigned short>((wchar_t *)L"V4_No_ChangeID_Present", (wchar_t *)this + 44) )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "PrintConfig::CConfigManager::FetchDeviceConfigData",
          L"There was no change ID found the last time we retrieved a PrintDeviceCapabilities file from this device. Skipping.");
        std::vector<char>::~vector<char>((char **)pData);
        goto LABEL_44;
      }
      std::vector<char>::~vector<char>((char **)pData);
    }
    else if ( PrinterDataW == 2 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::FetchDeviceConfigData",
        L"No cached Bidi PrintDeviceCapabilities changeid found");
    }
    else
    {
      v22 = PrinterDataW < 0;
      if ( PrinterDataW > 0 )
      {
        PrinterDataW = (unsigned __int16)PrinterDataW | 0x80070000;
        v22 = PrinterDataW < 0;
      }
      if ( v22 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, PrinterDataW);
        throw (hr_error *)&pExceptionObject;
      }
    }
  }
  pv = 0;
  cbMultiByte = 0;
  if ( *((_BYTE *)this + 28) )
  {
    *(_QWORD *)&pExceptionObject = this;
    *((_QWORD *)&pExceptionObject + 1) = &v56;
    si128.m128i_i64[0] = (__int64)&pv;
    si128.m128i_i64[1] = (__int64)&cbMultiByte;
    v18 = ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e_((__int64)&pExceptionObject);
    if ( v18 < 0 )
    {
      if ( v56 || v18 != -2147418113 || (v19 = pv) != 0 && cbMultiByte )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v18);
        throw (hr_error *)&pExceptionObject;
      }
      *a4 = 1;
      if ( v19 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v19);
        SetLastError(LastError);
      }
      pv = 0;
      v21 = (const unsigned __int16 *)((char *)this + 88);
      if ( *((_QWORD *)this + 14) > 7u )
        v21 = *(const unsigned __int16 **)v21;
      PrintConfig::CConfigManager::RetrieveBidiData(
        this,
        L"\\Printer.Capabilities:DefaultData",
        v21,
        7,
        (unsigned __int8 **)&pv,
        (unsigned int *)&cbMultiByte);
      Print::Driver::Telemetry::PrintConfigTelemetry::DefaultPDCFallback();
    }
  }
  else
  {
    pv = 0;
    v23 = L"\\Printer.Configuration.DriverConfigFiles:GPDFile";
    if ( !*((_DWORD *)this + 6) )
      v23 = L"\\Printer.Configuration.DriverConfigFiles:PPDFile";
    PrintConfig::CConfigManager::RetrieveBidiData(
      this,
      v23,
      0,
      4,
      (unsigned __int8 **)&pv,
      (unsigned int *)&cbMultiByte);
  }
  if ( pv )
  {
    if ( v56 && *((_BYTE *)this + 28) )
    {
      nNumberOfBytesToWrite = 0;
      v24 = PrintConfig::CConfigManager::CheckAndUpdateRegistryPdcChecksum(
              (HANDLE *)this,
              (unsigned __int8 *)pv,
              cbMultiByte,
              (int *)&nNumberOfBytesToWrite);
      if ( v24 < 0 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v24);
        throw (hr_error *)&pExceptionObject;
      }
      v44 = 0;
      v25 = PrintConfig::CConfigManager::CheckAndUpdateRegistryLanguage((HANDLE *)this, &v44);
      if ( v25 < 0 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v25);
        throw (hr_error *)&pExceptionObject;
      }
      if ( nNumberOfBytesToWrite || v44 )
      {
        PrintConfig::LanguageDatabase::ClearResources(*((HANDLE *)this + 8), (_QWORD *)this + 4, v26, 1, 0);
        PrintConfig::CConfigManager::UpgradeLanguageDatabase(this, v27, v28);
      }
    }
    *(_OWORD *)lpMultiByteStr = 0;
    v49 = 0;
    v29 = cbMultiByte;
    nNumberOfBytesToWrite = cbMultiByte;
    if ( !*((_BYTE *)this + 28) )
    {
      if ( cbMultiByte )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
          (__int64)lpMultiByteStr,
          (unsigned int)cbMultiByte);
        v29 = cbMultiByte;
      }
      v33 = lpMultiByteStr[0];
      v38 = WideCharToMultiByte(0, 0x400u, (LPCWCH)pv, -1, lpMultiByteStr[0], v29, 0, 0);
      v29 = v38;
      if ( !v38 )
      {
        v39 = GetLastError();
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::CConfigManager::FetchDeviceConfigData",
          L"WideCharToMultiByte failed: %d",
          v39);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x29D,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          v40);
      }
      if ( !lpMultiByteStr[0][v38 - 1] )
        v29 = v38 - 1;
      goto LABEL_85;
    }
    v46 = 0;
    pExceptionObject = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(pExceptionObject) = 0;
    v44 = 0;
    v45 = 0;
    if ( (int)PrintConfig::CConfigManager::RetrieveBestLanguageResource(
                (PrintConfig **)this,
                (__int64)&pExceptionObject,
                (__int64)&v45,
                (__int64)&v44) < 0 )
    {
      v32 = v45;
    }
    else
    {
      p_pExceptionObject = &pExceptionObject;
      if ( si128.m128i_i64[1] > 7uLL )
        p_pExceptionObject = (__int128 *)pExceptionObject;
      v31 = PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
              (const BYTE **)&pv,
              cbMultiByte,
              (const BYTE **)&v45,
              v44,
              (__int64)p_pExceptionObject,
              *((const wchar_t **)this + 2),
              &nNumberOfBytesToWrite,
              &v46);
      if ( v31 < 0 )
      {
        hr_error::hr_error((hr_error *)pData, v31);
        throw (hr_error *)pData;
      }
      v32 = v45;
      if ( v46 )
        PrintConfig::CConfigManager::CommitLanguageResources((__int64)this, &pExceptionObject, 0, (__int64)v45, v46);
      v29 = nNumberOfBytesToWrite;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_PrintIppPsaStabilityFixes_2505>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)this + 31) != 3 )
        goto LABEL_68;
    }
    else if ( !*((_BYTE *)this + 120) )
    {
      goto LABEL_68;
    }
    PrintConfig::CConfigManager::SavePScriptConfigDataIfNeeded(this, (unsigned __int8 *)pv, cbMultiByte);
LABEL_68:
    v33 = (LPSTR)pv;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
    {
      v34 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
      if ( v34 )
      {
        if ( *v34 )
        {
          v36 = v29;
          *(_OWORD *)pData = 0;
          v54 = 0;
          if ( v29 )
          {
            std::string::_Construct_from_iter<unsigned char const *,unsigned char const *,unsigned __int64>(
              pData,
              v33,
              v35,
              v29);
          }
          else
          {
            v54 = _mm_load_si128((const __m128i *)&_xmm);
            LOBYTE(pData[0]) = 0;
          }
          v37 = pData;
          if ( v54.m128i_i64[1] > 0xFuLL )
            v37 = (LPBYTE *)pData[0];
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "PrintConfig::CConfigManager::FetchDeviceConfigData",
            L"Regenerated PDC: %hs",
            v37,
            v36);
          std::string::~string((char **)pData);
        }
      }
    }
    if ( v32 )
      CoTaskMemFree(v32);
    std::wstring::~wstring((char **)&pExceptionObject);
LABEL_85:
    PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(this, v33, v29, v56, v5);
    std::vector<char>::~vector<char>(lpMultiByteStr);
    if ( pv )
      CoTaskMemFree(pv);
  }
LABEL_44:
  if ( v7 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800446d8  mov     [rsp-8+arg_8], edx
0x1800446dc  push    rbp
0x1800446dd  push    rbx
0x1800446de  push    rsi
0x1800446df  push    rdi
0x1800446e0  push    r12
0x1800446e2  push    r13
0x1800446e4  push    r14
0x1800446e6  push    r15
0x1800446e8  lea     rbp, [rsp-1Fh]
0x1800446ed  sub     rsp, 0D8h
0x1800446f4  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800446fc  mov     rax, cs:__security_cookie
0x180044703  xor     rax, rsp
0x180044706  mov     [rbp+57h+var_48], rax
0x18004470a  mov     r13, r9
0x18004470d  mov     r12, r8
0x180044710  mov     [rbp+57h+var_B8], r8
0x180044714  mov     rsi, rcx
0x180044717  xor     ebx, ebx
0x180044719  mov     edi, ebx
0x18004471b  mov     [rbp+57h+var_AC], ebx
0x18004471e  xor     edx, edx; dwCoInit
0x180044720  xor     ecx, ecx; pvReserved
0x180044722  call    cs:__imp_CoInitializeEx
0x180044729  nop     dword ptr [rax+rax+00h]
0x18004472e  test    eax, eax
0x180044730  jns     short loc_18004473F
0x180044732  cmp     eax, 80010106h
0x180044737  jnz     loc_180044D38
0x18004473d  jmp     short loc_180044747
0x18004473f  mov     edi, 1
0x180044744  mov     [rbp+57h+var_AC], edi
0x180044747  mov     [r12], ebx
0x18004474b  mov     [r13+0], ebx
0x18004474f  mov     r8, [rsi+10h]
0x180044753  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x18004475a  lea     r15, aPrintconfigCco_2; "PrintConfig::CConfigManager::FetchDevic"...
0x180044761  mov     rcx, r15; char *
0x180044764  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180044769  cmp     [rsi+1Ch], bl
0x18004476c  jz      loc_1800448D7
0x180044772  cmp     [rsi+1Dh], bl
0x180044775  jnz     short loc_18004478B
0x180044777  lea     rdx, aDriverIsPrintd; "Driver is PrintDeviceCapabilities-based"...
0x18004477e  mov     rcx, r15; char *
0x180044781  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180044786  jmp     loc_180044A28
0x18004478b  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x18004478e  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x180044792  mov     [rsp+110h+pcbNeeded], rax; pcbNeeded
0x180044797  mov     [rsp+110h+nSize], ebx; nSize
0x18004479b  xor     r9d, r9d; pData
0x18004479e  xor     r8d, r8d; pType
0x1800447a1  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x1800447a8  mov     rcx, [rsi+40h]; hPrinter
0x1800447ac  call    cs:__imp_GetPrinterDataW
0x1800447b3  nop     dword ptr [rax+rax+00h]
0x1800447b8  cmp     eax, 0EAh
0x1800447bd  jnz     loc_1800449B4
0x1800447c3  mov     edx, [rbp+57h+nNumberOfBytesToWrite]
0x1800447c6  add     rdx, 2
0x1800447ca  lea     rcx, [rbp+57h+pData]
0x1800447ce  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800447d3  nop
0x1800447d4  mov     r9, [rbp+57h+pData]; pData
0x1800447d8  mov     eax, dword ptr [rbp+57h+pData+8]
0x1800447db  sub     eax, r9d
0x1800447de  lea     rcx, [rbp+57h+nNumberOfBytesToWrite]
0x1800447e2  mov     [rsp+110h+pcbNeeded], rcx; pcbNeeded
0x1800447e7  mov     [rsp+110h+nSize], eax; nSize
0x1800447eb  xor     r8d, r8d; pType
0x1800447ee  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x1800447f5  mov     rcx, [rsi+40h]; hPrinter
0x1800447f9  call    cs:__imp_GetPrinterDataW
0x180044800  nop     dword ptr [rax+rax+00h]
0x180044805  test    eax, eax
0x180044807  jle     short loc_180044813
0x180044809  movzx   eax, ax
0x18004480c  or      eax, 80070000h
0x180044811  test    eax, eax
0x180044813  js      loc_180044D70
0x180044819  mov     r15, [rbp+57h+pData]
0x18004481d  mov     rcx, [rbp+57h+pData+8]
0x180044821  sub     rcx, r15
0x180044824  shr     rcx, 1
0x180044827  mov     [r15+rcx*2-2], bx
0x18004482d  lea     r14, [rsi+58h]
0x180044831  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180044835  inc     rdx
0x180044838  cmp     [r15+rdx*2], bx
0x18004483d  jnz     short loc_180044835
0x18004483f  cmp     rdx, [r14+18h]
0x180044843  ja      short loc_180044879
0x180044845  cmp     qword ptr [r14+18h], 7
0x18004484a  jbe     short loc_180044851
0x18004484c  mov     r12, [r14]
0x18004484f  jmp     short loc_180044854
0x180044851  mov     r12, r14
0x180044854  mov     [r14+10h], rdx
0x180044858  lea     rbx, [rdx+rdx]
0x18004485c  mov     r8, rbx; Size
0x18004485f  mov     rdx, r15; Src
0x180044862  mov     rcx, r12; void *
0x180044865  call    memmove_0
0x18004486a  xor     eax, eax
0x18004486c  mov     [rbx+r12], ax
0x180044871  mov     r12, [rbp+57h+var_B8]
0x180044875  xor     ebx, ebx
0x180044877  jmp     short loc_180044884
0x180044879  mov     r9, r15
0x18004487c  mov     rcx, r14
0x18004487f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180044884  mov     r8, r15
0x180044887  lea     rdx, aCachedBidiPrin; "Cached Bidi PrintDeviceCapabilities cha"...
0x18004488e  lea     r15, aPrintconfigCco_2; "PrintConfig::CConfigManager::FetchDevic"...
0x180044895  mov     rcx, r15; char *
0x180044898  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004489d  mov     rdx, r14; S1
0x1800448a0  lea     rcx, aV4NoChangeidPr; "V4_No_ChangeID_Present"
0x1800448a7  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x1800448ac  test    al, al
0x1800448ae  jz      short loc_1800448CE
0x1800448b0  lea     rdx, aThereWasNoChan; "There was no change ID found the last t"...
0x1800448b7  mov     rcx, r15; char *
0x1800448ba  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800448bf  nop
0x1800448c0  lea     rcx, [rbp+57h+pData]
0x1800448c4  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800448c9  jmp     loc_180044A28
0x1800448ce  lea     rcx, [rbp+57h+pData]
0x1800448d2  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800448d7  mov     [rbp+57h+pv], rbx
0x1800448db  mov     [rbp+57h+cbMultiByte], ebx
0x1800448de  cmp     [rsi+1Ch], bl
0x1800448e1  jz      loc_1800449E6
0x1800448e7  mov     qword ptr [rbp+57h+pExceptionObject], rsi
0x1800448eb  lea     rax, [rbp+57h+arg_8]
0x1800448ef  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x1800448f3  lea     rax, [rbp+57h+pv]
0x1800448f7  mov     qword ptr [rbp+57h+var_78], rax
0x1800448fb  lea     rax, [rbp+57h+cbMultiByte]
0x1800448ff  mov     qword ptr [rbp+57h+var_78+8], rax
0x180044903  lea     rcx, [rbp+57h+pExceptionObject]
0x180044907  call    ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e___; ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e_
0x18004490c  test    eax, eax
0x18004490e  jns     loc_180044A22
0x180044914  cmp     [rbp+57h+arg_8], ebx
0x180044917  jnz     loc_180044D8C
0x18004491d  cmp     eax, 8000FFFFh
0x180044922  jnz     loc_180044D8C
0x180044928  mov     r14, [rbp+57h+pv]
0x18004492c  test    r14, r14
0x18004492f  jz      short loc_18004493A
0x180044931  cmp     [rbp+57h+cbMultiByte], ebx
0x180044934  jnz     loc_180044D8C
0x18004493a  mov     dword ptr [r13+0], 1
0x180044942  test    r14, r14
0x180044945  jz      short loc_180044974
0x180044947  call    cs:__imp_GetLastError
0x18004494e  nop     dword ptr [rax+rax+00h]
0x180044953  mov     ebx, eax
0x180044955  mov     rcx, r14; pv
0x180044958  call    cs:__imp_CoTaskMemFree
0x18004495f  nop     dword ptr [rax+rax+00h]
0x180044964  mov     ecx, ebx; dwErrCode
0x180044966  call    cs:__imp_SetLastError
0x18004496d  nop     dword ptr [rax+rax+00h]
0x180044972  xor     ebx, ebx
0x180044974  mov     [rbp+57h+pv], rbx
0x180044978  lea     r8, [rsi+58h]
0x18004497c  cmp     qword ptr [r8+18h], 7
0x180044981  jbe     short loc_180044986
0x180044983  mov     r8, [r8]; unsigned __int16 *
0x180044986  lea     rax, [rbp+57h+cbMultiByte]
0x18004498a  mov     [rsp+110h+pcbNeeded], rax; unsigned int *
0x18004498f  lea     rax, [rbp+57h+pv]
0x180044993  mov     qword ptr [rsp+110h+nSize], rax; unsigned __int8 **
0x180044998  mov     r9d, 7; unsigned int
0x18004499e  lea     rdx, aPrinterCapabil_0; "\\Printer.Capabilities:DefaultData"
0x1800449a5  mov     rcx, rsi; this
0x1800449a8  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x1800449ad  call    ?DefaultPDCFallback@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXXZ; Print::Driver::Telemetry::PrintConfigTelemetry::DefaultPDCFallback(void)
0x1800449b2  jmp     short loc_180044A22
0x1800449b4  cmp     eax, 2
0x1800449b7  jnz     short loc_1800449CD
0x1800449b9  lea     rdx, aNoCachedBidiPr; "No cached Bidi PrintDeviceCapabilities "...
0x1800449c0  mov     rcx, r15; char *
0x1800449c3  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800449c8  jmp     loc_1800448D7
0x1800449cd  test    eax, eax
0x1800449cf  jle     short loc_1800449DB
0x1800449d1  movzx   eax, ax
0x1800449d4  or      eax, 80070000h
0x1800449d9  test    eax, eax
0x1800449db  js      loc_180044D54
0x1800449e1  jmp     loc_1800448D7
0x1800449e6  mov     [rbp+57h+pv], rbx
0x1800449ea  lea     rax, aPrinterConfigu; "\\Printer.Configuration.DriverConfigFil"...
0x1800449f1  lea     rdx, aPrinterConfigu_1; "\\Printer.Configuration.DriverConfigFil"...
0x1800449f8  cmp     [rsi+18h], ebx
0x1800449fb  cmovz   rdx, rax; unsigned __int16 *
0x1800449ff  lea     rax, [rbp+57h+cbMultiByte]
0x180044a03  mov     [rsp+110h+pcbNeeded], rax; unsigned int *
0x180044a08  lea     rax, [rbp+57h+pv]
0x180044a0c  mov     qword ptr [rsp+110h+nSize], rax; unsigned __int8 **
0x180044a11  mov     r9d, 4; unsigned int
0x180044a17  xor     r8d, r8d; unsigned __int16 *
0x180044a1a  mov     rcx, rsi; this
0x180044a1d  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180044a22  cmp     [rbp+57h+pv], rbx
0x180044a26  jnz     short loc_180044A59
0x180044a28  test    edi, edi
0x180044a2a  jz      short loc_180044A38
0x180044a2c  call    cs:__imp_CoUninitialize
0x180044a33  nop     dword ptr [rax+rax+00h]
0x180044a38  mov     rcx, [rbp+57h+var_48]
0x180044a3c  xor     rcx, rsp; StackCookie
0x180044a3f  call    __security_check_cookie
0x180044a44  add     rsp, 0D8h
0x180044a4b  pop     r15
0x180044a4d  pop     r14
0x180044a4f  pop     r13
0x180044a51  pop     r12
0x180044a53  pop     rdi
0x180044a54  pop     rsi
0x180044a55  pop     rbx
0x180044a56  pop     rbp
0x180044a57  retn
0x180044a59  cmp     [rbp+57h+arg_8], ebx
0x180044a5c  jz      short loc_180044ABF
0x180044a5e  cmp     [rsi+1Ch], bl
0x180044a61  jz      short loc_180044ABF
0x180044a63  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x180044a66  lea     r9, [rbp+57h+nNumberOfBytesToWrite]; int *
0x180044a6a  mov     r8d, [rbp+57h+cbMultiByte]; unsigned int
0x180044a6e  mov     rdx, [rbp+57h+pv]; unsigned __int8 *
0x180044a72  mov     rcx, rsi; this
0x180044a75  call    ?CheckAndUpdateRegistryPdcChecksum@CConfigManager@PrintConfig@@AEAAJPEAEKPEAH@Z; PrintConfig::CConfigManager::CheckAndUpdateRegistryPdcChecksum(uchar *,ulong,int *)
0x180044a7a  test    eax, eax
0x180044a7c  js      loc_180044DA8
0x180044a82  mov     [rbp+57h+var_C0], ebx
0x180044a85  lea     rdx, [rbp+57h+var_C0]; int *
0x180044a89  mov     rcx, rsi; this
0x180044a8c  call    ?CheckAndUpdateRegistryLanguage@CConfigManager@PrintConfig@@AEAAJPEAH@Z; PrintConfig::CConfigManager::CheckAndUpdateRegistryLanguage(int *)
0x180044a91  test    eax, eax
0x180044a93  js      loc_180044DC4
0x180044a99  cmp     [rbp+57h+nNumberOfBytesToWrite], ebx
0x180044a9c  jnz     short loc_180044AA3
0x180044a9e  cmp     [rbp+57h+var_C0], ebx
0x180044aa1  jz      short loc_180044ABF
0x180044aa3  lea     rdx, [rsi+20h]
0x180044aa7  mov     byte ptr [rsp+110h+nSize], bl; char
0x180044aab  mov     r9b, 1
0x180044aae  mov     rcx, [rsi+40h]; hPrinter
0x180044ab2  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x180044ab7  mov     rcx, rsi; this
0x180044aba  call    ?UpgradeLanguageDatabase@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::UpgradeLanguageDatabase(void)
0x180044abf  xorps   xmm0, xmm0
0x180044ac2  movdqu  xmmword ptr [rbp+57h+lpMultiByteStr], xmm0
0x180044ac7  mov     [rbp+57h+var_98], rbx
0x180044acb  mov     r14d, [rbp+57h+cbMultiByte]
0x180044acf  mov     [rbp+57h+nNumberOfBytesToWrite], r14d
0x180044ad3  cmp     [rsi+1Ch], bl
0x180044ad6  jz      loc_180044C61
0x180044adc  mov     [rbp+57h+var_B0], ebx
0x180044adf  movups  [rbp+57h+pExceptionObject], xmm0
0x180044ae3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180044aeb  movdqu  [rbp+57h+var_78], xmm1
0x180044af0  mov     word ptr [rbp+57h+pExceptionObject], bx
0x180044af4  mov     [rbp+57h+var_C0], ebx
0x180044af7  mov     [rbp+57h+var_B8], rbx
0x180044afb  lea     r9, [rbp+57h+var_C0]
0x180044aff  lea     r8, [rbp+57h+var_B8]
0x180044b03  lea     rdx, [rbp+57h+pExceptionObject]
0x180044b07  mov     rcx, rsi
0x180044b0a  call    ?RetrieveBestLanguageResource@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBestLanguageResource(std::wstring &,uchar * *,ulong *)
0x180044b0f  test    eax, eax
0x180044b11  js      short loc_180044B84
0x180044b13  mov     rax, [rsi+10h]
0x180044b17  lea     rcx, [rbp+57h+pExceptionObject]
0x180044b1b  cmp     qword ptr [rbp+57h+var_78+8], 7
0x180044b20  cmova   rcx, qword ptr [rbp+57h+pExceptionObject]
0x180044b25  lea     rdx, [rbp+57h+var_B0]
0x180044b29  mov     [rsp+110h+lpUsedDefaultChar], rdx
0x180044b2e  lea     rdx, [rbp+57h+nNumberOfBytesToWrite]
0x180044b32  mov     [rsp+110h+lpDefaultChar], rdx
0x180044b37  mov     [rsp+110h+pcbNeeded], rax
0x180044b3c  mov     qword ptr [rsp+110h+nSize], rcx
0x180044b41  mov     r9d, [rbp+57h+var_C0]
0x180044b45  lea     r8, [rbp+57h+var_B8]
0x180044b49  mov     edx, [rbp+57h+cbMultiByte]
0x180044b4c  lea     rcx, [rbp+57h+pv]
0x180044b50  call    ?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z; PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)
0x180044b55  test    eax, eax
0x180044b57  js      loc_180044DE0
0x180044b5d  mov     eax, [rbp+57h+var_B0]
0x180044b60  mov     rbx, [rbp+57h+var_B8]
0x180044b64  test    eax, eax
0x180044b66  jz      short loc_180044B7E
  ... truncated ...
```
