# __std_fs_remove

- ea: `0x1800b9cbc`
- end: `0x1800b9ffe`
- name: `__std_fs_remove`
- size: `834`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18006ca40`
- `0x18010cdfc`
- `0x18010d02c`

## callees

- `0x1800aed10`
- `0x1800b9594`
- `0x1800b9c60`
- `0x1800b9cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b9f1b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b9fc3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b9f1b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b9fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9d96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9d96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9fb9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800b9e48`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800b9e48`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9d25`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9ea1`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9ef5`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9d25`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9ea1`
- `KERNEL32!SetFileInformationByHandle` at `0x1800b9ef5`

## pseudocode

```c
HANDLE __fastcall _std_fs_remove(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  char v4; // si
  HANDLE v5; // rbx
  DWORD LastError; // edi
  int v7; // ebx
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE hFile; // [rsp+20h] [rbp-40h] BYREF
  __int64 FileInformation; // [rsp+28h] [rbp-38h] BYREF
  _OWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]

  v2 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 5 )
    {
      v12 = v2 - 2;
      if ( !v12
        || (v13 = v12 - 1) == 0
        || (v14 = v13 - 50) == 0
        || (v15 = v14 - 11) == 0
        || (v16 = v15 - 59) == 0
        || (v17 = v16 - 38) == 0
        || v17 == 106 )
      {
        v3 = 0;
      }
      if ( hFile != (HANDLE)-1LL && !CloseHandle(hFile) )
        goto LABEL_56;
      HIDWORD(hFile) = v3;
LABEL_58:
      LOBYTE(hFile) = 0;
      *(_WORD *)((char *)&hFile + 1) = 0;
      BYTE3(hFile) = 0;
      return hFile;
    }
    v4 = 0;
    v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
    if ( v7 )
    {
      if ( hFile == (HANDLE)-1LL || CloseHandle(hFile) )
      {
        LOBYTE(FileInformation) = 0;
        *(_WORD *)((char *)&FileInformation + 1) = 0;
        BYTE3(FileInformation) = 0;
        HIDWORD(FileInformation) = v7;
        return (HANDLE)FileInformation;
      }
      goto LABEL_56;
    }
  }
  else
  {
    v4 = 1;
  }
  v5 = hFile;
  LODWORD(FileInformation) = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
  {
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 0;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
      goto LABEL_7;
    }
LABEL_56:
    abort();
  }
  v9 = anonymous_namespace_::_Set_delete_flag(v5);
  v10 = v9;
  if ( !v9 )
  {
LABEL_4:
    LastError = 0;
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 1;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
LABEL_7:
      HIDWORD(FileInformation) = LastError;
      return (HANDLE)FileInformation;
    }
    goto LABEL_56;
  }
  if ( v9 != 5 || !v4 )
  {
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_56;
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
LABEL_33:
    HIDWORD(hFile) = v10;
    return hFile;
  }
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( !GetFileInformationByHandleEx(v5, FileBasicInfo, v20, 0x28u) )
  {
LABEL_24:
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    HIDWORD(hFile) = GetLastError();
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
      return hFile;
LABEL_38:
    abort();
  }
  if ( (v21 & 1) == 0 )
  {
LABEL_36:
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    HIDWORD(hFile) = 5;
    goto LABEL_58;
  }
  LODWORD(v21) = v21 ^ 1;
  if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
    goto LABEL_24;
  v11 = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !v11 )
  {
    v10 = 0;
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    LOBYTE(hFile) = 1;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    goto LABEL_33;
  }
  if ( v11 == 5 )
  {
    LODWORD(v21) = v21 | 1;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
      goto LABEL_24;
    goto LABEL_36;
  }
  LOBYTE(hFile) = 0;
  *(_WORD *)((char *)&hFile + 1) = 0;
  BYTE3(hFile) = 0;
  HIDWORD(hFile) = GetLastError();
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    goto LABEL_56;
  return hFile;
}

```

## disassembly

```asm
0x1800b9cbc  mov     [rsp-18h+arg_8], rbx
0x1800b9cc1  mov     [rsp-18h+arg_10], rsi
0x1800b9cc6  push    rbp
0x1800b9cc7  push    rdi
0x1800b9cc8  push    r15
0x1800b9cca  mov     rbp, rsp
0x1800b9ccd  sub     rsp, 60h
0x1800b9cd1  mov     rax, cs:__security_cookie
0x1800b9cd8  xor     rax, rsp
0x1800b9cdb  mov     [rbp+var_8], rax
0x1800b9cdf  mov     rdi, rcx
0x1800b9ce2  mov     rdx, rcx
0x1800b9ce5  lea     rcx, [rbp+hFile]
0x1800b9ce9  mov     r9d, 2200000h
0x1800b9cef  mov     r8d, 10180h
0x1800b9cf5  call    __std_fs_open_handle
0x1800b9cfa  mov     ebx, eax
0x1800b9cfc  mov     r15d, 5
0x1800b9d02  test    eax, eax
0x1800b9d04  jnz     short loc_1800B9D5D
0x1800b9d06  mov     sil, 1
0x1800b9d09  mov     rbx, [rbp+hFile]
0x1800b9d0d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800b9d11  mov     r9d, 4; dwBufferSize
0x1800b9d17  mov     dword ptr [rbp+FileInformation], 13h
0x1800b9d1e  mov     rcx, rbx; hFile
0x1800b9d21  lea     edx, [r9+11h]; FileInformationClass
0x1800b9d25  call    cs:__imp_SetFileInformationByHandle
0x1800b9d2b  test    eax, eax
0x1800b9d2d  jz      loc_1800B9DBC
0x1800b9d33  xor     edi, edi
0x1800b9d35  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9d39  jz      short loc_1800B9D4C
0x1800b9d3b  mov     rcx, rbx; hObject
0x1800b9d3e  call    cs:__imp_CloseHandle
0x1800b9d44  test    eax, eax
0x1800b9d46  jz      loc_1800B9FC3
0x1800b9d4c  mov     byte ptr [rbp+FileInformation], 1
0x1800b9d50  mov     word ptr [rbp+FileInformation+1], di
0x1800b9d54  mov     byte ptr [rbp+FileInformation+3], dil
0x1800b9d58  mov     dword ptr [rbp+FileInformation+4], edi
0x1800b9d5b  jmp     short loc_1800B9DB3
0x1800b9d5d  cmp     eax, r15d
0x1800b9d60  jnz     loc_1800B9F85
0x1800b9d66  mov     r9d, 2200000h
0x1800b9d6c  lea     rcx, [rbp+hFile]
0x1800b9d70  mov     r8d, 10000h
0x1800b9d76  mov     rdx, rdi
0x1800b9d79  xor     sil, sil
0x1800b9d7c  call    __std_fs_open_handle
0x1800b9d81  mov     ebx, eax
0x1800b9d83  test    eax, eax
0x1800b9d85  jz      short loc_1800B9D09
0x1800b9d87  mov     rcx, [rbp+hFile]; hObject
0x1800b9d8b  xor     dil, dil
0x1800b9d8e  xor     esi, esi
0x1800b9d90  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b9d94  jz      short loc_1800B9DA4
0x1800b9d96  call    cs:__imp_CloseHandle
0x1800b9d9c  test    eax, eax
0x1800b9d9e  jz      loc_1800B9FC3
0x1800b9da4  mov     byte ptr [rbp+FileInformation], dil
0x1800b9da8  mov     word ptr [rbp+FileInformation+1], si
0x1800b9dac  mov     byte ptr [rbp+FileInformation+3], sil
0x1800b9db0  mov     dword ptr [rbp+FileInformation+4], ebx
0x1800b9db3  mov     rax, [rbp+FileInformation]
0x1800b9db7  jmp     loc_1800B9FDD
0x1800b9dbc  call    cs:__imp_GetLastError
0x1800b9dc2  mov     ecx, eax
0x1800b9dc4  mov     edi, eax
0x1800b9dc6  sub     ecx, 1
0x1800b9dc9  jz      short loc_1800B9E04
0x1800b9dcb  sub     ecx, 31h ; '1'
0x1800b9dce  jz      short loc_1800B9E04
0x1800b9dd0  cmp     ecx, 25h ; '%'
0x1800b9dd3  jz      short loc_1800B9E04
0x1800b9dd5  xor     sil, sil
0x1800b9dd8  xor     r15d, r15d
0x1800b9ddb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9ddf  jz      short loc_1800B9DF2
0x1800b9de1  mov     rcx, rbx; hObject
0x1800b9de4  call    cs:__imp_CloseHandle
0x1800b9dea  test    eax, eax
0x1800b9dec  jz      loc_1800B9FC3
0x1800b9df2  mov     byte ptr [rbp+FileInformation], sil
0x1800b9df6  mov     word ptr [rbp+FileInformation+1], r15w
0x1800b9dfb  mov     byte ptr [rbp+FileInformation+3], r15b
0x1800b9dff  jmp     loc_1800B9D58
0x1800b9e04  mov     rcx, rbx; hFile
0x1800b9e07  call    _anonymous_namespace____Set_delete_flag
0x1800b9e0c  mov     edi, eax
0x1800b9e0e  test    eax, eax
0x1800b9e10  jz      loc_1800B9D33
0x1800b9e16  cmp     eax, r15d
0x1800b9e19  jnz     loc_1800B9F5A
0x1800b9e1f  test    sil, sil
0x1800b9e22  jz      loc_1800B9F5A
0x1800b9e28  xor     eax, eax
0x1800b9e2a  lea     r8, [rbp+var_30]; lpFileInformation
0x1800b9e2e  xorps   xmm0, xmm0
0x1800b9e31  mov     [rbp+var_10], rax
0x1800b9e35  xor     edx, edx; FileInformationClass
0x1800b9e37  mov     rcx, rbx; hFile
0x1800b9e3a  movups  [rbp+var_30], xmm0
0x1800b9e3e  lea     edi, [rax+28h]
0x1800b9e41  mov     r9d, edi; dwBufferSize
0x1800b9e44  movups  [rbp+var_20], xmm0
0x1800b9e48  call    cs:__imp_GetFileInformationByHandleEx
0x1800b9e4e  test    eax, eax
0x1800b9e50  jnz     short loc_1800B9E88
0x1800b9e52  xor     eax, eax
0x1800b9e54  mov     byte ptr [rbp+hFile], 0
0x1800b9e58  mov     word ptr [rbp+hFile+1], ax
0x1800b9e5c  mov     byte ptr [rbp+hFile+3], al
0x1800b9e5f  call    cs:__imp_GetLastError
0x1800b9e65  mov     dword ptr [rbp+hFile+4], eax
0x1800b9e68  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9e6c  jz      loc_1800B9FD9
0x1800b9e72  mov     rcx, rbx; hObject
0x1800b9e75  call    cs:__imp_CloseHandle
0x1800b9e7b  test    eax, eax
0x1800b9e7d  jz      loc_1800B9F1B
0x1800b9e83  jmp     loc_1800B9FD9
0x1800b9e88  mov     eax, dword ptr [rbp+var_10]
0x1800b9e8b  test    al, 1
0x1800b9e8d  jz      short loc_1800B9F03
0x1800b9e8f  xor     eax, 1
0x1800b9e92  lea     r8, [rbp+var_30]; lpFileInformation
0x1800b9e96  mov     r9d, edi; dwBufferSize
0x1800b9e99  mov     dword ptr [rbp+var_10], eax
0x1800b9e9c  xor     edx, edx; FileInformationClass
0x1800b9e9e  mov     rcx, rbx; hFile
0x1800b9ea1  call    cs:__imp_SetFileInformationByHandle
0x1800b9ea7  test    eax, eax
0x1800b9ea9  jz      short loc_1800B9E52
0x1800b9eab  mov     rcx, rbx; hFile
0x1800b9eae  call    _anonymous_namespace____Set_delete_flag
0x1800b9eb3  test    eax, eax
0x1800b9eb5  jnz     short loc_1800B9EE0
0x1800b9eb7  xor     edi, edi
0x1800b9eb9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9ebd  jz      short loc_1800B9ECC
0x1800b9ebf  mov     rcx, rbx; hObject
0x1800b9ec2  call    cs:__imp_CloseHandle
0x1800b9ec8  test    eax, eax
0x1800b9eca  jz      short loc_1800B9F1B
0x1800b9ecc  mov     byte ptr [rbp+hFile], 1
0x1800b9ed0  mov     word ptr [rbp+hFile+1], di
0x1800b9ed4  mov     byte ptr [rbp+hFile+3], dil
0x1800b9ed8  mov     dword ptr [rbp+hFile+4], edi
0x1800b9edb  jmp     loc_1800B9FD9
0x1800b9ee0  cmp     eax, r15d
0x1800b9ee3  jnz     short loc_1800B9F2B
0x1800b9ee5  or      dword ptr [rbp+var_10], 1
0x1800b9ee9  lea     r8, [rbp+var_30]; lpFileInformation
0x1800b9eed  mov     r9d, edi; dwBufferSize
0x1800b9ef0  xor     edx, edx; FileInformationClass
0x1800b9ef2  mov     rcx, rbx; hFile
0x1800b9ef5  call    cs:__imp_SetFileInformationByHandle
0x1800b9efb  test    eax, eax
0x1800b9efd  jz      loc_1800B9E52
0x1800b9f03  xor     dil, dil
0x1800b9f06  xor     esi, esi
0x1800b9f08  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9f0c  jz      short loc_1800B9F22
0x1800b9f0e  mov     rcx, rbx; hObject
0x1800b9f11  call    cs:__imp_CloseHandle
0x1800b9f17  test    eax, eax
0x1800b9f19  jnz     short loc_1800B9F22
0x1800b9f1b  call    cs:__imp_abort
0x1800b9f22  mov     dword ptr [rbp+hFile+4], r15d
0x1800b9f26  jmp     loc_1800B9FCD
0x1800b9f2b  xor     eax, eax
0x1800b9f2d  mov     byte ptr [rbp+hFile], 0
0x1800b9f31  mov     word ptr [rbp+hFile+1], ax
0x1800b9f35  mov     byte ptr [rbp+hFile+3], al
0x1800b9f38  call    cs:__imp_GetLastError
0x1800b9f3e  mov     dword ptr [rbp+hFile+4], eax
0x1800b9f41  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9f45  jz      loc_1800B9FD9
0x1800b9f4b  mov     rcx, rbx; hObject
0x1800b9f4e  call    cs:__imp_CloseHandle
0x1800b9f54  test    eax, eax
0x1800b9f56  jz      short loc_1800B9FC3
0x1800b9f58  jmp     short loc_1800B9FD9
0x1800b9f5a  xor     sil, sil
0x1800b9f5d  xor     r15d, r15d
0x1800b9f60  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9f64  jz      short loc_1800B9F73
0x1800b9f66  mov     rcx, rbx; hObject
0x1800b9f69  call    cs:__imp_CloseHandle
0x1800b9f6f  test    eax, eax
0x1800b9f71  jz      short loc_1800B9FC3
0x1800b9f73  mov     byte ptr [rbp+hFile], sil
0x1800b9f77  mov     word ptr [rbp+hFile+1], r15w
0x1800b9f7c  mov     byte ptr [rbp+hFile+3], r15b
0x1800b9f80  jmp     loc_1800B9ED8
0x1800b9f85  xor     dil, dil
0x1800b9f88  xor     esi, esi
0x1800b9f8a  sub     eax, 2
0x1800b9f8d  jz      short loc_1800B9FAD
0x1800b9f8f  sub     eax, 1
0x1800b9f92  jz      short loc_1800B9FAD
0x1800b9f94  sub     eax, 32h ; '2'
0x1800b9f97  jz      short loc_1800B9FAD
0x1800b9f99  sub     eax, 0Bh
0x1800b9f9c  jz      short loc_1800B9FAD
0x1800b9f9e  sub     eax, 3Bh ; ';'
0x1800b9fa1  jz      short loc_1800B9FAD
0x1800b9fa3  sub     eax, 26h ; '&'
0x1800b9fa6  jz      short loc_1800B9FAD
0x1800b9fa8  cmp     eax, 6Ah ; 'j'
0x1800b9fab  jnz     short loc_1800B9FAF
0x1800b9fad  xor     ebx, ebx
0x1800b9faf  mov     rcx, [rbp+hFile]; hObject
0x1800b9fb3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b9fb7  jz      short loc_1800B9FCA
0x1800b9fb9  call    cs:__imp_CloseHandle
0x1800b9fbf  test    eax, eax
0x1800b9fc1  jnz     short loc_1800B9FCA
0x1800b9fc3  call    cs:__imp_abort
0x1800b9fca  mov     dword ptr [rbp+hFile+4], ebx
0x1800b9fcd  mov     byte ptr [rbp+hFile], dil
0x1800b9fd1  mov     word ptr [rbp+hFile+1], si
0x1800b9fd5  mov     byte ptr [rbp+hFile+3], sil
0x1800b9fd9  mov     rax, [rbp+hFile]
0x1800b9fdd  mov     rcx, [rbp+var_8]
0x1800b9fe1  xor     rcx, rsp; StackCookie
0x1800b9fe4  call    __security_check_cookie
0x1800b9fe9  lea     r11, [rsp+60h+var_s0]
0x1800b9fee  mov     rbx, [r11+28h]
0x1800b9ff2  mov     rsi, [r11+30h]
0x1800b9ff6  mov     rsp, r11
0x1800b9ff9  pop     r15
0x1800b9ffb  pop     rdi
0x1800b9ffc  pop     rbp
0x1800b9ffd  retn
```
