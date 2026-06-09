# GpdLoadCachedBinaryData

- ea: `0x18016e680`
- end: `0x18016e878`
- name: `GpdLoadCachedBinaryData`
- size: `504`
- prototype: `_OWORD *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18016e3a8`

## callees

- `0x180150854`
- `0x18016c80c`
- `0x18016c854`
- `0x18016c970`
- `0x18016cb30`
- `0x18016e680`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18016e717`
- `KERNEL32!CreateFileMappingW` at `0x18016e717`
- `KERNEL32!MapViewOfFile` at `0x18016e745`
- `KERNEL32!MapViewOfFile` at `0x18016e745`
- `KERNEL32!GetFileSize` at `0x18016e6e2`
- `KERNEL32!GetFileSize` at `0x18016e6e2`
- `KERNEL32!CreateFileW` at `0x18016e6c4`
- `KERNEL32!CreateFileW` at `0x18016e6c4`
- `KERNEL32!CloseHandle` at `0x18016e757`
- `KERNEL32!CloseHandle` at `0x18016e84f`
- `KERNEL32!CloseHandle` at `0x18016e757`
- `KERNEL32!CloseHandle` at `0x18016e84f`
- `KERNEL32!SetLastError` at `0x18016e833`
- `KERNEL32!SetLastError` at `0x18016e833`
- `KERNEL32!LocalFree` at `0x18016e805`
- `KERNEL32!LocalFree` at `0x18016e85e`
- `KERNEL32!LocalFree` at `0x18016e805`
- `KERNEL32!LocalFree` at `0x18016e85e`
- `KERNEL32!LocalAlloc` at `0x18016e7a8`
- `KERNEL32!LocalAlloc` at `0x18016e7a8`

## string_xrefs

- `0x18016e81b`: `Invalid BUD data. Will attempt to reload GPD file`
- `0x18016e822`: `GpdLoadCachedBinaryData`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  _OWORD *v9; // rdi
  _OWORD *v10; // rax
  BOOL v11; // r14d

  GPDfilename = pwstrGenerateGPDfilename(a1);
  v2 = GPDfilename;
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
    && (unsigned int)BIsRawBinaryDataInDate((unsigned int *)v8, v2)
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
    v11 = BInitBUDPointers((__int64)v10) != 0;
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
0x18016e680  push    rbx
0x18016e682  push    rbp
0x18016e683  push    rsi
0x18016e684  push    rdi
0x18016e685  push    r14
0x18016e687  sub     rsp, 40h
0x18016e68b  call    pwstrGenerateGPDfilename
0x18016e690  mov     rbp, rax
0x18016e693  test    rax, rax
0x18016e696  jz      loc_18016E86A
0x18016e69c  xor     r9d, r9d; lpSecurityAttributes
0x18016e69f  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18016e6a8  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18016e6b0  mov     edx, 80000000h; dwDesiredAccess
0x18016e6b5  mov     rcx, rax; lpFileName
0x18016e6b8  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18016e6c0  lea     r8d, [r9+1]; dwShareMode
0x18016e6c4  call    cs:__imp_CreateFileW
0x18016e6cb  nop     dword ptr [rax+rax+00h]
0x18016e6d0  mov     rsi, rax
0x18016e6d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016e6d7  jz      loc_18016E85B
0x18016e6dd  xor     edx, edx; lpFileSizeHigh
0x18016e6df  mov     rcx, rax; hFile
0x18016e6e2  call    cs:__imp_GetFileSize
0x18016e6e9  nop     dword ptr [rax+rax+00h]
0x18016e6ee  mov     r14d, eax
0x18016e6f1  cmp     eax, 0FFFFFFFFh
0x18016e6f4  jz      loc_18016E84C
0x18016e6fa  xor     r9d, r9d; dwMaximumSizeHigh
0x18016e6fd  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18016e706  xor     edx, edx; lpFileMappingAttributes
0x18016e708  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18016e710  mov     rcx, rsi; hFile
0x18016e713  lea     r8d, [r9+2]; flProtect
0x18016e717  call    cs:__imp_CreateFileMappingW
0x18016e71e  nop     dword ptr [rax+rax+00h]
0x18016e723  mov     rdi, rax
0x18016e726  test    rax, rax
0x18016e729  jz      loc_18016E84C
0x18016e72f  xor     r9d, r9d; dwFileOffsetLow
0x18016e732  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18016e73b  xor     r8d, r8d; dwFileOffsetHigh
0x18016e73e  mov     rcx, rax; hFileMappingObject
0x18016e741  lea     edx, [r9+4]; dwDesiredAccess
0x18016e745  call    cs:__imp_MapViewOfFile
0x18016e74c  nop     dword ptr [rax+rax+00h]
0x18016e751  mov     rcx, rdi; hObject
0x18016e754  mov     rbx, rax
0x18016e757  call    cs:__imp_CloseHandle
0x18016e75e  nop     dword ptr [rax+rax+00h]
0x18016e763  test    rbx, rbx
0x18016e766  jz      loc_18016E84C
0x18016e76c  xor     edi, edi
0x18016e76e  cmp     r14d, 0E0h
0x18016e775  jbe     loc_18016E7FF
0x18016e77b  cmp     r14d, [rbx]
0x18016e77e  jb      short loc_18016E7FF
0x18016e780  cmp     dword ptr [rbx+8], 1A0073h
0x18016e787  jnz     short loc_18016E7FF
0x18016e789  cmp     dword ptr [rbx+4], 47504420h
0x18016e790  jnz     short loc_18016E7FF
0x18016e792  mov     rdx, rbp
0x18016e795  mov     rcx, rbx
0x18016e798  call    BIsRawBinaryDataInDate
0x18016e79d  test    eax, eax
0x18016e79f  jz      short loc_18016E7FF
0x18016e7a1  mov     edx, 0F8h; uBytes
0x18016e7a6  xor     ecx, ecx; uFlags
0x18016e7a8  call    cs:__imp_LocalAlloc
0x18016e7af  nop     dword ptr [rax+rax+00h]
0x18016e7b4  mov     rdi, rax
0x18016e7b7  test    rax, rax
0x18016e7ba  jz      short loc_18016E7FF
0x18016e7bc  movups  xmm0, xmmword ptr [rbx]
0x18016e7bf  mov     rcx, rax
0x18016e7c2  movups  xmmword ptr [rax], xmm0
0x18016e7c5  movups  xmm1, xmmword ptr [rbx+10h]
0x18016e7c9  movups  xmmword ptr [rax+10h], xmm1
0x18016e7cd  movups  xmm0, xmmword ptr [rbx+20h]
0x18016e7d1  movups  xmmword ptr [rax+20h], xmm0
0x18016e7d5  movsd   xmm1, qword ptr [rbx+30h]
0x18016e7da  movsd   qword ptr [rax+30h], xmm1
0x18016e7df  mov     [rax+38h], rbx
0x18016e7e3  mov     [rax+40h], rsi
0x18016e7e7  mov     [rax+48h], rbx
0x18016e7eb  mov     [rax+50h], r14d
0x18016e7ef  call    BInitBUDPointers
0x18016e7f4  neg     eax
0x18016e7f6  sbb     r14d, r14d
0x18016e7f9  and     r14d, 1
0x18016e7fd  jmp     short loc_18016E802
0x18016e7ff  xor     r14d, r14d
0x18016e802  mov     rcx, rbp; hMem
0x18016e805  call    cs:__imp_LocalFree
0x18016e80c  nop     dword ptr [rax+rax+00h]
0x18016e811  test    r14d, r14d
0x18016e814  jz      short loc_18016E81B
0x18016e816  mov     rax, rdi
0x18016e819  jmp     short loc_18016E86C
0x18016e81b  lea     rdx, aInvalidBudData; "Invalid BUD data. Will attempt to reloa"...
0x18016e822  lea     rcx, aGpdloadcachedb; "GpdLoadCachedBinaryData"
0x18016e829  call    WriteDbgTraceWarningGpd
0x18016e82e  mov     ecx, 0Dh; dwErrCode
0x18016e833  call    cs:__imp_SetLastError
0x18016e83a  nop     dword ptr [rax+rax+00h]
0x18016e83f  mov     rdx, rsi
0x18016e842  mov     rcx, rbx
0x18016e845  call    UnmapFileFromMemory
0x18016e84a  jmp     short loc_18016E86A
0x18016e84c  mov     rcx, rsi; hObject
0x18016e84f  call    cs:__imp_CloseHandle
0x18016e856  nop     dword ptr [rax+rax+00h]
0x18016e85b  mov     rcx, rbp; hMem
0x18016e85e  call    cs:__imp_LocalFree
0x18016e865  nop     dword ptr [rax+rax+00h]
0x18016e86a  xor     eax, eax
0x18016e86c  add     rsp, 40h
0x18016e870  pop     r14
0x18016e872  pop     rdi
0x18016e873  pop     rsi
0x18016e874  pop     rbp
0x18016e875  pop     rbx
0x18016e876  retn
```
