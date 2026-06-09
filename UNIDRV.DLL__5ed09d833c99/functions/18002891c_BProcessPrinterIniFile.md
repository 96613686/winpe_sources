# BProcessPrinterIniFile

- ea: `0x18002891c`
- end: `0x180028bd4`
- name: `BProcessPrinterIniFile`
- size: `696`
- prototype: `_BOOL8 __fastcall(struct _FILETIME, __int64, WCHAR **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180028534`

## callees

- `0x18002891c`
- `0x180028be0`
- `0x180028c54`
- `0x1800517b0`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180028a06`
- `KERNEL32!MapViewOfFile` at `0x180028a06`
- `KERNEL32!GetFileTime` at `0x180028b18`
- `KERNEL32!GetFileTime` at `0x180028b18`
- `KERNEL32!CloseHandle` at `0x180028a18`
- `KERNEL32!CloseHandle` at `0x180028a2c`
- `KERNEL32!CloseHandle` at `0x180028a83`
- `KERNEL32!CloseHandle` at `0x180028b62`
- `KERNEL32!CloseHandle` at `0x180028a18`
- `KERNEL32!CloseHandle` at `0x180028a2c`
- `KERNEL32!CloseHandle` at `0x180028a83`
- `KERNEL32!CloseHandle` at `0x180028b62`
- `KERNEL32!CreateFileW` at `0x180028999`
- `KERNEL32!CreateFileW` at `0x180028af3`
- `KERNEL32!CreateFileW` at `0x180028999`
- `KERNEL32!CreateFileW` at `0x180028af3`
- `KERNEL32!CompareFileTime` at `0x180028b35`
- `KERNEL32!CompareFileTime` at `0x180028b35`
- `KERNEL32!LocalFree` at `0x180028bc3`
- `KERNEL32!LocalFree` at `0x180028bc3`
- `KERNEL32!UnmapViewOfFile` at `0x180028a74`
- `KERNEL32!UnmapViewOfFile` at `0x180028a74`
- `KERNEL32!GetFileSize` at `0x1800289b7`
- `KERNEL32!GetFileSize` at `0x1800289b7`
- `KERNEL32!CreateFileMappingW` at `0x1800289e0`
- `KERNEL32!CreateFileMappingW` at `0x1800289e0`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, WCHAR **a3, int a4)
{
  const wchar_t *v4; // rcx
  BOOL v7; // ebx
  const WCHAR *v8; // rdi
  HANDLE v10; // rax
  void *v11; // rsi
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  void *v14; // r14
  wint_t *v15; // rdi
  WCHAR *v16; // rax
  __int64 v17; // rax
  const wchar_t *v18; // rcx
  const WCHAR *v19; // rax
  const WCHAR *v20; // rsi
  HANDLE FileW; // rax
  void *v22; // r14
  __int64 v23; // rax
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+48h] BYREF
  __int64 v26; // [rsp+98h] [rbp+58h] BYREF

  LODWORD(v26) = a4;
  LastWriteTime = a1;
  v4 = *(const wchar_t **)(a2 + 56);
  LODWORD(v26) = 0;
  v7 = 1;
  v8 = PtstrSearchDependentFileWithExtension(v4);
  if ( v8 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v8[v17] );
    if ( !PtstrSearchDependentFileWithExtension(&v8[v17 + 1]) )
      goto LABEL_4;
    v18 = *(const wchar_t **)(a2 + 56);
    v8 = 0;
    FileTime2 = 0;
    do
    {
      v19 = PtstrSearchDependentFileWithExtension(v18);
      v20 = v19;
      if ( !v19 )
        break;
      FileW = CreateFileW(v19, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v22 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v7 = 0;
      }
      else
      {
        LastWriteTime = 0;
        if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
        {
          if ( !v8 || CompareFileTime(&LastWriteTime, &FileTime2) == 1 )
          {
            v8 = v20;
            FileTime2 = LastWriteTime;
          }
        }
        else
        {
          v7 = 0;
        }
        CloseHandle(v22);
      }
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v18 = &v20[v23 + 1];
    }
    while ( v7 );
    if ( v8 )
    {
LABEL_4:
      v10 = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v11 = v10;
      if ( v10 == (HANDLE)-1LL )
        return 0;
      FileSize = GetFileSize(v10, 0);
      if ( FileSize == -1
        || (FileMappingW = CreateFileMappingW(v11, 0, 2u, 0, 0, 0), (v14 = FileMappingW) == 0)
        || (v15 = (wint_t *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v14), !v15) )
      {
        CloseHandle(v11);
        return 0;
      }
      if ( FileSize >= 2 && *(_BYTE *)v15 == 0xFF && *((_BYTE *)v15 + 1) == 0xFE )
        v16 = (WCHAR *)PwstrParsePrinterIniFileW(v15 + 1, (FileSize >> 1) - 1, &v26);
      else
        v16 = PwstrParsePrinterIniFileA((const char *)v15, FileSize, &v26);
      v7 = v16 != 0;
      if ( a3 )
      {
        *a3 = v16;
      }
      else if ( v16 )
      {
        LocalFree(v16);
      }
      UnmapViewOfFile(v15);
      CloseHandle(v11);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002891c  mov     dword ptr [rsp-38h+arg_18], r9d
0x180028921  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x180028926  push    rbp
0x180028927  push    rbx
0x180028928  push    rsi
0x180028929  push    rdi
0x18002892a  push    r12
0x18002892c  push    r14
0x18002892e  push    r15
0x180028930  mov     rbp, rsp
0x180028933  sub     rsp, 40h
0x180028937  mov     rcx, [rdx+38h]
0x18002893b  xor     r12d, r12d
0x18002893e  mov     r15, r8
0x180028941  mov     dword ptr [rbp+arg_18], r12d
0x180028945  mov     rsi, rdx
0x180028948  lea     ebx, [r12+1]
0x18002894d  call    PtstrSearchDependentFileWithExtension
0x180028952  mov     rdi, rax
0x180028955  test    rax, rax
0x180028958  jnz     loc_180028B53
0x18002895e  mov     eax, ebx
0x180028960  add     rsp, 40h
0x180028964  pop     r15
0x180028966  pop     r14
0x180028968  pop     r12
0x18002896a  pop     rdi
0x18002896b  pop     rsi
0x18002896c  pop     rbx
0x18002896d  pop     rbp
0x18002896e  retn
0x180028970  test    rdi, rdi
0x180028973  jz      short loc_18002895E
0x180028975  xor     r9d, r9d; lpSecurityAttributes
0x180028978  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x18002897d  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180028985  mov     edx, 80000000h; dwDesiredAccess
0x18002898a  mov     rcx, rdi; lpFileName
0x18002898d  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180028995  lea     r8d, [r9+1]; dwShareMode
0x180028999  call    cs:__imp_CreateFileW
0x1800289a0  nop     dword ptr [rax+rax+00h]
0x1800289a5  mov     rsi, rax
0x1800289a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800289ac  jz      loc_180028A38
0x1800289b2  xor     edx, edx; lpFileSizeHigh
0x1800289b4  mov     rcx, rax; hFile
0x1800289b7  call    cs:__imp_GetFileSize
0x1800289be  nop     dword ptr [rax+rax+00h]
0x1800289c3  mov     ebx, eax
0x1800289c5  cmp     eax, 0FFFFFFFFh
0x1800289c8  jz      short loc_180028A29
0x1800289ca  xor     r9d, r9d; dwMaximumSizeHigh
0x1800289cd  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x1800289d2  xor     edx, edx; lpFileMappingAttributes
0x1800289d4  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x1800289d9  mov     rcx, rsi; hFile
0x1800289dc  lea     r8d, [r9+2]; flProtect
0x1800289e0  call    cs:__imp_CreateFileMappingW
0x1800289e7  nop     dword ptr [rax+rax+00h]
0x1800289ec  mov     r14, rax
0x1800289ef  test    rax, rax
0x1800289f2  jz      short loc_180028A29
0x1800289f4  xor     r9d, r9d; dwFileOffsetLow
0x1800289f7  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x1800289fc  xor     r8d, r8d; dwFileOffsetHigh
0x1800289ff  mov     rcx, rax; hFileMappingObject
0x180028a02  lea     edx, [r9+4]; dwDesiredAccess
0x180028a06  call    cs:__imp_MapViewOfFile
0x180028a0d  nop     dword ptr [rax+rax+00h]
0x180028a12  mov     rcx, r14; hObject
0x180028a15  mov     rdi, rax
0x180028a18  call    cs:__imp_CloseHandle
0x180028a1f  nop     dword ptr [rax+rax+00h]
0x180028a24  test    rdi, rdi
0x180028a27  jnz     short loc_180028A40
0x180028a29  mov     rcx, rsi; hObject
0x180028a2c  call    cs:__imp_CloseHandle
0x180028a33  nop     dword ptr [rax+rax+00h]
0x180028a38  mov     ebx, r12d
0x180028a3b  jmp     loc_18002895E
0x180028a40  cmp     ebx, 2
0x180028a43  jb      short loc_180028A4E
0x180028a45  cmp     byte ptr [rdi], 0FFh
0x180028a48  jz      loc_180028B96
0x180028a4e  lea     r8, [rbp+arg_18]
0x180028a52  mov     edx, ebx
0x180028a54  mov     rcx, rdi
0x180028a57  call    PwstrParsePrinterIniFileA
0x180028a5c  test    rax, rax
0x180028a5f  mov     ebx, r12d
0x180028a62  setnz   bl
0x180028a65  test    r15, r15
0x180028a68  jz      loc_180028BB7
0x180028a6e  mov     [r15], rax
0x180028a71  mov     rcx, rdi; lpBaseAddress
0x180028a74  call    cs:__imp_UnmapViewOfFile
0x180028a7b  nop     dword ptr [rax+rax+00h]
0x180028a80  mov     rcx, rsi; hObject
0x180028a83  call    cs:__imp_CloseHandle
0x180028a8a  nop     dword ptr [rax+rax+00h]
0x180028a8f  jmp     loc_18002895E
0x180028a94  inc     rax
0x180028a97  cmp     [rdi+rax*2], r12w
0x180028a9c  jnz     short loc_180028A94
0x180028a9e  inc     rax
0x180028aa1  lea     rcx, [rdi+rax*2]
0x180028aa5  call    PtstrSearchDependentFileWithExtension
0x180028aaa  test    rax, rax
0x180028aad  jz      loc_180028975
0x180028ab3  mov     rcx, [rsi+38h]
0x180028ab7  mov     rdi, r12
0x180028aba  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x180028abe  call    PtstrSearchDependentFileWithExtension
0x180028ac3  mov     rsi, rax
0x180028ac6  test    rax, rax
0x180028ac9  jz      loc_180028970
0x180028acf  xor     r9d, r9d; lpSecurityAttributes
0x180028ad2  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x180028ad7  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180028adf  mov     edx, 80000000h; dwDesiredAccess
0x180028ae4  mov     rcx, rax; lpFileName
0x180028ae7  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180028aef  lea     r8d, [r9+1]; dwShareMode
0x180028af3  call    cs:__imp_CreateFileW
0x180028afa  nop     dword ptr [rax+rax+00h]
0x180028aff  mov     r14, rax
0x180028b02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028b06  jz      short loc_180028B70
0x180028b08  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180028b0c  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180028b10  xor     r8d, r8d; lpLastAccessTime
0x180028b13  xor     edx, edx; lpCreationTime
0x180028b15  mov     rcx, rax; hFile
0x180028b18  call    cs:__imp_GetFileTime
0x180028b1f  nop     dword ptr [rax+rax+00h]
0x180028b24  test    eax, eax
0x180028b26  jz      short loc_180028B5C
0x180028b28  test    rdi, rdi
0x180028b2b  jz      short loc_180028B46
0x180028b2d  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180028b31  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180028b35  call    cs:__imp_CompareFileTime
0x180028b3c  nop     dword ptr [rax+rax+00h]
0x180028b41  cmp     eax, 1
0x180028b44  jnz     short loc_180028B5F
0x180028b46  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x180028b4a  mov     rdi, rsi
0x180028b4d  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180028b51  jmp     short loc_180028B5F
0x180028b53  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028b57  jmp     loc_180028A94
0x180028b5c  mov     ebx, r12d
0x180028b5f  mov     rcx, r14; hObject
0x180028b62  call    cs:__imp_CloseHandle
0x180028b69  nop     dword ptr [rax+rax+00h]
0x180028b6e  jmp     short loc_180028B73
0x180028b70  mov     ebx, r12d
0x180028b73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028b77  inc     rax
0x180028b7a  cmp     [rsi+rax*2], r12w
0x180028b7f  jnz     short loc_180028B77
0x180028b81  lea     rcx, [rax+1]
0x180028b85  lea     rcx, [rsi+rcx*2]
0x180028b89  test    ebx, ebx
0x180028b8b  jnz     loc_180028ABE
0x180028b91  jmp     loc_18002895E
0x180028b96  cmp     byte ptr [rdi+1], 0FEh
0x180028b9a  jnz     loc_180028A4E
0x180028ba0  shr     ebx, 1
0x180028ba2  lea     rcx, [rdi+2]; Src
0x180028ba6  lea     r8, [rbp+arg_18]
0x180028baa  lea     edx, [rbx-1]
0x180028bad  call    PwstrParsePrinterIniFileW
0x180028bb2  jmp     loc_180028A5C
0x180028bb7  test    rax, rax
0x180028bba  jz      loc_180028A71
0x180028bc0  mov     rcx, rax; hMem
0x180028bc3  call    cs:__imp_LocalFree
0x180028bca  nop     dword ptr [rax+rax+00h]
0x180028bcf  jmp     loc_180028A71
```
