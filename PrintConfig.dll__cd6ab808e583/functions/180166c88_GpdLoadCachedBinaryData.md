# GpdLoadCachedBinaryData

- ea: `0x180166c88`
- end: `0x180166e3f`
- name: `GpdLoadCachedBinaryData`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180166a80`

## callees

- `0x180149ae8`
- `0x180164f58`
- `0x180164fa0`
- `0x1801650ac`
- `0x18016526c`
- `0x180166c88`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x180166d13`
- `KERNEL32!CreateFileMappingW` at `0x180166d13`
- `KERNEL32!MapViewOfFile` at `0x180166d3b`
- `KERNEL32!MapViewOfFile` at `0x180166d3b`
- `KERNEL32!GetFileSize` at `0x180166ce4`
- `KERNEL32!GetFileSize` at `0x180166ce4`
- `KERNEL32!CreateFileW` at `0x180166ccc`
- `KERNEL32!CreateFileW` at `0x180166ccc`
- `KERNEL32!CloseHandle` at `0x180166d47`
- `KERNEL32!CloseHandle` at `0x180166e23`
- `KERNEL32!CloseHandle` at `0x180166d47`
- `KERNEL32!CloseHandle` at `0x180166e23`
- `KERNEL32!SetLastError` at `0x180166e0d`
- `KERNEL32!SetLastError` at `0x180166e0d`
- `KERNEL32!LocalFree` at `0x180166de5`
- `KERNEL32!LocalFree` at `0x180166e2c`
- `KERNEL32!LocalFree` at `0x180166de5`
- `KERNEL32!LocalFree` at `0x180166e2c`
- `KERNEL32!LocalAlloc` at `0x180166d8e`
- `KERNEL32!LocalAlloc` at `0x180166d8e`

## string_xrefs

- `0x180166df5`: `Invalid BUD data. Will attempt to reload GPD file`
- `0x180166dfc`: `GpdLoadCachedBinaryData`

## pseudocode

```c
_OWORD *__fastcall GpdLoadCachedBinaryData(const wchar_t *a1)
{
  const WCHAR *GPDfilename; // rax
  WCHAR *v2; // rbp
  HANDLE FileW; // rax
  void *v4; // rsi
  DWORD FileSize; // r14d
  HANDLE FileMappingW; // rax
  void *v7; // rdi
  _OWORD *v8; // rbx
  _OWORD *v9; // rdi
  _OWORD *v10; // rax
  BOOL v11; // r14d

  GPDfilename = (const WCHAR *)pwstrGenerateGPDfilename(a1);
  v2 = (WCHAR *)GPDfilename;
  if ( !GPDfilename )
    return 0;
  FileW = CreateFileW(GPDfilename, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_18;
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize == -1
    || (FileMappingW = CreateFileMappingW(v4, 0, 2u, 0, 0, 0), (v7 = FileMappingW) == 0)
    || (v8 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v7), !v8) )
  {
    CloseHandle(v4);
LABEL_18:
    LocalFree(v2);
    return 0;
  }
  v9 = 0;
  if ( FileSize > 0xE0
    && FileSize >= *(_DWORD *)v8
    && *((_DWORD *)v8 + 2) == 1704051
    && *((_DWORD *)v8 + 1) == 1196442656
    && (unsigned int)BIsRawBinaryDataInDate(v8, v2)
    && (v10 = LocalAlloc(0, 0xF8u), (v9 = v10) != 0) )
  {
    *v10 = *v8;
    v10[1] = v8[1];
    v10[2] = v8[2];
    *((_QWORD *)v10 + 6) = *((_QWORD *)v8 + 6);
    *((_QWORD *)v10 + 7) = v8;
    *((_QWORD *)v10 + 8) = v4;
    *((_QWORD *)v10 + 9) = v8;
    *((_DWORD *)v10 + 20) = FileSize;
    v11 = BInitBUDPointers(v10) != 0;
  }
  else
  {
    v11 = 0;
  }
  LocalFree(v2);
  if ( v11 )
    return v9;
  WriteDbgTraceWarningGpd("GpdLoadCachedBinaryData", "Invalid BUD data. Will attempt to reload GPD file");
  SetLastError(0xDu);
  UnmapFileFromMemory(v8, v4);
  return 0;
}

```

## disassembly

```asm
0x180166c88  push    rbx
0x180166c8a  push    rbp
0x180166c8b  push    rsi
0x180166c8c  push    rdi
0x180166c8d  push    r14
0x180166c8f  sub     rsp, 40h
0x180166c93  call    pwstrGenerateGPDfilename
0x180166c98  mov     rbp, rax
0x180166c9b  test    rax, rax
0x180166c9e  jz      loc_180166E32
0x180166ca4  xor     r9d, r9d; lpSecurityAttributes
0x180166ca7  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180166cb0  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180166cb8  mov     edx, 80000000h; dwDesiredAccess
0x180166cbd  mov     rcx, rax; lpFileName
0x180166cc0  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180166cc8  lea     r8d, [r9+1]; dwShareMode
0x180166ccc  call    cs:__imp_CreateFileW
0x180166cd2  mov     rsi, rax
0x180166cd5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180166cd9  jz      loc_180166E29
0x180166cdf  xor     edx, edx; lpFileSizeHigh
0x180166ce1  mov     rcx, rax; hFile
0x180166ce4  call    cs:__imp_GetFileSize
0x180166cea  mov     r14d, eax
0x180166ced  cmp     eax, 0FFFFFFFFh
0x180166cf0  jz      loc_180166E20
0x180166cf6  xor     r9d, r9d; dwMaximumSizeHigh
0x180166cf9  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x180166d02  xor     edx, edx; lpFileMappingAttributes
0x180166d04  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180166d0c  mov     rcx, rsi; hFile
0x180166d0f  lea     r8d, [r9+2]; flProtect
0x180166d13  call    cs:__imp_CreateFileMappingW
0x180166d19  mov     rdi, rax
0x180166d1c  test    rax, rax
0x180166d1f  jz      loc_180166E20
0x180166d25  xor     r9d, r9d; dwFileOffsetLow
0x180166d28  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180166d31  xor     r8d, r8d; dwFileOffsetHigh
0x180166d34  mov     rcx, rax; hFileMappingObject
0x180166d37  lea     edx, [r9+4]; dwDesiredAccess
0x180166d3b  call    cs:__imp_MapViewOfFile
0x180166d41  mov     rcx, rdi; hObject
0x180166d44  mov     rbx, rax
0x180166d47  call    cs:__imp_CloseHandle
0x180166d4d  test    rbx, rbx
0x180166d50  jz      loc_180166E20
0x180166d56  xor     edi, edi
0x180166d58  cmp     r14d, 0E0h
0x180166d5f  jbe     short loc_180166DDF
0x180166d61  cmp     r14d, [rbx]
0x180166d64  jb      short loc_180166DDF
0x180166d66  cmp     dword ptr [rbx+8], 1A0073h
0x180166d6d  jnz     short loc_180166DDF
0x180166d6f  cmp     dword ptr [rbx+4], 47504420h
0x180166d76  jnz     short loc_180166DDF
0x180166d78  mov     rdx, rbp
0x180166d7b  mov     rcx, rbx
0x180166d7e  call    BIsRawBinaryDataInDate
0x180166d83  test    eax, eax
0x180166d85  jz      short loc_180166DDF
0x180166d87  mov     edx, 0F8h; uBytes
0x180166d8c  xor     ecx, ecx; uFlags
0x180166d8e  call    cs:__imp_LocalAlloc
0x180166d94  mov     rdi, rax
0x180166d97  test    rax, rax
0x180166d9a  jz      short loc_180166DDF
0x180166d9c  movups  xmm0, xmmword ptr [rbx]
0x180166d9f  mov     rcx, rax
0x180166da2  movups  xmmword ptr [rax], xmm0
0x180166da5  movups  xmm1, xmmword ptr [rbx+10h]
0x180166da9  movups  xmmword ptr [rax+10h], xmm1
0x180166dad  movups  xmm0, xmmword ptr [rbx+20h]
0x180166db1  movups  xmmword ptr [rax+20h], xmm0
0x180166db5  movsd   xmm1, qword ptr [rbx+30h]
0x180166dba  movsd   qword ptr [rax+30h], xmm1
0x180166dbf  mov     [rax+38h], rbx
0x180166dc3  mov     [rax+40h], rsi
0x180166dc7  mov     [rax+48h], rbx
0x180166dcb  mov     [rax+50h], r14d
0x180166dcf  call    BInitBUDPointers
0x180166dd4  neg     eax
0x180166dd6  sbb     r14d, r14d
0x180166dd9  and     r14d, 1
0x180166ddd  jmp     short loc_180166DE2
0x180166ddf  xor     r14d, r14d
0x180166de2  mov     rcx, rbp; hMem
0x180166de5  call    cs:__imp_LocalFree
0x180166deb  test    r14d, r14d
0x180166dee  jz      short loc_180166DF5
0x180166df0  mov     rax, rdi
0x180166df3  jmp     short loc_180166E34
0x180166df5  lea     rdx, aInvalidBudData; "Invalid BUD data. Will attempt to reloa"...
0x180166dfc  lea     rcx, aGpdloadcachedb; "GpdLoadCachedBinaryData"
0x180166e03  call    WriteDbgTraceWarningGpd
0x180166e08  mov     ecx, 0Dh; dwErrCode
0x180166e0d  call    cs:__imp_SetLastError
0x180166e13  mov     rdx, rsi
0x180166e16  mov     rcx, rbx
0x180166e19  call    UnmapFileFromMemory
0x180166e1e  jmp     short loc_180166E32
0x180166e20  mov     rcx, rsi; hObject
0x180166e23  call    cs:__imp_CloseHandle
0x180166e29  mov     rcx, rbp; hMem
0x180166e2c  call    cs:__imp_LocalFree
0x180166e32  xor     eax, eax
0x180166e34  add     rsp, 40h
0x180166e38  pop     r14
0x180166e3a  pop     rdi
0x180166e3b  pop     rsi
0x180166e3c  pop     rbp
0x180166e3d  pop     rbx
0x180166e3e  retn
```
