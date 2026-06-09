# __std_fs_copy_file

- ea: `0x140058b18`
- end: `0x140058e32`
- name: `__std_fs_copy_file`
- size: `794`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1401467f8`
- `0x14018bbf8`

## callees

- `0x1400586e0`
- `0x14005874c`
- `0x140058b18`
- `0x140378e10`
- `0x140379070`
- `0x1403816b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058de6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058c53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058d5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058d7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058c53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058d5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140058d7a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140058bd6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140058c1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140058bd6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140058c1d`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140058b64`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140058d06`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140058b64`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x140058d06`

## pseudocode

```c
__int64 __fastcall _std_fs_copy_file(LPCWSTR lpExistingFileName, LPCWSTR lpNewFileName, char a3)
{
  int v3; // esi
  __int64 result; // rax
  DWORD v7; // edi
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  HANDLE v10; // rdi
  DWORD v11; // eax
  int v12; // eax
  int file_id_by_handle; // eax
  int v14; // eax
  __int64 v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+60h] [rbp+7h]
  __int128 Buf1; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+78h] [rbp+1Fh]

  v3 = a3 & 0xF;
  if ( v3 == 2 )
    goto LABEL_29;
  if ( CopyFileW(lpExistingFileName, lpNewFileName, 1) )
  {
    v15 = 1;
  }
  else
  {
    LOBYTE(v15) = 0;
    *(_WORD *)((char *)&v15 + 1) = 0;
    BYTE3(v15) = 0;
    HIDWORD(v15) = GetLastError();
  }
  result = v15;
  if ( HIDWORD(v15) == 80 && v3 )
  {
    v7 = HIDWORD(v15) - 77;
    if ( v3 != 1 )
      v7 = 1;
    FileW = CreateFileW(lpExistingFileName, HIDWORD(v15) + 48, v7, 0, HIDWORD(v15) - 77, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        *(_WORD *)((char *)&v15 + 1) = 0;
        BYTE3(v15) = 0;
        goto LABEL_44;
      }
    }
    v10 = CreateFileW(lpNewFileName, 0x80u, v7, 0, 3u, 0, 0);
    if ( v10 == (HANDLE)-1LL )
    {
      v11 = GetLastError();
      if ( v11 )
      {
        LOBYTE(v15) = 0;
        *(_WORD *)((char *)&v15 + 1) = 0;
        BYTE3(v15) = 0;
        HIDWORD(v15) = v11;
LABEL_15:
        if ( FileW == (HANDLE)-1LL || CloseHandle(FileW) )
          return v15;
LABEL_47:
        abort();
      }
    }
    if ( v3 != 4 )
      goto LABEL_31;
    v15 = 0;
    v12 = anonymous_namespace_::_Get_last_write_time_by_handle(FileW, &v15);
    if ( v12 || (v16 = 0, (v12 = anonymous_namespace_::_Get_last_write_time_by_handle(v10, &v16)) != 0) )
    {
      LOBYTE(v15) = 0;
      *(_WORD *)((char *)&v15 + 1) = 0;
      BYTE3(v15) = 0;
      HIDWORD(v15) = v12;
      if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) )
        goto LABEL_47;
      goto LABEL_15;
    }
    if ( v16 >= v15 )
    {
LABEL_31:
      Buf1 = 0;
      v20 = 0;
      file_id_by_handle = anonymous_namespace_::_Get_file_id_by_handle(FileW, &Buf1);
      if ( file_id_by_handle
        || (Buf2 = 0, v18 = 0, (file_id_by_handle = anonymous_namespace_::_Get_file_id_by_handle(v10, &Buf2)) != 0) )
      {
        LOBYTE(v15) = 0;
        BYTE3(v15) = 0;
        *(_WORD *)((char *)&v15 + 1) = 0;
        HIDWORD(v15) = file_id_by_handle;
      }
      else
      {
        v14 = memcmp(&Buf1, &Buf2, 0x18u);
        LOBYTE(v15) = 0;
        if ( v14 )
          HIDWORD(v15) = 0;
        else
          HIDWORD(v15) = 32;
        *(_WORD *)((char *)&v15 + 1) = 0;
        BYTE3(v15) = 0;
      }
      if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) || FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
        abort();
      return v15;
    }
    if ( v10 != (HANDLE)-1LL && !CloseHandle(v10) || FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
      goto LABEL_47;
LABEL_29:
    if ( CopyFileW(lpExistingFileName, lpNewFileName, 0) )
      return 1;
    LastError = GetLastError();
    *(_WORD *)((char *)&v15 + 1) = 0;
    BYTE3(v15) = 0;
LABEL_44:
    HIDWORD(v15) = LastError;
    LOBYTE(v15) = 0;
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x140058b18  mov     [rsp-8+arg_10], rbx
0x140058b1d  mov     [rsp-8+arg_18], rsi
0x140058b22  push    rbp
0x140058b23  push    rdi
0x140058b24  push    r12
0x140058b26  push    r14
0x140058b28  push    r15
0x140058b2a  lea     rbp, [rsp-37h]
0x140058b2f  sub     rsp, 90h
0x140058b36  mov     rax, cs:__security_cookie
0x140058b3d  xor     rax, rsp
0x140058b40  mov     [rbp+57h+var_30], rax
0x140058b44  mov     esi, r8d
0x140058b47  xor     r12d, r12d
0x140058b4a  and     esi, 0Fh
0x140058b4d  mov     r14, rdx
0x140058b50  mov     r15, rcx
0x140058b53  mov     ebx, 1
0x140058b58  cmp     esi, 2
0x140058b5b  jz      loc_140058CFD
0x140058b61  mov     r8d, ebx; bFailIfExists
0x140058b64  call    cs:__imp_CopyFileW
0x140058b6a  test    eax, eax
0x140058b6c  jz      short loc_140058B80
0x140058b6e  xor     eax, eax
0x140058b70  mov     byte ptr [rbp+57h+var_70], bl
0x140058b73  mov     word ptr [rbp+57h+var_70+1], ax
0x140058b77  mov     byte ptr [rbp+57h+var_70+3], al
0x140058b7a  mov     dword ptr [rbp+57h+var_70+4], r12d
0x140058b7e  jmp     short loc_140058B96
0x140058b80  xor     eax, eax
0x140058b82  mov     byte ptr [rbp+57h+var_70], r12b
0x140058b86  mov     word ptr [rbp+57h+var_70+1], ax
0x140058b8a  mov     byte ptr [rbp+57h+var_70+3], al
0x140058b8d  call    cs:__imp_GetLastError
0x140058b93  mov     dword ptr [rbp+57h+var_70+4], eax
0x140058b96  mov     rax, [rbp+57h+var_70]
0x140058b9a  mov     rcx, rax
0x140058b9d  shr     rcx, 20h
0x140058ba1  cmp     ecx, 50h ; 'P'
0x140058ba4  jnz     loc_140058DFE
0x140058baa  test    esi, esi
0x140058bac  jz      loc_140058DFE
0x140058bb2  lea     eax, [rcx-4Dh]
0x140058bb5  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x140058bba  mov     edi, eax
0x140058bbc  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140058bc1  lea     edx, [rcx+30h]; dwDesiredAccess
0x140058bc4  mov     [rsp+0B0h+dwCreationDisposition], eax; dwCreationDisposition
0x140058bc8  cmp     esi, ebx
0x140058bca  mov     rcx, r15; lpFileName
0x140058bcd  cmovnz  edi, ebx
0x140058bd0  xor     r9d, r9d; lpSecurityAttributes
0x140058bd3  mov     r8d, edi; dwShareMode
0x140058bd6  call    cs:__imp_CreateFileW
0x140058bdc  mov     rbx, rax
0x140058bdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140058be3  jnz     short loc_140058BFD
0x140058be5  call    cs:__imp_GetLastError
0x140058beb  test    eax, eax
0x140058bed  jz      short loc_140058BFD
0x140058bef  xor     ecx, ecx
0x140058bf1  mov     word ptr [rbp+57h+var_70+1], cx
0x140058bf5  mov     byte ptr [rbp+57h+var_70+3], cl
0x140058bf8  jmp     loc_140058DF3
0x140058bfd  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x140058c02  xor     r9d, r9d; lpSecurityAttributes
0x140058c05  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140058c0a  mov     r8d, edi; dwShareMode
0x140058c0d  mov     edx, 80h; dwDesiredAccess
0x140058c12  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x140058c1a  mov     rcx, r14; lpFileName
0x140058c1d  call    cs:__imp_CreateFileW
0x140058c23  mov     rdi, rax
0x140058c26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140058c2a  jnz     short loc_140058C66
0x140058c2c  call    cs:__imp_GetLastError
0x140058c32  test    eax, eax
0x140058c34  jz      short loc_140058C66
0x140058c36  xor     ecx, ecx
0x140058c38  mov     byte ptr [rbp+57h+var_70], r12b
0x140058c3c  mov     word ptr [rbp+57h+var_70+1], cx
0x140058c40  mov     byte ptr [rbp+57h+var_70+3], cl
0x140058c43  mov     dword ptr [rbp+57h+var_70+4], eax
0x140058c46  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140058c4a  jz      loc_140058DFA
0x140058c50  mov     rcx, rbx; hObject
0x140058c53  call    cs:__imp_CloseHandle
0x140058c59  test    eax, eax
0x140058c5b  jz      loc_140058E26
0x140058c61  jmp     loc_140058DFA
0x140058c66  cmp     esi, 4
0x140058c69  jnz     loc_140058D29
0x140058c6f  lea     rdx, [rbp+57h+var_70]
0x140058c73  mov     [rbp+57h+var_70], r12
0x140058c77  mov     rcx, rbx
0x140058c7a  call    _anonymous_namespace____Get_last_write_time_by_handle
0x140058c7f  test    eax, eax
0x140058c81  jz      short loc_140058CAC
0x140058c83  xor     ecx, ecx
0x140058c85  mov     byte ptr [rbp+57h+var_70], r12b
0x140058c89  mov     word ptr [rbp+57h+var_70+1], cx
0x140058c8d  mov     byte ptr [rbp+57h+var_70+3], cl
0x140058c90  mov     dword ptr [rbp+57h+var_70+4], eax
0x140058c93  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140058c97  jz      short loc_140058C46
0x140058c99  mov     rcx, rdi; hObject
0x140058c9c  call    cs:__imp_CloseHandle
0x140058ca2  test    eax, eax
0x140058ca4  jz      loc_140058E26
0x140058caa  jmp     short loc_140058C46
0x140058cac  lea     rdx, [rbp+57h+var_68]
0x140058cb0  mov     [rbp+57h+var_68], r12
0x140058cb4  mov     rcx, rdi
0x140058cb7  call    _anonymous_namespace____Get_last_write_time_by_handle
0x140058cbc  test    eax, eax
0x140058cbe  jnz     short loc_140058C83
0x140058cc0  mov     rax, [rbp+57h+var_70]
0x140058cc4  cmp     [rbp+57h+var_68], rax
0x140058cc8  jge     short loc_140058D29
0x140058cca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140058cce  jz      short loc_140058CE1
0x140058cd0  mov     rcx, rdi; hObject
0x140058cd3  call    cs:__imp_CloseHandle
0x140058cd9  test    eax, eax
0x140058cdb  jz      loc_140058E26
0x140058ce1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140058ce5  jz      short loc_140058CF8
0x140058ce7  mov     rcx, rbx; hObject
0x140058cea  call    cs:__imp_CloseHandle
0x140058cf0  test    eax, eax
0x140058cf2  jz      loc_140058E26
0x140058cf8  mov     ebx, 1
0x140058cfd  xor     r8d, r8d; bFailIfExists
0x140058d00  mov     rdx, r14; lpNewFileName
0x140058d03  mov     rcx, r15; lpExistingFileName
0x140058d06  call    cs:__imp_CopyFileW
0x140058d0c  test    eax, eax
0x140058d0e  jz      loc_140058DE4
0x140058d14  xor     eax, eax
0x140058d16  mov     byte ptr [rbp+57h+var_70], bl
0x140058d19  mov     word ptr [rbp+57h+var_70+1], ax
0x140058d1d  mov     byte ptr [rbp+57h+var_70+3], al
0x140058d20  mov     dword ptr [rbp+57h+var_70+4], r12d
0x140058d24  jmp     loc_140058DFA
0x140058d29  xorps   xmm0, xmm0
0x140058d2c  lea     rdx, [rbp+57h+Buf1]; lpFileInformation
0x140058d30  xor     eax, eax
0x140058d32  mov     rcx, rbx; hFile
0x140058d35  movups  [rbp+57h+Buf1], xmm0
0x140058d39  mov     [rbp+57h+var_38], rax
0x140058d3d  call    _anonymous_namespace____Get_file_id_by_handle
0x140058d42  test    eax, eax
0x140058d44  jz      short loc_140058D8A
0x140058d46  xor     ecx, ecx
0x140058d48  mov     byte ptr [rbp+57h+var_70], r12b
0x140058d4c  mov     byte ptr [rbp+57h+var_70+3], cl
0x140058d4f  mov     word ptr [rbp+57h+var_70+1], cx
0x140058d53  mov     dword ptr [rbp+57h+var_70+4], eax
0x140058d56  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140058d5a  jz      short loc_140058D6D
0x140058d5c  mov     rcx, rdi; hObject
0x140058d5f  call    cs:__imp_CloseHandle
0x140058d65  test    eax, eax
0x140058d67  jz      loc_140058E2C
0x140058d6d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140058d71  jz      loc_140058DFA
0x140058d77  mov     rcx, rbx; hObject
0x140058d7a  call    cs:__imp_CloseHandle
0x140058d80  test    eax, eax
0x140058d82  jz      loc_140058E2C
0x140058d88  jmp     short loc_140058DFA
0x140058d8a  xorps   xmm0, xmm0
0x140058d8d  lea     rdx, [rbp+57h+Buf2]; lpFileInformation
0x140058d91  xor     eax, eax
0x140058d93  mov     rcx, rdi; hFile
0x140058d96  movups  [rbp+57h+Buf2], xmm0
0x140058d9a  mov     [rbp+57h+var_50], rax
0x140058d9e  call    _anonymous_namespace____Get_file_id_by_handle
0x140058da3  test    eax, eax
0x140058da5  jnz     short loc_140058D46
0x140058da7  lea     r8d, [rax+18h]; Size
0x140058dab  lea     rdx, [rbp+57h+Buf2]; Buf2
0x140058daf  lea     rcx, [rbp+57h+Buf1]; Buf1
0x140058db3  call    memcmp
0x140058db8  mov     byte ptr [rbp+57h+var_70], r12b
0x140058dbc  test    eax, eax
0x140058dbe  jnz     short loc_140058DD2
0x140058dc0  xor     eax, eax
0x140058dc2  mov     dword ptr [rbp+57h+var_70+4], 20h ; ' '
0x140058dc9  mov     word ptr [rbp+57h+var_70+1], ax
0x140058dcd  mov     byte ptr [rbp+57h+var_70+3], al
0x140058dd0  jmp     short loc_140058D56
0x140058dd2  xor     eax, eax
0x140058dd4  mov     dword ptr [rbp+57h+var_70+4], r12d
0x140058dd8  mov     word ptr [rbp+57h+var_70+1], ax
0x140058ddc  mov     byte ptr [rbp+57h+var_70+3], al
0x140058ddf  jmp     loc_140058D56
0x140058de4  xor     ebx, ebx
0x140058de6  call    cs:__imp_GetLastError
0x140058dec  mov     word ptr [rbp+57h+var_70+1], bx
0x140058df0  mov     byte ptr [rbp+57h+var_70+3], bl
0x140058df3  mov     dword ptr [rbp+57h+var_70+4], eax
0x140058df6  mov     byte ptr [rbp+57h+var_70], r12b
0x140058dfa  mov     rax, [rbp+57h+var_70]
0x140058dfe  mov     rcx, [rbp+57h+var_30]
0x140058e02  xor     rcx, rsp; StackCookie
0x140058e05  call    __security_check_cookie
0x140058e0a  lea     r11, [rsp+0B0h+var_20]
0x140058e12  mov     rbx, [r11+40h]
0x140058e16  mov     rsi, [r11+48h]
0x140058e1a  mov     rsp, r11
0x140058e1d  pop     r15
0x140058e1f  pop     r14
0x140058e21  pop     r12
0x140058e23  pop     rdi
0x140058e24  pop     rbp
0x140058e25  retn
0x140058e26  call    abort
0x140058e2c  call    abort
```
