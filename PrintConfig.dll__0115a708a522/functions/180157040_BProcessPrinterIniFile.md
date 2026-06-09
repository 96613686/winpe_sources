# BProcessPrinterIniFile

- ea: `0x180157040`
- end: `0x1801572ce`
- name: `BProcessPrinterIniFile`
- size: `654`
- prototype: `_BOOL8 __fastcall(struct _FILETIME, __int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801558d0`

## callees

- `0x180150854`
- `0x180151ad8`
- `0x180157040`
- `0x1801572d4`
- `0x180157508`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x1801571f7`
- `KERNEL32!CreateFileMappingW` at `0x1801571f7`
- `KERNEL32!MapViewOfFile` at `0x180157221`
- `KERNEL32!MapViewOfFile` at `0x180157221`
- `KERNEL32!GetFileSize` at `0x1801571ca`
- `KERNEL32!GetFileSize` at `0x1801571ca`
- `KERNEL32!CreateFileW` at `0x1801570e5`
- `KERNEL32!CreateFileW` at `0x1801571ac`
- `KERNEL32!CreateFileW` at `0x1801570e5`
- `KERNEL32!CreateFileW` at `0x1801571ac`
- `KERNEL32!CloseHandle` at `0x18015714b`
- `KERNEL32!CloseHandle` at `0x180157233`
- `KERNEL32!CloseHandle` at `0x1801572ad`
- `KERNEL32!CloseHandle` at `0x18015714b`
- `KERNEL32!CloseHandle` at `0x180157233`
- `KERNEL32!CloseHandle` at `0x1801572ad`
- `KERNEL32!LocalFree` at `0x180157291`
- `KERNEL32!LocalFree` at `0x180157291`
- `KERNEL32!CompareFileTime` at `0x180157127`
- `KERNEL32!CompareFileTime` at `0x180157127`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18015710a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18015710a`

## pseudocode

```c
_BOOL8 __fastcall BProcessPrinterIniFile(struct _FILETIME a1, __int64 a2, _QWORD *a3, int a4)
{
  const wchar_t *v4; // rcx
  BOOL v7; // ebx
  const WCHAR *v8; // rdi
  __int64 v9; // rax
  const wchar_t *v10; // rcx
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
  wint_t *v21; // rdi
  void *v22; // rax
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+88h] [rbp+48h] BYREF
  int v26; // [rsp+98h] [rbp+58h] BYREF

  v26 = a4;
  LastWriteTime = a1;
  v4 = *(const wchar_t **)(a2 + 56);
  v26 = 0;
  v7 = 1;
  v8 = PtstrSearchDependentFileWithExtension(v4);
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( !PtstrSearchDependentFileWithExtension(&v8[v9 + 1]) )
      goto LABEL_20;
    v10 = *(const wchar_t **)(a2 + 56);
    v8 = 0;
    FileTime2 = 0;
    do
    {
      v11 = PtstrSearchDependentFileWithExtension(v10);
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
            v21 = (wint_t *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
            CloseHandle(v20);
            if ( v21 )
            {
              if ( FileSize >= 2 && *(_BYTE *)v21 == 0xFF && *((_BYTE *)v21 + 1) == 0xFE )
                v22 = PwstrParsePrinterIniFileW(v21 + 1, (FileSize >> 1) - 1, &v26);
              else
                v22 = PwstrParsePrinterIniFileA((LPCCH)v21, FileSize, &v26);
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
0x180157040  mov     [rsp-38h+arg_18], r9d
0x180157045  mov     qword ptr [rsp-38h+LastWriteTime.dwLowDateTime], rcx
0x18015704a  push    rbp
0x18015704b  push    rbx
0x18015704c  push    rsi
0x18015704d  push    rdi
0x18015704e  push    r12
0x180157050  push    r14
0x180157052  push    r15
0x180157054  mov     rbp, rsp
0x180157057  sub     rsp, 40h
0x18015705b  mov     rcx, [rdx+38h]
0x18015705f  xor     r12d, r12d
0x180157062  mov     r15, r8
0x180157065  mov     [rbp+arg_18], r12d
0x180157069  mov     rsi, rdx
0x18015706c  lea     ebx, [r12+1]
0x180157071  call    PtstrSearchDependentFileWithExtension
0x180157076  mov     rdi, rax
0x180157079  test    rax, rax
0x18015707c  jz      loc_1801572BC
0x180157082  or      rax, 0FFFFFFFFFFFFFFFFh
0x180157086  inc     rax
0x180157089  cmp     [rdi+rax*2], r12w
0x18015708e  jnz     short loc_180157086
0x180157090  inc     rax
0x180157093  lea     rcx, [rdi+rax*2]
0x180157097  call    PtstrSearchDependentFileWithExtension
0x18015709c  test    rax, rax
0x18015709f  jz      loc_180157188
0x1801570a5  mov     rcx, [rsi+38h]
0x1801570a9  mov     rdi, r12
0x1801570ac  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r12
0x1801570b0  call    PtstrSearchDependentFileWithExtension
0x1801570b5  mov     rsi, rax
0x1801570b8  test    rax, rax
0x1801570bb  jz      loc_18015717F
0x1801570c1  xor     r9d, r9d; lpSecurityAttributes
0x1801570c4  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x1801570c9  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1801570d1  mov     edx, 80000000h; dwDesiredAccess
0x1801570d6  mov     rcx, rax; lpFileName
0x1801570d9  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1801570e1  lea     r8d, [r9+1]; dwShareMode
0x1801570e5  call    cs:__imp_CreateFileW
0x1801570ec  nop     dword ptr [rax+rax+00h]
0x1801570f1  mov     r14, rax
0x1801570f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801570f8  jz      short loc_180157159
0x1801570fa  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1801570fe  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], r12
0x180157102  xor     r8d, r8d; lpLastAccessTime
0x180157105  xor     edx, edx; lpCreationTime
0x180157107  mov     rcx, rax; hFile
0x18015710a  call    cs:__imp_GetFileTime
0x180157111  nop     dword ptr [rax+rax+00h]
0x180157116  test    eax, eax
0x180157118  jz      short loc_180157145
0x18015711a  test    rdi, rdi
0x18015711d  jz      short loc_180157138
0x18015711f  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180157123  lea     rcx, [rbp+LastWriteTime]; lpFileTime1
0x180157127  call    cs:__imp_CompareFileTime
0x18015712e  nop     dword ptr [rax+rax+00h]
0x180157133  cmp     eax, 1
0x180157136  jnz     short loc_180157148
0x180157138  mov     rax, qword ptr [rbp+LastWriteTime.dwLowDateTime]
0x18015713c  mov     rdi, rsi
0x18015713f  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180157143  jmp     short loc_180157148
0x180157145  mov     ebx, r12d
0x180157148  mov     rcx, r14; hObject
0x18015714b  call    cs:__imp_CloseHandle
0x180157152  nop     dword ptr [rax+rax+00h]
0x180157157  jmp     short loc_18015715C
0x180157159  mov     ebx, r12d
0x18015715c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180157160  inc     rax
0x180157163  cmp     [rsi+rax*2], r12w
0x180157168  jnz     short loc_180157160
0x18015716a  lea     rcx, [rax+1]
0x18015716e  lea     rcx, [rsi+rcx*2]
0x180157172  test    ebx, ebx
0x180157174  jnz     loc_1801570B0
0x18015717a  jmp     loc_1801572BC
0x18015717f  test    rdi, rdi
0x180157182  jz      loc_1801572BC
0x180157188  xor     r9d, r9d; lpSecurityAttributes
0x18015718b  mov     [rsp+40h+hTemplateFile], r12; hTemplateFile
0x180157190  mov     [rsp+40h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180157198  mov     edx, 80000000h; dwDesiredAccess
0x18015719d  mov     rcx, rdi; lpFileName
0x1801571a0  mov     [rsp+40h+dwCreationDisposition], 3; dwCreationDisposition
0x1801571a8  lea     r8d, [r9+1]; dwShareMode
0x1801571ac  call    cs:__imp_CreateFileW
0x1801571b3  nop     dword ptr [rax+rax+00h]
0x1801571b8  mov     rsi, rax
0x1801571bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801571bf  jz      loc_1801572B9
0x1801571c5  xor     edx, edx; lpFileSizeHigh
0x1801571c7  mov     rcx, rax; hFile
0x1801571ca  call    cs:__imp_GetFileSize
0x1801571d1  nop     dword ptr [rax+rax+00h]
0x1801571d6  mov     ebx, eax
0x1801571d8  cmp     eax, 0FFFFFFFFh
0x1801571db  jz      loc_1801572AA
0x1801571e1  xor     r9d, r9d; dwMaximumSizeHigh
0x1801571e4  mov     qword ptr [rsp+40h+dwFlagsAndAttributes], r12; lpName
0x1801571e9  xor     edx, edx; lpFileMappingAttributes
0x1801571eb  mov     [rsp+40h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x1801571f0  mov     rcx, rsi; hFile
0x1801571f3  lea     r8d, [r9+2]; flProtect
0x1801571f7  call    cs:__imp_CreateFileMappingW
0x1801571fe  nop     dword ptr [rax+rax+00h]
0x180157203  mov     r14, rax
0x180157206  test    rax, rax
0x180157209  jz      loc_1801572AA
0x18015720f  xor     r9d, r9d; dwFileOffsetLow
0x180157212  mov     qword ptr [rsp+40h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180157217  xor     r8d, r8d; dwFileOffsetHigh
0x18015721a  mov     rcx, rax; hFileMappingObject
0x18015721d  lea     edx, [r9+4]; dwDesiredAccess
0x180157221  call    cs:__imp_MapViewOfFile
0x180157228  nop     dword ptr [rax+rax+00h]
0x18015722d  mov     rcx, r14; hObject
0x180157230  mov     rdi, rax
0x180157233  call    cs:__imp_CloseHandle
0x18015723a  nop     dword ptr [rax+rax+00h]
0x18015723f  test    rdi, rdi
0x180157242  jz      short loc_1801572AA
0x180157244  cmp     ebx, 2
0x180157247  jb      short loc_180157268
0x180157249  cmp     byte ptr [rdi], 0FFh
0x18015724c  jnz     short loc_180157268
0x18015724e  cmp     byte ptr [rdi+1], 0FEh
0x180157252  jnz     short loc_180157268
0x180157254  shr     ebx, 1
0x180157256  lea     rcx, [rdi+2]; Src
0x18015725a  lea     r8, [rbp+arg_18]
0x18015725e  lea     edx, [rbx-1]
0x180157261  call    PwstrParsePrinterIniFileW
0x180157266  jmp     short loc_180157276
0x180157268  lea     r8, [rbp+arg_18]
0x18015726c  mov     edx, ebx
0x18015726e  mov     rcx, rdi; lpMultiByteStr
0x180157271  call    PwstrParsePrinterIniFileA
0x180157276  test    rax, rax
0x180157279  mov     ebx, r12d
0x18015727c  setnz   bl
0x18015727f  test    r15, r15
0x180157282  jz      short loc_180157289
0x180157284  mov     [r15], rax
0x180157287  jmp     short loc_18015729D
0x180157289  test    rax, rax
0x18015728c  jz      short loc_18015729D
0x18015728e  mov     rcx, rax; hMem
0x180157291  call    cs:__imp_LocalFree
0x180157298  nop     dword ptr [rax+rax+00h]
0x18015729d  mov     rdx, rsi
0x1801572a0  mov     rcx, rdi
0x1801572a3  call    UnmapFileFromMemory
0x1801572a8  jmp     short loc_1801572BC
0x1801572aa  mov     rcx, rsi; hObject
0x1801572ad  call    cs:__imp_CloseHandle
0x1801572b4  nop     dword ptr [rax+rax+00h]
0x1801572b9  mov     ebx, r12d
0x1801572bc  mov     eax, ebx
0x1801572be  add     rsp, 40h
0x1801572c2  pop     r15
0x1801572c4  pop     r14
0x1801572c6  pop     r12
0x1801572c8  pop     rdi
0x1801572c9  pop     rsi
0x1801572ca  pop     rbx
0x1801572cb  pop     rbp
0x1801572cc  retn
```
