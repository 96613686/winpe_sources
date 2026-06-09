# CabUtils::VerifyCabIntegrity(void *)

- ea: `0x1800c2cc8`
- end: `0x1800c2e08`
- name: `?VerifyCabIntegrity@CabUtils@@SAJPEAX@Z`
- size: `320`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a9cd0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180041c44`
- `0x1800c2a20`
- `0x1800c2cc8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c2ce3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800c2ce3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2dde`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2de9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2dde`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800c2de9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c2d87`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800c2d87`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c2d5b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c2d5b`

## string_xrefs

- `0x1800c2cf2`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c2d15`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c2d9d`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`
- `0x1800c2dc5`: `onecore\base\flighting\flightsettings\broker\lib\cabutils.cpp`

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
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
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
                        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
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
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
                  v7);
LABEL_15:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
    return LastError;
  }
  LastError = -2147024674;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\cabutils.cpp",
    (const char *)0x800700DELL,
    dwMaximumSizeLow);
  return LastError;
}

```

## disassembly

```asm
0x1800c2cc8  mov     [rsp+arg_0], rbx
0x1800c2ccd  push    rdi
0x1800c2cce  sub     rsp, 30h
0x1800c2cd2  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x1800c2cd7  mov     qword ptr [rsp+38h+FileSize], 0
0x1800c2ce0  mov     rdi, rcx
0x1800c2ce3  call    cs:__imp_GetFileSizeEx
0x1800c2ce9  test    eax, eax
0x1800c2ceb  jnz     short loc_1800C2D06
0x1800c2ced  mov     rcx, [rsp+38h]; this
0x1800c2cf2  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2cf9  lea     edx, [rax+3Ch]; void *
0x1800c2cfc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c2d01  jmp     loc_1800C2DFD
0x1800c2d06  mov     rax, qword ptr [rsp+38h+FileSize]
0x1800c2d0b  test    rax, rax
0x1800c2d0e  jnz     short loc_1800C2D31
0x1800c2d10  mov     rcx, [rsp+38h]; this
0x1800c2d15  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2d1c  mov     ebx, 800700DEh
0x1800c2d21  lea     edx, [rax+40h]; void *
0x1800c2d24  mov     r9d, ebx; char *
0x1800c2d27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2d2c  jmp     loc_1800C2DFB
0x1800c2d31  cmp     dword ptr [rsp+38h+FileSize+4], 0
0x1800c2d36  mov     ebx, 68h ; 'h'
0x1800c2d3b  jnz     short loc_1800C2D42
0x1800c2d3d  cmp     eax, ebx
0x1800c2d3f  cmovb   ebx, eax
0x1800c2d42  xor     r9d, r9d; dwMaximumSizeHigh
0x1800c2d45  mov     [rsp+38h+lpName], 0; lpName
0x1800c2d4e  xor     edx, edx; lpFileMappingAttributes
0x1800c2d50  mov     [rsp+38h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800c2d54  mov     rcx, rdi; hFile
0x1800c2d57  lea     r8d, [r9+2]; flProtect
0x1800c2d5b  call    cs:__imp_CreateFileMappingW
0x1800c2d61  mov     [rsp+38h+arg_10], rax
0x1800c2d66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c2d6a  jnz     short loc_1800C2D71
0x1800c2d6c  lea     edx, [rax+51h]
0x1800c2d6f  jmp     short loc_1800C2D98
0x1800c2d71  xor     r9d, r9d; dwFileOffsetLow
0x1800c2d74  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; unsigned int
0x1800c2d7d  xor     r8d, r8d; dwFileOffsetHigh
0x1800c2d80  mov     rcx, rax; hFileMappingObject
0x1800c2d83  lea     edx, [r9+4]; dwDesiredAccess
0x1800c2d87  call    cs:__imp_MapViewOfFile
0x1800c2d8d  mov     rdi, rax
0x1800c2d90  test    rax, rax
0x1800c2d93  jnz     short loc_1800C2DAD
0x1800c2d95  lea     edx, [rax+5Ah]; void *
0x1800c2d98  mov     rcx, [rsp+38h]; this
0x1800c2d9d  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2da4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c2da9  mov     ebx, eax
0x1800c2dab  jmp     short loc_1800C2DF1
0x1800c2dad  mov     r8, qword ptr [rsp+38h+FileSize]; __int64
0x1800c2db2  mov     edx, ebx; unsigned int
0x1800c2db4  mov     rcx, rdi; unsigned __int8 *
0x1800c2db7  call    ?StrictReadHeader@CabUtils@@CAKQEAEK_J@Z; CabUtils::StrictReadHeader(uchar * const,ulong,__int64)
0x1800c2dbc  test    eax, eax
0x1800c2dbe  jz      short loc_1800C2DE6
0x1800c2dc0  mov     rcx, [rsp+38h]; this
0x1800c2dc5  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\flightsetting"...
0x1800c2dcc  mov     r9d, eax; char *
0x1800c2dcf  mov     edx, 62h ; 'b'; void *
0x1800c2dd4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c2dd9  mov     rcx, rdi; lpBaseAddress
0x1800c2ddc  mov     ebx, eax
0x1800c2dde  call    cs:__imp_UnmapViewOfFile
0x1800c2de4  jmp     short loc_1800C2DF1
0x1800c2de6  mov     rcx, rdi; lpBaseAddress
0x1800c2de9  call    cs:__imp_UnmapViewOfFile
0x1800c2def  xor     ebx, ebx
0x1800c2df1  lea     rcx, [rsp+38h+arg_10]
0x1800c2df6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c2dfb  mov     eax, ebx
0x1800c2dfd  mov     rbx, [rsp+38h+arg_0]
0x1800c2e02  add     rsp, 30h
0x1800c2e06  pop     rdi
0x1800c2e07  retn
```
