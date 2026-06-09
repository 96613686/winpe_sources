# BloadFile

- ea: `0x18000ca1c`
- end: `0x18000cdc4`
- name: `BloadFile`
- size: `936`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d218`
- `0x180049248`

## callees

- `0x180007150`
- `0x18000aa88`
- `0x18000c6f8`
- `0x18000ca1c`
- `0x18000cdd0`
- `0x18003c748`
- `0x180076660`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18000cbaf`
- `KERNEL32!MapViewOfFile` at `0x18000cbaf`
- `KERNEL32!GetFileTime` at `0x18000ccd5`
- `KERNEL32!GetFileTime` at `0x18000ccd5`
- `KERNEL32!CloseHandle` at `0x18000cbc1`
- `KERNEL32!CloseHandle` at `0x18000cbd5`
- `KERNEL32!CloseHandle` at `0x18000cd2b`
- `KERNEL32!CloseHandle` at `0x18000cbc1`
- `KERNEL32!CloseHandle` at `0x18000cbd5`
- `KERNEL32!CloseHandle` at `0x18000cd2b`
- `KERNEL32!CreateFileW` at `0x18000cb23`
- `KERNEL32!CreateFileW` at `0x18000cb23`
- `KERNEL32!LocalAlloc` at `0x18000cc29`
- `KERNEL32!LocalAlloc` at `0x18000cc29`
- `KERNEL32!UnmapViewOfFile` at `0x18000cd16`
- `KERNEL32!UnmapViewOfFile` at `0x18000cd16`
- `KERNEL32!GetFileSize` at `0x18000cb55`
- `KERNEL32!GetFileSize` at `0x18000cb55`
- `KERNEL32!CreateFileMappingW` at `0x18000cb85`
- `KERNEL32!CreateFileMappingW` at `0x18000cb85`

## string_xrefs

- `0x18000cd81`: `unable to open GPD file: %S`

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
  if ( !(unsigned int)BallocElementFromMasterTable(10, &v28, (_DWORD *)a2) )
    return 0;
  v6 = (struct _FILETIME *)(v5 + 16LL * v28);
  *(_DWORD *)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 16) = dwStoreFileName(pszSrc, v6, a2);
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
    WriteDbgTraceErrorGpd((__int64)"BloadFile", "unable to open GPD file: %S", pszSrc);
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
      (__int64)"BloadFile",
      "Fatal: unable to alloc requested memory: %d bytes.",
      *(_DWORD *)(v20 + v19 + 12));
    v21 = *(_QWORD *)(a2 + 456);
    v22 = 32LL * *(unsigned int *)(a2 + 468);
    *(_DWORD *)(a2 + 2224) = 2;
    *(_DWORD *)(a2 + 2220) = 3;
    *(_DWORD *)(a2 + 2216) = 19;
    UnmapFileFromMemory(*(const void **)(v22 + v21 + 24), (void *)FileW);
    return 0;
  }
  memcpy_0(*(void **)(v20 + v19), v16, *(unsigned int *)(v20 + v19 + 12));
  if ( !GetFileTime((HANDLE)FileW, 0, 0, v6 + 1) )
    WriteDbgTraceErrorGpd((__int64)"BloadFile", "GetFileTime '%S' failed.", pszSrc);
  v23 = *(const void **)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 24);
  if ( v23 )
    UnmapViewOfFile(v23);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  v24 = *(_DWORD *)(a2 + 468);
  v25 = 32LL * v24;
  *(_DWORD *)(a2 + 736) = ComputeCrc32Checksum(
                            *(char **)(v25 + *(_QWORD *)(a2 + 456)),
                            *(_DWORD *)(v25 + *(_QWORD *)(a2 + 456) + 12),
                            *(_DWORD *)(a2 + 736));
  *(_DWORD *)(a2 + 468) = v24 + 1;
  result = 1;
  *(_DWORD *)(v25 + v27 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ca1c  mov     [rsp+arg_0], rbx
0x18000ca21  mov     [rsp+arg_10], rbp
0x18000ca26  push    rsi
0x18000ca27  push    rdi
0x18000ca28  push    r13
0x18000ca2a  push    r14
0x18000ca2c  push    r15
0x18000ca2e  sub     rsp, 40h
0x18000ca32  mov     eax, [rdx+1D0h]
0x18000ca38  mov     rsi, rdx
0x18000ca3b  mov     r14, rcx
0x18000ca3e  mov     [rsp+68h+arg_8], 0
0x18000ca46  cmp     [rdx+1D4h], eax
0x18000ca4c  jb      short loc_18000CA7A
0x18000ca4e  mov     ebx, 2
0x18000ca53  cmp     [rdx+8ACh], ebx
0x18000ca59  jge     loc_18000CDA8
0x18000ca5f  mov     [rdx+8ACh], ebx
0x18000ca65  mov     [rdx+8B0h], ebx
0x18000ca6b  mov     dword ptr [rdx+8A8h], 13h
0x18000ca75  jmp     loc_18000CDA8
0x18000ca7a  mov     rbx, [rdx+0F0h]
0x18000ca81  mov     r8, rsi
0x18000ca84  lea     rdx, [rsp+68h+arg_8]
0x18000ca89  mov     ecx, 0Ah
0x18000ca8e  call    BallocElementFromMasterTable
0x18000ca93  test    eax, eax
0x18000ca95  jz      loc_18000CDA8
0x18000ca9b  mov     r13d, [rsp+68h+arg_8]
0x18000caa0  mov     r8, rsi
0x18000caa3  shl     r13, 4
0x18000caa7  mov     rcx, r14; pszSrc
0x18000caaa  add     r13, rbx
0x18000caad  mov     rdx, r13
0x18000cab0  call    dwStoreFileName
0x18000cab5  mov     edx, [rsi+1D4h]
0x18000cabb  mov     rcx, [rsi+1C8h]
0x18000cac2  shl     rdx, 5
0x18000cac6  mov     [rdx+rcx+10h], eax
0x18000caca  mov     eax, [rsi+1D4h]
0x18000cad0  mov     rcx, [rsi+1C8h]
0x18000cad7  shl     rax, 5
0x18000cadb  cmp     dword ptr [rax+rcx+10h], 0FFFFFFFFh
0x18000cae0  jz      loc_18000CDA8
0x18000cae6  mov     edx, 1
0x18000caeb  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000caf4  mov     [rax+rcx+14h], edx
0x18000caf8  mov     r8d, edx; dwShareMode
0x18000cafb  mov     ebp, [rsi+1D4h]
0x18000cb01  mov     edx, 80000000h; dwDesiredAccess
0x18000cb06  mov     r15, [rsi+1C8h]
0x18000cb0d  mov     rcx, r14; lpFileName
0x18000cb10  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18000cb18  xor     r9d, r9d; lpSecurityAttributes
0x18000cb1b  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000cb23  call    cs:__imp_CreateFileW
0x18000cb2a  nop     dword ptr [rax+rax+00h]
0x18000cb2f  mov     rdi, rax
0x18000cb32  mov     ebx, 2
0x18000cb37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cb3b  jz      loc_18000CBE5
0x18000cb41  mov     eax, ebp
0x18000cb43  add     r15, 0Ch
0x18000cb47  shl     rax, 5
0x18000cb4b  add     r15, rax
0x18000cb4e  jz      short loc_18000CB69
0x18000cb50  xor     edx, edx; lpFileSizeHigh
0x18000cb52  mov     rcx, rdi; hFile
0x18000cb55  call    cs:__imp_GetFileSize
0x18000cb5c  nop     dword ptr [rax+rax+00h]
0x18000cb61  mov     [r15], eax
0x18000cb64  cmp     eax, 0FFFFFFFFh
0x18000cb67  jz      short loc_18000CBD2
0x18000cb69  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18000cb72  xor     r9d, r9d; dwMaximumSizeHigh
0x18000cb75  mov     r8d, ebx; flProtect
0x18000cb78  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18000cb80  xor     edx, edx; lpFileMappingAttributes
0x18000cb82  mov     rcx, rdi; hFile
0x18000cb85  call    cs:__imp_CreateFileMappingW
0x18000cb8c  nop     dword ptr [rax+rax+00h]
0x18000cb91  mov     r15, rax
0x18000cb94  test    rax, rax
0x18000cb97  jz      short loc_18000CBD2
0x18000cb99  xor     r9d, r9d; dwFileOffsetLow
0x18000cb9c  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18000cba5  xor     r8d, r8d; dwFileOffsetHigh
0x18000cba8  mov     rcx, rax; hFileMappingObject
0x18000cbab  lea     edx, [r9+4]; dwDesiredAccess
0x18000cbaf  call    cs:__imp_MapViewOfFile
0x18000cbb6  nop     dword ptr [rax+rax+00h]
0x18000cbbb  mov     rcx, r15; hObject
0x18000cbbe  mov     rbp, rax
0x18000cbc1  call    cs:__imp_CloseHandle
0x18000cbc8  nop     dword ptr [rax+rax+00h]
0x18000cbcd  test    rbp, rbp
0x18000cbd0  jnz     short loc_18000CBE7
0x18000cbd2  mov     rcx, rdi; hObject
0x18000cbd5  call    cs:__imp_CloseHandle
0x18000cbdc  nop     dword ptr [rax+rax+00h]
0x18000cbe1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000cbe5  xor     ebp, ebp
0x18000cbe7  mov     ecx, [rsi+1D4h]
0x18000cbed  mov     rax, [rsi+1C8h]
0x18000cbf4  shl     rcx, 5
0x18000cbf8  mov     [rcx+rax+18h], rbp
0x18000cbfd  mov     eax, [rsi+1D4h]
0x18000cc03  mov     rcx, [rsi+1C8h]
0x18000cc0a  shl     rax, 5
0x18000cc0e  cmp     qword ptr [rax+rcx+18h], 0
0x18000cc14  jz      loc_18000CD7E
0x18000cc1a  test    rbp, rbp
0x18000cc1d  jz      loc_18000CD7E
0x18000cc23  mov     edx, [rax+rcx+0Ch]; uBytes
0x18000cc27  xor     ecx, ecx; uFlags
0x18000cc29  call    cs:__imp_LocalAlloc
0x18000cc30  nop     dword ptr [rax+rax+00h]
0x18000cc35  mov     edx, [rsi+1D4h]
0x18000cc3b  mov     rcx, [rsi+1C8h]
0x18000cc42  shl     rdx, 5
0x18000cc46  mov     [rdx+rcx], rax
0x18000cc4a  mov     rax, [rsi+1C8h]
0x18000cc51  mov     ecx, [rsi+1D4h]
0x18000cc57  shl     rcx, 5
0x18000cc5b  mov     r9, [rcx+rax]
0x18000cc5f  mov     edx, [rcx+rax+0Ch]
0x18000cc63  test    r9, r9
0x18000cc66  jnz     short loc_18000CCBB
0x18000cc68  mov     r8d, edx
0x18000cc6b  lea     rcx, aBloadfile; "BloadFile"
0x18000cc72  lea     rdx, aFatalUnableToA; "Fatal: unable to alloc requested memory"...
0x18000cc79  call    WriteDbgTraceErrorGpd
0x18000cc7e  mov     eax, [rsi+1D4h]
0x18000cc84  mov     rdx, rdi
0x18000cc87  mov     rcx, [rsi+1C8h]
0x18000cc8e  shl     rax, 5
0x18000cc92  mov     [rsi+8B0h], ebx
0x18000cc98  mov     dword ptr [rsi+8ACh], 3
0x18000cca2  mov     dword ptr [rsi+8A8h], 13h
0x18000ccac  mov     rcx, [rax+rcx+18h]
0x18000ccb1  call    UnmapFileFromMemory
0x18000ccb6  jmp     loc_18000CDA8
0x18000ccbb  mov     r8, rdx; Size
0x18000ccbe  mov     rcx, r9; void *
0x18000ccc1  mov     rdx, rbp; Src
0x18000ccc4  call    memcpy_0
0x18000ccc9  lea     r9, [r13+8]; lpLastWriteTime
0x18000cccd  xor     r8d, r8d; lpLastAccessTime
0x18000ccd0  xor     edx, edx; lpCreationTime
0x18000ccd2  mov     rcx, rdi; hFile
0x18000ccd5  call    cs:__imp_GetFileTime
0x18000ccdc  nop     dword ptr [rax+rax+00h]
0x18000cce1  test    eax, eax
0x18000cce3  jnz     short loc_18000CCFB
0x18000cce5  mov     r8, r14
0x18000cce8  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x18000ccef  lea     rcx, aBloadfile; "BloadFile"
0x18000ccf6  call    WriteDbgTraceErrorGpd
0x18000ccfb  mov     ecx, [rsi+1D4h]
0x18000cd01  mov     rax, [rsi+1C8h]
0x18000cd08  shl     rcx, 5
0x18000cd0c  mov     rcx, [rcx+rax+18h]; lpBaseAddress
0x18000cd11  test    rcx, rcx
0x18000cd14  jz      short loc_18000CD22
0x18000cd16  call    cs:__imp_UnmapViewOfFile
0x18000cd1d  nop     dword ptr [rax+rax+00h]
0x18000cd22  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000cd26  jz      short loc_18000CD37
0x18000cd28  mov     rcx, rdi; hObject
0x18000cd2b  call    cs:__imp_CloseHandle
0x18000cd32  nop     dword ptr [rax+rax+00h]
0x18000cd37  mov     r11, [rsi+1C8h]
0x18000cd3e  mov     ebx, [rsi+1D4h]
0x18000cd44  mov     r8d, [rsi+2E0h]
0x18000cd4b  mov     edi, ebx
0x18000cd4d  shl     rdi, 5
0x18000cd51  mov     edx, [rdi+r11+0Ch]
0x18000cd56  mov     rcx, [rdi+r11]
0x18000cd5a  call    ComputeCrc32Checksum
0x18000cd5f  mov     [rsi+2E0h], eax
0x18000cd65  lea     ecx, [rbx+1]
0x18000cd68  mov     [rsi+1D4h], ecx
0x18000cd6e  mov     eax, 1
0x18000cd73  mov     dword ptr [rdi+r11+8], 0
0x18000cd7c  jmp     short loc_18000CDAA
0x18000cd7e  mov     r8, r14
0x18000cd81  lea     rdx, aUnableToOpenGp; "unable to open GPD file: %S"
0x18000cd88  lea     rcx, aBloadfile; "BloadFile"
0x18000cd8f  call    WriteDbgTraceErrorGpd
0x18000cd94  mov     dword ptr [rsi+8ACh], 3
0x18000cd9e  mov     dword ptr [rsi+8B0h], 3
0x18000cda8  xor     eax, eax
0x18000cdaa  lea     r11, [rsp+68h+var_28]
0x18000cdaf  mov     rbx, [r11+30h]
0x18000cdb3  mov     rbp, [r11+40h]
0x18000cdb7  mov     rsp, r11
0x18000cdba  pop     r15
0x18000cdbc  pop     r14
0x18000cdbe  pop     r13
0x18000cdc0  pop     rdi
0x18000cdc1  pop     rsi
0x18000cdc2  retn
```
