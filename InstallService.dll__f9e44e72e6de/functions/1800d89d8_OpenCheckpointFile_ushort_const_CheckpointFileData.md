# _OpenCheckpointFile(ushort const *,CheckpointFileData * *)

- ea: `0x1800d89d8`
- end: `0x1800d8de1`
- name: `?_OpenCheckpointFile@@YAJPEBGPEAPEAUCheckpointFileData@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CheckpointFileData **)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d7b64`
- `0x1800d80dc`
- `0x1800d8424`

## callees

- `0x180009ea0`
- `0x180010b54`
- `0x18001c414`
- `0x18001c844`
- `0x180072420`
- `0x180084010`
- `0x1800d70b8`
- `0x1800d8278`
- `0x1800d831c`
- `0x1800d8804`
- `0x1800d89d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8acd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8bfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8acd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8bfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d8d54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d8bac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d8bac`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800d8c1e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800d8c1e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d8aeb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d8b58`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d8aeb`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d8b58`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d8b19`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d8b19`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800d8cc5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800d8cc5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800d8ca1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800d8ca1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800d8d30`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800d8d30`

## string_xrefs

- `0x1800d8a3b`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d8d1c`: `onecoreuap\enduser\winstore\installservice\lib\checkpoint.cpp`
- `0x1800d8b6c`: `Path length does not match. Checkpoint file delete failed: Id = '%s'`
- `0x1800d8bc1`: `File path from handle do not match. Checkpoint file delete failed: Id = '%s'`
- `0x1800d8a2c`: `_OpenCheckpointFile`
- `0x1800d8be6`: `_OpenCheckpointFile`
- `0x1800d8c60`: `_OpenCheckpointFile`
- `0x1800d8d0f`: `_OpenCheckpointFile`
- `0x1800d8aa2`: `Symbolic link detected. Checkpoint file open failed: Id = '%s'`
- `0x1800d8a25`: `CheckpointFilename(szCheckpointPath, ARRAYSIZE(szCheckpointPath), pszProductId)`
- `0x1800d8d7d`: `Checkpoint file open failed: Id = '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _OpenCheckpointFile(const unsigned __int16 *a1, struct CheckpointFileData **a2)
{
  int v4; // eax
  int LastError; // ebx
  void *FileWithRetry; // rdi
  DWORD FinalPathNameByHandleW; // esi
  HANDLE FileW; // rax
  const char *v9; // r9
  const unsigned __int16 *v10; // rax
  unsigned int v11; // r8d
  __int64 v12; // rdx
  HANDLE FileMappingW; // rax
  void *v14; // r14
  _DWORD *v15; // rax
  const void *v16; // rsi
  int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v20; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String2[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR szFilePath[264]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+5D8h]

  *a2 = 0;
  v4 = CheckpointFilename(FileName, (unsigned __int64)a2, a1);
  LastError = TraceHR(
                "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
                0x1DEu,
                "_OpenCheckpointFile",
                "CheckpointFilename(szCheckpointPath, ARRAYSIZE(szCheckpointPath), pszProductId)",
                v4,
                dwFlagsAndAttributes);
  if ( LastError < 0 )
    return (unsigned int)LastError;
  FileWithRetry = _CreateFileWithRetry(FileName, 0xC0000000, 7u, 3u, 0x200080u);
  if ( FileWithRetry != (void *)-1LL )
  {
    if ( _IsFilePathSymlink(FileName) )
    {
      LastError = 5;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
        0x1EDu,
        "_OpenCheckpointFile",
        5,
        L"Symbolic link detected. Checkpoint file open failed: Id = '%s'",
        0,
        0,
        FileName);
      CloseHandle(FileWithRetry);
      return (unsigned int)LastError;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileWithRetry, szFilePath, 0x104u, 0);
    FileW = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v20 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1FF,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
                    v9);
LABEL_14:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      return (unsigned int)LastError;
    }
    if ( FinalPathNameByHandleW != GetFinalPathNameByHandleW(FileW, String2, 0x104u, 0) )
    {
      v10 = L"Path length does not match. Checkpoint file delete failed: Id = '%s'";
      v11 = 518;
LABEL_13:
      LastError = 5;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
        v11,
        "_OpenCheckpointFile",
        5,
        v10,
        0,
        0,
        FileName);
      CloseHandle(FileWithRetry);
      goto LABEL_14;
    }
    v12 = -1;
    do
      ++v12;
    while ( String2[v12] );
    if ( CompareStringOrdinal(szFilePath, v12, String2, -1, 1) != 2 )
    {
      v10 = L"File path from handle do not match. Checkpoint file delete failed: Id = '%s'";
      v11 = 526;
      goto LABEL_13;
    }
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(FileWithRetry, &FileSize) )
    {
      if ( FileSize.QuadPart >= 0xCAuLL )
        goto LABEL_20;
      LastError = -2147024883;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
        0x219u,
        "_OpenCheckpointFile",
        -2147024883,
        L"Unexpected checkpoint file size: Id = '%s', size = '%I64d'",
        0,
        0,
        a1,
        FileSize.QuadPart);
    }
    else
    {
      LastError = ResultFromKnownLastError();
    }
    if ( LastError < 0 )
    {
LABEL_29:
      CloseHandle(FileWithRetry);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      goto LABEL_31;
    }
LABEL_20:
    FileMappingW = CreateFileMappingW(FileWithRetry, 0, 4u, 0, 0, 0);
    v14 = FileMappingW;
    if ( FileMappingW )
    {
      v15 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0);
      v16 = v15;
      if ( v15 )
      {
        if ( *v15 == 12 && v15[1] == 192 )
        {
          *a2 = (struct CheckpointFileData *)v15;
        }
        else
        {
          LastError = -2147024883;
          LogMessage(
            2u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
            0x237u,
            "_OpenCheckpointFile",
            -1,
            L"Invalid/old checkpoint file: Id = '%s'",
            0,
            0,
            a1);
          UnmapViewOfFile(v16);
        }
      }
      else
      {
        LastError = ResultFromKnownLastError();
      }
      CloseHandle(v14);
    }
    else
    {
      LastError = ResultFromKnownLastError();
    }
    goto LABEL_29;
  }
  LastError = ResultFromKnownLastError();
  LogMessage(
    1u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\checkpoint.cpp",
    0x250u,
    "_OpenCheckpointFile",
    LastError,
    L"Checkpoint file open failed: Id = '%s'",
    0,
    0,
    a1);
LABEL_31:
  if ( LastError == -2147024883 )
    _DeleteCheckpointByName(FileName);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800d89d8  mov     [rsp-8+arg_10], rbx
0x1800d89dd  push    rbp
0x1800d89de  push    rsi
0x1800d89df  push    rdi
0x1800d89e0  push    r12
0x1800d89e2  push    r13
0x1800d89e4  push    r14
0x1800d89e6  push    r15
0x1800d89e8  lea     rbp, [rsp-5A0h]
0x1800d89f0  sub     rsp, 6A0h
0x1800d89f7  mov     rax, cs:__security_cookie
0x1800d89fe  xor     rax, rsp
0x1800d8a01  mov     [rbp+5D0h+var_40], rax
0x1800d8a08  mov     r12, rdx
0x1800d8a0b  mov     r15, rcx
0x1800d8a0e  xor     r13d, r13d
0x1800d8a11  mov     [rdx], r13
0x1800d8a14  mov     r8, rcx; unsigned __int16 *
0x1800d8a17  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1800d8a1c  call    ?CheckpointFilename@@YAJPEAG_KPEBG@Z; CheckpointFilename(ushort *,unsigned __int64,ushort const *)
0x1800d8a21  mov     [rsp+6D0h+dwCreationDisposition], eax; int
0x1800d8a25  lea     r9, aCheckpointfile; "CheckpointFilename(szCheckpointPath, AR"...
0x1800d8a2c  lea     rsi, aOpencheckpoint_0; "_OpenCheckpointFile"
0x1800d8a33  mov     r8, rsi; char *
0x1800d8a36  mov     edx, 1DEh; unsigned int
0x1800d8a3b  lea     r14, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d8a42  mov     rcx, r14; char *
0x1800d8a45  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x1800d8a4a  mov     ebx, eax
0x1800d8a4c  test    eax, eax
0x1800d8a4e  js      loc_1800D8DB5
0x1800d8a54  mov     [rsp+6D0h+dwCreationDisposition], 200080h; DWORD
0x1800d8a5c  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d8a61  lea     r9d, [r13+3]; dwCreationDisposition
0x1800d8a65  lea     r8d, [r13+7]; dwShareMode
0x1800d8a69  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800d8a6e  call    ?_CreateFileWithRetry@@YAPEAXPEBGKKKK@Z; _CreateFileWithRetry(ushort const *,ulong,ulong,ulong,ulong)
0x1800d8a73  mov     rdi, rax
0x1800d8a76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d8a7a  jz      loc_1800D8D67
0x1800d8a80  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1800d8a85  call    ?_IsFilePathSymlink@@YA_NPEBG@Z; _IsFilePathSymlink(ushort const *)
0x1800d8a8a  test    al, al
0x1800d8a8c  jz      short loc_1800D8AD8
0x1800d8a8e  lea     rax, [rsp+6D0h+FileName]
0x1800d8a93  mov     [rsp+6D0h+var_690], rax
0x1800d8a98  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d8a9d  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d8aa2  lea     rax, aSymbolicLinkDe_1; "Symbolic link detected. Checkpoint file"...
0x1800d8aa9  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d8aae  lea     ebx, [r13+5]
0x1800d8ab2  mov     [rsp+6D0h+dwCreationDisposition], ebx; int
0x1800d8ab6  mov     r9, rsi; char *
0x1800d8ab9  mov     r8d, 1EDh; unsigned int
0x1800d8abf  mov     rdx, r14; char *
0x1800d8ac2  lea     ecx, [rbx-4]; unsigned int
0x1800d8ac5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d8aca  mov     rcx, rdi; hObject
0x1800d8acd  call    cs:__imp_CloseHandle
0x1800d8ad3  jmp     loc_1800D8DB5
0x1800d8ad8  xor     r9d, r9d; dwFlags
0x1800d8adb  mov     r8d, 104h; cchFilePath
0x1800d8ae1  lea     rdx, [rbp+5D0h+szFilePath]; lpszFilePath
0x1800d8ae8  mov     rcx, rdi; hFile
0x1800d8aeb  call    cs:__imp_GetFinalPathNameByHandleW
0x1800d8af1  mov     esi, eax
0x1800d8af3  mov     [rsp+6D0h+hTemplateFile], r13; hTemplateFile
0x1800d8af8  mov     [rsp+6D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800d8b00  mov     [rsp+6D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800d8b08  xor     r9d, r9d; lpSecurityAttributes
0x1800d8b0b  mov     edx, 80000000h; dwDesiredAccess
0x1800d8b10  lea     r8d, [r9+7]; dwShareMode
0x1800d8b14  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800d8b19  call    cs:__imp_CreateFileW
0x1800d8b1f  mov     [rsp+6D0h+var_678], rax
0x1800d8b24  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d8b28  jnz     short loc_1800D8B45
0x1800d8b2a  mov     rcx, [rbp+5D8h]; this
0x1800d8b31  mov     r8, r14; unsigned int
0x1800d8b34  mov     edx, 1FFh; void *
0x1800d8b39  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d8b3e  mov     ebx, eax
0x1800d8b40  jmp     loc_1800D8C02
0x1800d8b45  xor     r9d, r9d; dwFlags
0x1800d8b48  mov     r8d, 104h; cchFilePath
0x1800d8b4e  lea     rdx, [rbp+5D0h+String2]; lpszFilePath
0x1800d8b55  mov     rcx, rax; hFile
0x1800d8b58  call    cs:__imp_GetFinalPathNameByHandleW
0x1800d8b5e  cmp     esi, eax
0x1800d8b60  jz      short loc_1800D8B7B
0x1800d8b62  lea     rax, [rsp+6D0h+FileName]
0x1800d8b67  mov     [rsp+6D0h+var_690], rax
0x1800d8b6c  lea     rax, aPathLengthDoes; "Path length does not match. Checkpoint "...
0x1800d8b73  mov     r8d, 206h
0x1800d8b79  jmp     short loc_1800D8BCE
0x1800d8b7b  lea     rcx, [rbp+5D0h+String2]
0x1800d8b82  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d8b86  mov     rdx, rax
0x1800d8b89  inc     rdx; cchCount1
0x1800d8b8c  cmp     [rcx+rdx*2], r13w
0x1800d8b91  jnz     short loc_1800D8B89
0x1800d8b93  mov     [rsp+6D0h+dwCreationDisposition], 1; bIgnoreCase
0x1800d8b9b  mov     r9d, eax; cchCount2
0x1800d8b9e  lea     r8, [rbp+5D0h+String2]; lpString2
0x1800d8ba5  lea     rcx, [rbp+5D0h+szFilePath]; lpString1
0x1800d8bac  call    cs:__imp_CompareStringOrdinal
0x1800d8bb2  cmp     eax, 2
0x1800d8bb5  jz      short loc_1800D8C11
0x1800d8bb7  lea     rax, [rsp+6D0h+FileName]
0x1800d8bbc  mov     [rsp+6D0h+var_690], rax
0x1800d8bc1  lea     rax, aFilePathFromHa; "File path from handle do not match. Che"...
0x1800d8bc8  mov     r8d, 20Eh; unsigned int
0x1800d8bce  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d8bd3  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d8bd8  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d8bdd  mov     ebx, 5
0x1800d8be2  mov     [rsp+6D0h+dwCreationDisposition], ebx; int
0x1800d8be6  lea     r9, aOpencheckpoint_0; "_OpenCheckpointFile"
0x1800d8bed  mov     rdx, r14; char *
0x1800d8bf0  lea     ecx, [rbx-4]; unsigned int
0x1800d8bf3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d8bf8  mov     rcx, rdi; hObject
0x1800d8bfb  call    cs:__imp_CloseHandle
0x1800d8c01  nop
0x1800d8c02  lea     rcx, [rsp+6D0h+var_678]
0x1800d8c07  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d8c0c  jmp     loc_1800D8DB5
0x1800d8c11  mov     qword ptr [rsp+6D0h+FileSize], r13
0x1800d8c16  lea     rdx, [rsp+6D0h+FileSize]; lpFileSize
0x1800d8c1b  mov     rcx, rdi; hFile
0x1800d8c1e  call    cs:__imp_GetFileSizeEx
0x1800d8c24  test    eax, eax
0x1800d8c26  jz      short loc_1800D8C7C
0x1800d8c28  mov     rax, qword ptr [rsp+6D0h+FileSize]
0x1800d8c2d  cmp     rax, 0CAh
0x1800d8c33  jnb     short loc_1800D8C8B
0x1800d8c35  mov     ecx, 8007000Dh
0x1800d8c3a  mov     ebx, ecx
0x1800d8c3c  mov     [rsp+6D0h+var_688], rax
0x1800d8c41  mov     [rsp+6D0h+var_690], r15
0x1800d8c46  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d8c4b  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d8c50  lea     rax, aUnexpectedChec; "Unexpected checkpoint file size: Id = '"...
0x1800d8c57  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d8c5c  mov     [rsp+6D0h+dwCreationDisposition], ecx; int
0x1800d8c60  lea     r9, aOpencheckpoint_0; "_OpenCheckpointFile"
0x1800d8c67  mov     r8d, 219h; unsigned int
0x1800d8c6d  mov     rdx, r14; char *
0x1800d8c70  mov     ecx, 1; unsigned int
0x1800d8c75  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d8c7a  jmp     short loc_1800D8C83
0x1800d8c7c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8c81  mov     ebx, eax
0x1800d8c83  test    ebx, ebx
0x1800d8c85  js      loc_1800D8D51
0x1800d8c8b  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], r13; lpName
0x1800d8c90  mov     [rsp+6D0h+dwCreationDisposition], r13d; dwMaximumSizeLow
0x1800d8c95  xor     r9d, r9d; dwMaximumSizeHigh
0x1800d8c98  xor     edx, edx; lpFileMappingAttributes
0x1800d8c9a  lea     r8d, [r9+4]; flProtect
0x1800d8c9e  mov     rcx, rdi; hFile
0x1800d8ca1  call    cs:__imp_CreateFileMappingW
0x1800d8ca7  mov     r14, rax
0x1800d8caa  test    rax, rax
0x1800d8cad  jz      loc_1800D8D4A
0x1800d8cb3  mov     qword ptr [rsp+6D0h+dwCreationDisposition], r13; dwNumberOfBytesToMap
0x1800d8cb8  xor     r9d, r9d; dwFileOffsetLow
0x1800d8cbb  xor     r8d, r8d; dwFileOffsetHigh
0x1800d8cbe  lea     edx, [r9+6]; dwDesiredAccess
0x1800d8cc2  mov     rcx, rax; hFileMappingObject
0x1800d8cc5  call    cs:__imp_MapViewOfFile
0x1800d8ccb  mov     rsi, rax
0x1800d8cce  test    rax, rax
0x1800d8cd1  jz      short loc_1800D8D38
0x1800d8cd3  cmp     dword ptr [rax], 0Ch
0x1800d8cd6  jnz     short loc_1800D8CE7
0x1800d8cd8  cmp     dword ptr [rax+4], 0C0h
0x1800d8cdf  jnz     short loc_1800D8CE7
0x1800d8ce1  mov     [r12], rax
0x1800d8ce5  jmp     short loc_1800D8D3F
0x1800d8ce7  mov     ebx, 8007000Dh
0x1800d8cec  mov     [rsp+6D0h+var_690], r15
0x1800d8cf1  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d8cf6  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d8cfb  lea     rax, aInvalidOldChec; "Invalid/old checkpoint file: Id = '%s'"
0x1800d8d02  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d8d07  mov     [rsp+6D0h+dwCreationDisposition], 0FFFFFFFFh; int
0x1800d8d0f  lea     r9, aOpencheckpoint_0; "_OpenCheckpointFile"
0x1800d8d16  mov     r8d, 237h; unsigned int
0x1800d8d1c  lea     rdx, aOnecoreuapEndu_45; "onecoreuap\\enduser\\winstore\\installs"...
0x1800d8d23  mov     ecx, 2; unsigned int
0x1800d8d28  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d8d2d  mov     rcx, rsi; lpBaseAddress
0x1800d8d30  call    cs:__imp_UnmapViewOfFile
0x1800d8d36  jmp     short loc_1800D8D3F
0x1800d8d38  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8d3d  mov     ebx, eax
0x1800d8d3f  mov     rcx, r14; hObject
0x1800d8d42  call    cs:__imp_CloseHandle
0x1800d8d48  jmp     short loc_1800D8D51
0x1800d8d4a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8d4f  mov     ebx, eax
0x1800d8d51  mov     rcx, rdi; hObject
0x1800d8d54  call    cs:__imp_CloseHandle
0x1800d8d5a  nop
0x1800d8d5b  lea     rcx, [rsp+6D0h+var_678]
0x1800d8d60  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d8d65  jmp     short loc_1800D8DA3
0x1800d8d67  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d8d6c  mov     ebx, eax
0x1800d8d6e  mov     [rsp+6D0h+var_690], r15
0x1800d8d73  mov     [rsp+6D0h+var_698], r13; unsigned __int16 *
0x1800d8d78  mov     [rsp+6D0h+hTemplateFile], r13; char *
0x1800d8d7d  lea     rax, aCheckpointFile; "Checkpoint file open failed: Id = '%s'"
0x1800d8d84  mov     qword ptr [rsp+6D0h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1800d8d89  mov     [rsp+6D0h+dwCreationDisposition], ebx; int
0x1800d8d8d  mov     r9, rsi; char *
0x1800d8d90  mov     r8d, 250h; unsigned int
0x1800d8d96  mov     rdx, r14; char *
0x1800d8d99  mov     ecx, 1; unsigned int
0x1800d8d9e  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800d8da3  cmp     ebx, 8007000Dh
0x1800d8da9  jnz     short loc_1800D8DB5
0x1800d8dab  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x1800d8db0  call    ?_DeleteCheckpointByName@@YAJPEBG@Z; _DeleteCheckpointByName(ushort const *)
0x1800d8db5  mov     eax, ebx
0x1800d8db7  mov     rcx, [rbp+5D0h+var_40]
0x1800d8dbe  xor     rcx, rsp; StackCookie
0x1800d8dc1  call    __security_check_cookie
0x1800d8dc6  mov     rbx, [rsp+6D0h+arg_10]
0x1800d8dce  add     rsp, 6A0h
0x1800d8dd5  pop     r15
0x1800d8dd7  pop     r14
0x1800d8dd9  pop     r13
0x1800d8ddb  pop     r12
0x1800d8ddd  pop     rdi
0x1800d8dde  pop     rsi
0x1800d8ddf  pop     rbp
0x1800d8de0  retn
```
