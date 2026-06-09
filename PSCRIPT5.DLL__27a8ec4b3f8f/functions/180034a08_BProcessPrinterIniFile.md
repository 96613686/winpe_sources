# BProcessPrinterIniFile

- ea: `0x180034a08`
- end: `0x180034cab`
- name: `BProcessPrinterIniFile`
- size: `675`
- prototype: `_BOOL8 __fastcall(struct _FILETIME, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003224c`

## callees

- `0x1800305d4`
- `0x180031330`
- `0x180034a08`
- `0x180034cb4`
- `0x180034ee8`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180034bfe`
- `KERNEL32!MapViewOfFile` at `0x180034bfe`
- `KERNEL32!CreateFileMappingW` at `0x180034bd4`
- `KERNEL32!CreateFileMappingW` at `0x180034bd4`
- `KERNEL32!GetFileSize` at `0x180034ba7`
- `KERNEL32!GetFileSize` at `0x180034ba7`
- `KERNEL32!GetFileTime` at `0x180034ae7`
- `KERNEL32!GetFileTime` at `0x180034ae7`
- `KERNEL32!CompareFileTime` at `0x180034b04`
- `KERNEL32!CompareFileTime` at `0x180034b04`
- `KERNEL32!CreateFileW` at `0x180034ac2`
- `KERNEL32!CreateFileW` at `0x180034b89`
- `KERNEL32!CreateFileW` at `0x180034ac2`
- `KERNEL32!CreateFileW` at `0x180034b89`
- `KERNEL32!CloseHandle` at `0x180034b28`
- `KERNEL32!CloseHandle` at `0x180034c10`
- `KERNEL32!CloseHandle` at `0x180034c8a`
- `KERNEL32!CloseHandle` at `0x180034b28`
- `KERNEL32!CloseHandle` at `0x180034c10`
- `KERNEL32!CloseHandle` at `0x180034c8a`
- `KERNEL32!LocalFree` at `0x180034c6e`
- `KERNEL32!LocalFree` at `0x180034c6e`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, _QWORD *a3)
{
  BOOL v5; // ebx
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  const WCHAR *v9; // rax
  const WCHAR *v10; // rsi
  HANDLE FileW; // rax
  void *v12; // r14
  __int64 v13; // rax
  HANDLE v14; // rax
  void *v15; // rsi
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  void *v18; // r14
  wint_t *v19; // rdi
  void *v20; // rax
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+48h] BYREF
  int v24; // [rsp+98h] [rbp+58h] BYREF

  LastWriteTime = a1;
  v24 = 0;
  v5 = 1;
  v6 = PtstrSearchDependentFileWithExtension(*(const wchar_t **)(a2 + 56), L".INI");
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( !PtstrSearchDependentFileWithExtension(&v6[v7 + 1], L".INI") )
      goto LABEL_20;
    v8 = *(const wchar_t **)(a2 + 56);
    v6 = 0;
    FileTime2 = 0;
    do
    {
      v9 = PtstrSearchDependentFileWithExtension(v8, L".INI");
      v10 = v9;
      if ( !v9 )
        break;
      FileW = CreateFileW(v9, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v12 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v5 = 0;
      }
      else
      {
        LastWriteTime = 0;
        if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
        {
          if ( !v6 || CompareFileTime(&LastWriteTime, &FileTime2) == 1 )
          {
            v6 = v10;
            FileTime2 = LastWriteTime;
          }
        }
        else
        {
          v5 = 0;
        }
        CloseHandle(v12);
      }
      v13 = -1;
      do
        ++v13;
      while ( v10[v13] );
      v8 = &v10[v13 + 1];
    }
    while ( v5 );
    if ( v6 )
    {
LABEL_20:
      v14 = CreateFileW(v6, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v15 = v14;
      if ( v14 != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(v14, 0);
        if ( FileSize != -1 )
        {
          FileMappingW = CreateFileMappingW(v15, 0, 2u, 0, 0, 0);
          v18 = FileMappingW;
          if ( FileMappingW )
          {
            v19 = (wint_t *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
            CloseHandle(v18);
            if ( v19 )
            {
              if ( FileSize >= 2 && *(_BYTE *)v19 == 0xFF && *((_BYTE *)v19 + 1) == 0xFE )
                v20 = PwstrParsePrinterIniFileW(v19 + 1, (FileSize >> 1) - 1, &v24);
              else
                v20 = PwstrParsePrinterIniFileA((LPCCH)v19, FileSize, &v24);
              v5 = v20 != 0;
              if ( a3 )
              {
                *a3 = v20;
              }
              else if ( v20 )
              {
                LocalFree(v20);
              }
              UnmapFileFromMemory(v19, v15);
              return v5;
            }
          }
        }
        CloseHandle(v15);
      }
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180034a08  mov     [rsp-38h+arg_18], r9d
0x180034a0d  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x180034a12  push    rbp
0x180034a13  push    rbx
0x180034a14  push    rsi
0x180034a15  push    rdi
0x180034a16  push    r12
0x180034a18  push    r14
0x180034a1a  push    r15
0x180034a1c  mov     rbp, rsp
0x180034a1f  sub     rsp, 40h
0x180034a23  mov     rsi, rdx
0x180034a26  xor     r12d, r12d
0x180034a29  lea     rdx, aIni; ".INI"
0x180034a30  mov     [rbp+arg_18], r12d
0x180034a34  mov     r15, r8
0x180034a37  mov     rcx, [rsi+38h]
0x180034a3b  lea     ebx, [r12+1]
0x180034a40  call    PtstrSearchDependentFileWithExtension
0x180034a45  mov     rdi, rax
0x180034a48  test    rax, rax
0x180034a4b  jz      loc_180034C99
0x180034a51  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034a55  inc     rax
0x180034a58  cmp     [rdi+rax*2], r12w
0x180034a5d  jnz     short loc_180034A55
0x180034a5f  inc     rax
0x180034a62  lea     rdx, aIni; ".INI"
0x180034a69  lea     rcx, [rdi+rax*2]
0x180034a6d  call    PtstrSearchDependentFileWithExtension
0x180034a72  test    rax, rax
0x180034a75  jz      loc_180034B65
0x180034a7b  mov     rcx, [rsi+38h]
0x180034a7f  mov     rdi, r12
0x180034a82  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x180034a86  lea     rdx, aIni; ".INI"
0x180034a8d  call    PtstrSearchDependentFileWithExtension
0x180034a92  mov     rsi, rax
0x180034a95  test    rax, rax
0x180034a98  jz      loc_180034B5C
0x180034a9e  xor     r9d, r9d; lpSecurityAttributes
0x180034aa1  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x180034aa6  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180034aae  mov     edx, 80000000h; dwDesiredAccess
0x180034ab3  mov     rcx, rax; lpFileName
0x180034ab6  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180034abe  lea     r8d, [r9+1]; dwShareMode
0x180034ac2  call    cs:__imp_CreateFileW
0x180034ac9  nop     dword ptr [rax+rax+00h]
0x180034ace  mov     r14, rax
0x180034ad1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034ad5  jz      short loc_180034B36
0x180034ad7  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180034adb  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180034adf  xor     r8d, r8d; lpLastAccessTime
0x180034ae2  xor     edx, edx; lpCreationTime
0x180034ae4  mov     rcx, rax; hFile
0x180034ae7  call    cs:__imp_GetFileTime
0x180034aee  nop     dword ptr [rax+rax+00h]
0x180034af3  test    eax, eax
0x180034af5  jz      short loc_180034B22
0x180034af7  test    rdi, rdi
0x180034afa  jz      short loc_180034B15
0x180034afc  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180034b00  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180034b04  call    cs:__imp_CompareFileTime
0x180034b0b  nop     dword ptr [rax+rax+00h]
0x180034b10  cmp     eax, 1
0x180034b13  jnz     short loc_180034B25
0x180034b15  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x180034b19  mov     rdi, rsi
0x180034b1c  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180034b20  jmp     short loc_180034B25
0x180034b22  mov     ebx, r12d
0x180034b25  mov     rcx, r14; hObject
0x180034b28  call    cs:__imp_CloseHandle
0x180034b2f  nop     dword ptr [rax+rax+00h]
0x180034b34  jmp     short loc_180034B39
0x180034b36  mov     ebx, r12d
0x180034b39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034b3d  inc     rax
0x180034b40  cmp     [rsi+rax*2], r12w
0x180034b45  jnz     short loc_180034B3D
0x180034b47  lea     rcx, [rax+1]
0x180034b4b  lea     rcx, [rsi+rcx*2]
0x180034b4f  test    ebx, ebx
0x180034b51  jnz     loc_180034A86
0x180034b57  jmp     loc_180034C99
0x180034b5c  test    rdi, rdi
0x180034b5f  jz      loc_180034C99
0x180034b65  xor     r9d, r9d; lpSecurityAttributes
0x180034b68  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x180034b6d  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180034b75  mov     edx, 80000000h; dwDesiredAccess
0x180034b7a  mov     rcx, rdi; lpFileName
0x180034b7d  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180034b85  lea     r8d, [r9+1]; dwShareMode
0x180034b89  call    cs:__imp_CreateFileW
0x180034b90  nop     dword ptr [rax+rax+00h]
0x180034b95  mov     rsi, rax
0x180034b98  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034b9c  jz      loc_180034C96
0x180034ba2  xor     edx, edx; lpFileSizeHigh
0x180034ba4  mov     rcx, rax; hFile
0x180034ba7  call    cs:__imp_GetFileSize
0x180034bae  nop     dword ptr [rax+rax+00h]
0x180034bb3  mov     ebx, eax
0x180034bb5  cmp     eax, 0FFFFFFFFh
0x180034bb8  jz      loc_180034C87
0x180034bbe  xor     r9d, r9d; dwMaximumSizeHigh
0x180034bc1  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x180034bc6  xor     edx, edx; lpFileMappingAttributes
0x180034bc8  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180034bcd  mov     rcx, rsi; hFile
0x180034bd0  lea     r8d, [r9+2]; flProtect
0x180034bd4  call    cs:__imp_CreateFileMappingW
0x180034bdb  nop     dword ptr [rax+rax+00h]
0x180034be0  mov     r14, rax
0x180034be3  test    rax, rax
0x180034be6  jz      loc_180034C87
0x180034bec  xor     r9d, r9d; dwFileOffsetLow
0x180034bef  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180034bf4  xor     r8d, r8d; dwFileOffsetHigh
0x180034bf7  mov     rcx, rax; hFileMappingObject
0x180034bfa  lea     edx, [r9+4]; dwDesiredAccess
0x180034bfe  call    cs:__imp_MapViewOfFile
0x180034c05  nop     dword ptr [rax+rax+00h]
0x180034c0a  mov     rcx, r14; hObject
0x180034c0d  mov     rdi, rax
0x180034c10  call    cs:__imp_CloseHandle
0x180034c17  nop     dword ptr [rax+rax+00h]
0x180034c1c  test    rdi, rdi
0x180034c1f  jz      short loc_180034C87
0x180034c21  cmp     ebx, 2
0x180034c24  jb      short loc_180034C45
0x180034c26  cmp     byte ptr [rdi], 0FFh
0x180034c29  jnz     short loc_180034C45
0x180034c2b  cmp     byte ptr [rdi+1], 0FEh
0x180034c2f  jnz     short loc_180034C45
0x180034c31  shr     ebx, 1
0x180034c33  lea     rcx, [rdi+2]; Src
0x180034c37  lea     r8, [rbp+arg_18]
0x180034c3b  lea     edx, [rbx-1]
0x180034c3e  call    PwstrParsePrinterIniFileW
0x180034c43  jmp     short loc_180034C53
0x180034c45  lea     r8, [rbp+arg_18]
0x180034c49  mov     edx, ebx
0x180034c4b  mov     rcx, rdi; lpMultiByteStr
0x180034c4e  call    PwstrParsePrinterIniFileA
0x180034c53  test    rax, rax
0x180034c56  mov     ebx, r12d
0x180034c59  setnz   bl
0x180034c5c  test    r15, r15
0x180034c5f  jz      short loc_180034C66
0x180034c61  mov     [r15], rax
0x180034c64  jmp     short loc_180034C7A
0x180034c66  test    rax, rax
0x180034c69  jz      short loc_180034C7A
0x180034c6b  mov     rcx, rax; hMem
0x180034c6e  call    cs:__imp_LocalFree
0x180034c75  nop     dword ptr [rax+rax+00h]
0x180034c7a  mov     rdx, rsi
0x180034c7d  mov     rcx, rdi
0x180034c80  call    UnmapFileFromMemory
0x180034c85  jmp     short loc_180034C99
0x180034c87  mov     rcx, rsi; hObject
0x180034c8a  call    cs:__imp_CloseHandle
0x180034c91  nop     dword ptr [rax+rax+00h]
0x180034c96  mov     ebx, r12d
0x180034c99  mov     eax, ebx
0x180034c9b  add     rsp, 40h
0x180034c9f  pop     r15
0x180034ca1  pop     r14
0x180034ca3  pop     r12
0x180034ca5  pop     rdi
0x180034ca6  pop     rsi
0x180034ca7  pop     rbx
0x180034ca8  pop     rbp
0x180034ca9  retn
```
