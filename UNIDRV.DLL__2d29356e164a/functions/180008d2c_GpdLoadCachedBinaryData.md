# GpdLoadCachedBinaryData

- ea: `0x180008d2c`
- end: `0x180008edd`
- name: `GpdLoadCachedBinaryData`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800271d4`

## callees

- `0x1800085b0`
- `0x1800088ac`
- `0x180008d2c`
- `0x18003d66c`
- `0x1800453c8`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180008dd3`
- `KERNEL32!MapViewOfFile` at `0x180008dd3`
- `KERNEL32!CloseHandle` at `0x180008ddf`
- `KERNEL32!CloseHandle` at `0x180008ded`
- `KERNEL32!CloseHandle` at `0x180008e62`
- `KERNEL32!CloseHandle` at `0x180008ddf`
- `KERNEL32!CloseHandle` at `0x180008ded`
- `KERNEL32!CloseHandle` at `0x180008e62`
- `KERNEL32!CreateFileW` at `0x180008d70`
- `KERNEL32!CreateFileW` at `0x180008d70`
- `KERNEL32!LocalFree` at `0x180008df6`
- `KERNEL32!LocalFree` at `0x180008e28`
- `KERNEL32!LocalFree` at `0x180008df6`
- `KERNEL32!LocalFree` at `0x180008e28`
- `KERNEL32!LocalAlloc` at `0x180008e89`
- `KERNEL32!LocalAlloc` at `0x180008e89`
- `KERNEL32!SetLastError` at `0x180008e50`
- `KERNEL32!SetLastError` at `0x180008e50`
- `KERNEL32!UnmapViewOfFile` at `0x180008e59`
- `KERNEL32!UnmapViewOfFile` at `0x180008e59`
- `KERNEL32!GetFileSize` at `0x180008d84`
- `KERNEL32!GetFileSize` at `0x180008d84`
- `KERNEL32!CreateFileMappingW` at `0x180008daf`
- `KERNEL32!CreateFileMappingW` at `0x180008daf`

## string_xrefs

- `0x180008e3f`: `GpdLoadCachedBinaryData`
- `0x180008e38`: `Invalid BUD data. Will attempt to reload GPD file`

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
  _OWORD *v10; // rdi
  BOOL v11; // r14d
  _OWORD *v12; // rax

  GPDfilename = (const WCHAR *)pwstrGenerateGPDfilename(a1);
  v2 = (WCHAR *)GPDfilename;
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
    && (unsigned int)BIsRawBinaryDataInDate(v8, v2)
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
    v11 = BInitBUDPointers(v12) != 0;
  }
  else
  {
    v11 = 0;
  }
  LocalFree(v2);
  if ( !v11 )
  {
    WriteDbgTraceWarningGpd("GpdLoadCachedBinaryData", "Invalid BUD data. Will attempt to reload GPD file");
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
0x180008d2c  push    rbx
0x180008d2e  push    rbp
0x180008d2f  push    rsi
0x180008d30  push    rdi
0x180008d31  push    r14
0x180008d33  sub     rsp, 40h
0x180008d37  call    pwstrGenerateGPDfilename
0x180008d3c  mov     rbp, rax
0x180008d3f  test    rax, rax
0x180008d42  jz      loc_180008DFC
0x180008d48  xor     r9d, r9d; lpSecurityAttributes
0x180008d4b  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180008d54  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180008d5c  mov     edx, 80000000h; dwDesiredAccess
0x180008d61  mov     rcx, rax; lpFileName
0x180008d64  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180008d6c  lea     r8d, [r9+1]; dwShareMode
0x180008d70  call    cs:__imp_CreateFileW
0x180008d76  mov     rsi, rax
0x180008d79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d7d  jz      short loc_180008DF3
0x180008d7f  xor     edx, edx; lpFileSizeHigh
0x180008d81  mov     rcx, rax; hFile
0x180008d84  call    cs:__imp_GetFileSize
0x180008d8a  mov     r14d, eax
0x180008d8d  cmp     eax, 0FFFFFFFFh
0x180008d90  jz      short loc_180008DEA
0x180008d92  xor     r9d, r9d; dwMaximumSizeHigh
0x180008d95  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x180008d9e  xor     edx, edx; lpFileMappingAttributes
0x180008da0  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180008da8  mov     rcx, rsi; hFile
0x180008dab  lea     r8d, [r9+2]; flProtect
0x180008daf  call    cs:__imp_CreateFileMappingW
0x180008db5  mov     rdi, rax
0x180008db8  test    rax, rax
0x180008dbb  jz      short loc_180008DEA
0x180008dbd  xor     r9d, r9d; dwFileOffsetLow
0x180008dc0  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180008dc9  xor     r8d, r8d; dwFileOffsetHigh
0x180008dcc  mov     rcx, rax; hFileMappingObject
0x180008dcf  lea     edx, [r9+4]; dwDesiredAccess
0x180008dd3  call    cs:__imp_MapViewOfFile
0x180008dd9  mov     rcx, rdi; hObject
0x180008ddc  mov     rbx, rax
0x180008ddf  call    cs:__imp_CloseHandle
0x180008de5  test    rbx, rbx
0x180008de8  jnz     short loc_180008E09
0x180008dea  mov     rcx, rsi; hObject
0x180008ded  call    cs:__imp_CloseHandle
0x180008df3  mov     rcx, rbp; hMem
0x180008df6  call    cs:__imp_LocalFree
0x180008dfc  xor     eax, eax
0x180008dfe  add     rsp, 40h
0x180008e02  pop     r14
0x180008e04  pop     rdi
0x180008e05  pop     rsi
0x180008e06  pop     rbp
0x180008e07  pop     rbx
0x180008e08  retn
0x180008e09  xor     edi, edi
0x180008e0b  cmp     r14d, 0E0h
0x180008e12  jbe     short loc_180008E22
0x180008e14  cmp     r14d, [rbx]
0x180008e17  jb      short loc_180008E22
0x180008e19  cmp     dword ptr [rbx+8], 1A0073h
0x180008e20  jz      short loc_180008E6A
0x180008e22  xor     r14d, r14d
0x180008e25  mov     rcx, rbp; hMem
0x180008e28  call    cs:__imp_LocalFree
0x180008e2e  test    r14d, r14d
0x180008e31  jz      short loc_180008E38
0x180008e33  mov     rax, rdi
0x180008e36  jmp     short loc_180008DFE
0x180008e38  lea     rdx, aInvalidBudData; "Invalid BUD data. Will attempt to reloa"...
0x180008e3f  lea     rcx, aGpdloadcachedb; "GpdLoadCachedBinaryData"
0x180008e46  call    WriteDbgTraceWarningGpd
0x180008e4b  mov     ecx, 0Dh; dwErrCode
0x180008e50  call    cs:__imp_SetLastError
0x180008e56  mov     rcx, rbx; lpBaseAddress
0x180008e59  call    cs:__imp_UnmapViewOfFile
0x180008e5f  mov     rcx, rsi; hObject
0x180008e62  call    cs:__imp_CloseHandle
0x180008e68  jmp     short loc_180008DFC
0x180008e6a  cmp     dword ptr [rbx+4], 47504420h
0x180008e71  jnz     short loc_180008E22
0x180008e73  mov     rdx, rbp
0x180008e76  mov     rcx, rbx
0x180008e79  call    BIsRawBinaryDataInDate
0x180008e7e  test    eax, eax
0x180008e80  jz      short loc_180008E22
0x180008e82  mov     edx, 0F8h; uBytes
0x180008e87  xor     ecx, ecx; uFlags
0x180008e89  call    cs:__imp_LocalAlloc
0x180008e8f  mov     rdi, rax
0x180008e92  test    rax, rax
0x180008e95  jz      short loc_180008E22
0x180008e97  movups  xmm0, xmmword ptr [rbx]
0x180008e9a  mov     rcx, rax
0x180008e9d  movups  xmmword ptr [rax], xmm0
0x180008ea0  movups  xmm1, xmmword ptr [rbx+10h]
0x180008ea4  movups  xmmword ptr [rax+10h], xmm1
0x180008ea8  movups  xmm0, xmmword ptr [rbx+20h]
0x180008eac  movups  xmmword ptr [rax+20h], xmm0
0x180008eb0  movsd   xmm1, qword ptr [rbx+30h]
0x180008eb5  movsd   qword ptr [rax+30h], xmm1
0x180008eba  mov     [rax+38h], rbx
0x180008ebe  mov     [rax+40h], rsi
0x180008ec2  mov     [rax+48h], rbx
0x180008ec6  mov     [rax+50h], r14d
0x180008eca  call    BInitBUDPointers
0x180008ecf  neg     eax
0x180008ed1  sbb     r14d, r14d
0x180008ed4  and     r14d, 1
0x180008ed8  jmp     loc_180008E25
```
