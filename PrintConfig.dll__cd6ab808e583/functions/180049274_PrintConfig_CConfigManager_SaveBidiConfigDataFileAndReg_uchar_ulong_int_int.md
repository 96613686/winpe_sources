# PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(uchar *,ulong,int,int *)

- ea: `0x180049274`
- end: `0x1800496cb`
- name: `?SaveBidiConfigDataFileAndReg@CConfigManager@PrintConfig@@AEAAXPEAEKHPEAH@Z`
- size: `1111`
- prototype: `void __usercall(PrintConfig::CConfigManager *__hidden this@<rcx>, LPCVOID lpBuffer@<rdx>, DWORD nNumberOfBytesToWrite@<r8d>, int@<r9d>, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180042dac`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018818`
- `0x18002c8b4`
- `0x180038054`
- `0x180041c4c`
- `0x180048514`
- `0x180049274`
- `0x1801495bc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180049498`
- `KERNEL32!WriteFile` at `0x180049498`
- `KERNEL32!DeleteFileW` at `0x180049638`
- `KERNEL32!DeleteFileW` at `0x180049638`
- `KERNEL32!CreateFileW` at `0x180049468`
- `KERNEL32!CreateFileW` at `0x180049468`
- `KERNEL32!CloseHandle` at `0x1800494a3`
- `KERNEL32!CloseHandle` at `0x1800494a3`
- `KERNEL32!GetLastError` at `0x1800494ff`
- `KERNEL32!GetLastError` at `0x180049606`
- `KERNEL32!GetLastError` at `0x180049699`
- `KERNEL32!GetLastError` at `0x1800494ff`
- `KERNEL32!GetLastError` at `0x180049606`
- `KERNEL32!GetLastError` at `0x180049699`
- `ole32!CoTaskMemFree` at `0x1800495d2`
- `ole32!CoTaskMemFree` at `0x1800495d2`
- `WINSPOOL!SetPrinterDataW` at `0x1800494f3`
- `WINSPOOL!SetPrinterDataW` at `0x1800495c3`
- `WINSPOOL!SetPrinterDataW` at `0x1800494f3`
- `WINSPOOL!SetPrinterDataW` at `0x1800495c3`
- `WINSPOOL!GetPrinterDataW` at `0x18004930e`
- `WINSPOOL!GetPrinterDataW` at `0x18004930e`

## string_xrefs

- `0x1800496b9`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x1800493a6`: `device_bidi_pdc.xml`
- `0x180049366`: `No device Bidi config file content change.`
- `0x180049327`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004936d`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004942e`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x1800494cb`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x180049512`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004961e`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x1800496a9`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x180049303`: `V4_DeviceBidi_ConfigFile_CRC`
- `0x1800494e8`: `V4_DeviceBidi_ConfigFile_CRC`
- `0x1800496a2`: `CreateFile failed: %d`
- `0x1800494c4`: `WriteFile OK: cbWritten=%d`
- `0x180049617`: `WriteFile failed: last_error=%d, uSize=%d, cbWritten=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(
        PrintConfig::CConfigManager *this,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        DWORD a4,
        int *a5)
{
  int v8; // eax
  DWORD PrinterDataW; // eax
  signed int v10; // ebx
  int v11; // edx
  int v12; // eax
  const wchar_t *v13; // rcx
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  char *v16; // r9
  LPCWSTR *v17; // r8
  const WCHAR *v18; // rcx
  HANDLE FileW; // rax
  void *v20; // r14
  BOOL v21; // ebx
  DWORD v22; // r14d
  signed int v23; // ebx
  DWORD v24; // eax
  bool v25; // sf
  LPBYTE v26; // rbx
  DWORD v27; // eax
  const WCHAR *v28; // rcx
  DWORD LastError; // eax
  const char *v30; // r9
  DWORD nSize[2]; // [rsp+28h] [rbp-71h]
  DWORD cbData; // [rsp+48h] [rbp-51h] BYREF
  BYTE pData[4]; // [rsp+4Ch] [rbp-4Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-49h] BYREF
  BYTE v35[4]; // [rsp+54h] [rbp-45h] BYREF
  DWORD pcbNeeded; // [rsp+58h] [rbp-41h] BYREF
  DWORD pType; // [rsp+5Ch] [rbp-3Dh] BYREF
  HANDLE hPrinter; // [rsp+60h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+68h] [rbp-31h] BYREF
  LPBYTE v40[4]; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]

  v40[3] = (LPBYTE)-2LL;
  cbData = a4;
  pType = 0;
  *(_DWORD *)pData = 0;
  pcbNeeded = 0;
  *a5 = 0;
  hPrinter = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, &hPrinter);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v8);
    throw (hr_error *)&pExceptionObject;
  }
  PrinterDataW = GetPrinterDataW(hPrinter, (LPWSTR)L"V4_DeviceBidi_ConfigFile_CRC", &pType, pData, 4u, &pcbNeeded);
  v10 = PrinterDataW;
  if ( (PrinterDataW & 0xFFFFFFFD) != 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
      L"GetPrinterData failed: dwRet=%d",
      PrinterDataW);
    v11 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
    if ( v11 < 0 )
    {
      hr_error::hr_error((hr_error *)&pExceptionObject, v11);
      throw (hr_error *)&pExceptionObject;
    }
  }
  v12 = ComputeCrc32Checksum(lpBuffer, nNumberOfBytesToWrite, 0);
  *(_DWORD *)v35 = v12;
  if ( v10 || *(_DWORD *)pData != v12 )
  {
    if ( *((_BYTE *)this + 28) )
    {
      v13 = L"device_bidi_pdc.xml";
    }
    else
    {
      v13 = L"device_bidi.gpd";
      if ( !*((_DWORD *)this + 6) )
        v13 = L"device_bidi.ppd";
    }
    v14 = *((_QWORD *)this + 6);
    v15 = -1;
    do
      ++v15;
    while ( v13[v15] );
    if ( 0x7FFFFFFFFFFFFFFELL - v14 < v15 )
      std::_Xlen_string();
    if ( *((_QWORD *)this + 7) <= 7u )
      v16 = (char *)this + 32;
    else
      v16 = (char *)*((_QWORD *)this + 4);
    std::wstring::wstring(lpFileName, v15, v14, v16, v14, v13, v15);
    v17 = lpFileName;
    if ( v42 > 7 )
      v17 = (LPCWSTR *)lpFileName[0];
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
      L"BidiFileName=%ws",
      v17);
    v18 = (const WCHAR *)lpFileName;
    if ( v42 > 7 )
      v18 = lpFileName[0];
    FileW = CreateFileW(v18, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
    v20 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
        L"CreateFile failed: %d",
        LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10C,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        v30);
    }
    NumberOfBytesWritten = 0;
    v21 = WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
    CloseHandle(v20);
    v22 = NumberOfBytesWritten;
    if ( !v21 || NumberOfBytesWritten != nNumberOfBytesToWrite )
    {
      v27 = GetLastError();
      nSize[0] = v22;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
        L"WriteFile failed: last_error=%d, uSize=%d, cbWritten=%d",
        v27,
        nNumberOfBytesToWrite,
        *(_QWORD *)nSize);
      v28 = (const WCHAR *)lpFileName;
      if ( v42 > 7 )
        v28 = lpFileName[0];
      DeleteFileW(v28);
      hr_error::hr_error((hr_error *)&pExceptionObject, -2147467259);
      throw (hr_error *)&pExceptionObject;
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
      L"WriteFile OK: cbWritten=%d",
      NumberOfBytesWritten);
    v23 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_DeviceBidi_ConfigFile_CRC", 4u, v35, 4u);
    if ( v23 )
    {
      v24 = GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
        L"SetPrinterData failed: dwRet=%d, error=%d",
        (unsigned int)v23,
        v24);
      v25 = v23 < 0;
      if ( v23 > 0 )
      {
        v23 = (unsigned __int16)v23 | 0x80070000;
        v25 = v23 < 0;
      }
      if ( v25 )
      {
        hr_error::hr_error((hr_error *)&pExceptionObject, v23);
        throw (hr_error *)&pExceptionObject;
      }
    }
    if ( *((_BYTE *)this + 28) )
    {
      PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(this, lpFileName);
      if ( !cbData )
        PrintConfig::LanguageDatabase::ClearResources(*((HANDLE *)this + 8), 0);
      pExceptionObject = &CoTaskMemRAII<unsigned char *>::`vftable';
      v40[0] = 0;
      cbData = 0;
      PrintConfig::CConfigManager::RetrieveBidiData(this, L"\\Printer.DeviceInfo:Manufacturer", 0, 4u, v40, &cbData);
      v26 = v40[0];
      if ( cbData )
        SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_PDC_Manufacturer", 1u, v40[0], cbData);
      if ( v26 )
        CoTaskMemFree(v26);
    }
    *a5 = 1;
    std::wstring::~wstring(lpFileName);
  }
  else
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
      L"No device Bidi config file content change.");
  }
}

```

## disassembly

```asm
0x180049274  mov     rax, rsp
0x180049277  push    rbp
0x180049278  push    rsi
0x180049279  push    rdi
0x18004927a  push    r12
0x18004927c  push    r13
0x18004927e  push    r14
0x180049280  push    r15
0x180049282  lea     rbp, [rax-57h]
0x180049286  sub     rsp, 0B0h
0x18004928d  mov     [rbp+4Fh+var_60], 0FFFFFFFFFFFFFFFEh
0x180049295  mov     [rax+20h], rbx
0x180049299  mov     rax, cs:__security_cookie
0x1800492a0  xor     rax, rsp
0x1800492a3  mov     [rbp+4Fh+var_38], rax
0x1800492a7  mov     [rbp+4Fh+cbData], r9d
0x1800492ab  mov     r15d, r8d
0x1800492ae  mov     r12, rdx
0x1800492b1  mov     rdi, rcx
0x1800492b4  mov     r13, [rbp+4Fh+arg_20]
0x1800492b8  xor     r14d, r14d
0x1800492bb  mov     [rbp+4Fh+pType], r14d
0x1800492bf  mov     dword ptr [rbp+4Fh+pData], r14d
0x1800492c3  mov     [rbp+4Fh+var_90], r14d
0x1800492c7  mov     [r13+0], r14d
0x1800492cb  mov     [rbp+4Fh+hPrinter], r14
0x1800492cf  mov     rcx, [rcx]
0x1800492d2  mov     rax, [rcx]
0x1800492d5  lea     rdx, [rbp+4Fh+hPrinter]
0x1800492d9  mov     rax, [rax+38h]
0x1800492dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492e2  test    eax, eax
0x1800492e4  js      loc_18004965D
0x1800492ea  lea     rax, [rbp+4Fh+var_90]
0x1800492ee  mov     [rsp+0E0h+pcbNeeded], rax; pcbNeeded
0x1800492f3  mov     [rsp+0E0h+nSize], 4; nSize
0x1800492fb  lea     r9, [rbp+4Fh+pData]; pData
0x1800492ff  lea     r8, [rbp+4Fh+pType]; pType
0x180049303  lea     rdx, aV4DevicebidiCo; "V4_DeviceBidi_ConfigFile_CRC"
0x18004930a  mov     rcx, [rbp+4Fh+hPrinter]; hPrinter
0x18004930e  call    cs:__imp_GetPrinterDataW
0x180049314  mov     ebx, eax
0x180049316  test    eax, 0FFFFFFFDh
0x18004931b  jz      short loc_18004934C
0x18004931d  mov     r8d, eax
0x180049320  lea     rdx, aGetprinterdata_6; "GetPrinterData failed: dwRet=%d"
0x180049327  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004932e  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180049333  test    ebx, ebx
0x180049335  jg      short loc_18004933B
0x180049337  mov     edx, ebx
0x180049339  jmp     short loc_180049344
0x18004933b  movzx   edx, bx
0x18004933e  or      edx, 80070000h; int
0x180049344  test    edx, edx
0x180049346  js      loc_180049679
0x18004934c  xor     r8d, r8d
0x18004934f  mov     edx, r15d
0x180049352  mov     rcx, r12
0x180049355  call    ComputeCrc32Checksum
0x18004935a  mov     dword ptr [rbp+4Fh+var_94], eax
0x18004935d  test    ebx, ebx
0x18004935f  jnz     short loc_1800493A0
0x180049361  cmp     dword ptr [rbp+4Fh+pData], eax
0x180049364  jnz     short loc_1800493A0
0x180049366  lea     rdx, aNoDeviceBidiCo; "No device Bidi config file content chan"...
0x18004936d  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x180049374  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180049379  mov     rcx, [rbp+4Fh+var_38]
0x18004937d  xor     rcx, rsp; StackCookie
0x180049380  call    __security_check_cookie
0x180049385  mov     rbx, [rsp+0E0h+arg_18]
0x18004938d  add     rsp, 0B0h
0x180049394  pop     r15
0x180049396  pop     r14
0x180049398  pop     r13
0x18004939a  pop     r12
0x18004939c  pop     rdi
0x18004939d  pop     rsi
0x18004939e  pop     rbp
0x18004939f  retn
0x1800493a0  cmp     [rdi+1Ch], r14b
0x1800493a4  jz      short loc_1800493AF
0x1800493a6  lea     rcx, aDeviceBidiPdcX; "device_bidi_pdc.xml"
0x1800493ad  jmp     short loc_1800493C5
0x1800493af  lea     rcx, aDeviceBidiGpd; "device_bidi.gpd"
0x1800493b6  lea     rax, aDeviceBidiPpd; "device_bidi.ppd"
0x1800493bd  cmp     [rdi+18h], r14d
0x1800493c1  cmovz   rcx, rax
0x1800493c5  lea     rsi, [rdi+20h]
0x1800493c9  mov     r8, [rsi+10h]
0x1800493cd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800493d1  inc     rdx
0x1800493d4  cmp     [rcx+rdx*2], r14w
0x1800493d9  jnz     short loc_1800493D1
0x1800493db  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800493e5  sub     rax, r8
0x1800493e8  cmp     rax, rdx
0x1800493eb  jb      loc_180049693
0x1800493f1  cmp     qword ptr [rsi+18h], 7
0x1800493f6  jbe     short loc_1800493FD
0x1800493f8  mov     r9, [rsi]
0x1800493fb  jmp     short loc_180049400
0x1800493fd  mov     r9, rsi
0x180049400  mov     [rsp+30h], rdx
0x180049405  mov     [rsp+0E0h+pcbNeeded], rcx
0x18004940a  mov     qword ptr [rsp+0E0h+nSize], r8
0x18004940f  lea     rcx, [rbp+4Fh+lpFileName]
0x180049413  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180049418  nop
0x180049419  lea     r8, [rbp+4Fh+lpFileName]
0x18004941d  cmp     [rbp+4Fh+var_40], 7
0x180049422  cmova   r8, [rbp+4Fh+lpFileName]
0x180049427  lea     rdx, aBidifilenameWs; "BidiFileName=%ws"
0x18004942e  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x180049435  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004943a  lea     rcx, [rbp+4Fh+lpFileName]
0x18004943e  cmp     [rbp+4Fh+var_40], 7
0x180049443  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x180049448  mov     [rsp+30h], r14; hTemplateFile
0x18004944d  mov     dword ptr [rsp+0E0h+pcbNeeded], 8100080h; dwFlagsAndAttributes
0x180049455  mov     [rsp+0E0h+nSize], 2; dwCreationDisposition
0x18004945d  xor     r9d, r9d; lpSecurityAttributes
0x180049460  xor     r8d, r8d; dwShareMode
0x180049463  mov     edx, 40000000h; dwDesiredAccess
0x180049468  call    cs:__imp_CreateFileW
0x18004946e  mov     r14, rax
0x180049471  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049475  jz      loc_180049699
0x18004947b  mov     [rbp+4Fh+NumberOfBytesWritten], 0
0x180049482  mov     qword ptr [rsp+0E0h+nSize], 0; lpOverlapped
0x18004948b  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004948f  mov     r8d, r15d; nNumberOfBytesToWrite
0x180049492  mov     rdx, r12; lpBuffer
0x180049495  mov     rcx, rax; hFile
0x180049498  call    cs:__imp_WriteFile
0x18004949e  mov     ebx, eax
0x1800494a0  mov     rcx, r14; hObject
0x1800494a3  call    cs:__imp_CloseHandle
0x1800494a9  mov     r14d, [rbp+4Fh+NumberOfBytesWritten]
0x1800494ad  xor     r12d, r12d
0x1800494b0  test    ebx, ebx
0x1800494b2  jz      loc_180049606
0x1800494b8  cmp     r14d, r15d
0x1800494bb  jnz     loc_180049606
0x1800494c1  mov     r8d, r14d
0x1800494c4  lea     rdx, aWritefileOkCbw; "WriteFile OK: cbWritten=%d"
0x1800494cb  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x1800494d2  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800494d7  lea     r15d, [r12+4]
0x1800494dc  mov     [rsp+0E0h+nSize], r15d; cbData
0x1800494e1  lea     r9, [rbp+4Fh+var_94]; pData
0x1800494e5  mov     r8d, r15d; Type
0x1800494e8  lea     rdx, aV4DevicebidiCo; "V4_DeviceBidi_ConfigFile_CRC"
0x1800494ef  mov     rcx, [rdi+40h]; hPrinter
0x1800494f3  call    cs:__imp_SetPrinterDataW
0x1800494f9  mov     ebx, eax
0x1800494fb  test    eax, eax
0x1800494fd  jz      short loc_180049533
0x1800494ff  call    cs:__imp_GetLastError
0x180049505  mov     r9d, eax
0x180049508  mov     r8d, ebx
0x18004950b  lea     rdx, aSetprinterdata_4; "SetPrinterData failed: dwRet=%d, error="...
0x180049512  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x180049519  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004951e  test    ebx, ebx
0x180049520  jle     short loc_18004952D
0x180049522  movzx   ebx, bx
0x180049525  or      ebx, 80070000h
0x18004952b  test    ebx, ebx
0x18004952d  js      loc_1800495EA
0x180049533  mov     r14d, 1
0x180049539  cmp     [rdi+1Ch], r12b
0x18004953d  jz      loc_1800495D8
0x180049543  lea     rdx, [rbp+4Fh+lpFileName]
0x180049547  mov     rcx, rdi
0x18004954a  call    ?ExtractPrintDeviceCapabilitiesChangeID@CConfigManager@PrintConfig@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(std::wstring const &)
0x18004954f  cmp     [rbp+4Fh+cbData], r12d
0x180049553  jnz     short loc_180049569
0x180049555  mov     byte ptr [rsp+0E0h+nSize], r12b; char
0x18004955a  mov     r9b, r14b
0x18004955d  mov     rdx, rsi
0x180049560  mov     rcx, [rdi+40h]; hPrinter
0x180049564  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x180049569  lea     rax, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x180049570  mov     [rbp+4Fh+pExceptionObject], rax
0x180049574  mov     [rbp+4Fh+var_78], r12
0x180049578  mov     [rbp+4Fh+cbData], r12d
0x18004957c  lea     rax, [rbp+4Fh+cbData]
0x180049580  mov     [rsp+0E0h+pcbNeeded], rax; unsigned int *
0x180049585  lea     rax, [rbp+4Fh+var_78]
0x180049589  mov     qword ptr [rsp+0E0h+nSize], rax; unsigned __int8 **
0x18004958e  mov     r9d, r15d; unsigned int
0x180049591  xor     r8d, r8d; unsigned __int16 *
0x180049594  lea     rdx, aPrinterDevicei; "\\Printer.DeviceInfo:Manufacturer"
0x18004959b  mov     rcx, rdi; this
0x18004959e  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x1800495a3  mov     rbx, [rbp+4Fh+var_78]
0x1800495a7  mov     eax, [rbp+4Fh+cbData]
0x1800495aa  test    eax, eax
0x1800495ac  jz      short loc_1800495CA
0x1800495ae  mov     [rsp+0E0h+nSize], eax; cbData
0x1800495b2  mov     r9, rbx; pData
0x1800495b5  mov     r8d, r14d; Type
0x1800495b8  lea     rdx, aV4PdcManufactu; "V4_PDC_Manufacturer"
0x1800495bf  mov     rcx, [rdi+40h]; hPrinter
0x1800495c3  call    cs:__imp_SetPrinterDataW
0x1800495c9  nop
0x1800495ca  test    rbx, rbx
0x1800495cd  jz      short loc_1800495D8
0x1800495cf  mov     rcx, rbx; pv
0x1800495d2  call    cs:__imp_CoTaskMemFree
0x1800495d8  mov     [r13+0], r14d
0x1800495dc  lea     rcx, [rbp+4Fh+lpFileName]
0x1800495e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800495e5  jmp     loc_180049379
0x1800495ea  mov     edx, ebx; int
0x1800495ec  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x1800495f0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800495f5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800495fc  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180049600  call    _CxxThrowException_0
0x180049606  call    cs:__imp_GetLastError
0x18004960c  mov     [rsp+0E0h+nSize], r14d
0x180049611  mov     r9d, r15d
0x180049614  mov     r8d, eax
0x180049617  lea     rdx, aWritefileFaile_0; "WriteFile failed: last_error=%d, uSize="...
0x18004961e  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x180049625  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004962a  lea     rcx, [rbp+4Fh+lpFileName]
0x18004962e  cmp     [rbp+4Fh+var_40], 7
0x180049633  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x180049638  call    cs:__imp_DeleteFileW
0x18004963e  mov     edx, 80004005h; int
0x180049643  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180049647  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004964c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180049653  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180049657  call    _CxxThrowException_0
0x18004965d  mov     edx, eax; int
0x18004965f  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x180049663  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180049668  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004966f  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180049673  call    _CxxThrowException_0
0x180049679  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004967d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180049682  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180049689  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004968d  call    _CxxThrowException_0
0x180049693  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180049699  call    cs:__imp_GetLastError
0x18004969f  mov     r8d, eax
0x1800496a2  lea     rdx, aCreatefileFail_0; "CreateFile failed: %d"
0x1800496a9  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x1800496b0  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800496b5  mov     rcx, [rbp+57h]; this
0x1800496b9  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x1800496c0  mov     edx, 10Ch; void *
0x1800496c5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
