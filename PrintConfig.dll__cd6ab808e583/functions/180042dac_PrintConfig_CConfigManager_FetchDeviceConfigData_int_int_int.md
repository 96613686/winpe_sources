# PrintConfig::CConfigManager::FetchDeviceConfigData(int,int *,int *)

- ea: `0x180042dac`
- end: `0x180043475`
- name: `?FetchDeviceConfigData@CConfigManager@PrintConfig@@QEAAXHPEAH0@Z`
- size: `1737`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this, int, int *, int *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001aecc`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000dadc`
- `0x18000e04c`
- `0x18000e420`
- `0x18000f380`
- `0x18000f590`
- `0x18000f6a0`
- `0x180014a48`
- `0x1800183a0`
- `0x1800183f8`
- `0x180021820`
- `0x18002c8b4`
- `0x180038054`
- `0x180038ccc`
- `0x180039030`
- `0x180039dc4`
- `0x180040adc`
- `0x180040efc`
- `0x180041038`
- `0x1800414e8`
- `0x180042dac`
- `0x180048240`
- `0x180048514`
- `0x180049274`
- `0x1800499b0`
- `0x18004bce4`
- `0x180050cd8`
- `0x180057994`
- `0x1801adb58`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180043328`
- `KERNEL32!WideCharToMultiByte` at `0x180043328`
- `KERNEL32!SetLastError` at `0x18004301c`
- `KERNEL32!SetLastError` at `0x18004301c`
- `KERNEL32!GetLastError` at `0x180043009`
- `KERNEL32!GetLastError` at `0x18004337f`
- `KERNEL32!GetLastError` at `0x180043009`
- `KERNEL32!GetLastError` at `0x18004337f`
- `ole32!CoInitializeEx` at `0x180042df6`
- `ole32!CoInitializeEx` at `0x180042df6`
- `ole32!CoUninitialize` at `0x1800430dc`
- `ole32!CoUninitialize` at `0x1800430dc`
- `ole32!CoTaskMemFree` at `0x180043014`
- `ole32!CoTaskMemFree` at `0x1800432da`
- `ole32!CoTaskMemFree` at `0x180043374`
- `ole32!CoTaskMemFree` at `0x180043014`
- `ole32!CoTaskMemFree` at `0x1800432da`
- `ole32!CoTaskMemFree` at `0x180043374`
- `WINSPOOL!GetPrinterDataW` at `0x180042e7a`
- `WINSPOOL!GetPrinterDataW` at `0x180042ec1`
- `WINSPOOL!GetPrinterDataW` at `0x180042e7a`
- `WINSPOOL!GetPrinterDataW` at `0x180042ec1`

## string_xrefs

- `0x18004339f`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180042e28`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x180042f50`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x1800432bb`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x18004338f`: `PrintConfig::CConfigManager::FetchDeviceConfigData`
- `0x180043069`: `No cached Bidi PrintDeviceCapabilities changeid found`
- `0x180042f49`: `Cached Bidi PrintDeviceCapabilities changeid: %ws`
- `0x18004309a`: `\Printer.Configuration.DriverConfigFiles:PPDFile`
- `0x1800430a1`: `\Printer.Configuration.DriverConfigFiles:GPDFile`

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
  signed int v10; // eax
  bool v11; // sf
  LPBYTE v12; // r15
  unsigned __int64 v13; // rdx
  char *v14; // r12
  __int64 v15; // rbx
  int v16; // eax
  void *v17; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v19; // r8
  bool v20; // sf
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  int v23; // eax
  DWORD v24; // r14d
  __int128 *p_pExceptionObject; // rcx
  int v26; // eax
  void *v27; // rbx
  LPSTR v28; // r15
  _DWORD *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  LPBYTE *v32; // r8
  int v33; // eax
  __int64 v34; // r8
  const char *v35; // r9
  DWORD nNumberOfBytesToWrite; // [rsp+40h] [rbp-79h] BYREF
  int cbMultiByte; // [rsp+44h] [rbp-75h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-71h] BYREF
  int v39; // [rsp+50h] [rbp-69h] BYREF
  LPVOID v40; // [rsp+58h] [rbp-61h] BYREF
  int v41; // [rsp+60h] [rbp-59h] BYREF
  int v42; // [rsp+64h] [rbp-55h]
  LPSTR lpMultiByteStr[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v44; // [rsp+78h] [rbp-41h]
  __int64 v45; // [rsp+80h] [rbp-39h]
  __int128 pExceptionObject; // [rsp+88h] [rbp-31h] BYREF
  __m128i si128; // [rsp+98h] [rbp-21h]
  LPBYTE pData[2]; // [rsp+A8h] [rbp-11h] BYREF
  __m128i v49; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v51; // [rsp+128h] [rbp+6Fh] BYREF

  v51 = a2;
  v45 = -2;
  v5 = a3;
  v40 = a3;
  v7 = 0;
  v42 = 0;
  v8 = CoInitializeEx(0, 0);
  if ( v8 >= 0 )
  {
    v7 = 1;
    v42 = 1;
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
      std::vector<unsigned char>::vector<unsigned char>(pData, nNumberOfBytesToWrite + 2LL);
      v10 = GetPrinterDataW(
              *((HANDLE *)this + 8),
              (LPWSTR)L"V4_PDC_ChangeID",
              0,
              pData[0],
              LODWORD(pData[1]) - LODWORD(pData[0]),
              &nNumberOfBytesToWrite);
      v11 = v10 < 0;
      if ( v10 > 0 )
      {
        v10 = (unsigned __int16)v10 | 0x80070000;
        v11 = v10 < 0;
      }
      if ( v11 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v10);
        throw (hr_error *)&pExceptionObject;
      }
      v12 = pData[0];
      *(_WORD *)&pData[0][2 * ((unsigned __int64)(pData[1] - pData[0]) >> 1) - 2] = 0;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v12[2 * v13] );
      if ( v13 > *((_QWORD *)this + 14) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)this + 88);
      }
      else
      {
        if ( *((_QWORD *)this + 14) <= 7u )
          v14 = (char *)this + 88;
        else
          v14 = (char *)*((_QWORD *)this + 11);
        *((_QWORD *)this + 13) = v13;
        v15 = 2 * v13;
        memmove_0(v14, v12, 2 * v13);
        *(_WORD *)&v14[v15] = 0;
        v5 = (int *)v40;
      }
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::FetchDeviceConfigData",
        L"Cached Bidi PrintDeviceCapabilities changeid: %ws",
        v12);
      if ( (unsigned __int8)std::operator==<unsigned short>((wchar_t *)L"V4_No_ChangeID_Present", (wchar_t *)this + 44) )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "PrintConfig::CConfigManager::FetchDeviceConfigData",
          L"There was no change ID found the last time we retrieved a PrintDeviceCapabilities file from this device. Skipping.");
        std::vector<char>::~vector<char>(pData);
        goto LABEL_44;
      }
      std::vector<char>::~vector<char>(pData);
    }
    else if ( PrinterDataW == 2 )
    {
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::FetchDeviceConfigData",
        L"No cached Bidi PrintDeviceCapabilities changeid found");
    }
    else
    {
      v20 = PrinterDataW < 0;
      if ( PrinterDataW > 0 )
      {
        PrinterDataW = (unsigned __int16)PrinterDataW | 0x80070000;
        v20 = PrinterDataW < 0;
      }
      if ( v20 )
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
    *((_QWORD *)&pExceptionObject + 1) = &v51;
    si128.m128i_i64[0] = (__int64)&pv;
    si128.m128i_i64[1] = (__int64)&cbMultiByte;
    v16 = ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e_(&pExceptionObject);
    if ( v16 < 0 )
    {
      if ( v51 || v16 != -2147418113 || (v17 = pv) != 0 && cbMultiByte )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v16);
        throw (hr_error *)&pExceptionObject;
      }
      *a4 = 1;
      if ( v17 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v17);
        SetLastError(LastError);
      }
      pv = 0;
      v19 = (const unsigned __int16 *)((char *)this + 88);
      if ( *((_QWORD *)this + 14) > 7u )
        v19 = *(const unsigned __int16 **)v19;
      PrintConfig::CConfigManager::RetrieveBidiData(
        this,
        L"\\Printer.Capabilities:DefaultData",
        v19,
        7,
        (unsigned __int8 **)&pv,
        (unsigned int *)&cbMultiByte);
      Print::Driver::Telemetry::PrintConfigTelemetry::DefaultPDCFallback();
    }
  }
  else
  {
    pv = 0;
    v21 = L"\\Printer.Configuration.DriverConfigFiles:GPDFile";
    if ( !*((_DWORD *)this + 6) )
      v21 = L"\\Printer.Configuration.DriverConfigFiles:PPDFile";
    PrintConfig::CConfigManager::RetrieveBidiData(
      this,
      v21,
      0,
      4,
      (unsigned __int8 **)&pv,
      (unsigned int *)&cbMultiByte);
  }
  if ( pv )
  {
    if ( v51 && *((_BYTE *)this + 28) )
    {
      nNumberOfBytesToWrite = 0;
      v22 = PrintConfig::CConfigManager::CheckAndUpdateRegistryPdcChecksum(
              this,
              (unsigned __int8 *)pv,
              cbMultiByte,
              (int *)&nNumberOfBytesToWrite);
      if ( v22 < 0 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v22);
        throw (hr_error *)&pExceptionObject;
      }
      v39 = 0;
      v23 = PrintConfig::CConfigManager::CheckAndUpdateRegistryLanguage(this, &v39);
      if ( v23 < 0 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v23);
        throw (hr_error *)&pExceptionObject;
      }
      if ( nNumberOfBytesToWrite || v39 )
      {
        PrintConfig::LanguageDatabase::ClearResources(*((HANDLE *)this + 8), 0);
        PrintConfig::CConfigManager::UpgradeLanguageDatabase(this);
      }
    }
    *(_OWORD *)lpMultiByteStr = 0;
    v44 = 0;
    v24 = cbMultiByte;
    nNumberOfBytesToWrite = cbMultiByte;
    if ( *((_BYTE *)this + 28) )
    {
      v41 = 0;
      pExceptionObject = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(pExceptionObject) = 0;
      v39 = 0;
      v40 = 0;
      if ( (int)PrintConfig::CConfigManager::RetrieveBestLanguageResource(this, &pExceptionObject, &v40, &v39) < 0 )
      {
        v27 = v40;
      }
      else
      {
        p_pExceptionObject = &pExceptionObject;
        if ( si128.m128i_i64[1] > 7uLL )
          p_pExceptionObject = (__int128 *)pExceptionObject;
        v26 = PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(
                (const BYTE **)&pv,
                cbMultiByte,
                (const BYTE **)&v40,
                v39,
                (__int64)p_pExceptionObject,
                *((_QWORD *)this + 2),
                &nNumberOfBytesToWrite,
                &v41);
        if ( v26 < 0 )
        {
          hr_error::hr_error((hr_error *)pData, v26);
          throw (hr_error *)pData;
        }
        v27 = v40;
        if ( v41 )
          PrintConfig::CConfigManager::CommitLanguageResources(
            (_DWORD)this,
            (unsigned int)&pExceptionObject,
            0,
            (_DWORD)v40,
            v41);
        v24 = nNumberOfBytesToWrite;
      }
      if ( *((_DWORD *)this + 30) == 3 )
        PrintConfig::CConfigManager::SavePScriptConfigDataIfNeeded(this, (unsigned __int8 *)pv, cbMultiByte);
      v28 = (LPSTR)pv;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
      {
        v29 = (_DWORD *)*((_QWORD *)Print::Driver::Telemetry::PrintConfigTelemetry::Instance() + 1);
        if ( v29 )
        {
          if ( *v29 )
          {
            v31 = v24;
            *(_OWORD *)pData = 0;
            v49 = 0;
            if ( v24 )
            {
              std::string::_Construct_from_iter<unsigned char const *,unsigned char const *,unsigned __int64>(
                pData,
                v28,
                v30,
                v24);
            }
            else
            {
              v49 = _mm_load_si128((const __m128i *)&_xmm);
              LOBYTE(pData[0]) = 0;
            }
            v32 = pData;
            if ( v49.m128i_i64[1] > 0xFuLL )
              v32 = (LPBYTE *)pData[0];
            Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
              "PrintConfig::CConfigManager::FetchDeviceConfigData",
              L"Regenerated PDC: %hs",
              v32,
              v31);
            std::string::~string((char **)pData);
          }
        }
      }
      if ( v27 )
        CoTaskMemFree(v27);
      std::wstring::~wstring(&pExceptionObject);
    }
    else
    {
      if ( cbMultiByte )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(lpMultiByteStr, (unsigned int)cbMultiByte);
        v24 = cbMultiByte;
      }
      v28 = lpMultiByteStr[0];
      v33 = WideCharToMultiByte(0, 0x400u, (LPCWCH)pv, -1, lpMultiByteStr[0], v24, 0, 0);
      v24 = v33;
      if ( !v33 )
      {
        v34 = GetLastError();
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "PrintConfig::CConfigManager::FetchDeviceConfigData",
          L"WideCharToMultiByte failed: %d",
          v34);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x28B,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          v35);
      }
      if ( !lpMultiByteStr[0][v33 - 1] )
        v24 = v33 - 1;
    }
    PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(this, v28, v24, v51, v5);
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
0x180042dac  mov     [rsp-8+arg_8], edx
0x180042db0  push    rbp
0x180042db1  push    rbx
0x180042db2  push    rsi
0x180042db3  push    rdi
0x180042db4  push    r12
0x180042db6  push    r13
0x180042db8  push    r14
0x180042dba  push    r15
0x180042dbc  lea     rbp, [rsp-1Fh]
0x180042dc1  sub     rsp, 0D8h
0x180042dc8  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180042dd0  mov     rax, cs:__security_cookie
0x180042dd7  xor     rax, rsp
0x180042dda  mov     [rbp+57h+var_48], rax
0x180042dde  mov     r13, r9
0x180042de1  mov     r12, r8
0x180042de4  mov     [rbp+57h+var_B8], r8
0x180042de8  mov     rsi, rcx
0x180042deb  xor     ebx, ebx
0x180042ded  mov     edi, ebx
0x180042def  mov     [rbp+57h+var_AC], ebx
0x180042df2  xor     edx, edx; dwCoInit
0x180042df4  xor     ecx, ecx; pvReserved
0x180042df6  call    cs:__imp_CoInitializeEx
0x180042dfc  test    eax, eax
0x180042dfe  jns     short loc_180042E0D
0x180042e00  cmp     eax, 80010106h
0x180042e05  jnz     loc_1800433B1
0x180042e0b  jmp     short loc_180042E15
0x180042e0d  mov     edi, 1
0x180042e12  mov     [rbp+57h+var_AC], edi
0x180042e15  mov     [r12], ebx
0x180042e19  mov     [r13+0], ebx
0x180042e1d  mov     r8, [rsi+10h]
0x180042e21  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x180042e28  lea     r15, aPrintconfigCco_2; "PrintConfig::CConfigManager::FetchDevic"...
0x180042e2f  mov     rcx, r15; char *
0x180042e32  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042e37  cmp     [rsi+1Ch], bl
0x180042e3a  jz      loc_180042F99
0x180042e40  cmp     [rsi+1Dh], bl
0x180042e43  jnz     short loc_180042E59
0x180042e45  lea     rdx, aDriverIsPrintd; "Driver is PrintDeviceCapabilities-based"...
0x180042e4c  mov     rcx, r15; char *
0x180042e4f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042e54  jmp     loc_1800430D8
0x180042e59  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x180042e5c  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x180042e60  mov     [rsp+110h+pcbNeeded], rax; pcbNeeded
0x180042e65  mov     [rsp+110h+nSize], ebx; nSize
0x180042e69  xor     r9d, r9d; pData
0x180042e6c  xor     r8d, r8d; pType
0x180042e6f  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x180042e76  mov     rcx, [rsi+40h]; hPrinter
0x180042e7a  call    cs:__imp_GetPrinterDataW
0x180042e80  cmp     eax, 0EAh
0x180042e85  jnz     loc_180043064
0x180042e8b  mov     edx, [rbp+57h+nNumberOfBytesToWrite]
0x180042e8e  add     rdx, 2
0x180042e92  lea     rcx, [rbp+57h+pData]
0x180042e96  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180042e9b  nop
0x180042e9c  mov     r9, [rbp+57h+pData]; pData
0x180042ea0  mov     eax, dword ptr [rbp+57h+pData+8]
0x180042ea3  sub     eax, r9d
0x180042ea6  lea     rcx, [rbp+57h+nNumberOfBytesToWrite]
0x180042eaa  mov     [rsp+110h+pcbNeeded], rcx; pcbNeeded
0x180042eaf  mov     [rsp+110h+nSize], eax; nSize
0x180042eb3  xor     r8d, r8d; pType
0x180042eb6  lea     rdx, aV4PdcChangeid; "V4_PDC_ChangeID"
0x180042ebd  mov     rcx, [rsi+40h]; hPrinter
0x180042ec1  call    cs:__imp_GetPrinterDataW
0x180042ec7  test    eax, eax
0x180042ec9  jle     short loc_180042ED5
0x180042ecb  movzx   eax, ax
0x180042ece  or      eax, 80070000h
0x180042ed3  test    eax, eax
0x180042ed5  js      loc_1800433E9
0x180042edb  mov     r15, [rbp+57h+pData]
0x180042edf  mov     rcx, [rbp+57h+pData+8]
0x180042ee3  sub     rcx, r15
0x180042ee6  shr     rcx, 1
0x180042ee9  mov     [r15+rcx*2-2], bx
0x180042eef  lea     r14, [rsi+58h]
0x180042ef3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180042ef7  inc     rdx
0x180042efa  cmp     [r15+rdx*2], bx
0x180042eff  jnz     short loc_180042EF7
0x180042f01  cmp     rdx, [r14+18h]
0x180042f05  ja      short loc_180042F3B
0x180042f07  cmp     qword ptr [r14+18h], 7
0x180042f0c  jbe     short loc_180042F13
0x180042f0e  mov     r12, [r14]
0x180042f11  jmp     short loc_180042F16
0x180042f13  mov     r12, r14
0x180042f16  mov     [r14+10h], rdx
0x180042f1a  lea     rbx, [rdx+rdx]
0x180042f1e  mov     r8, rbx; Size
0x180042f21  mov     rdx, r15; Src
0x180042f24  mov     rcx, r12; void *
0x180042f27  call    memmove_0
0x180042f2c  xor     eax, eax
0x180042f2e  mov     [rbx+r12], ax
0x180042f33  mov     r12, [rbp+57h+var_B8]
0x180042f37  xor     ebx, ebx
0x180042f39  jmp     short loc_180042F46
0x180042f3b  mov     r9, r15
0x180042f3e  mov     rcx, r14
0x180042f41  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180042f46  mov     r8, r15
0x180042f49  lea     rdx, aCachedBidiPrin; "Cached Bidi PrintDeviceCapabilities cha"...
0x180042f50  lea     r15, aPrintconfigCco_2; "PrintConfig::CConfigManager::FetchDevic"...
0x180042f57  mov     rcx, r15; char *
0x180042f5a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042f5f  mov     rdx, r14; S1
0x180042f62  lea     rcx, aV4NoChangeidPr; "V4_No_ChangeID_Present"
0x180042f69  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x180042f6e  test    al, al
0x180042f70  jz      short loc_180042F90
0x180042f72  lea     rdx, aThereWasNoChan; "There was no change ID found the last t"...
0x180042f79  mov     rcx, r15; char *
0x180042f7c  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180042f81  nop
0x180042f82  lea     rcx, [rbp+57h+pData]
0x180042f86  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180042f8b  jmp     loc_1800430D8
0x180042f90  lea     rcx, [rbp+57h+pData]
0x180042f94  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180042f99  mov     [rbp+57h+pv], rbx
0x180042f9d  mov     [rbp+57h+cbMultiByte], ebx
0x180042fa0  cmp     [rsi+1Ch], bl
0x180042fa3  jz      loc_180043096
0x180042fa9  mov     qword ptr [rbp+57h+pExceptionObject], rsi
0x180042fad  lea     rax, [rbp+57h+arg_8]
0x180042fb1  mov     qword ptr [rbp+57h+pExceptionObject+8], rax
0x180042fb5  lea     rax, [rbp+57h+pv]
0x180042fb9  mov     qword ptr [rbp+57h+var_78], rax
0x180042fbd  lea     rax, [rbp+57h+cbMultiByte]
0x180042fc1  mov     qword ptr [rbp+57h+var_78+8], rax
0x180042fc5  lea     rcx, [rbp+57h+pExceptionObject]
0x180042fc9  call    ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e___; ExceptionBoundary__lambda_ee8da189f0c76455c44c9eba6677294e_
0x180042fce  test    eax, eax
0x180042fd0  jns     loc_1800430D2
0x180042fd6  cmp     [rbp+57h+arg_8], ebx
0x180042fd9  jnz     loc_180043405
0x180042fdf  cmp     eax, 8000FFFFh
0x180042fe4  jnz     loc_180043405
0x180042fea  mov     r14, [rbp+57h+pv]
0x180042fee  test    r14, r14
0x180042ff1  jz      short loc_180042FFC
0x180042ff3  cmp     [rbp+57h+cbMultiByte], ebx
0x180042ff6  jnz     loc_180043405
0x180042ffc  mov     dword ptr [r13+0], 1
0x180043004  test    r14, r14
0x180043007  jz      short loc_180043024
0x180043009  call    cs:__imp_GetLastError
0x18004300f  mov     ebx, eax
0x180043011  mov     rcx, r14; pv
0x180043014  call    cs:__imp_CoTaskMemFree
0x18004301a  mov     ecx, ebx; dwErrCode
0x18004301c  call    cs:__imp_SetLastError
0x180043022  xor     ebx, ebx
0x180043024  mov     [rbp+57h+pv], rbx
0x180043028  lea     r8, [rsi+58h]
0x18004302c  cmp     qword ptr [r8+18h], 7
0x180043031  jbe     short loc_180043036
0x180043033  mov     r8, [r8]; unsigned __int16 *
0x180043036  lea     rax, [rbp+57h+cbMultiByte]
0x18004303a  mov     [rsp+110h+pcbNeeded], rax; unsigned int *
0x18004303f  lea     rax, [rbp+57h+pv]
0x180043043  mov     qword ptr [rsp+110h+nSize], rax; unsigned __int8 **
0x180043048  mov     r9d, 7; unsigned int
0x18004304e  lea     rdx, aPrinterCapabil_0; "\\Printer.Capabilities:DefaultData"
0x180043055  mov     rcx, rsi; this
0x180043058  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18004305d  call    ?DefaultPDCFallback@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXXZ; Print::Driver::Telemetry::PrintConfigTelemetry::DefaultPDCFallback(void)
0x180043062  jmp     short loc_1800430D2
0x180043064  cmp     eax, 2
0x180043067  jnz     short loc_18004307D
0x180043069  lea     rdx, aNoCachedBidiPr; "No cached Bidi PrintDeviceCapabilities "...
0x180043070  mov     rcx, r15; char *
0x180043073  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043078  jmp     loc_180042F99
0x18004307d  test    eax, eax
0x18004307f  jle     short loc_18004308B
0x180043081  movzx   eax, ax
0x180043084  or      eax, 80070000h
0x180043089  test    eax, eax
0x18004308b  js      loc_1800433CD
0x180043091  jmp     loc_180042F99
0x180043096  mov     [rbp+57h+pv], rbx
0x18004309a  lea     rax, aPrinterConfigu; "\\Printer.Configuration.DriverConfigFil"...
0x1800430a1  lea     rdx, aPrinterConfigu_1; "\\Printer.Configuration.DriverConfigFil"...
0x1800430a8  cmp     [rsi+18h], ebx
0x1800430ab  cmovz   rdx, rax; unsigned __int16 *
0x1800430af  lea     rax, [rbp+57h+cbMultiByte]
0x1800430b3  mov     [rsp+110h+pcbNeeded], rax; unsigned int *
0x1800430b8  lea     rax, [rbp+57h+pv]
0x1800430bc  mov     qword ptr [rsp+110h+nSize], rax; unsigned __int8 **
0x1800430c1  mov     r9d, 4; unsigned int
0x1800430c7  xor     r8d, r8d; unsigned __int16 *
0x1800430ca  mov     rcx, rsi; this
0x1800430cd  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x1800430d2  cmp     [rbp+57h+pv], rbx
0x1800430d6  jnz     short loc_180043102
0x1800430d8  test    edi, edi
0x1800430da  jz      short loc_1800430E2
0x1800430dc  call    cs:__imp_CoUninitialize
0x1800430e2  mov     rcx, [rbp+57h+var_48]
0x1800430e6  xor     rcx, rsp; StackCookie
0x1800430e9  call    __security_check_cookie
0x1800430ee  add     rsp, 0D8h
0x1800430f5  pop     r15
0x1800430f7  pop     r14
0x1800430f9  pop     r13
0x1800430fb  pop     r12
0x1800430fd  pop     rdi
0x1800430fe  pop     rsi
0x1800430ff  pop     rbx
0x180043100  pop     rbp
0x180043101  retn
0x180043102  cmp     [rbp+57h+arg_8], ebx
0x180043105  jz      short loc_180043168
0x180043107  cmp     [rsi+1Ch], bl
0x18004310a  jz      short loc_180043168
0x18004310c  mov     [rbp+57h+nNumberOfBytesToWrite], ebx
0x18004310f  lea     r9, [rbp+57h+nNumberOfBytesToWrite]; int *
0x180043113  mov     r8d, [rbp+57h+cbMultiByte]; unsigned int
0x180043117  mov     rdx, [rbp+57h+pv]; unsigned __int8 *
0x18004311b  mov     rcx, rsi; this
0x18004311e  call    ?CheckAndUpdateRegistryPdcChecksum@CConfigManager@PrintConfig@@AEAAJPEAEKPEAH@Z; PrintConfig::CConfigManager::CheckAndUpdateRegistryPdcChecksum(uchar *,ulong,int *)
0x180043123  test    eax, eax
0x180043125  js      loc_180043421
0x18004312b  mov     [rbp+57h+var_C0], ebx
0x18004312e  lea     rdx, [rbp+57h+var_C0]; int *
0x180043132  mov     rcx, rsi; this
0x180043135  call    ?CheckAndUpdateRegistryLanguage@CConfigManager@PrintConfig@@AEAAJPEAH@Z; PrintConfig::CConfigManager::CheckAndUpdateRegistryLanguage(int *)
0x18004313a  test    eax, eax
0x18004313c  js      loc_18004343D
0x180043142  cmp     [rbp+57h+nNumberOfBytesToWrite], ebx
0x180043145  jnz     short loc_18004314C
0x180043147  cmp     [rbp+57h+var_C0], ebx
0x18004314a  jz      short loc_180043168
0x18004314c  lea     rdx, [rsi+20h]
0x180043150  mov     byte ptr [rsp+110h+nSize], bl; char
0x180043154  mov     r9b, 1
0x180043157  mov     rcx, [rsi+40h]; hPrinter
0x18004315b  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x180043160  mov     rcx, rsi; this
0x180043163  call    ?UpgradeLanguageDatabase@CConfigManager@PrintConfig@@QEAAXXZ; PrintConfig::CConfigManager::UpgradeLanguageDatabase(void)
0x180043168  xorps   xmm0, xmm0
0x18004316b  movdqu  xmmword ptr [rbp+57h+lpMultiByteStr], xmm0
0x180043170  mov     [rbp+57h+var_98], rbx
0x180043174  mov     r14d, [rbp+57h+cbMultiByte]
0x180043178  mov     [rbp+57h+nNumberOfBytesToWrite], r14d
0x18004317c  cmp     [rsi+1Ch], bl
0x18004317f  jz      loc_1800432EC
0x180043185  mov     [rbp+57h+var_B0], ebx
0x180043188  movups  [rbp+57h+pExceptionObject], xmm0
0x18004318c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180043194  movdqu  [rbp+57h+var_78], xmm1
0x180043199  mov     word ptr [rbp+57h+pExceptionObject], bx
0x18004319d  mov     [rbp+57h+var_C0], ebx
0x1800431a0  mov     [rbp+57h+var_B8], rbx
0x1800431a4  lea     r9, [rbp+57h+var_C0]
0x1800431a8  lea     r8, [rbp+57h+var_B8]
0x1800431ac  lea     rdx, [rbp+57h+pExceptionObject]
0x1800431b0  mov     rcx, rsi
0x1800431b3  call    ?RetrieveBestLanguageResource@CConfigManager@PrintConfig@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBestLanguageResource(std::wstring &,uchar * *,ulong *)
0x1800431b8  test    eax, eax
0x1800431ba  js      short loc_18004322D
0x1800431bc  mov     rax, [rsi+10h]
0x1800431c0  lea     rcx, [rbp+57h+pExceptionObject]
0x1800431c4  cmp     qword ptr [rbp+57h+var_78+8], 7
0x1800431c9  cmova   rcx, qword ptr [rbp+57h+pExceptionObject]
0x1800431ce  lea     rdx, [rbp+57h+var_B0]
0x1800431d2  mov     [rsp+110h+lpUsedDefaultChar], rdx
0x1800431d7  lea     rdx, [rbp+57h+nNumberOfBytesToWrite]
0x1800431db  mov     [rsp+110h+lpDefaultChar], rdx
0x1800431e0  mov     [rsp+110h+pcbNeeded], rax
0x1800431e5  mov     qword ptr [rsp+110h+nSize], rcx
0x1800431ea  mov     r9d, [rbp+57h+var_C0]
0x1800431ee  lea     r8, [rbp+57h+var_B8]
0x1800431f2  mov     edx, [rbp+57h+cbMultiByte]
0x1800431f5  lea     rcx, [rbp+57h+pv]
0x1800431f9  call    ?CallPsaUpdatePdcAndPdrIfNeeded@CIppCSRHelper@PrintConfig@@SAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@H0HPEBG1PEAK2@Z; PrintConfig::CIppCSRHelper::CallPsaUpdatePdcAndPdrIfNeeded(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,int,ushort const *,ushort const *,ulong *,ulong *)
0x1800431fe  test    eax, eax
0x180043200  js      loc_180043459
0x180043206  mov     eax, [rbp+57h+var_B0]
0x180043209  mov     rbx, [rbp+57h+var_B8]
0x18004320d  test    eax, eax
0x18004320f  jz      short loc_180043227
0x180043211  mov     [rsp+110h+nSize], eax
0x180043215  mov     r9, rbx
0x180043218  xor     r8d, r8d
0x18004321b  lea     rdx, [rbp+57h+pExceptionObject]
0x18004321f  mov     rcx, rsi
0x180043222  call    ?CommitLanguageResources@CConfigManager@PrintConfig@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NPEBEK@Z; PrintConfig::CConfigManager::CommitLanguageResources(std::wstring const &,bool,uchar const *,ulong)
0x180043227  mov     r14d, [rbp+57h+nNumberOfBytesToWrite]
  ... truncated ...
```
