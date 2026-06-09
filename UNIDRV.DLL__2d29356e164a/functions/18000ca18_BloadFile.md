# BloadFile

- ea: `0x18000ca18`
- end: `0x18000cd83`
- name: `BloadFile`
- size: `875`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d1d8`
- `0x180047da0`

## callees

- `0x180007220`
- `0x18000aa88`
- `0x18000c700`
- `0x18000ca18`
- `0x18000cd90`
- `0x18003b9c8`
- `0x180074580`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000cb99`
- `KERNEL32!MapViewOfFile` at `0x18000cb99`
- `KERNEL32!GetFileTime` at `0x18000cca7`
- `KERNEL32!GetFileTime` at `0x18000cca7`
- `KERNEL32!CloseHandle` at `0x18000cba5`
- `KERNEL32!CloseHandle` at `0x18000cbb3`
- `KERNEL32!CloseHandle` at `0x18000ccf1`
- `KERNEL32!CloseHandle` at `0x18000cba5`
- `KERNEL32!CloseHandle` at `0x18000cbb3`
- `KERNEL32!CloseHandle` at `0x18000ccf1`
- `KERNEL32!CreateFileW` at `0x18000cb1f`
- `KERNEL32!CreateFileW` at `0x18000cb1f`
- `KERNEL32!LocalAlloc` at `0x18000cc01`
- `KERNEL32!LocalAlloc` at `0x18000cc01`
- `KERNEL32!UnmapViewOfFile` at `0x18000cce2`
- `KERNEL32!UnmapViewOfFile` at `0x18000cce2`
- `KERNEL32!GetFileSize` at `0x18000cb4b`
- `KERNEL32!GetFileSize` at `0x18000cb4b`
- `KERNEL32!CreateFileMappingW` at `0x18000cb75`
- `KERNEL32!CreateFileMappingW` at `0x18000cb75`

## string_xrefs

- `0x18000cd41`: `unable to open GPD file: %S`

## pseudocode

```c
__int64 __fastcall BloadFile(STRSAFE_LPCWSTR pszSrc, __int64 a2)
{
  unsigned int v2; // eax
  __int64 v5; // rbx
  struct _FILETIME *v6; // r13
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // ebp
  __int64 v10; // r15
  __int64 FileW; // rdi
  DWORD *v12; // r15
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  void *v15; // r15
  const void *v16; // rbp
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  const void *v23; // rcx
  unsigned int v24; // ebx
  __int64 v25; // rdi
  __int64 result; // rax
  __int64 v27; // r11
  unsigned int v28; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a2 + 464);
  v28 = 0;
  if ( *(_DWORD *)(a2 + 468) >= v2 )
  {
    if ( *(int *)(a2 + 2220) < 2 )
    {
      *(_DWORD *)(a2 + 2220) = 2;
      *(_DWORD *)(a2 + 2224) = 2;
      *(_DWORD *)(a2 + 2216) = 19;
    }
    return 0;
  }
  v5 = *(_QWORD *)(a2 + 240);
  if ( !(unsigned int)BallocElementFromMasterTable(10, &v28, a2) )
    return 0;
  v6 = (struct _FILETIME *)(v5 + 16LL * v28);
  *(_DWORD *)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 16) = dwStoreFileName(pszSrc);
  v7 = *(_QWORD *)(a2 + 456);
  v8 = 32LL * *(unsigned int *)(a2 + 468);
  if ( *(_DWORD *)(v8 + v7 + 16) == -1 )
    return 0;
  *(_DWORD *)(v8 + v7 + 20) = 1;
  v9 = *(_DWORD *)(a2 + 468);
  v10 = *(_QWORD *)(a2 + 456);
  FileW = (__int64)CreateFileW(pszSrc, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  if ( FileW == -1 )
    goto LABEL_12;
  v12 = (DWORD *)(32LL * v9 + v10 + 12);
  if ( v12 && (FileSize = GetFileSize((HANDLE)FileW, 0), *v12 = FileSize, FileSize == -1)
    || (FileMappingW = CreateFileMappingW((HANDLE)FileW, 0, 2u, 0, 0, 0), (v15 = FileMappingW) == 0)
    || (v16 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v15), !v16) )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
LABEL_12:
    v16 = 0;
  }
  *(_QWORD *)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 24) = v16;
  v17 = *(_QWORD *)(a2 + 456);
  v18 = 32LL * *(unsigned int *)(a2 + 468);
  if ( !*(_QWORD *)(v18 + v17 + 24) || !v16 )
  {
    WriteDbgTraceErrorGpd("BloadFile", "unable to open GPD file: %S", pszSrc);
    *(_DWORD *)(a2 + 2220) = 3;
    *(_DWORD *)(a2 + 2224) = 3;
    return 0;
  }
  *(_QWORD *)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456)) = LocalAlloc(
                                                                              0,
                                                                              *(unsigned int *)(v18 + v17 + 12));
  v19 = *(_QWORD *)(a2 + 456);
  v20 = 32LL * *(unsigned int *)(a2 + 468);
  if ( !*(_QWORD *)(v20 + v19) )
  {
    WriteDbgTraceErrorGpd(
      "BloadFile",
      "Fatal: unable to alloc requested memory: %d bytes.",
      *(_DWORD *)(v20 + v19 + 12));
    v21 = *(_QWORD *)(a2 + 456);
    v22 = 32LL * *(unsigned int *)(a2 + 468);
    *(_DWORD *)(a2 + 2224) = 2;
    *(_DWORD *)(a2 + 2220) = 3;
    *(_DWORD *)(a2 + 2216) = 19;
    UnmapFileFromMemory(*(_QWORD *)(v22 + v21 + 24), FileW);
    return 0;
  }
  memcpy_0(*(void **)(v20 + v19), v16, *(unsigned int *)(v20 + v19 + 12));
  if ( !GetFileTime((HANDLE)FileW, 0, 0, v6 + 1) )
    WriteDbgTraceErrorGpd("BloadFile", "GetFileTime '%S' failed.", pszSrc);
  v23 = *(const void **)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 24);
  if ( v23 )
    UnmapViewOfFile(v23);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  v24 = *(_DWORD *)(a2 + 468);
  v25 = 32LL * v24;
  *(_DWORD *)(a2 + 736) = ComputeCrc32Checksum(
                            *(_QWORD *)(v25 + *(_QWORD *)(a2 + 456)),
                            *(unsigned int *)(v25 + *(_QWORD *)(a2 + 456) + 12),
                            *(unsigned int *)(a2 + 736));
  *(_DWORD *)(a2 + 468) = v24 + 1;
  result = 1;
  *(_DWORD *)(v25 + v27 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ca18  mov     [rsp+arg_0], rbx
0x18000ca1d  mov     [rsp+arg_10], rbp
0x18000ca22  push    rsi
0x18000ca23  push    rdi
0x18000ca24  push    r13
0x18000ca26  push    r14
0x18000ca28  push    r15
0x18000ca2a  sub     rsp, 40h
0x18000ca2e  mov     eax, [rdx+1D0h]
0x18000ca34  mov     rsi, rdx
0x18000ca37  mov     r14, rcx
0x18000ca3a  mov     [rsp+68h+arg_8], 0
0x18000ca42  cmp     [rdx+1D4h], eax
0x18000ca48  jb      short loc_18000CA76
0x18000ca4a  mov     ebx, 2
0x18000ca4f  cmp     [rdx+8ACh], ebx
0x18000ca55  jge     loc_18000CD68
0x18000ca5b  mov     [rdx+8ACh], ebx
0x18000ca61  mov     [rdx+8B0h], ebx
0x18000ca67  mov     dword ptr [rdx+8A8h], 13h
0x18000ca71  jmp     loc_18000CD68
0x18000ca76  mov     rbx, [rdx+0F0h]
0x18000ca7d  mov     r8, rsi
0x18000ca80  lea     rdx, [rsp+68h+arg_8]
0x18000ca85  mov     ecx, 0Ah
0x18000ca8a  call    BallocElementFromMasterTable
0x18000ca8f  test    eax, eax
0x18000ca91  jz      loc_18000CD68
0x18000ca97  mov     r13d, [rsp+68h+arg_8]
0x18000ca9c  mov     r8, rsi
0x18000ca9f  shl     r13, 4
0x18000caa3  mov     rcx, r14; pszSrc
0x18000caa6  add     r13, rbx
0x18000caa9  mov     rdx, r13
0x18000caac  call    dwStoreFileName
0x18000cab1  mov     edx, [rsi+1D4h]
0x18000cab7  mov     rcx, [rsi+1C8h]
0x18000cabe  shl     rdx, 5
0x18000cac2  mov     [rdx+rcx+10h], eax
0x18000cac6  mov     eax, [rsi+1D4h]
0x18000cacc  mov     rcx, [rsi+1C8h]
0x18000cad3  shl     rax, 5
0x18000cad7  cmp     dword ptr [rax+rcx+10h], 0FFFFFFFFh
0x18000cadc  jz      loc_18000CD68
0x18000cae2  mov     edx, 1
0x18000cae7  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000caf0  mov     [rax+rcx+14h], edx
0x18000caf4  mov     r8d, edx; dwShareMode
0x18000caf7  mov     ebp, [rsi+1D4h]
0x18000cafd  mov     edx, 80000000h; dwDesiredAccess
0x18000cb02  mov     r15, [rsi+1C8h]
0x18000cb09  mov     rcx, r14; lpFileName
0x18000cb0c  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18000cb14  xor     r9d, r9d; lpSecurityAttributes
0x18000cb17  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000cb1f  call    cs:__imp_CreateFileW
0x18000cb25  mov     rdi, rax
0x18000cb28  mov     ebx, 2
0x18000cb2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cb31  jz      loc_18000CBBD
0x18000cb37  mov     eax, ebp
0x18000cb39  add     r15, 0Ch
0x18000cb3d  shl     rax, 5
0x18000cb41  add     r15, rax
0x18000cb44  jz      short loc_18000CB59
0x18000cb46  xor     edx, edx; lpFileSizeHigh
0x18000cb48  mov     rcx, rdi; hFile
0x18000cb4b  call    cs:__imp_GetFileSize
0x18000cb51  mov     [r15], eax
0x18000cb54  cmp     eax, 0FFFFFFFFh
0x18000cb57  jz      short loc_18000CBB0
0x18000cb59  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18000cb62  xor     r9d, r9d; dwMaximumSizeHigh
0x18000cb65  mov     r8d, ebx; flProtect
0x18000cb68  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000cb70  xor     edx, edx; lpFileMappingAttributes
0x18000cb72  mov     rcx, rdi; hFile
0x18000cb75  call    cs:__imp_CreateFileMappingW
0x18000cb7b  mov     r15, rax
0x18000cb7e  test    rax, rax
0x18000cb81  jz      short loc_18000CBB0
0x18000cb83  xor     r9d, r9d; dwFileOffsetLow
0x18000cb86  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000cb8f  xor     r8d, r8d; dwFileOffsetHigh
0x18000cb92  mov     rcx, rax; hFileMappingObject
0x18000cb95  lea     edx, [r9+4]; dwDesiredAccess
0x18000cb99  call    cs:__imp_MapViewOfFile
0x18000cb9f  mov     rcx, r15; hObject
0x18000cba2  mov     rbp, rax
0x18000cba5  call    cs:__imp_CloseHandle
0x18000cbab  test    rbp, rbp
0x18000cbae  jnz     short loc_18000CBBF
0x18000cbb0  mov     rcx, rdi; hObject
0x18000cbb3  call    cs:__imp_CloseHandle
0x18000cbb9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000cbbd  xor     ebp, ebp
0x18000cbbf  mov     ecx, [rsi+1D4h]
0x18000cbc5  mov     rax, [rsi+1C8h]
0x18000cbcc  shl     rcx, 5
0x18000cbd0  mov     [rcx+rax+18h], rbp
0x18000cbd5  mov     eax, [rsi+1D4h]
0x18000cbdb  mov     rcx, [rsi+1C8h]
0x18000cbe2  shl     rax, 5
0x18000cbe6  cmp     qword ptr [rax+rcx+18h], 0
0x18000cbec  jz      loc_18000CD3E
0x18000cbf2  test    rbp, rbp
0x18000cbf5  jz      loc_18000CD3E
0x18000cbfb  mov     edx, [rax+rcx+0Ch]; uBytes
0x18000cbff  xor     ecx, ecx; uFlags
0x18000cc01  call    cs:__imp_LocalAlloc
0x18000cc07  mov     edx, [rsi+1D4h]
0x18000cc0d  mov     rcx, [rsi+1C8h]
0x18000cc14  shl     rdx, 5
0x18000cc18  mov     [rdx+rcx], rax
0x18000cc1c  mov     rax, [rsi+1C8h]
0x18000cc23  mov     ecx, [rsi+1D4h]
0x18000cc29  shl     rcx, 5
0x18000cc2d  mov     r9, [rcx+rax]
0x18000cc31  mov     edx, [rcx+rax+0Ch]
0x18000cc35  test    r9, r9
0x18000cc38  jnz     short loc_18000CC8D
0x18000cc3a  mov     r8d, edx
0x18000cc3d  lea     rcx, aBloadfile; "BloadFile"
0x18000cc44  lea     rdx, aFatalUnableToA; "Fatal: unable to alloc requested memory"...
0x18000cc4b  call    WriteDbgTraceErrorGpd
0x18000cc50  mov     eax, [rsi+1D4h]
0x18000cc56  mov     rdx, rdi
0x18000cc59  mov     rcx, [rsi+1C8h]
0x18000cc60  shl     rax, 5
0x18000cc64  mov     [rsi+8B0h], ebx
0x18000cc6a  mov     dword ptr [rsi+8ACh], 3
0x18000cc74  mov     dword ptr [rsi+8A8h], 13h
0x18000cc7e  mov     rcx, [rax+rcx+18h]
0x18000cc83  call    UnmapFileFromMemory
0x18000cc88  jmp     loc_18000CD68
0x18000cc8d  mov     r8, rdx; Size
0x18000cc90  mov     rcx, r9; void *
0x18000cc93  mov     rdx, rbp; Src
0x18000cc96  call    memcpy_0
0x18000cc9b  lea     r9, [r13+8]; lpLastWriteTime
0x18000cc9f  xor     r8d, r8d; lpLastAccessTime
0x18000cca2  xor     edx, edx; lpCreationTime
0x18000cca4  mov     rcx, rdi; hFile
0x18000cca7  call    cs:__imp_GetFileTime
0x18000ccad  test    eax, eax
0x18000ccaf  jnz     short loc_18000CCC7
0x18000ccb1  mov     r8, r14
0x18000ccb4  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x18000ccbb  lea     rcx, aBloadfile; "BloadFile"
0x18000ccc2  call    WriteDbgTraceErrorGpd
0x18000ccc7  mov     ecx, [rsi+1D4h]
0x18000cccd  mov     rax, [rsi+1C8h]
0x18000ccd4  shl     rcx, 5
0x18000ccd8  mov     rcx, [rcx+rax+18h]; lpBaseAddress
0x18000ccdd  test    rcx, rcx
0x18000cce0  jz      short loc_18000CCE8
0x18000cce2  call    cs:__imp_UnmapViewOfFile
0x18000cce8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ccec  jz      short loc_18000CCF7
0x18000ccee  mov     rcx, rdi; hObject
0x18000ccf1  call    cs:__imp_CloseHandle
0x18000ccf7  mov     r11, [rsi+1C8h]
0x18000ccfe  mov     ebx, [rsi+1D4h]
0x18000cd04  mov     r8d, [rsi+2E0h]
0x18000cd0b  mov     edi, ebx
0x18000cd0d  shl     rdi, 5
0x18000cd11  mov     edx, [rdi+r11+0Ch]
0x18000cd16  mov     rcx, [rdi+r11]
0x18000cd1a  call    ComputeCrc32Checksum
0x18000cd1f  mov     [rsi+2E0h], eax
0x18000cd25  lea     ecx, [rbx+1]
0x18000cd28  mov     [rsi+1D4h], ecx
0x18000cd2e  mov     eax, 1
0x18000cd33  mov     dword ptr [rdi+r11+8], 0
0x18000cd3c  jmp     short loc_18000CD6A
0x18000cd3e  mov     r8, r14
0x18000cd41  lea     rdx, aUnableToOpenGp; "unable to open GPD file: %S"
0x18000cd48  lea     rcx, aBloadfile; "BloadFile"
0x18000cd4f  call    WriteDbgTraceErrorGpd
0x18000cd54  mov     dword ptr [rsi+8ACh], 3
0x18000cd5e  mov     dword ptr [rsi+8B0h], 3
0x18000cd68  xor     eax, eax
0x18000cd6a  lea     r11, [rsp+68h+var_28]
0x18000cd6f  mov     rbx, [r11+30h]
0x18000cd73  mov     rbp, [r11+40h]
0x18000cd77  mov     rsp, r11
0x18000cd7a  pop     r15
0x18000cd7c  pop     r14
0x18000cd7e  pop     r13
0x18000cd80  pop     rdi
0x18000cd81  pop     rsi
0x18000cd82  retn
```
