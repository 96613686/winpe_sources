# PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(uchar *,ulong,int,int *)

- ea: `0x18004b124`
- end: `0x18004b53e`
- name: `?SaveBidiConfigDataFileAndReg@CConfigManager@PrintConfig@@AEAAXPEAEKHPEAH@Z`
- size: `1050`
- prototype: `void __fastcall(PrintConfig::CConfigManager *this, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, int, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800446d8`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180019388`
- `0x18002dbc8`
- `0x180039584`
- `0x180042108`
- `0x1800434d8`
- `0x18004b124`
- `0x1801502f4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18004b355`
- `KERNEL32!WriteFile` at `0x18004b355`
- `KERNEL32!DeleteFileW` at `0x18004b49f`
- `KERNEL32!DeleteFileW` at `0x18004b49f`
- `KERNEL32!CreateFileW` at `0x18004b31f`
- `KERNEL32!CreateFileW` at `0x18004b31f`
- `KERNEL32!CloseHandle` at `0x18004b366`
- `KERNEL32!CloseHandle` at `0x18004b366`
- `KERNEL32!GetLastError` at `0x18004b3cb`
- `KERNEL32!GetLastError` at `0x18004b467`
- `KERNEL32!GetLastError` at `0x18004b506`
- `KERNEL32!GetLastError` at `0x18004b3cb`
- `KERNEL32!GetLastError` at `0x18004b467`
- `KERNEL32!GetLastError` at `0x18004b506`
- `WINSPOOL!SetPrinterDataW` at `0x18004b3b9`
- `WINSPOOL!SetPrinterDataW` at `0x18004b3b9`
- `WINSPOOL!GetPrinterDataW` at `0x18004b1be`
- `WINSPOOL!GetPrinterDataW` at `0x18004b1be`

## string_xrefs

- `0x18004b52c`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004b25d`: `device_bidi_pdc.xml`
- `0x18004b21c`: `No device Bidi config file content change.`
- `0x18004b1dd`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b223`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b2e5`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b394`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b3e4`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b485`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b51c`: `PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg`
- `0x18004b1b3`: `V4_DeviceBidi_ConfigFile_CRC`
- `0x18004b3ae`: `V4_DeviceBidi_ConfigFile_CRC`
- `0x18004b515`: `CreateFile failed: %d`
- `0x18004b38d`: `WriteFile OK: cbWritten=%d`
- `0x18004b47e`: `WriteFile failed: last_error=%d, uSize=%d, cbWritten=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg(
        PrintConfig::CConfigManager *this,
        _BYTE *lpBuffer,
        DWORD nNumberOfBytesToWrite,
        int a4,
        int *a5)
{
  int v8; // eax
  DWORD PrinterDataW; // eax
  signed int v10; // ebx
  int v11; // edx
  int v12; // eax
  wchar_t *v13; // rcx
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
  __int64 v26; // r8
  DWORD v27; // eax
  const WCHAR *v28; // rcx
  DWORD LastError; // eax
  const char *v30; // r9
  DWORD nSize[2]; // [rsp+28h] [rbp-71h]
  BYTE pData[4]; // [rsp+48h] [rbp-51h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-4Dh] BYREF
  BYTE v34[4]; // [rsp+50h] [rbp-49h] BYREF
  DWORD pcbNeeded; // [rsp+54h] [rbp-45h] BYREF
  DWORD pType; // [rsp+58h] [rbp-41h] BYREF
  int v37; // [rsp+5Ch] [rbp-3Dh]
  HANDLE hPrinter; // [rsp+60h] [rbp-39h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v40; // [rsp+88h] [rbp-11h]
  LPCWSTR lpFileName[3]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]

  v40 = -2;
  v37 = a4;
  pType = 0;
  *(_DWORD *)pData = 0;
  pcbNeeded = 0;
  *a5 = 0;
  hPrinter = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, HANDLE *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, &hPrinter);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v8);
    throw (hr_error *)pExceptionObject;
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
      hr_error::hr_error((hr_error *)pExceptionObject, v11);
      throw (hr_error *)pExceptionObject;
    }
  }
  v12 = ComputeCrc32Checksum(lpBuffer, nNumberOfBytesToWrite, 0);
  *(_DWORD *)v34 = v12;
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
    std::wstring::wstring((char *)lpFileName, v15, v14, v16, v14, v13, v15);
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
        (void *)0x114,
        (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
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
      hr_error::hr_error((hr_error *)pExceptionObject, -2147467259);
      throw (hr_error *)pExceptionObject;
    }
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::SaveBidiConfigDataFileAndReg",
      L"WriteFile OK: cbWritten=%d",
      NumberOfBytesWritten);
    v23 = SetPrinterDataW(*((HANDLE *)this + 8), (LPWSTR)L"V4_DeviceBidi_ConfigFile_CRC", 4u, v34, 4u);
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
        hr_error::hr_error((hr_error *)pExceptionObject, v23);
        throw (hr_error *)pExceptionObject;
      }
    }
    if ( *((_BYTE *)this + 28) )
    {
      PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID((__int64)this, (OLECHAR *)lpFileName);
      if ( !v37 )
        PrintConfig::LanguageDatabase::ClearResources(*((HANDLE *)this + 8), (_QWORD *)this + 4, v26, 1, 0);
      PrintConfig::CConfigManager::CacheManufacturerName((HANDLE *)this);
    }
    *a5 = 1;
    std::wstring::~wstring((char **)lpFileName);
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
0x18004b124  mov     rax, rsp
0x18004b127  push    rbp
0x18004b128  push    rsi
0x18004b129  push    rdi
0x18004b12a  push    r12
0x18004b12c  push    r13
0x18004b12e  push    r14
0x18004b130  push    r15
0x18004b132  lea     rbp, [rax-57h]
0x18004b136  sub     rsp, 0B0h
0x18004b13d  mov     [rbp+4Fh+var_60], 0FFFFFFFFFFFFFFFEh
0x18004b145  mov     [rax+20h], rbx
0x18004b149  mov     rax, cs:__security_cookie
0x18004b150  xor     rax, rsp
0x18004b153  mov     [rbp+4Fh+var_38], rax
0x18004b157  mov     [rbp+4Fh+var_8C], r9d
0x18004b15b  mov     r15d, r8d
0x18004b15e  mov     r12, rdx
0x18004b161  mov     rdi, rcx
0x18004b164  mov     r13, [rbp+4Fh+arg_20]
0x18004b168  xor     r14d, r14d
0x18004b16b  mov     [rbp+4Fh+pType], r14d
0x18004b16f  mov     dword ptr [rbp+4Fh+pData], r14d
0x18004b173  mov     [rbp+4Fh+var_94], r14d
0x18004b177  mov     [r13+0], r14d
0x18004b17b  mov     [rbp+4Fh+hPrinter], r14
0x18004b17f  mov     rcx, [rcx]
0x18004b182  mov     rax, [rcx]
0x18004b185  lea     rdx, [rbp+4Fh+hPrinter]
0x18004b189  mov     rax, [rax+38h]
0x18004b18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b192  test    eax, eax
0x18004b194  js      loc_18004B4CA
0x18004b19a  lea     rax, [rbp+4Fh+var_94]
0x18004b19e  mov     [rsp+0E0h+pcbNeeded], rax; pcbNeeded
0x18004b1a3  mov     [rsp+0E0h+nSize], 4; nSize
0x18004b1ab  lea     r9, [rbp+4Fh+pData]; pData
0x18004b1af  lea     r8, [rbp+4Fh+pType]; pType
0x18004b1b3  lea     rdx, aV4DevicebidiCo; "V4_DeviceBidi_ConfigFile_CRC"
0x18004b1ba  mov     rcx, [rbp+4Fh+hPrinter]; hPrinter
0x18004b1be  call    cs:__imp_GetPrinterDataW
0x18004b1c5  nop     dword ptr [rax+rax+00h]
0x18004b1ca  mov     ebx, eax
0x18004b1cc  test    eax, 0FFFFFFFDh
0x18004b1d1  jz      short loc_18004B202
0x18004b1d3  mov     r8d, eax
0x18004b1d6  lea     rdx, aGetprinterdata_6; "GetPrinterData failed: dwRet=%d"
0x18004b1dd  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b1e4  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b1e9  test    ebx, ebx
0x18004b1eb  jg      short loc_18004B1F1
0x18004b1ed  mov     edx, ebx
0x18004b1ef  jmp     short loc_18004B1FA
0x18004b1f1  movzx   edx, bx
0x18004b1f4  or      edx, 80070000h; int
0x18004b1fa  test    edx, edx
0x18004b1fc  js      loc_18004B4E6
0x18004b202  xor     r8d, r8d
0x18004b205  mov     edx, r15d
0x18004b208  mov     rcx, r12
0x18004b20b  call    ComputeCrc32Checksum
0x18004b210  mov     dword ptr [rbp+4Fh+var_98], eax
0x18004b213  test    ebx, ebx
0x18004b215  jnz     short loc_18004B257
0x18004b217  cmp     dword ptr [rbp+4Fh+pData], eax
0x18004b21a  jnz     short loc_18004B257
0x18004b21c  lea     rdx, aNoDeviceBidiCo; "No device Bidi config file content chan"...
0x18004b223  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b22a  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b22f  mov     rcx, [rbp+4Fh+var_38]
0x18004b233  xor     rcx, rsp; StackCookie
0x18004b236  call    __security_check_cookie
0x18004b23b  mov     rbx, [rsp+0E0h+arg_18]
0x18004b243  add     rsp, 0B0h
0x18004b24a  pop     r15
0x18004b24c  pop     r14
0x18004b24e  pop     r13
0x18004b250  pop     r12
0x18004b252  pop     rdi
0x18004b253  pop     rsi
0x18004b254  pop     rbp
0x18004b255  retn
0x18004b257  cmp     [rdi+1Ch], r14b
0x18004b25b  jz      short loc_18004B266
0x18004b25d  lea     rcx, aDeviceBidiPdcX; "device_bidi_pdc.xml"
0x18004b264  jmp     short loc_18004B27C
0x18004b266  lea     rcx, aDeviceBidiGpd; "device_bidi.gpd"
0x18004b26d  lea     rax, aDeviceBidiPpd; "device_bidi.ppd"
0x18004b274  cmp     [rdi+18h], r14d
0x18004b278  cmovz   rcx, rax
0x18004b27c  lea     rsi, [rdi+20h]
0x18004b280  mov     r8, [rsi+10h]
0x18004b284  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b288  inc     rdx
0x18004b28b  cmp     [rcx+rdx*2], r14w
0x18004b290  jnz     short loc_18004B288
0x18004b292  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004b29c  sub     rax, r8
0x18004b29f  cmp     rax, rdx
0x18004b2a2  jb      loc_18004B500
0x18004b2a8  cmp     qword ptr [rsi+18h], 7
0x18004b2ad  jbe     short loc_18004B2B4
0x18004b2af  mov     r9, [rsi]
0x18004b2b2  jmp     short loc_18004B2B7
0x18004b2b4  mov     r9, rsi
0x18004b2b7  mov     [rsp+30h], rdx
0x18004b2bc  mov     [rsp+0E0h+pcbNeeded], rcx
0x18004b2c1  mov     qword ptr [rsp+0E0h+nSize], r8
0x18004b2c6  lea     rcx, [rbp+4Fh+lpFileName]
0x18004b2ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004b2cf  nop
0x18004b2d0  lea     r8, [rbp+4Fh+lpFileName]
0x18004b2d4  cmp     [rbp+4Fh+var_40], 7
0x18004b2d9  cmova   r8, [rbp+4Fh+lpFileName]
0x18004b2de  lea     rdx, aBidifilenameWs; "BidiFileName=%ws"
0x18004b2e5  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b2ec  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b2f1  lea     rcx, [rbp+4Fh+lpFileName]
0x18004b2f5  cmp     [rbp+4Fh+var_40], 7
0x18004b2fa  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18004b2ff  mov     [rsp+30h], r14; hTemplateFile
0x18004b304  mov     dword ptr [rsp+0E0h+pcbNeeded], 8100080h; dwFlagsAndAttributes
0x18004b30c  mov     [rsp+0E0h+nSize], 2; dwCreationDisposition
0x18004b314  xor     r9d, r9d; lpSecurityAttributes
0x18004b317  xor     r8d, r8d; dwShareMode
0x18004b31a  mov     edx, 40000000h; dwDesiredAccess
0x18004b31f  call    cs:__imp_CreateFileW
0x18004b326  nop     dword ptr [rax+rax+00h]
0x18004b32b  mov     r14, rax
0x18004b32e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004b332  jz      loc_18004B506
0x18004b338  mov     [rbp+4Fh+NumberOfBytesWritten], 0
0x18004b33f  mov     qword ptr [rsp+0E0h+nSize], 0; lpOverlapped
0x18004b348  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004b34c  mov     r8d, r15d; nNumberOfBytesToWrite
0x18004b34f  mov     rdx, r12; lpBuffer
0x18004b352  mov     rcx, rax; hFile
0x18004b355  call    cs:__imp_WriteFile
0x18004b35c  nop     dword ptr [rax+rax+00h]
0x18004b361  mov     ebx, eax
0x18004b363  mov     rcx, r14; hObject
0x18004b366  call    cs:__imp_CloseHandle
0x18004b36d  nop     dword ptr [rax+rax+00h]
0x18004b372  mov     r14d, [rbp+4Fh+NumberOfBytesWritten]
0x18004b376  xor     r12d, r12d
0x18004b379  test    ebx, ebx
0x18004b37b  jz      loc_18004B467
0x18004b381  cmp     r14d, r15d
0x18004b384  jnz     loc_18004B467
0x18004b38a  mov     r8d, r14d
0x18004b38d  lea     rdx, aWritefileOkCbw; "WriteFile OK: cbWritten=%d"
0x18004b394  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b39b  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18004b3a0  lea     r8d, [r12+4]; Type
0x18004b3a5  mov     [rsp+0E0h+nSize], r8d; cbData
0x18004b3aa  lea     r9, [rbp+4Fh+var_98]; pData
0x18004b3ae  lea     rdx, aV4DevicebidiCo; "V4_DeviceBidi_ConfigFile_CRC"
0x18004b3b5  mov     rcx, [rdi+40h]; hPrinter
0x18004b3b9  call    cs:__imp_SetPrinterDataW
0x18004b3c0  nop     dword ptr [rax+rax+00h]
0x18004b3c5  mov     ebx, eax
0x18004b3c7  test    eax, eax
0x18004b3c9  jz      short loc_18004B401
0x18004b3cb  call    cs:__imp_GetLastError
0x18004b3d2  nop     dword ptr [rax+rax+00h]
0x18004b3d7  mov     r9d, eax
0x18004b3da  mov     r8d, ebx
0x18004b3dd  lea     rdx, aSetprinterdata_4; "SetPrinterData failed: dwRet=%d, error="...
0x18004b3e4  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b3eb  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b3f0  test    ebx, ebx
0x18004b3f2  jle     short loc_18004B3FF
0x18004b3f4  movzx   ebx, bx
0x18004b3f7  or      ebx, 80070000h
0x18004b3fd  test    ebx, ebx
0x18004b3ff  js      short loc_18004B44B
0x18004b401  cmp     [rdi+1Ch], r12b
0x18004b405  jz      short loc_18004B435
0x18004b407  lea     rdx, [rbp+4Fh+lpFileName]
0x18004b40b  mov     rcx, rdi
0x18004b40e  call    ?ExtractPrintDeviceCapabilitiesChangeID@CConfigManager@PrintConfig@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintConfig::CConfigManager::ExtractPrintDeviceCapabilitiesChangeID(std::wstring const &)
0x18004b413  cmp     [rbp+4Fh+var_8C], r12d
0x18004b417  jnz     short loc_18004B42D
0x18004b419  mov     byte ptr [rsp+0E0h+nSize], r12b; char
0x18004b41e  mov     r9b, 1
0x18004b421  mov     rdx, rsi
0x18004b424  mov     rcx, [rdi+40h]; hPrinter
0x18004b428  call    ?ClearResources@LanguageDatabase@PrintConfig@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N22@Z; PrintConfig::LanguageDatabase::ClearResources(void *,std::wstring const &,bool,bool,bool)
0x18004b42d  mov     rcx, rdi; this
0x18004b430  call    ?CacheManufacturerName@CConfigManager@PrintConfig@@AEAAXXZ; PrintConfig::CConfigManager::CacheManufacturerName(void)
0x18004b435  mov     dword ptr [r13+0], 1
0x18004b43d  lea     rcx, [rbp+4Fh+lpFileName]
0x18004b441  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004b446  jmp     loc_18004B22F
0x18004b44b  mov     edx, ebx; int
0x18004b44d  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004b451  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b456  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b45d  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004b461  call    _CxxThrowException_0
0x18004b467  call    cs:__imp_GetLastError
0x18004b46e  nop     dword ptr [rax+rax+00h]
0x18004b473  mov     [rsp+0E0h+nSize], r14d
0x18004b478  mov     r9d, r15d
0x18004b47b  mov     r8d, eax
0x18004b47e  lea     rdx, aWritefileFaile_0; "WriteFile failed: last_error=%d, uSize="...
0x18004b485  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b48c  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b491  lea     rcx, [rbp+4Fh+lpFileName]
0x18004b495  cmp     [rbp+4Fh+var_40], 7
0x18004b49a  cmova   rcx, [rbp+4Fh+lpFileName]; lpFileName
0x18004b49f  call    cs:__imp_DeleteFileW
0x18004b4a6  nop     dword ptr [rax+rax+00h]
0x18004b4ab  mov     edx, 80004005h; int
0x18004b4b0  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004b4b4  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b4b9  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b4c0  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004b4c4  call    _CxxThrowException_0
0x18004b4ca  mov     edx, eax; int
0x18004b4cc  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004b4d0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b4d5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b4dc  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004b4e0  call    _CxxThrowException_0
0x18004b4e6  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x18004b4ea  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18004b4ef  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004b4f6  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004b4fa  call    _CxxThrowException_0
0x18004b500  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18004b506  call    cs:__imp_GetLastError
0x18004b50d  nop     dword ptr [rax+rax+00h]
0x18004b512  mov     r8d, eax
0x18004b515  lea     rdx, aCreatefileFail_0; "CreateFile failed: %d"
0x18004b51c  lea     rcx, aPrintconfigCco_0; "PrintConfig::CConfigManager::SaveBidiCo"...
0x18004b523  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004b528  mov     rcx, [rbp+57h]; this
0x18004b52c  lea     r8, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004b533  mov     edx, 114h; void *
0x18004b538  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
