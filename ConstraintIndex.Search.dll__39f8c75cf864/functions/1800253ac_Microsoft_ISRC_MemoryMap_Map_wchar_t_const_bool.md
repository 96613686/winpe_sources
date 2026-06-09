# Microsoft::ISRC::MemoryMap::Map(wchar_t const *,bool)

- ea: `0x1800253ac`
- end: `0x1800254de`
- name: `?Map@MemoryMap@ISRC@Microsoft@@QEAAXPEB_W_N@Z`
- size: `306`
- prototype: `void(Microsoft::ISRC::MemoryMap *__hidden this, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005d5ec`

## callees

- `0x1800049e0`
- `0x180005e50`
- `0x18000a5c8`
- `0x1800253ac`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800254c1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800254c1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025479`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025479`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800253ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800253ef`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025431`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025431`

## string_xrefs

- `0x180025488`: `Cannot create file mapping`

## pseudocode

```c
void __fastcall Microsoft::ISRC::MemoryMap::Map(Microsoft::ISRC::MemoryMap *this, const wchar_t *a2)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  unsigned __int64 v5; // rdx
  HANDLE FileMappingW; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-38h] BYREF
  DWORD FileSizeHigh; // [rsp+58h] [rbp-20h] BYREF

  FileW = CreateFileW(a2, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  *(_QWORD *)this = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    std::exception::exception((std::exception *)pExceptionObject, "File not found");
    throw (std::exception *)pExceptionObject;
  }
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  v5 = (unsigned __int64)FileSizeHigh << 32;
  *((_QWORD *)this + 3) = FileSize + v5;
  if ( FileSize + v5 )
  {
    FileMappingW = CreateFileMappingW(*(HANDLE *)this, 0, 2u, 0, 0, 0);
    *((_QWORD *)this + 1) = FileMappingW;
    if ( !FileMappingW )
    {
      std::exception::exception((std::exception *)pExceptionObject, "Cannot create file mapping");
      throw (std::exception *)pExceptionObject;
    }
    *((_QWORD *)this + 2) = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  }
  else
  {
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800253ac  push    rbx
0x1800253ae  sub     rsp, 70h
0x1800253b2  mov     rax, cs:__security_cookie
0x1800253b9  xor     rax, rsp
0x1800253bc  mov     [rsp+78h+var_18], rax
0x1800253c1  mov     rax, rdx
0x1800253c4  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800253cd  xor     r9d, r9d; lpSecurityAttributes
0x1800253d0  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800253d8  mov     rbx, rcx
0x1800253db  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800253e3  mov     edx, 80000000h; dwDesiredAccess
0x1800253e8  mov     rcx, rax; lpFileName
0x1800253eb  lea     r8d, [r9+5]; dwShareMode
0x1800253ef  call    cs:__imp_CreateFileW
0x1800253f5  mov     [rbx], rax
0x1800253f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800253fc  jnz     short loc_180025421
0x1800253fe  lea     rdx, aFileNotFound; "File not found"
0x180025405  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18002540a  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18002540f  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180025416  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18002541b  call    _CxxThrowException_0
0x180025421  lea     rdx, [rsp+78h+FileSizeHigh]; lpFileSizeHigh
0x180025426  mov     [rsp+78h+FileSizeHigh], 0
0x18002542e  mov     rcx, rax; hFile
0x180025431  call    cs:__imp_GetFileSize
0x180025437  mov     edx, [rsp+78h+FileSizeHigh]
0x18002543b  shl     rdx, 20h
0x18002543f  mov     eax, eax
0x180025441  add     rdx, rax
0x180025444  mov     [rbx+18h], rdx
0x180025448  jnz     short loc_18002545C
0x18002544a  mov     qword ptr [rbx+8], 0
0x180025452  mov     qword ptr [rbx+10h], 0
0x18002545a  jmp     short loc_1800254CB
0x18002545c  mov     rcx, [rbx]; hFile
0x18002545f  xor     r9d, r9d; dwMaximumSizeHigh
0x180025462  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x18002546b  xor     edx, edx; lpFileMappingAttributes
0x18002546d  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180025475  lea     r8d, [r9+2]; flProtect
0x180025479  call    cs:__imp_CreateFileMappingW
0x18002547f  mov     [rbx+8], rax
0x180025483  test    rax, rax
0x180025486  jnz     short loc_1800254AB
0x180025488  lea     rdx, aCannotCreateFi; "Cannot create file mapping"
0x18002548f  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180025494  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180025499  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x1800254a0  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800254a5  call    _CxxThrowException_0
0x1800254ab  xor     r9d, r9d; dwFileOffsetLow
0x1800254ae  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800254b7  xor     r8d, r8d; dwFileOffsetHigh
0x1800254ba  mov     rcx, rax; hFileMappingObject
0x1800254bd  lea     edx, [r9+4]; dwDesiredAccess
0x1800254c1  call    cs:__imp_MapViewOfFile
0x1800254c7  mov     [rbx+10h], rax
0x1800254cb  mov     rcx, [rsp+78h+var_18]
0x1800254d0  xor     rcx, rsp; StackCookie
0x1800254d3  call    __security_check_cookie
0x1800254d8  add     rsp, 70h
0x1800254dc  pop     rbx
0x1800254dd  retn
```
