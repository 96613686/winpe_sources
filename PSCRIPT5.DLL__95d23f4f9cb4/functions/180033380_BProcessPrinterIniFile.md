# BProcessPrinterIniFile

- ea: `0x180033380`
- end: `0x1800335e7`
- name: `BProcessPrinterIniFile`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180030c2c`

## callees

- `0x18002f0cc`
- `0x180033380`
- `0x1800335f0`
- `0x180033810`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x18003354c`
- `KERNEL32!MapViewOfFile` at `0x18003354c`
- `KERNEL32!CreateFileMappingW` at `0x180033528`
- `KERNEL32!CreateFileMappingW` at `0x180033528`
- `KERNEL32!GetFileSize` at `0x180033501`
- `KERNEL32!GetFileSize` at `0x180033501`
- `KERNEL32!GetFileTime` at `0x180033459`
- `KERNEL32!GetFileTime` at `0x180033459`
- `KERNEL32!CompareFileTime` at `0x180033470`
- `KERNEL32!CompareFileTime` at `0x180033470`
- `KERNEL32!CreateFileW` at `0x18003343a`
- `KERNEL32!CreateFileW` at `0x1800334e9`
- `KERNEL32!CreateFileW` at `0x18003343a`
- `KERNEL32!CreateFileW` at `0x1800334e9`
- `KERNEL32!CloseHandle` at `0x18003348e`
- `KERNEL32!CloseHandle` at `0x180033558`
- `KERNEL32!CloseHandle` at `0x1800335c2`
- `KERNEL32!CloseHandle` at `0x1800335cd`
- `KERNEL32!CloseHandle` at `0x18003348e`
- `KERNEL32!CloseHandle` at `0x180033558`
- `KERNEL32!CloseHandle` at `0x1800335c2`
- `KERNEL32!CloseHandle` at `0x1800335cd`
- `KERNEL32!LocalFree` at `0x1800335b0`
- `KERNEL32!LocalFree` at `0x1800335b0`
- `KERNEL32!UnmapViewOfFile` at `0x1800335b9`
- `KERNEL32!UnmapViewOfFile` at `0x1800335b9`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, _QWORD *a3)
{
  BOOL v5; // ebx
  const WCHAR *v6; // rdi
  __int64 v7; // rax
  const WCHAR *v8; // rcx
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
  const CHAR *v19; // rdi
  void *v20; // rax
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+48h] BYREF
  int v24; // [rsp+98h] [rbp+58h]

  LastWriteTime = a1;
  v24 = 0;
  v5 = 1;
  v6 = (const WCHAR *)PtstrSearchDependentFileWithExtension(*(_QWORD *)(a2 + 56), L".INI");
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( !PtstrSearchDependentFileWithExtension(&v6[v7 + 1], L".INI") )
      goto LABEL_20;
    v8 = *(const WCHAR **)(a2 + 56);
    v6 = 0;
    FileTime2 = 0;
    do
    {
      v9 = (const WCHAR *)PtstrSearchDependentFileWithExtension(v8, L".INI");
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
            v19 = (const CHAR *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
            CloseHandle(v18);
            if ( v19 )
            {
              if ( FileSize >= 2 && *v19 == -1 && v19[1] == -2 )
                v20 = (void *)PwstrParsePrinterIniFileW((void *)(v19 + 2));
              else
                v20 = (void *)PwstrParsePrinterIniFileA(v19);
              v5 = v20 != 0;
              if ( a3 )
              {
                *a3 = v20;
              }
              else if ( v20 )
              {
                LocalFree(v20);
              }
              UnmapViewOfFile(v19);
              CloseHandle(v15);
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
0x180033380  mov     [rsp-38h+arg_18], r9d
0x180033385  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x18003338a  push    rbp
0x18003338b  push    rbx
0x18003338c  push    rsi
0x18003338d  push    rdi
0x18003338e  push    r12
0x180033390  push    r14
0x180033392  push    r15
0x180033394  mov     rbp, rsp
0x180033397  sub     rsp, 40h
0x18003339b  mov     rsi, rdx
0x18003339e  xor     r12d, r12d
0x1800333a1  lea     rdx, aIni; ".INI"
0x1800333a8  mov     [rbp+arg_18], r12d
0x1800333ac  mov     r15, r8
0x1800333af  mov     rcx, [rsi+38h]
0x1800333b3  lea     ebx, [r12+1]
0x1800333b8  call    PtstrSearchDependentFileWithExtension
0x1800333bd  mov     rdi, rax
0x1800333c0  test    rax, rax
0x1800333c3  jz      loc_1800335D6
0x1800333c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800333cd  inc     rax
0x1800333d0  cmp     [rdi+rax*2], r12w
0x1800333d5  jnz     short loc_1800333CD
0x1800333d7  inc     rax
0x1800333da  lea     rdx, aIni; ".INI"
0x1800333e1  lea     rcx, [rdi+rax*2]
0x1800333e5  call    PtstrSearchDependentFileWithExtension
0x1800333ea  test    rax, rax
0x1800333ed  jz      loc_1800334C5
0x1800333f3  mov     rcx, [rsi+38h]
0x1800333f7  mov     rdi, r12
0x1800333fa  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x1800333fe  lea     rdx, aIni; ".INI"
0x180033405  call    PtstrSearchDependentFileWithExtension
0x18003340a  mov     rsi, rax
0x18003340d  test    rax, rax
0x180033410  jz      loc_1800334BC
0x180033416  xor     r9d, r9d; lpSecurityAttributes
0x180033419  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x18003341e  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180033426  mov     edx, 80000000h; dwDesiredAccess
0x18003342b  mov     rcx, rax; lpFileName
0x18003342e  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x180033436  lea     r8d, [r9+1]; dwShareMode
0x18003343a  call    cs:__imp_CreateFileW
0x180033440  mov     r14, rax
0x180033443  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033447  jz      short loc_180033496
0x180033449  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x18003344d  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180033451  xor     r8d, r8d; lpLastAccessTime
0x180033454  xor     edx, edx; lpCreationTime
0x180033456  mov     rcx, rax; hFile
0x180033459  call    cs:__imp_GetFileTime
0x18003345f  test    eax, eax
0x180033461  jz      short loc_180033488
0x180033463  test    rdi, rdi
0x180033466  jz      short loc_18003347B
0x180033468  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18003346c  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180033470  call    cs:__imp_CompareFileTime
0x180033476  cmp     eax, 1
0x180033479  jnz     short loc_18003348B
0x18003347b  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x18003347f  mov     rdi, rsi
0x180033482  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180033486  jmp     short loc_18003348B
0x180033488  mov     ebx, r12d
0x18003348b  mov     rcx, r14; hObject
0x18003348e  call    cs:__imp_CloseHandle
0x180033494  jmp     short loc_180033499
0x180033496  mov     ebx, r12d
0x180033499  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003349d  inc     rax
0x1800334a0  cmp     [rsi+rax*2], r12w
0x1800334a5  jnz     short loc_18003349D
0x1800334a7  lea     rcx, [rax+1]
0x1800334ab  lea     rcx, [rsi+rcx*2]
0x1800334af  test    ebx, ebx
0x1800334b1  jnz     loc_1800333FE
0x1800334b7  jmp     loc_1800335D6
0x1800334bc  test    rdi, rdi
0x1800334bf  jz      loc_1800335D6
0x1800334c5  xor     r9d, r9d; lpSecurityAttributes
0x1800334c8  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1800334cd  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800334d5  mov     edx, 80000000h; dwDesiredAccess
0x1800334da  mov     rcx, rdi; lpFileName
0x1800334dd  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1800334e5  lea     r8d, [r9+1]; dwShareMode
0x1800334e9  call    cs:__imp_CreateFileW
0x1800334ef  mov     rsi, rax
0x1800334f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800334f6  jz      loc_1800335D3
0x1800334fc  xor     edx, edx; lpFileSizeHigh
0x1800334fe  mov     rcx, rax; hFile
0x180033501  call    cs:__imp_GetFileSize
0x180033507  mov     ebx, eax
0x180033509  cmp     eax, 0FFFFFFFFh
0x18003350c  jz      loc_1800335CA
0x180033512  xor     r9d, r9d; dwMaximumSizeHigh
0x180033515  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x18003351a  xor     edx, edx; lpFileMappingAttributes
0x18003351c  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180033521  mov     rcx, rsi; hFile
0x180033524  lea     r8d, [r9+2]; flProtect
0x180033528  call    cs:__imp_CreateFileMappingW
0x18003352e  mov     r14, rax
0x180033531  test    rax, rax
0x180033534  jz      loc_1800335CA
0x18003353a  xor     r9d, r9d; dwFileOffsetLow
0x18003353d  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180033542  xor     r8d, r8d; dwFileOffsetHigh
0x180033545  mov     rcx, rax; hFileMappingObject
0x180033548  lea     edx, [r9+4]; dwDesiredAccess
0x18003354c  call    cs:__imp_MapViewOfFile
0x180033552  mov     rcx, r14; hObject
0x180033555  mov     rdi, rax
0x180033558  call    cs:__imp_CloseHandle
0x18003355e  test    rdi, rdi
0x180033561  jz      short loc_1800335CA
0x180033563  cmp     ebx, 2
0x180033566  jb      short loc_180033587
0x180033568  cmp     byte ptr [rdi], 0FFh
0x18003356b  jnz     short loc_180033587
0x18003356d  cmp     byte ptr [rdi+1], 0FEh
0x180033571  jnz     short loc_180033587
0x180033573  shr     ebx, 1
0x180033575  lea     rcx, [rdi+2]; Src
0x180033579  lea     r8, [rbp+arg_18]
0x18003357d  lea     edx, [rbx-1]
0x180033580  call    PwstrParsePrinterIniFileW
0x180033585  jmp     short loc_180033595
0x180033587  lea     r8, [rbp+arg_18]
0x18003358b  mov     edx, ebx
0x18003358d  mov     rcx, rdi; lpMultiByteStr
0x180033590  call    PwstrParsePrinterIniFileA
0x180033595  test    rax, rax
0x180033598  mov     ebx, r12d
0x18003359b  setnz   bl
0x18003359e  test    r15, r15
0x1800335a1  jz      short loc_1800335A8
0x1800335a3  mov     [r15], rax
0x1800335a6  jmp     short loc_1800335B6
0x1800335a8  test    rax, rax
0x1800335ab  jz      short loc_1800335B6
0x1800335ad  mov     rcx, rax; hMem
0x1800335b0  call    cs:__imp_LocalFree
0x1800335b6  mov     rcx, rdi; lpBaseAddress
0x1800335b9  call    cs:__imp_UnmapViewOfFile
0x1800335bf  mov     rcx, rsi; hObject
0x1800335c2  call    cs:__imp_CloseHandle
0x1800335c8  jmp     short loc_1800335D6
0x1800335ca  mov     rcx, rsi; hObject
0x1800335cd  call    cs:__imp_CloseHandle
0x1800335d3  mov     ebx, r12d
0x1800335d6  mov     eax, ebx
0x1800335d8  add     rsp, 40h
0x1800335dc  pop     r15
0x1800335de  pop     r14
0x1800335e0  pop     r12
0x1800335e2  pop     rdi
0x1800335e3  pop     rsi
0x1800335e4  pop     rbx
0x1800335e5  pop     rbp
0x1800335e6  retn
```
