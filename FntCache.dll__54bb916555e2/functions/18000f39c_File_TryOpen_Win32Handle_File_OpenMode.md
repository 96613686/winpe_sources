# File::TryOpen(Win32Handle &&,File::OpenMode)

- ea: `0x18000f39c`
- end: `0x18000f4d7`
- name: `?TryOpen@File@@QEAAJ$$QEAVWin32Handle@@W4OpenMode@1@@Z`
- size: `315`
- prototype: `__int64 __fastcall(__int64, void **, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000e3f0`
- `0x180068544`

## callees

- `0x18000e53c`
- `0x18000f39c`
- `0x1800aa650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f48c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f48c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4cc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000f3e7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000f3e7`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000f4b8`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000f4b8`

## pseudocode

```c
__int64 __fastcall File::TryOpen(__int64 a1, void **a2, char a3)
{
  void *v6; // rcx
  int v7; // ecx
  unsigned __int64 v8; // rbx
  void *v9; // rax
  __int64 result; // rax
  DWORD LastError; // eax
  void *v12; // rcx
  FILETIME LastAccessTime; // [rsp+20h] [rbp-50h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+28h] [rbp-48h] BYREF

  if ( (a3 & 0x10) != 0 )
  {
    v12 = *a2;
    LastAccessTime.dwLowDateTime = -1;
    LastAccessTime.dwHighDateTime = -1;
    SetFileTime(v12, 0, &LastAccessTime, &LastAccessTime);
  }
  v6 = *a2;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(v6, &FileInformation) )
  {
    v7 = FileInformation.dwFileAttributes & 0x10;
    *(_BYTE *)(a1 + 32) = v7 != 0;
    if ( ((a3 & 1) != 0 || v7)
      && (LastAccessTime = (FILETIME)__PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow),
          v8 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow),
          __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow) <= 0x7FFFFFFFFFFFFFFFLL) )
    {
      if ( *(_QWORD *)a1 )
        CloseHandle(*(HANDLE *)a1);
      *(FILETIME *)(a1 + 16) = FileInformation.ftLastWriteTime;
      LastAccessTime = FileInformation.ftCreationTime;
      *(FILETIME *)(a1 + 24) = FileInformation.ftCreationTime;
      v9 = *a2;
      *a2 = 0;
      *(_QWORD *)a1 = v9;
      result = 0;
      *(_QWORD *)(a1 + 8) = v8;
    }
    else
    {
      return 2291683328LL;
    }
  }
  else
  {
    LastError = GetLastError();
    return IOException::MapFileOpenError(LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18000f39c  mov     [rsp-18h+arg_10], rbx
0x18000f3a1  push    rbp
0x18000f3a2  push    rsi
0x18000f3a3  push    rdi
0x18000f3a4  mov     rbp, rsp
0x18000f3a7  sub     rsp, 70h
0x18000f3ab  mov     rax, cs:__security_cookie
0x18000f3b2  xor     rax, rsp
0x18000f3b5  mov     [rbp+var_10], rax
0x18000f3b9  mov     ebx, r8d
0x18000f3bc  mov     rsi, rdx
0x18000f3bf  mov     rdi, rcx
0x18000f3c2  test    r8b, 10h
0x18000f3c6  jnz     loc_18000F4A2
0x18000f3cc  mov     rcx, [rsi]; hFile
0x18000f3cf  lea     rdx, [rbp+FileInformation]; lpFileInformation
0x18000f3d3  xorps   xmm0, xmm0
0x18000f3d6  xor     eax, eax
0x18000f3d8  movups  xmmword ptr [rbp+FileInformation.dwFileAttributes], xmm0
0x18000f3dc  mov     [rbp+FileInformation.nFileIndexLow], eax
0x18000f3df  movups  xmmword ptr [rbp+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000f3e3  movups  xmmword ptr [rbp+FileInformation.nFileSizeHigh], xmm0
0x18000f3e7  call    cs:__imp_GetFileInformationByHandle
0x18000f3ed  test    eax, eax
0x18000f3ef  jz      loc_18000F48C
0x18000f3f5  mov     ecx, [rbp+FileInformation.dwFileAttributes]
0x18000f3f8  and     ecx, 10h
0x18000f3fb  setnz   al
0x18000f3fe  mov     [rdi+20h], al
0x18000f401  test    bl, 1
0x18000f404  jz      loc_18000F4C3
0x18000f40a  mov     eax, [rbp+FileInformation.nFileSizeHigh]
0x18000f40d  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x18000f410  mov     eax, [rbp+FileInformation.nFileSizeLow]
0x18000f413  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x18000f416  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f420  mov     rbx, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x18000f424  cmp     rbx, rax
0x18000f427  ja      short loc_18000F49B
0x18000f429  mov     rcx, [rdi]; hObject
0x18000f42c  test    rcx, rcx
0x18000f42f  jnz     loc_18000F4CC
0x18000f435  mov     eax, [rbp+FileInformation.ftLastWriteTime.dwHighDateTime]
0x18000f438  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x18000f43b  mov     eax, [rbp+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18000f43e  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x18000f441  mov     rax, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x18000f445  mov     [rdi+10h], rax
0x18000f449  mov     eax, [rbp+FileInformation.ftCreationTime.dwHighDateTime]
0x18000f44c  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x18000f44f  mov     eax, [rbp+FileInformation.ftCreationTime.dwLowDateTime]
0x18000f452  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x18000f455  mov     rax, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x18000f459  mov     [rdi+18h], rax
0x18000f45d  mov     rax, [rsi]
0x18000f460  mov     qword ptr [rsi], 0
0x18000f467  mov     [rdi], rax
0x18000f46a  xor     eax, eax
0x18000f46c  mov     [rdi+8], rbx
0x18000f470  mov     rcx, [rbp+var_10]
0x18000f474  xor     rcx, rsp; StackCookie
0x18000f477  call    __security_check_cookie
0x18000f47c  mov     rbx, [rsp+70h+arg_10]
0x18000f484  add     rsp, 70h
0x18000f488  pop     rdi
0x18000f489  pop     rsi
0x18000f48a  pop     rbp
0x18000f48b  retn
0x18000f48c  call    cs:__imp_GetLastError
0x18000f492  mov     ecx, eax; int
0x18000f494  call    ?MapFileOpenError@IOException@@SAHH@Z; IOException::MapFileOpenError(int)
0x18000f499  jmp     short loc_18000F470
0x18000f49b  mov     eax, 88985000h
0x18000f4a0  jmp     short loc_18000F470
0x18000f4a2  mov     rcx, [rsi]; hFile
0x18000f4a5  lea     r9, [rbp+LastAccessTime]; lpLastWriteTime
0x18000f4a9  or      eax, 0FFFFFFFFh
0x18000f4ac  lea     r8, [rbp+LastAccessTime]; lpLastAccessTime
0x18000f4b0  xor     edx, edx; lpCreationTime
0x18000f4b2  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x18000f4b5  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x18000f4b8  call    cs:__imp_SetFileTime
0x18000f4be  jmp     loc_18000F3CC
0x18000f4c3  test    ecx, ecx
0x18000f4c5  jz      short loc_18000F49B
0x18000f4c7  jmp     loc_18000F40A
0x18000f4cc  call    cs:__imp_CloseHandle
0x18000f4d2  jmp     loc_18000F435
```
