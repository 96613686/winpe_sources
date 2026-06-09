# CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)

- ea: `0x180010d40`
- end: `0x180010ef3`
- name: `?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, struct Win32HandleRAII *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001053c`
- `0x180017e70`

## callees

- `0x180010d40`
- `0x1800183a0`
- `0x1800183f8`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180010de3`
- `KERNEL32!WriteFile` at `0x180010e99`
- `KERNEL32!WriteFile` at `0x180010de3`
- `KERNEL32!WriteFile` at `0x180010e99`
- `KERNEL32!CreateFileW` at `0x180010dae`
- `KERNEL32!CreateFileW` at `0x180010e71`
- `KERNEL32!CreateFileW` at `0x180010dae`
- `KERNEL32!CreateFileW` at `0x180010e71`
- `KERNEL32!CloseHandle` at `0x180010dc4`
- `KERNEL32!CloseHandle` at `0x180010ed8`
- `KERNEL32!CloseHandle` at `0x180010dc4`
- `KERNEL32!CloseHandle` at `0x180010ed8`
- `KERNEL32!GetLastError` at `0x180010e1e`
- `KERNEL32!GetLastError` at `0x180010eb6`
- `KERNEL32!GetLastError` at `0x180010e1e`
- `KERNEL32!GetLastError` at `0x180010eb6`

## string_xrefs

- `0x180010d78`: `In CreateDataFile, file Handle value (%p)`
- `0x180010d7f`: `CreateDataFile`
- `0x180010e0d`: `CreateDataFile`
- `0x180010e40`: `CreateDataFile`
- `0x180010e39`: `WriteFile failed: pFileHandle is %p, result = (hr: 0x%x)`
- `0x180010e06`: `WriteFile failed: bytesWritten = %d byteCount = %d`

## pseudocode

```c
__int64 __fastcall CreateDataFile(
        LPCWSTR lpFileName,
        LPCVOID lpBuffer,
        __int64 nNumberOfBytesToWrite,
        struct Win32HandleRAII *a4)
{
  unsigned int v8; // edi
  HANDLE FileW; // r14
  signed int LastError; // eax
  char *v11; // rbx
  signed int v12; // eax
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  NumberOfBytesWritten = 0;
  if ( a4 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "CreateDataFile",
      L"In CreateDataFile, file Handle value (%p)",
      a4);
    FileW = CreateFileW(lpFileName, 0xC0010000, 0, 0, 2u, 0x8100080u, 0);
    if ( (unsigned __int64)(*(_QWORD *)a4 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)a4);
    *(_QWORD *)a4 = FileW;
    if ( WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
      {
        v8 = -2147467260;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "CreateDataFile",
          L"WriteFile failed: bytesWritten = %d byteCount = %d",
          NumberOfBytesWritten,
          nNumberOfBytesToWrite);
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "CreateDataFile",
        L"WriteFile failed: pFileHandle is %p, result = (hr: 0x%x)",
        a4,
        v8);
    }
    return v8;
  }
  v11 = (char *)CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x8100080u, 0);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
    && WriteFile(v11, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
      v8 = -2147467260;
LABEL_17:
    CloseHandle(v11);
    return v8;
  }
  v12 = GetLastError();
  v8 = v12;
  if ( v12 > 0 )
    v8 = (unsigned __int16)v12 | 0x80070000;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_17;
  return v8;
}

```

## disassembly

```asm
0x180010d40  mov     rax, rsp
0x180010d43  push    rsi
0x180010d44  push    rdi
0x180010d45  push    r14
0x180010d47  sub     rsp, 50h
0x180010d4b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180010d53  mov     [rax+8], rbx
0x180010d57  mov     [rax+10h], rbp
0x180010d5b  mov     rbx, r9
0x180010d5e  mov     rsi, r8
0x180010d61  mov     rbp, rdx
0x180010d64  mov     r14, rcx
0x180010d67  xor     edi, edi
0x180010d69  mov     [rax+20h], edi
0x180010d6c  test    r9, r9
0x180010d6f  jz      loc_180010E51
0x180010d75  mov     r8, rbx
0x180010d78  lea     rdx, aInCreatedatafi; "In CreateDataFile, file Handle value (%"...
0x180010d7f  lea     rcx, aCreatedatafile; "CreateDataFile"
0x180010d86  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180010d8b  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x180010d90  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180010d98  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180010da0  xor     r9d, r9d; lpSecurityAttributes
0x180010da3  xor     r8d, r8d; dwShareMode
0x180010da6  mov     edx, 0C0010000h; dwDesiredAccess
0x180010dab  mov     rcx, r14; lpFileName
0x180010dae  call    cs:__imp_CreateFileW
0x180010db4  mov     r14, rax
0x180010db7  mov     rcx, [rbx]; hObject
0x180010dba  lea     rax, [rcx-1]
0x180010dbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010dc2  ja      short loc_180010DCA
0x180010dc4  call    cs:__imp_CloseHandle
0x180010dca  mov     [rbx], r14
0x180010dcd  mov     r8d, esi; nNumberOfBytesToWrite
0x180010dd0  mov     qword ptr [rsp+68h+dwCreationDisposition], rdi; lpOverlapped
0x180010dd5  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180010ddd  mov     rdx, rbp; lpBuffer
0x180010de0  mov     rcx, r14; hFile
0x180010de3  call    cs:__imp_WriteFile
0x180010de9  test    eax, eax
0x180010deb  jz      short loc_180010E1E
0x180010ded  mov     r8d, [rsp+68h+NumberOfBytesWritten]
0x180010df5  cmp     r8, rsi
0x180010df8  jz      loc_180010EDE
0x180010dfe  mov     edi, 80004004h
0x180010e03  mov     r9, rsi
0x180010e06  lea     rdx, aWritefileFaile_1; "WriteFile failed: bytesWritten = %d byt"...
0x180010e0d  lea     rcx, aCreatedatafile; "CreateDataFile"
0x180010e14  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180010e19  jmp     loc_180010EDE
0x180010e1e  call    cs:__imp_GetLastError
0x180010e24  mov     edi, eax
0x180010e26  test    eax, eax
0x180010e28  jle     short loc_180010E33
0x180010e2a  movzx   edi, ax
0x180010e2d  or      edi, 80070000h
0x180010e33  mov     r9d, edi
0x180010e36  mov     r8, rbx
0x180010e39  lea     rdx, aWritefileFaile; "WriteFile failed: pFileHandle is %p, re"...
0x180010e40  lea     rcx, aCreatedatafile; "CreateDataFile"
0x180010e47  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180010e4c  jmp     loc_180010EDE
0x180010e51  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x180010e56  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180010e5e  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180010e66  xor     r9d, r9d; lpSecurityAttributes
0x180010e69  xor     r8d, r8d; dwShareMode
0x180010e6c  mov     edx, 40000000h; dwDesiredAccess
0x180010e71  call    cs:__imp_CreateFileW
0x180010e77  mov     rbx, rax
0x180010e7a  dec     rax
0x180010e7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010e81  ja      short loc_180010EB6
0x180010e83  mov     r8d, esi; nNumberOfBytesToWrite
0x180010e86  mov     qword ptr [rsp+68h+dwCreationDisposition], rdi; lpOverlapped
0x180010e8b  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180010e93  mov     rdx, rbp; lpBuffer
0x180010e96  mov     rcx, rbx; hFile
0x180010e99  call    cs:__imp_WriteFile
0x180010e9f  test    eax, eax
0x180010ea1  jz      short loc_180010EB6
0x180010ea3  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x180010eaa  cmp     rax, rsi
0x180010ead  jz      short loc_180010ED5
0x180010eaf  mov     edi, 80004004h
0x180010eb4  jmp     short loc_180010ED5
0x180010eb6  call    cs:__imp_GetLastError
0x180010ebc  mov     edi, eax
0x180010ebe  test    eax, eax
0x180010ec0  jle     short loc_180010ECB
0x180010ec2  movzx   edi, ax
0x180010ec5  or      edi, 80070000h
0x180010ecb  lea     rax, [rbx-1]
0x180010ecf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010ed3  ja      short loc_180010EDE
0x180010ed5  mov     rcx, rbx; hObject
0x180010ed8  call    cs:__imp_CloseHandle
0x180010ede  mov     eax, edi
0x180010ee0  mov     rbx, [rsp+68h+arg_0]
0x180010ee5  mov     rbp, [rsp+68h+arg_8]
0x180010eea  add     rsp, 50h
0x180010eee  pop     r14
0x180010ef0  pop     rdi
0x180010ef1  pop     rsi
0x180010ef2  retn
```
