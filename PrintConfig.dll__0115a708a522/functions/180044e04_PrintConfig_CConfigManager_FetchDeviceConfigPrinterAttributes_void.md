# PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(void)

- ea: `0x180044e04`
- end: `0x180045097`
- name: `?FetchDeviceConfigPrinterAttributes@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `659`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001bb3c`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000e750`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180019388`
- `0x180044e04`
- `0x18004a36c`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18004501d`
- `KERNEL32!WriteFile` at `0x18004501d`
- `KERNEL32!DeleteFileW` at `0x180045063`
- `KERNEL32!DeleteFileW` at `0x180045063`
- `KERNEL32!CreateFileW` at `0x180044f57`
- `KERNEL32!CreateFileW` at `0x180044f57`
- `KERNEL32!CloseHandle` at `0x180044fa9`
- `KERNEL32!CloseHandle` at `0x180044fa9`
- `KERNEL32!GetLastError` at `0x180044f79`
- `KERNEL32!GetLastError` at `0x180045033`
- `KERNEL32!GetLastError` at `0x180044f79`
- `KERNEL32!GetLastError` at `0x180045033`
- `ole32!CoInitializeEx` at `0x180044e38`
- `ole32!CoInitializeEx` at `0x180044e38`
- `ole32!CoUninitialize` at `0x180044fd5`
- `ole32!CoUninitialize` at `0x180044fd5`
- `ole32!CoTaskMemFree` at `0x180044fc4`
- `ole32!CoTaskMemFree` at `0x180044fc4`

## string_xrefs

- `0x180044f88`: `CreateFile failed: error=%d`
- `0x180045042`: `WriteFile failed: error=%d`
- `0x180044e68`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x180044ec6`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x180044f8f`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x180045049`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(PrintConfig::CConfigManager *this)
{
  int v2; // ebx
  HRESULT v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // r9
  __int64 v7; // rcx
  const WCHAR *v8; // rcx
  char *FileW; // rdi
  __int64 v10; // r8
  DWORD v11; // r14d
  __int64 LastError; // r8
  const WCHAR *v13; // rcx
  DWORD nNumberOfBytesToWrite; // [rsp+40h] [rbp-39h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-35h] BYREF
  int v16; // [rsp+48h] [rbp-31h]
  void **pExceptionObject; // [rsp+50h] [rbp-29h] BYREF
  LPVOID pv[5]; // [rsp+58h] [rbp-21h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp+1Fh]

  pv[3] = (LPVOID)-2LL;
  v2 = 0;
  v16 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    v2 = 1;
    v16 = 1;
  }
  else if ( v3 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)&pExceptionObject, v3);
    throw (hr_error *)&pExceptionObject;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes",
    L"m_printerName=%ws",
    *((_QWORD *)this + 2));
  pExceptionObject = &CoTaskMemRAII<unsigned char *>::`vftable';
  pv[0] = 0;
  nNumberOfBytesToWrite = 0;
  PrintConfig::CConfigManager::RetrieveBidiData(
    this,
    L"\\Printer.Capabilities:PrinterAttributes",
    0,
    7,
    (unsigned __int8 **)pv,
    &nNumberOfBytesToWrite);
  if ( !pv[0] )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes",
      L"BIDI query for printer attributes returned null.");
    goto LABEL_16;
  }
  v6 = (_QWORD *)((char *)this + 32);
  v7 = *((_QWORD *)this + 6);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v7) < 0x22 )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 7) > 7u )
    v6 = (_QWORD *)*v6;
  std::wstring::wstring((char *)lpFileName, v4, v5, v6, v7, L"device_bidi_printer_attributes.ipp", 34);
  v8 = (const WCHAR *)lpFileName;
  if ( v20 > 7 )
    v8 = lpFileName[0];
  FileW = (char *)CreateFileW(v8, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
  pv[4] = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    NumberOfBytesWritten = 0;
    v11 = nNumberOfBytesToWrite;
    if ( !WriteFile(FileW, pv[0], nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v11 )
    {
      LastError = GetLastError();
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes",
        L"WriteFile failed: error=%d",
        LastError);
      v13 = (const WCHAR *)lpFileName;
      if ( v20 > 7 )
        v13 = lpFileName[0];
      DeleteFileW(v13);
    }
    goto LABEL_14;
  }
  v10 = GetLastError();
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
    "PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes",
    L"CreateFile failed: error=%d",
    v10);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_14:
    CloseHandle(FileW);
  std::wstring::~wstring((char **)lpFileName);
  CoTaskMemFree(pv[0]);
LABEL_16:
  if ( v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180044e04  push    rbp
0x180044e06  push    rbx
0x180044e07  push    rdi
0x180044e08  push    r14
0x180044e0a  lea     rbp, [rsp-3Fh]
0x180044e0f  sub     rsp, 0B8h
0x180044e16  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x180044e1e  mov     rax, cs:__security_cookie
0x180044e25  xor     rax, rsp
0x180044e28  mov     [rbp+57h+var_30], rax
0x180044e2c  mov     rdi, rcx
0x180044e2f  xor     ebx, ebx
0x180044e31  mov     [rbp+57h+var_88], ebx
0x180044e34  xor     edx, edx; dwCoInit
0x180044e36  xor     ecx, ecx; pvReserved
0x180044e38  call    cs:__imp_CoInitializeEx
0x180044e3f  nop     dword ptr [rax+rax+00h]
0x180044e44  test    eax, eax
0x180044e46  jns     short loc_180044E55
0x180044e48  cmp     eax, 80010106h
0x180044e4d  jnz     loc_18004507B
0x180044e53  jmp     short loc_180044E5D
0x180044e55  mov     ebx, 1
0x180044e5a  mov     [rbp+57h+var_88], ebx
0x180044e5d  mov     r8, [rdi+10h]
0x180044e61  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x180044e68  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x180044e6f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180044e74  lea     rax, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x180044e7b  mov     [rbp+57h+pExceptionObject], rax
0x180044e7f  mov     [rbp+57h+pv], 0
0x180044e87  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x180044e8e  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x180044e92  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; unsigned int *
0x180044e97  lea     rax, [rbp+57h+pv]
0x180044e9b  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int8 **
0x180044ea0  mov     r9d, 7; unsigned int
0x180044ea6  xor     r8d, r8d; unsigned __int16 *
0x180044ea9  lea     rdx, aPrinterCapabil_1; "\\Printer.Capabilities:PrinterAttribute"...
0x180044eb0  mov     rcx, rdi; this
0x180044eb3  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180044eb8  cmp     [rbp+57h+pv], 0
0x180044ebd  jnz     short loc_180044ED8
0x180044ebf  lea     rdx, aBidiQueryForPr; "BIDI query for printer attributes retur"...
0x180044ec6  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x180044ecd  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180044ed2  nop
0x180044ed3  jmp     loc_180044FD1
0x180044ed8  lea     r9, [rdi+20h]
0x180044edc  mov     rcx, [r9+10h]
0x180044ee0  mov     rax, 7FFFFFFFFFFFFFFEh
0x180044eea  sub     rax, rcx
0x180044eed  cmp     rax, 22h ; '"'
0x180044ef1  jb      loc_180045075
0x180044ef7  cmp     qword ptr [r9+18h], 7
0x180044efc  jbe     short loc_180044F01
0x180044efe  mov     r9, [r9]
0x180044f01  mov     [rsp+0D0h+hTemplateFile], 22h ; '"'
0x180044f0a  lea     rax, aDeviceBidiPrin; "device_bidi_printer_attributes.ipp"
0x180044f11  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x180044f16  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx
0x180044f1b  lea     rcx, [rbp+57h+lpFileName]
0x180044f1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180044f24  nop
0x180044f25  lea     rcx, [rbp+57h+lpFileName]
0x180044f29  cmp     [rbp+57h+var_38], 7
0x180044f2e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180044f33  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180044f3c  mov     [rsp+0D0h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180044f44  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180044f4c  xor     r9d, r9d; lpSecurityAttributes
0x180044f4f  xor     r8d, r8d; dwShareMode
0x180044f52  mov     edx, 40000000h; dwDesiredAccess
0x180044f57  call    cs:__imp_CreateFileW
0x180044f5e  nop     dword ptr [rax+rax+00h]
0x180044f63  mov     rdi, rax
0x180044f66  mov     [rbp+57h+var_58], rax
0x180044f6a  inc     rax
0x180044f6d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180044f73  jnz     loc_180044FFB
0x180044f79  call    cs:__imp_GetLastError
0x180044f80  nop     dword ptr [rax+rax+00h]
0x180044f85  mov     r8d, eax
0x180044f88  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x180044f8f  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x180044f96  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180044f9b  nop
0x180044f9c  lea     rax, [rdi-1]
0x180044fa0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180044fa4  ja      short loc_180044FB6
0x180044fa6  mov     rcx, rdi; hObject
0x180044fa9  call    cs:__imp_CloseHandle
0x180044fb0  nop     dword ptr [rax+rax+00h]
0x180044fb5  nop
0x180044fb6  lea     rcx, [rbp+57h+lpFileName]
0x180044fba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044fbf  nop
0x180044fc0  mov     rcx, [rbp+57h+pv]; pv
0x180044fc4  call    cs:__imp_CoTaskMemFree
0x180044fcb  nop     dword ptr [rax+rax+00h]
0x180044fd0  nop
0x180044fd1  test    ebx, ebx
0x180044fd3  jz      short loc_180044FE1
0x180044fd5  call    cs:__imp_CoUninitialize
0x180044fdc  nop     dword ptr [rax+rax+00h]
0x180044fe1  mov     rcx, [rbp+57h+var_30]
0x180044fe5  xor     rcx, rsp; StackCookie
0x180044fe8  call    __security_check_cookie
0x180044fed  add     rsp, 0B8h
0x180044ff4  pop     r14
0x180044ff6  pop     rdi
0x180044ff7  pop     rbx
0x180044ff8  pop     rbp
0x180044ff9  retn
0x180044ffb  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180045002  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x18004500b  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004500f  mov     r14d, [rbp+57h+nNumberOfBytesToWrite]
0x180045013  mov     r8d, r14d; nNumberOfBytesToWrite
0x180045016  mov     rdx, [rbp+57h+pv]; lpBuffer
0x18004501a  mov     rcx, rdi; hFile
0x18004501d  call    cs:__imp_WriteFile
0x180045024  nop     dword ptr [rax+rax+00h]
0x180045029  test    eax, eax
0x18004502b  jz      short loc_180045033
0x18004502d  cmp     [rbp+57h+NumberOfBytesWritten], r14d
0x180045031  jz      short loc_180045070
0x180045033  call    cs:__imp_GetLastError
0x18004503a  nop     dword ptr [rax+rax+00h]
0x18004503f  mov     r8d, eax
0x180045042  lea     rdx, aWritefileFaile_2; "WriteFile failed: error=%d"
0x180045049  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x180045050  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180045055  lea     rcx, [rbp+57h+lpFileName]
0x180045059  cmp     [rbp+57h+var_38], 7
0x18004505e  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180045063  call    cs:__imp_DeleteFileW
0x18004506a  nop     dword ptr [rax+rax+00h]
0x18004506f  nop
0x180045070  jmp     loc_180044FA6
0x180045075  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18004507b  mov     edx, eax; int
0x18004507d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180045081  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180045086  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18004508d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180045091  call    _CxxThrowException_0
```
