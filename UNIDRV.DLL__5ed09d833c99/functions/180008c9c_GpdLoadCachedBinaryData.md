# GpdLoadCachedBinaryData

- ea: `0x180008c9c`
- end: `0x180008ea1`
- name: `GpdLoadCachedBinaryData`
- size: `517`
- prototype: `_OWORD *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800278e0`

## callees

- `0x1800084f0`
- `0x18000881c`
- `0x180008c9c`
- `0x18003e45c`
- `0x180046748`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180008d59`
- `KERNEL32!MapViewOfFile` at `0x180008d59`
- `KERNEL32!CloseHandle` at `0x180008d6b`
- `KERNEL32!CloseHandle` at `0x180008d7f`
- `KERNEL32!CloseHandle` at `0x180008e13`
- `KERNEL32!CloseHandle` at `0x180008d6b`
- `KERNEL32!CloseHandle` at `0x180008d7f`
- `KERNEL32!CloseHandle` at `0x180008e13`
- `KERNEL32!CreateFileW` at `0x180008ce0`
- `KERNEL32!CreateFileW` at `0x180008ce0`
- `KERNEL32!LocalFree` at `0x180008d8e`
- `KERNEL32!LocalFree` at `0x180008dc7`
- `KERNEL32!LocalFree` at `0x180008d8e`
- `KERNEL32!LocalFree` at `0x180008dc7`
- `KERNEL32!LocalAlloc` at `0x180008e43`
- `KERNEL32!LocalAlloc` at `0x180008e43`
- `KERNEL32!SetLastError` at `0x180008df5`
- `KERNEL32!SetLastError` at `0x180008df5`
- `KERNEL32!UnmapViewOfFile` at `0x180008e04`
- `KERNEL32!UnmapViewOfFile` at `0x180008e04`
- `KERNEL32!GetFileSize` at `0x180008cfe`
- `KERNEL32!GetFileSize` at `0x180008cfe`
- `KERNEL32!CreateFileMappingW` at `0x180008d2f`
- `KERNEL32!CreateFileMappingW` at `0x180008d2f`

## string_xrefs

- `0x180008de4`: `GpdLoadCachedBinaryData`
- `0x180008ddd`: `Invalid BUD data. Will attempt to reload GPD file`

## pseudocode

```c
_OWORD *__fastcall GpdLoadCachedBinaryData(const wchar_t *a1)
{
  wchar_t *GPDfilename; // rax
  wchar_t *v2; // rbp
  HANDLE FileW; // rax
  void *v4; // rsi
  DWORD FileSize; // r14d
  HANDLE FileMappingW; // rax
  void *v7; // rdi
  _OWORD *v8; // rbx
  _OWORD *v10; // rdi
  BOOL v11; // r14d
  _OWORD *v12; // rax

  GPDfilename = pwstrGenerateGPDfilename(a1);
  v2 = GPDfilename;
  if ( !GPDfilename )
    return 0;
  FileW = CreateFileW(GPDfilename, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_7;
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize == -1
    || (FileMappingW = CreateFileMappingW(v4, 0, 2u, 0, 0, 0), (v7 = FileMappingW) == 0)
    || (v8 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v7), !v8) )
  {
    CloseHandle(v4);
LABEL_7:
    LocalFree(v2);
    return 0;
  }
  v10 = 0;
  if ( FileSize > 0xE0
    && FileSize >= *(_DWORD *)v8
    && *((_DWORD *)v8 + 2) == 1704051
    && *((_DWORD *)v8 + 1) == 1196442656
    && (unsigned int)BIsRawBinaryDataInDate((unsigned int *)v8, v2)
    && (v12 = LocalAlloc(0, 0xF8u), (v10 = v12) != 0) )
  {
    *v12 = *v8;
    v12[1] = v8[1];
    v12[2] = v8[2];
    *((_QWORD *)v12 + 6) = *((_QWORD *)v8 + 6);
    *((_QWORD *)v12 + 7) = v8;
    *((_QWORD *)v12 + 8) = v4;
    *((_QWORD *)v12 + 9) = v8;
    *((_DWORD *)v12 + 20) = FileSize;
    v11 = BInitBUDPointers((__int64)v12) != 0;
  }
  else
  {
    v11 = 0;
  }
  LocalFree(v2);
  if ( !v11 )
  {
    WriteDbgTraceWarningGpd((__int64)"GpdLoadCachedBinaryData", "Invalid BUD data. Will attempt to reload GPD file");
    SetLastError(0xDu);
    UnmapViewOfFile(v8);
    CloseHandle(v4);
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180008c9c  push    rbx
0x180008c9e  push    rbp
0x180008c9f  push    rsi
0x180008ca0  push    rdi
0x180008ca1  push    r14
0x180008ca3  sub     rsp, 40h
0x180008ca7  call    pwstrGenerateGPDfilename
0x180008cac  mov     rbp, rax
0x180008caf  test    rax, rax
0x180008cb2  jz      loc_180008D9A
0x180008cb8  xor     r9d, r9d; lpSecurityAttributes
0x180008cbb  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180008cc4  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180008ccc  mov     edx, 80000000h; dwDesiredAccess
0x180008cd1  mov     rcx, rax; lpFileName
0x180008cd4  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180008cdc  lea     r8d, [r9+1]; dwShareMode
0x180008ce0  call    cs:__imp_CreateFileW
0x180008ce7  nop     dword ptr [rax+rax+00h]
0x180008cec  mov     rsi, rax
0x180008cef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008cf3  jz      loc_180008D8B
0x180008cf9  xor     edx, edx; lpFileSizeHigh
0x180008cfb  mov     rcx, rax; hFile
0x180008cfe  call    cs:__imp_GetFileSize
0x180008d05  nop     dword ptr [rax+rax+00h]
0x180008d0a  mov     r14d, eax
0x180008d0d  cmp     eax, 0FFFFFFFFh
0x180008d10  jz      short loc_180008D7C
0x180008d12  xor     r9d, r9d; dwMaximumSizeHigh
0x180008d15  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x180008d1e  xor     edx, edx; lpFileMappingAttributes
0x180008d20  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180008d28  mov     rcx, rsi; hFile
0x180008d2b  lea     r8d, [r9+2]; flProtect
0x180008d2f  call    cs:__imp_CreateFileMappingW
0x180008d36  nop     dword ptr [rax+rax+00h]
0x180008d3b  mov     rdi, rax
0x180008d3e  test    rax, rax
0x180008d41  jz      short loc_180008D7C
0x180008d43  xor     r9d, r9d; dwFileOffsetLow
0x180008d46  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180008d4f  xor     r8d, r8d; dwFileOffsetHigh
0x180008d52  mov     rcx, rax; hFileMappingObject
0x180008d55  lea     edx, [r9+4]; dwDesiredAccess
0x180008d59  call    cs:__imp_MapViewOfFile
0x180008d60  nop     dword ptr [rax+rax+00h]
0x180008d65  mov     rcx, rdi; hObject
0x180008d68  mov     rbx, rax
0x180008d6b  call    cs:__imp_CloseHandle
0x180008d72  nop     dword ptr [rax+rax+00h]
0x180008d77  test    rbx, rbx
0x180008d7a  jnz     short loc_180008DA8
0x180008d7c  mov     rcx, rsi; hObject
0x180008d7f  call    cs:__imp_CloseHandle
0x180008d86  nop     dword ptr [rax+rax+00h]
0x180008d8b  mov     rcx, rbp; hMem
0x180008d8e  call    cs:__imp_LocalFree
0x180008d95  nop     dword ptr [rax+rax+00h]
0x180008d9a  xor     eax, eax
0x180008d9c  add     rsp, 40h
0x180008da0  pop     r14
0x180008da2  pop     rdi
0x180008da3  pop     rsi
0x180008da4  pop     rbp
0x180008da5  pop     rbx
0x180008da6  retn
0x180008da8  xor     edi, edi
0x180008daa  cmp     r14d, 0E0h
0x180008db1  jbe     short loc_180008DC1
0x180008db3  cmp     r14d, [rbx]
0x180008db6  jb      short loc_180008DC1
0x180008db8  cmp     dword ptr [rbx+8], 1A0073h
0x180008dbf  jz      short loc_180008E24
0x180008dc1  xor     r14d, r14d
0x180008dc4  mov     rcx, rbp; hMem
0x180008dc7  call    cs:__imp_LocalFree
0x180008dce  nop     dword ptr [rax+rax+00h]
0x180008dd3  test    r14d, r14d
0x180008dd6  jz      short loc_180008DDD
0x180008dd8  mov     rax, rdi
0x180008ddb  jmp     short loc_180008D9C
0x180008ddd  lea     rdx, aInvalidBudData; "Invalid BUD data. Will attempt to reloa"...
0x180008de4  lea     rcx, aGpdloadcachedb; "GpdLoadCachedBinaryData"
0x180008deb  call    WriteDbgTraceWarningGpd
0x180008df0  mov     ecx, 0Dh; dwErrCode
0x180008df5  call    cs:__imp_SetLastError
0x180008dfc  nop     dword ptr [rax+rax+00h]
0x180008e01  mov     rcx, rbx; lpBaseAddress
0x180008e04  call    cs:__imp_UnmapViewOfFile
0x180008e0b  nop     dword ptr [rax+rax+00h]
0x180008e10  mov     rcx, rsi; hObject
0x180008e13  call    cs:__imp_CloseHandle
0x180008e1a  nop     dword ptr [rax+rax+00h]
0x180008e1f  jmp     loc_180008D9A
0x180008e24  cmp     dword ptr [rbx+4], 47504420h
0x180008e2b  jnz     short loc_180008DC1
0x180008e2d  mov     rdx, rbp
0x180008e30  mov     rcx, rbx
0x180008e33  call    BIsRawBinaryDataInDate
0x180008e38  test    eax, eax
0x180008e3a  jz      short loc_180008DC1
0x180008e3c  mov     edx, 0F8h; uBytes
0x180008e41  xor     ecx, ecx; uFlags
0x180008e43  call    cs:__imp_LocalAlloc
0x180008e4a  nop     dword ptr [rax+rax+00h]
0x180008e4f  mov     rdi, rax
0x180008e52  test    rax, rax
0x180008e55  jz      loc_180008DC1
0x180008e5b  movups  xmm0, xmmword ptr [rbx]
0x180008e5e  mov     rcx, rax
0x180008e61  movups  xmmword ptr [rax], xmm0
0x180008e64  movups  xmm1, xmmword ptr [rbx+10h]
0x180008e68  movups  xmmword ptr [rax+10h], xmm1
0x180008e6c  movups  xmm0, xmmword ptr [rbx+20h]
0x180008e70  movups  xmmword ptr [rax+20h], xmm0
0x180008e74  movsd   xmm1, qword ptr [rbx+30h]
0x180008e79  movsd   qword ptr [rax+30h], xmm1
0x180008e7e  mov     [rax+38h], rbx
0x180008e82  mov     [rax+40h], rsi
0x180008e86  mov     [rax+48h], rbx
0x180008e8a  mov     [rax+50h], r14d
0x180008e8e  call    BInitBUDPointers
0x180008e93  neg     eax
0x180008e95  sbb     r14d, r14d
0x180008e98  and     r14d, 1
0x180008e9c  jmp     loc_180008DC4
```
