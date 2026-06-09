# BProcessPrinterIniFile

- ea: `0x180028170`
- end: `0x1800283d5`
- name: `BProcessPrinterIniFile`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180027d9c`

## callees

- `0x180028170`
- `0x1800283e0`
- `0x180028454`
- `0x180050048`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180028243`
- `KERNEL32!MapViewOfFile` at `0x180028243`
- `KERNEL32!GetFileTime` at `0x180028331`
- `KERNEL32!GetFileTime` at `0x180028331`
- `KERNEL32!CloseHandle` at `0x18002824f`
- `KERNEL32!CloseHandle` at `0x18002825d`
- `KERNEL32!CloseHandle` at `0x1800282a8`
- `KERNEL32!CloseHandle` at `0x18002836f`
- `KERNEL32!CloseHandle` at `0x18002824f`
- `KERNEL32!CloseHandle` at `0x18002825d`
- `KERNEL32!CloseHandle` at `0x1800282a8`
- `KERNEL32!CloseHandle` at `0x18002836f`
- `KERNEL32!CreateFileW` at `0x1800281ec`
- `KERNEL32!CreateFileW` at `0x180028312`
- `KERNEL32!CreateFileW` at `0x1800281ec`
- `KERNEL32!CreateFileW` at `0x180028312`
- `KERNEL32!CompareFileTime` at `0x180028348`
- `KERNEL32!CompareFileTime` at `0x180028348`
- `KERNEL32!LocalFree` at `0x1800283ca`
- `KERNEL32!LocalFree` at `0x1800283ca`
- `KERNEL32!UnmapViewOfFile` at `0x18002829f`
- `KERNEL32!UnmapViewOfFile` at `0x18002829f`
- `KERNEL32!GetFileSize` at `0x180028200`
- `KERNEL32!GetFileSize` at `0x180028200`
- `KERNEL32!CreateFileMappingW` at `0x180028223`
- `KERNEL32!CreateFileMappingW` at `0x180028223`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, _QWORD *a3, int a4)
{
  __int64 v4; // rcx
  BOOL v7; // ebx
  const WCHAR *v8; // rdi
  HANDLE v10; // rax
  void *v11; // rsi
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  void *v14; // r14
  _BYTE *v15; // rdi
  void *v16; // rax
  __int64 v17; // rax
  const WCHAR *v18; // rcx
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
  v4 = *(_QWORD *)(a2 + 56);
  LODWORD(v26) = 0;
  v7 = 1;
  v8 = (const WCHAR *)PtstrSearchDependentFileWithExtension(v4);
  if ( v8 )
  {
    v17 = -1;
    do
      ++v17;
    while ( v8[v17] );
    if ( !PtstrSearchDependentFileWithExtension(&v8[v17 + 1]) )
      goto LABEL_4;
    v18 = *(const WCHAR **)(a2 + 56);
    v8 = 0;
    FileTime2 = 0;
    do
    {
      v19 = (const WCHAR *)PtstrSearchDependentFileWithExtension(v18);
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
        || (v15 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v14), !v15) )
      {
        CloseHandle(v11);
        return 0;
      }
      if ( FileSize >= 2 && *v15 == 0xFF && v15[1] == 0xFE )
        v16 = (void *)PwstrParsePrinterIniFileW(v15 + 2);
      else
        v16 = (void *)PwstrParsePrinterIniFileA(v15, FileSize, &v26);
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
0x180028170  mov     dword ptr [rsp-38h+arg_18], r9d
0x180028175  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x18002817a  push    rbp
0x18002817b  push    rbx
0x18002817c  push    rsi
0x18002817d  push    rdi
0x18002817e  push    r12
0x180028180  push    r14
0x180028182  push    r15
0x180028184  mov     rbp, rsp
0x180028187  sub     rsp, 40h
0x18002818b  mov     rcx, [rdx+38h]
0x18002818f  xor     r12d, r12d
0x180028192  mov     r15, r8
0x180028195  mov     dword ptr [rbp+arg_18], r12d
0x180028199  mov     rsi, rdx
0x18002819c  lea     ebx, [r12+1]
0x1800281a1  call    PtstrSearchDependentFileWithExtension
0x1800281a6  mov     rdi, rax
0x1800281a9  test    rax, rax
0x1800281ac  jnz     loc_180028360
0x1800281b2  mov     eax, ebx
0x1800281b4  add     rsp, 40h
0x1800281b8  pop     r15
0x1800281ba  pop     r14
0x1800281bc  pop     r12
0x1800281be  pop     rdi
0x1800281bf  pop     rsi
0x1800281c0  pop     rbx
0x1800281c1  pop     rbp
0x1800281c2  retn
0x1800281c3  test    rdi, rdi
0x1800281c6  jz      short loc_1800281B2
0x1800281c8  xor     r9d, r9d; lpSecurityAttributes
0x1800281cb  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1800281d0  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800281d8  mov     edx, 80000000h; dwDesiredAccess
0x1800281dd  mov     rcx, rdi; lpFileName
0x1800281e0  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1800281e8  lea     r8d, [r9+1]; dwShareMode
0x1800281ec  call    cs:__imp_CreateFileW
0x1800281f2  mov     rsi, rax
0x1800281f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800281f9  jz      short loc_180028263
0x1800281fb  xor     edx, edx; lpFileSizeHigh
0x1800281fd  mov     rcx, rax; hFile
0x180028200  call    cs:__imp_GetFileSize
0x180028206  mov     ebx, eax
0x180028208  cmp     eax, 0FFFFFFFFh
0x18002820b  jz      short loc_18002825A
0x18002820d  xor     r9d, r9d; dwMaximumSizeHigh
0x180028210  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x180028215  xor     edx, edx; lpFileMappingAttributes
0x180028217  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18002821c  mov     rcx, rsi; hFile
0x18002821f  lea     r8d, [r9+2]; flProtect
0x180028223  call    cs:__imp_CreateFileMappingW
0x180028229  mov     r14, rax
0x18002822c  test    rax, rax
0x18002822f  jz      short loc_18002825A
0x180028231  xor     r9d, r9d; dwFileOffsetLow
0x180028234  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180028239  xor     r8d, r8d; dwFileOffsetHigh
0x18002823c  mov     rcx, rax; hFileMappingObject
0x18002823f  lea     edx, [r9+4]; dwDesiredAccess
0x180028243  call    cs:__imp_MapViewOfFile
0x180028249  mov     rcx, r14; hObject
0x18002824c  mov     rdi, rax
0x18002824f  call    cs:__imp_CloseHandle
0x180028255  test    rdi, rdi
0x180028258  jnz     short loc_18002826B
0x18002825a  mov     rcx, rsi; hObject
0x18002825d  call    cs:__imp_CloseHandle
0x180028263  mov     ebx, r12d
0x180028266  jmp     loc_1800281B2
0x18002826b  cmp     ebx, 2
0x18002826e  jb      short loc_180028279
0x180028270  cmp     byte ptr [rdi], 0FFh
0x180028273  jz      loc_18002839D
0x180028279  lea     r8, [rbp+arg_18]
0x18002827d  mov     edx, ebx
0x18002827f  mov     rcx, rdi
0x180028282  call    PwstrParsePrinterIniFileA
0x180028287  test    rax, rax
0x18002828a  mov     ebx, r12d
0x18002828d  setnz   bl
0x180028290  test    r15, r15
0x180028293  jz      loc_1800283BE
0x180028299  mov     [r15], rax
0x18002829c  mov     rcx, rdi; lpBaseAddress
0x18002829f  call    cs:__imp_UnmapViewOfFile
0x1800282a5  mov     rcx, rsi; hObject
0x1800282a8  call    cs:__imp_CloseHandle
0x1800282ae  jmp     loc_1800281B2
0x1800282b3  inc     rax
0x1800282b6  cmp     [rdi+rax*2], r12w
0x1800282bb  jnz     short loc_1800282B3
0x1800282bd  inc     rax
0x1800282c0  lea     rcx, [rdi+rax*2]
0x1800282c4  call    PtstrSearchDependentFileWithExtension
0x1800282c9  test    rax, rax
0x1800282cc  jz      loc_1800281C8
0x1800282d2  mov     rcx, [rsi+38h]
0x1800282d6  mov     rdi, r12
0x1800282d9  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x1800282dd  call    PtstrSearchDependentFileWithExtension
0x1800282e2  mov     rsi, rax
0x1800282e5  test    rax, rax
0x1800282e8  jz      loc_1800281C3
0x1800282ee  xor     r9d, r9d; lpSecurityAttributes
0x1800282f1  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1800282f6  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800282fe  mov     edx, 80000000h; dwDesiredAccess
0x180028303  mov     rcx, rax; lpFileName
0x180028306  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x18002830e  lea     r8d, [r9+1]; dwShareMode
0x180028312  call    cs:__imp_CreateFileW
0x180028318  mov     r14, rax
0x18002831b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002831f  jz      short loc_180028377
0x180028321  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180028325  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180028329  xor     r8d, r8d; lpLastAccessTime
0x18002832c  xor     edx, edx; lpCreationTime
0x18002832e  mov     rcx, rax; hFile
0x180028331  call    cs:__imp_GetFileTime
0x180028337  test    eax, eax
0x180028339  jz      short loc_180028369
0x18002833b  test    rdi, rdi
0x18002833e  jz      short loc_180028353
0x180028340  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180028344  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180028348  call    cs:__imp_CompareFileTime
0x18002834e  cmp     eax, 1
0x180028351  jnz     short loc_18002836C
0x180028353  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x180028357  mov     rdi, rsi
0x18002835a  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18002835e  jmp     short loc_18002836C
0x180028360  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028364  jmp     loc_1800282B3
0x180028369  mov     ebx, r12d
0x18002836c  mov     rcx, r14; hObject
0x18002836f  call    cs:__imp_CloseHandle
0x180028375  jmp     short loc_18002837A
0x180028377  mov     ebx, r12d
0x18002837a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002837e  inc     rax
0x180028381  cmp     [rsi+rax*2], r12w
0x180028386  jnz     short loc_18002837E
0x180028388  lea     rcx, [rax+1]
0x18002838c  lea     rcx, [rsi+rcx*2]
0x180028390  test    ebx, ebx
0x180028392  jnz     loc_1800282DD
0x180028398  jmp     loc_1800281B2
0x18002839d  cmp     byte ptr [rdi+1], 0FEh
0x1800283a1  jnz     loc_180028279
0x1800283a7  shr     ebx, 1
0x1800283a9  lea     rcx, [rdi+2]; Src
0x1800283ad  lea     r8, [rbp+arg_18]
0x1800283b1  lea     edx, [rbx-1]
0x1800283b4  call    PwstrParsePrinterIniFileW
0x1800283b9  jmp     loc_180028287
0x1800283be  test    rax, rax
0x1800283c1  jz      loc_18002829C
0x1800283c7  mov     rcx, rax; hMem
0x1800283ca  call    cs:__imp_LocalFree
0x1800283d0  jmp     loc_18002829C
```
