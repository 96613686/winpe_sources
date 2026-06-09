# GpReadOnlyMemoryStream::InitFile(ushort const *)

- ea: `0x18000a934`
- end: `0x18000aa43`
- name: `?InitFile@GpReadOnlyMemoryStream@@QEAAJPEBG@Z`
- size: `271`
- prototype: `int(GpReadOnlyMemoryStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a86c`

## callees

- `0x1800056bc`
- `0x18000a934`
- `0x1800f05d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a980`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a980`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000a9a4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000a9a4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a9fe`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a9fe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000a9da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000a9da`

## pseudocode

```c
__int64 __fastcall GpReadOnlyMemoryStream::InitFile(GpReadOnlyMemoryStream *this, GpRuntime *a2)
{
  unsigned __int16 *v4; // rax
  HANDLE FileW; // rax
  DWORD FileSize; // edi
  HANDLE FileMappingA; // rax
  void *v8; // rsi
  LPVOID v9; // rbp
  __int64 result; // rax
  DWORD FileSizeHigh; // [rsp+70h] [rbp+8h] BYREF

  v4 = GpRuntime::UnicodeStringDuplicate(a2, (const unsigned __int16 *)a2);
  *((_QWORD *)this + 7) = v4;
  if ( !v4 )
    return 2147942414LL;
  FileW = CreateFileW((LPCWSTR)a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 6) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetWin32HRESULT();
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 )
    return GetWin32HRESULT();
  if ( FileSizeHigh )
    return GetWin32HRESULT();
  FileMappingA = CreateFileMappingA(*((HANDLE *)this + 6), 0, 2u, 0, 0, 0);
  v8 = FileMappingA;
  if ( !FileMappingA )
    return GetWin32HRESULT();
  v9 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
  CloseHandle(v8);
  if ( !v9 )
    return GetWin32HRESULT();
  *((_QWORD *)this + 3) = v9;
  result = 0;
  *((_DWORD *)this + 8) = FileSize;
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 10) = 4;
  return result;
}

```

## disassembly

```asm
0x18000a934  push    rbx
0x18000a936  push    rbp
0x18000a937  push    rsi
0x18000a938  push    rdi
0x18000a939  sub     rsp, 48h
0x18000a93d  mov     rbx, rcx
0x18000a940  mov     rdi, rdx
0x18000a943  mov     rcx, rdx; this
0x18000a946  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18000a94b  mov     [rbx+38h], rax
0x18000a94f  test    rax, rax
0x18000a952  jz      loc_18000AA3C
0x18000a958  xor     r9d, r9d; lpSecurityAttributes
0x18000a95b  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000a964  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a96c  mov     edx, 80000000h; dwDesiredAccess
0x18000a971  mov     rcx, rdi; lpFileName
0x18000a974  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a97c  lea     r8d, [r9+1]; dwShareMode
0x18000a980  call    cs:__imp_CreateFileW
0x18000a986  mov     [rbx+30h], rax
0x18000a98a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a98e  jz      loc_18000AA35
0x18000a994  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x18000a999  mov     [rsp+68h+FileSizeHigh], 0
0x18000a9a1  mov     rcx, rax; hFile
0x18000a9a4  call    cs:__imp_GetFileSize
0x18000a9aa  mov     edi, eax
0x18000a9ac  cmp     eax, 0FFFFFFFFh
0x18000a9af  jz      loc_18000AA35
0x18000a9b5  cmp     [rsp+68h+FileSizeHigh], 0
0x18000a9ba  jnz     short loc_18000AA35
0x18000a9bc  mov     rcx, [rbx+30h]; hFile
0x18000a9c0  xor     r9d, r9d; dwMaximumSizeHigh
0x18000a9c3  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18000a9cc  xor     edx, edx; lpFileMappingAttributes
0x18000a9ce  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000a9d6  lea     r8d, [r9+2]; flProtect
0x18000a9da  call    cs:__imp_CreateFileMappingA
0x18000a9e0  mov     rsi, rax
0x18000a9e3  test    rax, rax
0x18000a9e6  jz      short loc_18000AA35
0x18000a9e8  xor     r9d, r9d; dwFileOffsetLow
0x18000a9eb  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000a9f4  xor     r8d, r8d; dwFileOffsetHigh
0x18000a9f7  mov     rcx, rax; hFileMappingObject
0x18000a9fa  lea     edx, [r9+4]; dwDesiredAccess
0x18000a9fe  call    cs:__imp_MapViewOfFile
0x18000aa04  mov     rcx, rsi; hObject
0x18000aa07  mov     rbp, rax
0x18000aa0a  call    cs:__imp_CloseHandle
0x18000aa10  test    rbp, rbp
0x18000aa13  jz      short loc_18000AA35
0x18000aa15  mov     [rbx+18h], rbp
0x18000aa19  xor     eax, eax
0x18000aa1b  mov     [rbx+20h], edi
0x18000aa1e  mov     dword ptr [rbx+24h], 0
0x18000aa25  mov     dword ptr [rbx+28h], 4
0x18000aa2c  add     rsp, 48h
0x18000aa30  pop     rdi
0x18000aa31  pop     rsi
0x18000aa32  pop     rbp
0x18000aa33  pop     rbx
0x18000aa34  retn
0x18000aa35  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x18000aa3a  jmp     short loc_18000AA2C
0x18000aa3c  mov     eax, 8007000Eh
0x18000aa41  jmp     short loc_18000AA2C
```
