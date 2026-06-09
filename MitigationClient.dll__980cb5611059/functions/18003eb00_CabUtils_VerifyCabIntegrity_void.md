# CabUtils::VerifyCabIntegrity(void *)

- ea: `0x18003eb00`
- end: `0x18003ec40`
- name: `?VerifyCabIntegrity@CabUtils@@SAJPEAX@Z`
- size: `320`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ccf0`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18001fb04`
- `0x18003e85c`
- `0x18003eb00`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003eb1b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003eb1b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003eb93`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003eb93`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ec16`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ec21`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ec16`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18003ec21`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003ebbf`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003ebbf`

## string_xrefs

- `0x18003eb2a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003eb4d`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003ebd5`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003ebfd`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
__int64 __fastcall CabUtils::VerifyCabIntegrity(HANDLE hFile)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  DWORD LowPart; // ebx
  HANDLE FileMappingW; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rdi
  unsigned int Header; // eax
  int dwMaximumSizeLow; // [rsp+20h] [rbp-18h]
  unsigned int dwMaximumSizeLowa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v16; // [rsp+50h] [rbp+18h] BYREF

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(hFile, &FileSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x3C,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
             v2);
  if ( FileSize.QuadPart )
  {
    LowPart = 104;
    if ( FileSize.QuadPart < 0x68uLL )
      LowPart = FileSize.LowPart;
    FileMappingW = CreateFileMappingW(hFile, 0, 2u, 0, LowPart, 0);
    v16 = FileMappingW;
    if ( FileMappingW == (HANDLE)-1LL )
    {
      v8 = 80;
    }
    else
    {
      v9 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v10 = v9;
      if ( v9 )
      {
        Header = CabUtils::StrictReadHeader(v9, LowPart, FileSize.QuadPart);
        if ( Header )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x62,
                        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                        (const char *)Header,
                        dwMaximumSizeLowa);
          UnmapViewOfFile(v10);
        }
        else
        {
          UnmapViewOfFile(v10);
          LastError = 0;
        }
        goto LABEL_15;
      }
      v8 = 90;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                  v7);
LABEL_15:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
    return LastError;
  }
  LastError = -2147024674;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
    (const char *)0x800700DELL,
    dwMaximumSizeLow);
  return LastError;
}

```

## disassembly

```asm
0x18003eb00  mov     [rsp+arg_0], rbx
0x18003eb05  push    rdi
0x18003eb06  sub     rsp, 30h
0x18003eb0a  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x18003eb0f  mov     qword ptr [rsp+38h+FileSize], 0
0x18003eb18  mov     rdi, rcx
0x18003eb1b  call    cs:__imp_GetFileSizeEx
0x18003eb21  test    eax, eax
0x18003eb23  jnz     short loc_18003EB3E
0x18003eb25  mov     rcx, [rsp+38h]; this
0x18003eb2a  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003eb31  lea     edx, [rax+3Ch]; void *
0x18003eb34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003eb39  jmp     loc_18003EC35
0x18003eb3e  mov     rax, qword ptr [rsp+38h+FileSize]
0x18003eb43  test    rax, rax
0x18003eb46  jnz     short loc_18003EB69
0x18003eb48  mov     rcx, [rsp+38h]; this
0x18003eb4d  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003eb54  mov     ebx, 800700DEh
0x18003eb59  lea     edx, [rax+40h]; void *
0x18003eb5c  mov     r9d, ebx; char *
0x18003eb5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb64  jmp     loc_18003EC33
0x18003eb69  cmp     dword ptr [rsp+38h+FileSize+4], 0
0x18003eb6e  mov     ebx, 68h ; 'h'
0x18003eb73  jnz     short loc_18003EB7A
0x18003eb75  cmp     eax, ebx
0x18003eb77  cmovb   ebx, eax
0x18003eb7a  xor     r9d, r9d; dwMaximumSizeHigh
0x18003eb7d  mov     [rsp+38h+lpName], 0; lpName
0x18003eb86  xor     edx, edx; lpFileMappingAttributes
0x18003eb88  mov     [rsp+38h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18003eb8c  mov     rcx, rdi; hFile
0x18003eb8f  lea     r8d, [r9+2]; flProtect
0x18003eb93  call    cs:__imp_CreateFileMappingW
0x18003eb99  mov     [rsp+38h+arg_10], rax
0x18003eb9e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003eba2  jnz     short loc_18003EBA9
0x18003eba4  lea     edx, [rax+51h]
0x18003eba7  jmp     short loc_18003EBD0
0x18003eba9  xor     r9d, r9d; dwFileOffsetLow
0x18003ebac  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; unsigned int
0x18003ebb5  xor     r8d, r8d; dwFileOffsetHigh
0x18003ebb8  mov     rcx, rax; hFileMappingObject
0x18003ebbb  lea     edx, [r9+4]; dwDesiredAccess
0x18003ebbf  call    cs:__imp_MapViewOfFile
0x18003ebc5  mov     rdi, rax
0x18003ebc8  test    rax, rax
0x18003ebcb  jnz     short loc_18003EBE5
0x18003ebcd  lea     edx, [rax+5Ah]; void *
0x18003ebd0  mov     rcx, [rsp+38h]; this
0x18003ebd5  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ebdc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ebe1  mov     ebx, eax
0x18003ebe3  jmp     short loc_18003EC29
0x18003ebe5  mov     r8, qword ptr [rsp+38h+FileSize]; __int64
0x18003ebea  mov     edx, ebx; unsigned int
0x18003ebec  mov     rcx, rdi; unsigned __int8 *
0x18003ebef  call    ?StrictReadHeader@CabUtils@@CAKQEAEK_J@Z; CabUtils::StrictReadHeader(uchar * const,ulong,__int64)
0x18003ebf4  test    eax, eax
0x18003ebf6  jz      short loc_18003EC1E
0x18003ebf8  mov     rcx, [rsp+38h]; this
0x18003ebfd  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ec04  mov     r9d, eax; char *
0x18003ec07  mov     edx, 62h ; 'b'; void *
0x18003ec0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ec11  mov     rcx, rdi; lpBaseAddress
0x18003ec14  mov     ebx, eax
0x18003ec16  call    cs:__imp_UnmapViewOfFile
0x18003ec1c  jmp     short loc_18003EC29
0x18003ec1e  mov     rcx, rdi; lpBaseAddress
0x18003ec21  call    cs:__imp_UnmapViewOfFile
0x18003ec27  xor     ebx, ebx
0x18003ec29  lea     rcx, [rsp+38h+arg_10]
0x18003ec2e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003ec33  mov     eax, ebx
0x18003ec35  mov     rbx, [rsp+38h+arg_0]
0x18003ec3a  add     rsp, 30h
0x18003ec3e  pop     rdi
0x18003ec3f  retn
```
