# BloadFile

- ea: `0x180177e78`
- end: `0x180178205`
- name: `BloadFile`
- size: `909`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801778ac`
- `0x180178584`

## callees

- `0x1801502f4`
- `0x180150854`
- `0x18016a374`
- `0x180177e78`
- `0x18017917c`
- `0x18017e404`
- `0x1801b56bc`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x180177fe1`
- `KERNEL32!CreateFileMappingW` at `0x180177fe1`
- `KERNEL32!MapViewOfFile` at `0x18017800b`
- `KERNEL32!MapViewOfFile` at `0x18017800b`
- `KERNEL32!GetFileSize` at `0x180177fb1`
- `KERNEL32!GetFileSize` at `0x180177fb1`
- `KERNEL32!CreateFileW` at `0x180177f7f`
- `KERNEL32!CreateFileW` at `0x180177f7f`
- `KERNEL32!CloseHandle` at `0x18017801d`
- `KERNEL32!CloseHandle` at `0x180178031`
- `KERNEL32!CloseHandle` at `0x18017801d`
- `KERNEL32!CloseHandle` at `0x180178031`
- `KERNEL32!LocalAlloc` at `0x180178085`
- `KERNEL32!LocalAlloc` at `0x180178085`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180178131`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180178131`

## string_xrefs

- `0x1801781c2`: `unable to open GPD file: %S`

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
  __int64 FileW; // rsi
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
  __int64 v23; // rbx
  int v24; // r11d
  __int64 result; // rax
  __int64 v26; // r10
  unsigned int v27; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a2 + 464);
  v27 = 0;
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
  if ( !(unsigned int)BallocElementFromMasterTable(10, &v27, (_DWORD *)a2) )
    return 0;
  v6 = (struct _FILETIME *)(v5 + 16LL * v27);
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
    UnmapFileFromMemory(*(const void **)(v22 + v21 + 24), (void *)FileW);
    return 0;
  }
  memcpy_0(*(void **)(v20 + v19), v16, *(unsigned int *)(v20 + v19 + 12));
  if ( !GetFileTime((HANDLE)FileW, 0, 0, v6 + 1) )
    WriteDbgTraceErrorGpd("BloadFile", "GetFileTime '%S' failed.", pszSrc);
  UnmapFileFromMemory(*(const void **)(32LL * *(unsigned int *)(a2 + 468) + *(_QWORD *)(a2 + 456) + 24), (void *)FileW);
  v23 = 32LL * *(unsigned int *)(a2 + 468);
  *(_DWORD *)(a2 + 736) = ComputeCrc32Checksum(
                            *(_BYTE **)(v23 + *(_QWORD *)(a2 + 456)),
                            *(_DWORD *)(v23 + *(_QWORD *)(a2 + 456) + 12),
                            *(_DWORD *)(a2 + 736));
  *(_DWORD *)(a2 + 468) = v24 + 1;
  result = 1;
  *(_DWORD *)(v23 + v26 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180177e78  mov     [rsp+arg_0], rbx
0x180177e7d  mov     [rsp+arg_10], rbp
0x180177e82  push    rsi
0x180177e83  push    rdi
0x180177e84  push    r13
0x180177e86  push    r14
0x180177e88  push    r15
0x180177e8a  sub     rsp, 40h
0x180177e8e  mov     eax, [rdx+1D0h]
0x180177e94  mov     rdi, rdx
0x180177e97  mov     r14, rcx
0x180177e9a  mov     [rsp+68h+arg_8], 0
0x180177ea2  cmp     [rdx+1D4h], eax
0x180177ea8  jb      short loc_180177ED6
0x180177eaa  mov     ebx, 2
0x180177eaf  cmp     [rdx+8ACh], ebx
0x180177eb5  jge     loc_1801781E9
0x180177ebb  mov     [rdx+8ACh], ebx
0x180177ec1  mov     [rdx+8B0h], ebx
0x180177ec7  mov     dword ptr [rdx+8A8h], 13h
0x180177ed1  jmp     loc_1801781E9
0x180177ed6  mov     rbx, [rdx+0F0h]
0x180177edd  mov     r8, rdi
0x180177ee0  lea     rdx, [rsp+68h+arg_8]
0x180177ee5  mov     ecx, 0Ah
0x180177eea  call    BallocElementFromMasterTable
0x180177eef  test    eax, eax
0x180177ef1  jz      loc_1801781E9
0x180177ef7  mov     r13d, [rsp+68h+arg_8]
0x180177efc  mov     r8, rdi
0x180177eff  shl     r13, 4
0x180177f03  mov     rcx, r14; pszSrc
0x180177f06  add     r13, rbx
0x180177f09  mov     rdx, r13
0x180177f0c  call    dwStoreFileName
0x180177f11  mov     edx, [rdi+1D4h]
0x180177f17  mov     rcx, [rdi+1C8h]
0x180177f1e  shl     rdx, 5
0x180177f22  mov     [rdx+rcx+10h], eax
0x180177f26  mov     eax, [rdi+1D4h]
0x180177f2c  mov     rcx, [rdi+1C8h]
0x180177f33  shl     rax, 5
0x180177f37  cmp     dword ptr [rax+rcx+10h], 0FFFFFFFFh
0x180177f3c  jz      loc_1801781E9
0x180177f42  mov     edx, 1
0x180177f47  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180177f50  mov     [rax+rcx+14h], edx
0x180177f54  mov     r8d, edx; dwShareMode
0x180177f57  mov     ebp, [rdi+1D4h]
0x180177f5d  mov     edx, 80000000h; dwDesiredAccess
0x180177f62  mov     r15, [rdi+1C8h]
0x180177f69  mov     rcx, r14; lpFileName
0x180177f6c  mov     [rsp+68h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180177f74  xor     r9d, r9d; lpSecurityAttributes
0x180177f77  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180177f7f  call    cs:__imp_CreateFileW
0x180177f86  nop     dword ptr [rax+rax+00h]
0x180177f8b  mov     rsi, rax
0x180177f8e  mov     ebx, 2
0x180177f93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180177f97  jz      loc_180178041
0x180177f9d  mov     eax, ebp
0x180177f9f  add     r15, 0Ch
0x180177fa3  shl     rax, 5
0x180177fa7  add     r15, rax
0x180177faa  jz      short loc_180177FC5
0x180177fac  xor     edx, edx; lpFileSizeHigh
0x180177fae  mov     rcx, rsi; hFile
0x180177fb1  call    cs:__imp_GetFileSize
0x180177fb8  nop     dword ptr [rax+rax+00h]
0x180177fbd  mov     [r15], eax
0x180177fc0  cmp     eax, 0FFFFFFFFh
0x180177fc3  jz      short loc_18017802E
0x180177fc5  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x180177fce  xor     r9d, r9d; dwMaximumSizeHigh
0x180177fd1  mov     r8d, ebx; flProtect
0x180177fd4  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180177fdc  xor     edx, edx; lpFileMappingAttributes
0x180177fde  mov     rcx, rsi; hFile
0x180177fe1  call    cs:__imp_CreateFileMappingW
0x180177fe8  nop     dword ptr [rax+rax+00h]
0x180177fed  mov     r15, rax
0x180177ff0  test    rax, rax
0x180177ff3  jz      short loc_18017802E
0x180177ff5  xor     r9d, r9d; dwFileOffsetLow
0x180177ff8  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180178001  xor     r8d, r8d; dwFileOffsetHigh
0x180178004  mov     rcx, rax; hFileMappingObject
0x180178007  lea     edx, [r9+4]; dwDesiredAccess
0x18017800b  call    cs:__imp_MapViewOfFile
0x180178012  nop     dword ptr [rax+rax+00h]
0x180178017  mov     rcx, r15; hObject
0x18017801a  mov     rbp, rax
0x18017801d  call    cs:__imp_CloseHandle
0x180178024  nop     dword ptr [rax+rax+00h]
0x180178029  test    rbp, rbp
0x18017802c  jnz     short loc_180178043
0x18017802e  mov     rcx, rsi; hObject
0x180178031  call    cs:__imp_CloseHandle
0x180178038  nop     dword ptr [rax+rax+00h]
0x18017803d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180178041  xor     ebp, ebp
0x180178043  mov     ecx, [rdi+1D4h]
0x180178049  mov     rax, [rdi+1C8h]
0x180178050  shl     rcx, 5
0x180178054  mov     [rcx+rax+18h], rbp
0x180178059  mov     eax, [rdi+1D4h]
0x18017805f  mov     rcx, [rdi+1C8h]
0x180178066  shl     rax, 5
0x18017806a  cmp     qword ptr [rax+rcx+18h], 0
0x180178070  jz      loc_1801781BF
0x180178076  test    rbp, rbp
0x180178079  jz      loc_1801781BF
0x18017807f  mov     edx, [rax+rcx+0Ch]; uBytes
0x180178083  xor     ecx, ecx; uFlags
0x180178085  call    cs:__imp_LocalAlloc
0x18017808c  nop     dword ptr [rax+rax+00h]
0x180178091  mov     edx, [rdi+1D4h]
0x180178097  mov     rcx, [rdi+1C8h]
0x18017809e  shl     rdx, 5
0x1801780a2  mov     [rdx+rcx], rax
0x1801780a6  mov     rax, [rdi+1C8h]
0x1801780ad  mov     ecx, [rdi+1D4h]
0x1801780b3  shl     rcx, 5
0x1801780b7  mov     r9, [rcx+rax]
0x1801780bb  mov     edx, [rcx+rax+0Ch]
0x1801780bf  test    r9, r9
0x1801780c2  jnz     short loc_180178117
0x1801780c4  mov     r8d, edx
0x1801780c7  lea     rcx, aBloadfile; "BloadFile"
0x1801780ce  lea     rdx, aFatalUnableToA; "Fatal: unable to alloc requested memory"...
0x1801780d5  call    WriteDbgTraceErrorGpd
0x1801780da  mov     eax, [rdi+1D4h]
0x1801780e0  mov     rdx, rsi
0x1801780e3  mov     rcx, [rdi+1C8h]
0x1801780ea  shl     rax, 5
0x1801780ee  mov     [rdi+8B0h], ebx
0x1801780f4  mov     dword ptr [rdi+8ACh], 3
0x1801780fe  mov     dword ptr [rdi+8A8h], 13h
0x180178108  mov     rcx, [rax+rcx+18h]
0x18017810d  call    UnmapFileFromMemory
0x180178112  jmp     loc_1801781E9
0x180178117  mov     r8, rdx; Size
0x18017811a  mov     rcx, r9; void *
0x18017811d  mov     rdx, rbp; Src
0x180178120  call    memcpy_0
0x180178125  lea     r9, [r13+8]; lpLastWriteTime
0x180178129  xor     r8d, r8d; lpLastAccessTime
0x18017812c  xor     edx, edx; lpCreationTime
0x18017812e  mov     rcx, rsi; hFile
0x180178131  call    cs:__imp_GetFileTime
0x180178138  nop     dword ptr [rax+rax+00h]
0x18017813d  test    eax, eax
0x18017813f  jnz     short loc_180178157
0x180178141  mov     r8, r14
0x180178144  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x18017814b  lea     rcx, aBloadfile; "BloadFile"
0x180178152  call    WriteDbgTraceErrorGpd
0x180178157  mov     eax, [rdi+1D4h]
0x18017815d  mov     rdx, rsi
0x180178160  mov     rcx, [rdi+1C8h]
0x180178167  shl     rax, 5
0x18017816b  mov     rcx, [rax+rcx+18h]
0x180178170  call    UnmapFileFromMemory
0x180178175  mov     r10, [rdi+1C8h]
0x18017817c  mov     r11d, [rdi+1D4h]
0x180178183  mov     r8d, [rdi+2E0h]
0x18017818a  mov     ebx, r11d
0x18017818d  shl     rbx, 5
0x180178191  mov     edx, [rbx+r10+0Ch]
0x180178196  mov     rcx, [rbx+r10]
0x18017819a  call    ComputeCrc32Checksum
0x18017819f  mov     [rdi+2E0h], eax
0x1801781a5  lea     ecx, [r11+1]
0x1801781a9  mov     [rdi+1D4h], ecx
0x1801781af  mov     eax, 1
0x1801781b4  mov     dword ptr [rbx+r10+8], 0
0x1801781bd  jmp     short loc_1801781EB
0x1801781bf  mov     r8, r14
0x1801781c2  lea     rdx, aUnableToOpenGp; "unable to open GPD file: %S"
0x1801781c9  lea     rcx, aBloadfile; "BloadFile"
0x1801781d0  call    WriteDbgTraceErrorGpd
0x1801781d5  mov     dword ptr [rdi+8ACh], 3
0x1801781df  mov     dword ptr [rdi+8B0h], 3
0x1801781e9  xor     eax, eax
0x1801781eb  lea     r11, [rsp+68h+var_28]
0x1801781f0  mov     rbx, [r11+30h]
0x1801781f4  mov     rbp, [r11+40h]
0x1801781f8  mov     rsp, r11
0x1801781fb  pop     r15
0x1801781fd  pop     r14
0x1801781ff  pop     r13
0x180178201  pop     rdi
0x180178202  pop     rsi
0x180178203  retn
```
