# __std_fs_remove

- ea: `0x180005df4`
- end: `0x180006136`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800b6e80`

## callees

- `0x1800031d0`
- `0x180004f54`
- `0x180005cc0`
- `0x180005df4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006053`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800060fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006053`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800060fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006070`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060f1`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180005f80`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180005f80`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005e5d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005fd9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000602d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005e5d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005fd9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000602d`

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
0x180005df4  mov     [rsp-18h+arg_8], rbx
0x180005df9  mov     [rsp-18h+arg_10], rsi
0x180005dfe  push    rbp
0x180005dff  push    rdi
0x180005e00  push    r15
0x180005e02  mov     rbp, rsp
0x180005e05  sub     rsp, 60h
0x180005e09  mov     rax, cs:__security_cookie
0x180005e10  xor     rax, rsp
0x180005e13  mov     [rbp+var_8], rax
0x180005e17  mov     rdi, rcx
0x180005e1a  mov     rdx, rcx
0x180005e1d  lea     rcx, [rbp+hFile]
0x180005e21  mov     r9d, 2200000h
0x180005e27  mov     r8d, 10180h
0x180005e2d  call    __std_fs_open_handle
0x180005e32  mov     ebx, eax
0x180005e34  mov     r15d, 5
0x180005e3a  test    eax, eax
0x180005e3c  jnz     short loc_180005E95
0x180005e3e  mov     sil, 1
0x180005e41  mov     rbx, [rbp+hFile]
0x180005e45  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180005e49  mov     r9d, 4; dwBufferSize
0x180005e4f  mov     dword ptr [rbp+FileInformation], 13h
0x180005e56  mov     rcx, rbx; hFile
0x180005e59  lea     edx, [r9+11h]; FileInformationClass
0x180005e5d  call    cs:__imp_SetFileInformationByHandle
0x180005e63  test    eax, eax
0x180005e65  jz      loc_180005EF4
0x180005e6b  xor     edi, edi
0x180005e6d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005e71  jz      short loc_180005E84
0x180005e73  mov     rcx, rbx; hObject
0x180005e76  call    cs:__imp_CloseHandle
0x180005e7c  test    eax, eax
0x180005e7e  jz      loc_1800060FB
0x180005e84  mov     byte ptr [rbp+FileInformation], 1
0x180005e88  mov     word ptr [rbp+FileInformation+1], di
0x180005e8c  mov     byte ptr [rbp+FileInformation+3], dil
0x180005e90  mov     dword ptr [rbp+FileInformation+4], edi
0x180005e93  jmp     short loc_180005EEB
0x180005e95  cmp     eax, r15d
0x180005e98  jnz     loc_1800060BD
0x180005e9e  mov     r9d, 2200000h
0x180005ea4  lea     rcx, [rbp+hFile]
0x180005ea8  mov     r8d, 10000h
0x180005eae  mov     rdx, rdi
0x180005eb1  xor     sil, sil
0x180005eb4  call    __std_fs_open_handle
0x180005eb9  mov     ebx, eax
0x180005ebb  test    eax, eax
0x180005ebd  jz      short loc_180005E41
0x180005ebf  mov     rcx, [rbp+hFile]; hObject
0x180005ec3  xor     dil, dil
0x180005ec6  xor     esi, esi
0x180005ec8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005ecc  jz      short loc_180005EDC
0x180005ece  call    cs:__imp_CloseHandle
0x180005ed4  test    eax, eax
0x180005ed6  jz      loc_1800060FB
0x180005edc  mov     byte ptr [rbp+FileInformation], dil
0x180005ee0  mov     word ptr [rbp+FileInformation+1], si
0x180005ee4  mov     byte ptr [rbp+FileInformation+3], sil
0x180005ee8  mov     dword ptr [rbp+FileInformation+4], ebx
0x180005eeb  mov     rax, [rbp+FileInformation]
0x180005eef  jmp     loc_180006115
0x180005ef4  call    cs:__imp_GetLastError
0x180005efa  mov     ecx, eax
0x180005efc  mov     edi, eax
0x180005efe  sub     ecx, 1
0x180005f01  jz      short loc_180005F3C
0x180005f03  sub     ecx, 31h ; '1'
0x180005f06  jz      short loc_180005F3C
0x180005f08  cmp     ecx, 25h ; '%'
0x180005f0b  jz      short loc_180005F3C
0x180005f0d  xor     sil, sil
0x180005f10  xor     r15d, r15d
0x180005f13  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005f17  jz      short loc_180005F2A
0x180005f19  mov     rcx, rbx; hObject
0x180005f1c  call    cs:__imp_CloseHandle
0x180005f22  test    eax, eax
0x180005f24  jz      loc_1800060FB
0x180005f2a  mov     byte ptr [rbp+FileInformation], sil
0x180005f2e  mov     word ptr [rbp+FileInformation+1], r15w
0x180005f33  mov     byte ptr [rbp+FileInformation+3], r15b
0x180005f37  jmp     loc_180005E90
0x180005f3c  mov     rcx, rbx; hFile
0x180005f3f  call    _anonymous_namespace____Set_delete_flag
0x180005f44  mov     edi, eax
0x180005f46  test    eax, eax
0x180005f48  jz      loc_180005E6B
0x180005f4e  cmp     eax, r15d
0x180005f51  jnz     loc_180006092
0x180005f57  test    sil, sil
0x180005f5a  jz      loc_180006092
0x180005f60  xor     eax, eax
0x180005f62  lea     r8, [rbp+var_30]; lpFileInformation
0x180005f66  xorps   xmm0, xmm0
0x180005f69  mov     [rbp+var_10], rax
0x180005f6d  xor     edx, edx; FileInformationClass
0x180005f6f  mov     rcx, rbx; hFile
0x180005f72  movups  [rbp+var_30], xmm0
0x180005f76  lea     edi, [rax+28h]
0x180005f79  mov     r9d, edi; dwBufferSize
0x180005f7c  movups  [rbp+var_20], xmm0
0x180005f80  call    cs:__imp_GetFileInformationByHandleEx
0x180005f86  test    eax, eax
0x180005f88  jnz     short loc_180005FC0
0x180005f8a  xor     eax, eax
0x180005f8c  mov     byte ptr [rbp+hFile], 0
0x180005f90  mov     word ptr [rbp+hFile+1], ax
0x180005f94  mov     byte ptr [rbp+hFile+3], al
0x180005f97  call    cs:__imp_GetLastError
0x180005f9d  mov     dword ptr [rbp+hFile+4], eax
0x180005fa0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005fa4  jz      loc_180006111
0x180005faa  mov     rcx, rbx; hObject
0x180005fad  call    cs:__imp_CloseHandle
0x180005fb3  test    eax, eax
0x180005fb5  jz      loc_180006053
0x180005fbb  jmp     loc_180006111
0x180005fc0  mov     eax, dword ptr [rbp+var_10]
0x180005fc3  test    al, 1
0x180005fc5  jz      short loc_18000603B
0x180005fc7  xor     eax, 1
0x180005fca  lea     r8, [rbp+var_30]; lpFileInformation
0x180005fce  mov     r9d, edi; dwBufferSize
0x180005fd1  mov     dword ptr [rbp+var_10], eax
0x180005fd4  xor     edx, edx; FileInformationClass
0x180005fd6  mov     rcx, rbx; hFile
0x180005fd9  call    cs:__imp_SetFileInformationByHandle
0x180005fdf  test    eax, eax
0x180005fe1  jz      short loc_180005F8A
0x180005fe3  mov     rcx, rbx; hFile
0x180005fe6  call    _anonymous_namespace____Set_delete_flag
0x180005feb  test    eax, eax
0x180005fed  jnz     short loc_180006018
0x180005fef  xor     edi, edi
0x180005ff1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005ff5  jz      short loc_180006004
0x180005ff7  mov     rcx, rbx; hObject
0x180005ffa  call    cs:__imp_CloseHandle
0x180006000  test    eax, eax
0x180006002  jz      short loc_180006053
0x180006004  mov     byte ptr [rbp+hFile], 1
0x180006008  mov     word ptr [rbp+hFile+1], di
0x18000600c  mov     byte ptr [rbp+hFile+3], dil
0x180006010  mov     dword ptr [rbp+hFile+4], edi
0x180006013  jmp     loc_180006111
0x180006018  cmp     eax, r15d
0x18000601b  jnz     short loc_180006063
0x18000601d  or      dword ptr [rbp+var_10], 1
0x180006021  lea     r8, [rbp+var_30]; lpFileInformation
0x180006025  mov     r9d, edi; dwBufferSize
0x180006028  xor     edx, edx; FileInformationClass
0x18000602a  mov     rcx, rbx; hFile
0x18000602d  call    cs:__imp_SetFileInformationByHandle
0x180006033  test    eax, eax
0x180006035  jz      loc_180005F8A
0x18000603b  xor     dil, dil
0x18000603e  xor     esi, esi
0x180006040  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180006044  jz      short loc_18000605A
0x180006046  mov     rcx, rbx; hObject
0x180006049  call    cs:__imp_CloseHandle
0x18000604f  test    eax, eax
0x180006051  jnz     short loc_18000605A
0x180006053  call    cs:__imp_abort
0x18000605a  mov     dword ptr [rbp+hFile+4], r15d
0x18000605e  jmp     loc_180006105
0x180006063  xor     eax, eax
0x180006065  mov     byte ptr [rbp+hFile], 0
0x180006069  mov     word ptr [rbp+hFile+1], ax
0x18000606d  mov     byte ptr [rbp+hFile+3], al
0x180006070  call    cs:__imp_GetLastError
0x180006076  mov     dword ptr [rbp+hFile+4], eax
0x180006079  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000607d  jz      loc_180006111
0x180006083  mov     rcx, rbx; hObject
0x180006086  call    cs:__imp_CloseHandle
0x18000608c  test    eax, eax
0x18000608e  jz      short loc_1800060FB
0x180006090  jmp     short loc_180006111
0x180006092  xor     sil, sil
0x180006095  xor     r15d, r15d
0x180006098  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000609c  jz      short loc_1800060AB
0x18000609e  mov     rcx, rbx; hObject
0x1800060a1  call    cs:__imp_CloseHandle
0x1800060a7  test    eax, eax
0x1800060a9  jz      short loc_1800060FB
0x1800060ab  mov     byte ptr [rbp+hFile], sil
0x1800060af  mov     word ptr [rbp+hFile+1], r15w
0x1800060b4  mov     byte ptr [rbp+hFile+3], r15b
0x1800060b8  jmp     loc_180006010
0x1800060bd  xor     dil, dil
0x1800060c0  xor     esi, esi
0x1800060c2  sub     eax, 2
0x1800060c5  jz      short loc_1800060E5
0x1800060c7  sub     eax, 1
0x1800060ca  jz      short loc_1800060E5
0x1800060cc  sub     eax, 32h ; '2'
0x1800060cf  jz      short loc_1800060E5
0x1800060d1  sub     eax, 0Bh
0x1800060d4  jz      short loc_1800060E5
0x1800060d6  sub     eax, 3Bh ; ';'
0x1800060d9  jz      short loc_1800060E5
0x1800060db  sub     eax, 26h ; '&'
0x1800060de  jz      short loc_1800060E5
0x1800060e0  cmp     eax, 6Ah ; 'j'
0x1800060e3  jnz     short loc_1800060E7
0x1800060e5  xor     ebx, ebx
0x1800060e7  mov     rcx, [rbp+hFile]; hObject
0x1800060eb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060ef  jz      short loc_180006102
0x1800060f1  call    cs:__imp_CloseHandle
0x1800060f7  test    eax, eax
0x1800060f9  jnz     short loc_180006102
0x1800060fb  call    cs:__imp_abort
0x180006102  mov     dword ptr [rbp+hFile+4], ebx
0x180006105  mov     byte ptr [rbp+hFile], dil
0x180006109  mov     word ptr [rbp+hFile+1], si
0x18000610d  mov     byte ptr [rbp+hFile+3], sil
0x180006111  mov     rax, [rbp+hFile]
0x180006115  mov     rcx, [rbp+var_8]
0x180006119  xor     rcx, rsp; StackCookie
0x18000611c  call    __security_check_cookie
0x180006121  lea     r11, [rsp+60h+var_s0]
0x180006126  mov     rbx, [r11+28h]
0x18000612a  mov     rsi, [r11+30h]
0x18000612e  mov     rsp, r11
0x180006131  pop     r15
0x180006133  pop     rdi
0x180006134  pop     rbp
0x180006135  retn
```
