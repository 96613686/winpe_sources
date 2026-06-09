# CreateDataFile(ushort const *,uchar *,unsigned __int64,Win32HandleRAII *)

- ea: `0x180011350`
- end: `0x180011534`
- name: `?CreateDataFile@@YAJPEBGPEAE_KPEAVWin32HandleRAII@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, __int64 nNumberOfBytesToWrite, struct Win32HandleRAII *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180010abc`
- `0x1800189a4`

## callees

- `0x180011350`
- `0x180018f00`
- `0x180018f58`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1800113ff`
- `KERNEL32!WriteFile` at `0x1800114c7`
- `KERNEL32!WriteFile` at `0x1800113ff`
- `KERNEL32!WriteFile` at `0x1800114c7`
- `KERNEL32!CreateFileW` at `0x1800113be`
- `KERNEL32!CreateFileW` at `0x180011499`
- `KERNEL32!CreateFileW` at `0x1800113be`
- `KERNEL32!CreateFileW` at `0x180011499`
- `KERNEL32!CloseHandle` at `0x1800113da`
- `KERNEL32!CloseHandle` at `0x180011512`
- `KERNEL32!CloseHandle` at `0x1800113da`
- `KERNEL32!CloseHandle` at `0x180011512`
- `KERNEL32!GetLastError` at `0x180011440`
- `KERNEL32!GetLastError` at `0x1800114ea`
- `KERNEL32!GetLastError` at `0x180011440`
- `KERNEL32!GetLastError` at `0x1800114ea`

## string_xrefs

- `0x180011388`: `In CreateDataFile, file Handle value (%p)`
- `0x18001138f`: `CreateDataFile`
- `0x18001142f`: `CreateDataFile`
- `0x180011468`: `CreateDataFile`
- `0x180011461`: `WriteFile failed: pFileHandle is %p, result = (hr: 0x%x)`
- `0x180011428`: `WriteFile failed: bytesWritten = %d byteCount = %d`

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
0x180011350  mov     rax, rsp
0x180011353  push    rsi
0x180011354  push    rdi
0x180011355  push    r14
0x180011357  sub     rsp, 50h
0x18001135b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180011363  mov     [rax+8], rbx
0x180011367  mov     [rax+10h], rbp
0x18001136b  mov     rbx, r9
0x18001136e  mov     rsi, r8
0x180011371  mov     rbp, rdx
0x180011374  mov     r14, rcx
0x180011377  xor     edi, edi
0x180011379  mov     [rax+20h], edi
0x18001137c  test    r9, r9
0x18001137f  jz      loc_180011479
0x180011385  mov     r8, rbx
0x180011388  lea     rdx, aInCreatedatafi; "In CreateDataFile, file Handle value (%"...
0x18001138f  lea     rcx, aCreatedatafile; "CreateDataFile"
0x180011396  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001139b  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x1800113a0  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1800113a8  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1800113b0  xor     r9d, r9d; lpSecurityAttributes
0x1800113b3  xor     r8d, r8d; dwShareMode
0x1800113b6  mov     edx, 0C0010000h; dwDesiredAccess
0x1800113bb  mov     rcx, r14; lpFileName
0x1800113be  call    cs:__imp_CreateFileW
0x1800113c5  nop     dword ptr [rax+rax+00h]
0x1800113ca  mov     r14, rax
0x1800113cd  mov     rcx, [rbx]; hObject
0x1800113d0  lea     rax, [rcx-1]
0x1800113d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800113d8  ja      short loc_1800113E6
0x1800113da  call    cs:__imp_CloseHandle
0x1800113e1  nop     dword ptr [rax+rax+00h]
0x1800113e6  mov     [rbx], r14
0x1800113e9  mov     r8d, esi; nNumberOfBytesToWrite
0x1800113ec  mov     qword ptr [rsp+68h+dwCreationDisposition], rdi; lpOverlapped
0x1800113f1  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800113f9  mov     rdx, rbp; lpBuffer
0x1800113fc  mov     rcx, r14; hFile
0x1800113ff  call    cs:__imp_WriteFile
0x180011406  nop     dword ptr [rax+rax+00h]
0x18001140b  test    eax, eax
0x18001140d  jz      short loc_180011440
0x18001140f  mov     r8d, [rsp+68h+NumberOfBytesWritten]
0x180011417  cmp     r8, rsi
0x18001141a  jz      loc_18001151E
0x180011420  mov     edi, 80004004h
0x180011425  mov     r9, rsi
0x180011428  lea     rdx, aWritefileFaile_1; "WriteFile failed: bytesWritten = %d byt"...
0x18001142f  lea     rcx, aCreatedatafile; "CreateDataFile"
0x180011436  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001143b  jmp     loc_18001151E
0x180011440  call    cs:__imp_GetLastError
0x180011447  nop     dword ptr [rax+rax+00h]
0x18001144c  mov     edi, eax
0x18001144e  test    eax, eax
0x180011450  jle     short loc_18001145B
0x180011452  movzx   edi, ax
0x180011455  or      edi, 80070000h
0x18001145b  mov     r9d, edi
0x18001145e  mov     r8, rbx
0x180011461  lea     rdx, aWritefileFaile; "WriteFile failed: pFileHandle is %p, re"...
0x180011468  lea     rcx, aCreatedatafile; "CreateDataFile"
0x18001146f  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180011474  jmp     loc_18001151E
0x180011479  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x18001147e  mov     [rsp+68h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180011486  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18001148e  xor     r9d, r9d; lpSecurityAttributes
0x180011491  xor     r8d, r8d; dwShareMode
0x180011494  mov     edx, 40000000h; dwDesiredAccess
0x180011499  call    cs:__imp_CreateFileW
0x1800114a0  nop     dword ptr [rax+rax+00h]
0x1800114a5  mov     rbx, rax
0x1800114a8  dec     rax
0x1800114ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800114af  ja      short loc_1800114EA
0x1800114b1  mov     r8d, esi; nNumberOfBytesToWrite
0x1800114b4  mov     qword ptr [rsp+68h+dwCreationDisposition], rdi; lpOverlapped
0x1800114b9  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800114c1  mov     rdx, rbp; lpBuffer
0x1800114c4  mov     rcx, rbx; hFile
0x1800114c7  call    cs:__imp_WriteFile
0x1800114ce  nop     dword ptr [rax+rax+00h]
0x1800114d3  test    eax, eax
0x1800114d5  jz      short loc_1800114EA
0x1800114d7  mov     eax, [rsp+68h+NumberOfBytesWritten]
0x1800114de  cmp     rax, rsi
0x1800114e1  jz      short loc_18001150F
0x1800114e3  mov     edi, 80004004h
0x1800114e8  jmp     short loc_18001150F
0x1800114ea  call    cs:__imp_GetLastError
0x1800114f1  nop     dword ptr [rax+rax+00h]
0x1800114f6  mov     edi, eax
0x1800114f8  test    eax, eax
0x1800114fa  jle     short loc_180011505
0x1800114fc  movzx   edi, ax
0x1800114ff  or      edi, 80070000h
0x180011505  lea     rax, [rbx-1]
0x180011509  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001150d  ja      short loc_18001151E
0x18001150f  mov     rcx, rbx; hObject
0x180011512  call    cs:__imp_CloseHandle
0x180011519  nop     dword ptr [rax+rax+00h]
0x18001151e  mov     eax, edi
0x180011520  mov     rbx, [rsp+68h+arg_0]
0x180011525  mov     rbp, [rsp+68h+arg_8]
0x18001152a  add     rsp, 50h
0x18001152e  pop     r14
0x180011530  pop     rdi
0x180011531  pop     rsi
0x180011532  retn
```
