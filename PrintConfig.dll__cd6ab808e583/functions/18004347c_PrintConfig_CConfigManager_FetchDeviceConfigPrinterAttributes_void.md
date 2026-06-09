# PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes(void)

- ea: `0x18004347c`
- end: `0x1800436d4`
- name: `?FetchDeviceConfigPrinterAttributes@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `600`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18001aecc`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000e348`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018818`
- `0x18004347c`
- `0x180048514`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18004366c`
- `KERNEL32!WriteFile` at `0x18004366c`
- `KERNEL32!DeleteFileW` at `0x1800436a6`
- `KERNEL32!DeleteFileW` at `0x1800436a6`
- `KERNEL32!CreateFileW` at `0x1800435c9`
- `KERNEL32!CreateFileW` at `0x1800435c9`
- `KERNEL32!CloseHandle` at `0x18004360b`
- `KERNEL32!CloseHandle` at `0x18004360b`
- `KERNEL32!GetLastError` at `0x1800435e1`
- `KERNEL32!GetLastError` at `0x18004367c`
- `KERNEL32!GetLastError` at `0x1800435e1`
- `KERNEL32!GetLastError` at `0x18004367c`
- `ole32!CoInitializeEx` at `0x1800434b0`
- `ole32!CoInitializeEx` at `0x1800434b0`
- `ole32!CoUninitialize` at `0x18004362b`
- `ole32!CoUninitialize` at `0x18004362b`
- `ole32!CoTaskMemFree` at `0x180043620`
- `ole32!CoTaskMemFree` at `0x180043620`

## string_xrefs

- `0x1800435ea`: `CreateFile failed: error=%d`
- `0x180043685`: `WriteFile failed: error=%d`
- `0x1800434da`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x180043538`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x1800435f1`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`
- `0x18004368c`: `PrintConfig::CConfigManager::FetchDeviceConfigPrinterAttributes`

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
    7u,
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
  std::wstring::wstring(lpFileName, v4, v5, v6, v7, L"device_bidi_printer_attributes.ipp", 34);
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
  std::wstring::~wstring(lpFileName);
  CoTaskMemFree(pv[0]);
LABEL_16:
  if ( v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18004347c  push    rbp
0x18004347e  push    rbx
0x18004347f  push    rdi
0x180043480  push    r14
0x180043482  lea     rbp, [rsp-3Fh]
0x180043487  sub     rsp, 0B8h
0x18004348e  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x180043496  mov     rax, cs:__security_cookie
0x18004349d  xor     rax, rsp
0x1800434a0  mov     [rbp+57h+var_30], rax
0x1800434a4  mov     rdi, rcx
0x1800434a7  xor     ebx, ebx
0x1800434a9  mov     [rbp+57h+var_88], ebx
0x1800434ac  xor     edx, edx; dwCoInit
0x1800434ae  xor     ecx, ecx; pvReserved
0x1800434b0  call    cs:__imp_CoInitializeEx
0x1800434b6  test    eax, eax
0x1800434b8  jns     short loc_1800434C7
0x1800434ba  cmp     eax, 80010106h
0x1800434bf  jnz     loc_1800436B8
0x1800434c5  jmp     short loc_1800434CF
0x1800434c7  mov     ebx, 1
0x1800434cc  mov     [rbp+57h+var_88], ebx
0x1800434cf  mov     r8, [rdi+10h]
0x1800434d3  lea     rdx, aMPrinternameWs; "m_printerName=%ws"
0x1800434da  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x1800434e1  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800434e6  lea     rax, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x1800434ed  mov     [rbp+57h+pExceptionObject], rax
0x1800434f1  mov     [rbp+57h+pv], 0
0x1800434f9  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x180043500  lea     rax, [rbp+57h+nNumberOfBytesToWrite]
0x180043504  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; unsigned int *
0x180043509  lea     rax, [rbp+57h+pv]
0x18004350d  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; unsigned __int8 **
0x180043512  mov     r9d, 7; unsigned int
0x180043518  xor     r8d, r8d; unsigned __int16 *
0x18004351b  lea     rdx, aPrinterCapabil_1; "\\Printer.Capabilities:PrinterAttribute"...
0x180043522  mov     rcx, rdi; this
0x180043525  call    ?RetrieveBidiData@CConfigManager@PrintConfig@@AEAAXPEBG0KPEAPEAEPEAK@Z; PrintConfig::CConfigManager::RetrieveBidiData(ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18004352a  cmp     [rbp+57h+pv], 0
0x18004352f  jnz     short loc_18004354A
0x180043531  lea     rdx, aBidiQueryForPr; "BIDI query for printer attributes retur"...
0x180043538  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x18004353f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180043544  nop
0x180043545  jmp     loc_180043627
0x18004354a  lea     r9, [rdi+20h]
0x18004354e  mov     rcx, [r9+10h]
0x180043552  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004355c  sub     rax, rcx
0x18004355f  cmp     rax, 22h ; '"'
0x180043563  jb      loc_1800436B2
0x180043569  cmp     qword ptr [r9+18h], 7
0x18004356e  jbe     short loc_180043573
0x180043570  mov     r9, [r9]
0x180043573  mov     [rsp+0D0h+hTemplateFile], 22h ; '"'
0x18004357c  lea     rax, aDeviceBidiPrin; "device_bidi_printer_attributes.ipp"
0x180043583  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x180043588  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rcx
0x18004358d  lea     rcx, [rbp+57h+lpFileName]
0x180043591  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180043596  nop
0x180043597  lea     rcx, [rbp+57h+lpFileName]
0x18004359b  cmp     [rbp+57h+var_38], 7
0x1800435a0  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800435a5  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1800435ae  mov     [rsp+0D0h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1800435b6  mov     [rsp+0D0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800435be  xor     r9d, r9d; lpSecurityAttributes
0x1800435c1  xor     r8d, r8d; dwShareMode
0x1800435c4  mov     edx, 40000000h; dwDesiredAccess
0x1800435c9  call    cs:__imp_CreateFileW
0x1800435cf  mov     rdi, rax
0x1800435d2  mov     [rbp+57h+var_58], rax
0x1800435d6  inc     rax
0x1800435d9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800435df  jnz     short loc_18004364A
0x1800435e1  call    cs:__imp_GetLastError
0x1800435e7  mov     r8d, eax
0x1800435ea  lea     rdx, aCreatefileFail; "CreateFile failed: error=%d"
0x1800435f1  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x1800435f8  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800435fd  nop
0x1800435fe  lea     rax, [rdi-1]
0x180043602  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043606  ja      short loc_180043612
0x180043608  mov     rcx, rdi; hObject
0x18004360b  call    cs:__imp_CloseHandle
0x180043611  nop
0x180043612  lea     rcx, [rbp+57h+lpFileName]
0x180043616  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004361b  nop
0x18004361c  mov     rcx, [rbp+57h+pv]; pv
0x180043620  call    cs:__imp_CoTaskMemFree
0x180043626  nop
0x180043627  test    ebx, ebx
0x180043629  jz      short loc_180043631
0x18004362b  call    cs:__imp_CoUninitialize
0x180043631  mov     rcx, [rbp+57h+var_30]
0x180043635  xor     rcx, rsp; StackCookie
0x180043638  call    __security_check_cookie
0x18004363d  add     rsp, 0B8h
0x180043644  pop     r14
0x180043646  pop     rdi
0x180043647  pop     rbx
0x180043648  pop     rbp
0x180043649  retn
0x18004364a  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180043651  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x18004365a  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004365e  mov     r14d, [rbp+57h+nNumberOfBytesToWrite]
0x180043662  mov     r8d, r14d; nNumberOfBytesToWrite
0x180043665  mov     rdx, [rbp+57h+pv]; lpBuffer
0x180043669  mov     rcx, rdi; hFile
0x18004366c  call    cs:__imp_WriteFile
0x180043672  test    eax, eax
0x180043674  jz      short loc_18004367C
0x180043676  cmp     [rbp+57h+NumberOfBytesWritten], r14d
0x18004367a  jz      short loc_1800436AD
0x18004367c  call    cs:__imp_GetLastError
0x180043682  mov     r8d, eax
0x180043685  lea     rdx, aWritefileFaile_2; "WriteFile failed: error=%d"
0x18004368c  lea     rcx, aPrintconfigCco_4; "PrintConfig::CConfigManager::FetchDevic"...
0x180043693  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180043698  lea     rcx, [rbp+57h+lpFileName]
0x18004369c  cmp     [rbp+57h+var_38], 7
0x1800436a1  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800436a6  call    cs:__imp_DeleteFileW
0x1800436ac  nop
0x1800436ad  jmp     loc_180043608
0x1800436b2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800436b8  mov     edx, eax; int
0x1800436ba  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800436be  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800436c3  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800436ca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800436ce  call    _CxxThrowException_0
```
