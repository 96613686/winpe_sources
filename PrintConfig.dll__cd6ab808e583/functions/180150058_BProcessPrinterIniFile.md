# BProcessPrinterIniFile

- ea: `0x180150058`
- end: `0x1801502a3`
- name: `BProcessPrinterIniFile`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18014e970`

## callees

- `0x180149ae8`
- `0x18014ac64`
- `0x180150058`
- `0x1801502ac`
- `0x1801504cc`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1801501eb`
- `KERNEL32!CreateFileMappingW` at `0x1801501eb`
- `KERNEL32!MapViewOfFile` at `0x18015020f`
- `KERNEL32!MapViewOfFile` at `0x18015020f`
- `KERNEL32!GetFileSize` at `0x1801501c4`
- `KERNEL32!GetFileSize` at `0x1801501c4`
- `KERNEL32!CreateFileW` at `0x1801500fd`
- `KERNEL32!CreateFileW` at `0x1801501ac`
- `KERNEL32!CreateFileW` at `0x1801500fd`
- `KERNEL32!CreateFileW` at `0x1801501ac`
- `KERNEL32!CloseHandle` at `0x180150151`
- `KERNEL32!CloseHandle` at `0x18015021b`
- `KERNEL32!CloseHandle` at `0x180150289`
- `KERNEL32!CloseHandle` at `0x180150151`
- `KERNEL32!CloseHandle` at `0x18015021b`
- `KERNEL32!CloseHandle` at `0x180150289`
- `KERNEL32!LocalFree` at `0x180150273`
- `KERNEL32!LocalFree` at `0x180150273`
- `KERNEL32!CompareFileTime` at `0x180150133`
- `KERNEL32!CompareFileTime` at `0x180150133`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18015011c`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18015011c`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, _QWORD *a3, int a4)
{
  __int64 v4; // rcx
  BOOL v7; // ebx
  const WCHAR *v8; // rdi
  __int64 v9; // rax
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rax
  const WCHAR *v12; // rsi
  HANDLE FileW; // rax
  void *v14; // r14
  __int64 v15; // rax
  HANDLE v16; // rax
  void *v17; // rsi
  DWORD FileSize; // ebx
  HANDLE FileMappingW; // rax
  void *v20; // r14
  const CHAR *v21; // rdi
  void *v22; // rax
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+48h] BYREF
  int v26; // [rsp+98h] [rbp+58h]

  v26 = a4;
  LastWriteTime = a1;
  v4 = *(_QWORD *)(a2 + 56);
  v26 = 0;
  v7 = 1;
  v8 = (const WCHAR *)PtstrSearchDependentFileWithExtension(v4);
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( !PtstrSearchDependentFileWithExtension(&v8[v9 + 1]) )
      goto LABEL_20;
    v10 = *(const WCHAR **)(a2 + 56);
    v8 = 0;
    FileTime2 = 0;
    do
    {
      v11 = (const WCHAR *)PtstrSearchDependentFileWithExtension(v10);
      v12 = v11;
      if ( !v11 )
        break;
      FileW = CreateFileW(v11, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v14 = FileW;
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
            v8 = v12;
            FileTime2 = LastWriteTime;
          }
        }
        else
        {
          v7 = 0;
        }
        CloseHandle(v14);
      }
      v15 = -1;
      do
        ++v15;
      while ( v12[v15] );
      v10 = &v12[v15 + 1];
    }
    while ( v7 );
    if ( v8 )
    {
LABEL_20:
      v16 = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v17 = v16;
      if ( v16 != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(v16, 0);
        if ( FileSize != -1 )
        {
          FileMappingW = CreateFileMappingW(v17, 0, 2u, 0, 0, 0);
          v20 = FileMappingW;
          if ( FileMappingW )
          {
            v21 = (const CHAR *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
            CloseHandle(v20);
            if ( v21 )
            {
              if ( FileSize >= 2 && *v21 == -1 && v21[1] == -2 )
                v22 = (void *)PwstrParsePrinterIniFileW((void *)(v21 + 2));
              else
                v22 = (void *)PwstrParsePrinterIniFileA(v21);
              v7 = v22 != 0;
              if ( a3 )
              {
                *a3 = v22;
              }
              else if ( v22 )
              {
                LocalFree(v22);
              }
              UnmapFileFromMemory(v21, v17);
              return v7;
            }
          }
        }
        CloseHandle(v17);
      }
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180150058  mov     [rsp-38h+arg_18], r9d
0x18015005d  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x180150062  push    rbp
0x180150063  push    rbx
0x180150064  push    rsi
0x180150065  push    rdi
0x180150066  push    r12
0x180150068  push    r14
0x18015006a  push    r15
0x18015006c  mov     rbp, rsp
0x18015006f  sub     rsp, 40h
0x180150073  mov     rcx, [rdx+38h]
0x180150077  xor     r12d, r12d
0x18015007a  mov     r15, r8
0x18015007d  mov     [rbp+arg_18], r12d
0x180150081  mov     rsi, rdx
0x180150084  lea     ebx, [r12+1]
0x180150089  call    PtstrSearchDependentFileWithExtension
0x18015008e  mov     rdi, rax
0x180150091  test    rax, rax
0x180150094  jz      loc_180150292
0x18015009a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18015009e  inc     rax
0x1801500a1  cmp     [rdi+rax*2], r12w
0x1801500a6  jnz     short loc_18015009E
0x1801500a8  inc     rax
0x1801500ab  lea     rcx, [rdi+rax*2]
0x1801500af  call    PtstrSearchDependentFileWithExtension
0x1801500b4  test    rax, rax
0x1801500b7  jz      loc_180150188
0x1801500bd  mov     rcx, [rsi+38h]
0x1801500c1  mov     rdi, r12
0x1801500c4  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x1801500c8  call    PtstrSearchDependentFileWithExtension
0x1801500cd  mov     rsi, rax
0x1801500d0  test    rax, rax
0x1801500d3  jz      loc_18015017F
0x1801500d9  xor     r9d, r9d; lpSecurityAttributes
0x1801500dc  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1801500e1  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1801500e9  mov     edx, 80000000h; dwDesiredAccess
0x1801500ee  mov     rcx, rax; lpFileName
0x1801500f1  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1801500f9  lea     r8d, [r9+1]; dwShareMode
0x1801500fd  call    cs:__imp_CreateFileW
0x180150103  mov     r14, rax
0x180150106  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015010a  jz      short loc_180150159
0x18015010c  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180150110  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180150114  xor     r8d, r8d; lpLastAccessTime
0x180150117  xor     edx, edx; lpCreationTime
0x180150119  mov     rcx, rax; hFile
0x18015011c  call    cs:__imp_GetFileTime
0x180150122  test    eax, eax
0x180150124  jz      short loc_18015014B
0x180150126  test    rdi, rdi
0x180150129  jz      short loc_18015013E
0x18015012b  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18015012f  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180150133  call    cs:__imp_CompareFileTime
0x180150139  cmp     eax, 1
0x18015013c  jnz     short loc_18015014E
0x18015013e  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x180150142  mov     rdi, rsi
0x180150145  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180150149  jmp     short loc_18015014E
0x18015014b  mov     ebx, r12d
0x18015014e  mov     rcx, r14; hObject
0x180150151  call    cs:__imp_CloseHandle
0x180150157  jmp     short loc_18015015C
0x180150159  mov     ebx, r12d
0x18015015c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180150160  inc     rax
0x180150163  cmp     [rsi+rax*2], r12w
0x180150168  jnz     short loc_180150160
0x18015016a  lea     rcx, [rax+1]
0x18015016e  lea     rcx, [rsi+rcx*2]
0x180150172  test    ebx, ebx
0x180150174  jnz     loc_1801500C8
0x18015017a  jmp     loc_180150292
0x18015017f  test    rdi, rdi
0x180150182  jz      loc_180150292
0x180150188  xor     r9d, r9d; lpSecurityAttributes
0x18015018b  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x180150190  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180150198  mov     edx, 80000000h; dwDesiredAccess
0x18015019d  mov     rcx, rdi; lpFileName
0x1801501a0  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1801501a8  lea     r8d, [r9+1]; dwShareMode
0x1801501ac  call    cs:__imp_CreateFileW
0x1801501b2  mov     rsi, rax
0x1801501b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801501b9  jz      loc_18015028F
0x1801501bf  xor     edx, edx; lpFileSizeHigh
0x1801501c1  mov     rcx, rax; hFile
0x1801501c4  call    cs:__imp_GetFileSize
0x1801501ca  mov     ebx, eax
0x1801501cc  cmp     eax, 0FFFFFFFFh
0x1801501cf  jz      loc_180150286
0x1801501d5  xor     r9d, r9d; dwMaximumSizeHigh
0x1801501d8  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x1801501dd  xor     edx, edx; lpFileMappingAttributes
0x1801501df  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x1801501e4  mov     rcx, rsi; hFile
0x1801501e7  lea     r8d, [r9+2]; flProtect
0x1801501eb  call    cs:__imp_CreateFileMappingW
0x1801501f1  mov     r14, rax
0x1801501f4  test    rax, rax
0x1801501f7  jz      loc_180150286
0x1801501fd  xor     r9d, r9d; dwFileOffsetLow
0x180150200  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180150205  xor     r8d, r8d; dwFileOffsetHigh
0x180150208  mov     rcx, rax; hFileMappingObject
0x18015020b  lea     edx, [r9+4]; dwDesiredAccess
0x18015020f  call    cs:__imp_MapViewOfFile
0x180150215  mov     rcx, r14; hObject
0x180150218  mov     rdi, rax
0x18015021b  call    cs:__imp_CloseHandle
0x180150221  test    rdi, rdi
0x180150224  jz      short loc_180150286
0x180150226  cmp     ebx, 2
0x180150229  jb      short loc_18015024A
0x18015022b  cmp     byte ptr [rdi], 0FFh
0x18015022e  jnz     short loc_18015024A
0x180150230  cmp     byte ptr [rdi+1], 0FEh
0x180150234  jnz     short loc_18015024A
0x180150236  shr     ebx, 1
0x180150238  lea     rcx, [rdi+2]; Src
0x18015023c  lea     r8, [rbp+arg_18]
0x180150240  lea     edx, [rbx-1]
0x180150243  call    PwstrParsePrinterIniFileW
0x180150248  jmp     short loc_180150258
0x18015024a  lea     r8, [rbp+arg_18]
0x18015024e  mov     edx, ebx
0x180150250  mov     rcx, rdi; lpMultiByteStr
0x180150253  call    PwstrParsePrinterIniFileA
0x180150258  test    rax, rax
0x18015025b  mov     ebx, r12d
0x18015025e  setnz   bl
0x180150261  test    r15, r15
0x180150264  jz      short loc_18015026B
0x180150266  mov     [r15], rax
0x180150269  jmp     short loc_180150279
0x18015026b  test    rax, rax
0x18015026e  jz      short loc_180150279
0x180150270  mov     rcx, rax; hMem
0x180150273  call    cs:__imp_LocalFree
0x180150279  mov     rdx, rsi
0x18015027c  mov     rcx, rdi
0x18015027f  call    UnmapFileFromMemory
0x180150284  jmp     short loc_180150292
0x180150286  mov     rcx, rsi; hObject
0x180150289  call    cs:__imp_CloseHandle
0x18015028f  mov     ebx, r12d
0x180150292  mov     eax, ebx
0x180150294  add     rsp, 40h
0x180150298  pop     r15
0x18015029a  pop     r14
0x18015029c  pop     r12
0x18015029e  pop     rdi
0x18015029f  pop     rsi
0x1801502a0  pop     rbx
0x1801502a1  pop     rbp
0x1801502a2  retn
```
