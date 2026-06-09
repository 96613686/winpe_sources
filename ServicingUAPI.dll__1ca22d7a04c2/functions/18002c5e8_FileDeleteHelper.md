# FileDeleteHelper

- ea: `0x18002c5e8`
- end: `0x18002c76c`
- name: `FileDeleteHelper`
- size: `388`
- prototype: `__int64 __fastcall(LPCWSTR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002c084`
- `0x18002f428`

## callees

- `0x1800031d0`
- `0x18002c5e8`
- `0x18002e6ac`
- `0x18002e70c`

## import_xrefs

- `ntdll!NtClose` at `0x18002c68a`
- `ntdll!NtClose` at `0x18002c750`
- `ntdll!NtClose` at `0x18002c68a`
- `ntdll!NtClose` at `0x18002c750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65a`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c738`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002c738`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c63c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c63c`

## pseudocode

```c
__int64 __fastcall FileDeleteHelper(LPCWSTR *a1)
{
  unsigned __int16 v2; // dx
  unsigned __int16 v3; // cx
  HANDLE FileW; // rbx
  unsigned __int16 v5; // r8
  bool v6; // cc
  unsigned __int64 v7; // rax
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // cx
  unsigned __int16 v11; // r8
  FILE_INFO_BY_HANDLE_CLASS v12; // esi
  char *p_FileInformation; // r14
  DWORD v14; // edi
  _BYTE v15[8]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h]
  HANDLE v17; // [rsp+50h] [rbp-28h]
  char v18; // [rsp+58h] [rbp-20h] BYREF
  int FileInformation; // [rsp+5Ch] [rbp-1Ch] BYREF

  v16 = -2;
  FileW = CreateFileW(*a1, 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  v17 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v18 = 0;
    FileInformation = 0;
    v15[0] = 0;
    if ( !IsWindowsVersionOrGreaterEx(v3, v2, v5, 0x383Au) || (int)IsPathFAT(FileW, a1, v15) < 0 || v15[0] )
    {
      v12 = FileDispositionInfo;
      v18 = 1;
      p_FileInformation = &v18;
      v14 = 1;
    }
    else
    {
      v12 = FileRenameInfoEx|FileDispositionInfo;
      p_FileInformation = (char *)&FileInformation;
      v14 = 4;
      FileInformation = 3;
      if ( IsWindowsVersionOrGreaterEx(v10, v9, v11, 0x4563u) )
        FileInformation |= 0x10u;
    }
    if ( !SetFileInformationByHandle(FileW, v12, p_FileInformation, v14) )
      goto LABEL_16;
    goto LABEL_6;
  }
  v6 = GetLastError() - 2 <= 1;
  v7 = (unsigned __int64)FileW - 1;
  if ( v6 )
  {
    if ( v7 > 0xFFFFFFFFFFFFFFFDuLL )
      return 1;
LABEL_6:
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
    return 1;
  }
  if ( v7 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_16:
    if ( NtClose(FileW) < 0 )
      __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c5e8  push    rbp
0x18002c5ea  push    rbx
0x18002c5eb  push    rsi
0x18002c5ec  push    rdi
0x18002c5ed  push    r12
0x18002c5ef  push    r14
0x18002c5f1  mov     rbp, rsp
0x18002c5f4  sub     rsp, 78h
0x18002c5f8  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18002c600  mov     rax, cs:__security_cookie
0x18002c607  xor     rax, rsp
0x18002c60a  mov     [rbp+var_18], rax
0x18002c60e  mov     rdi, rcx
0x18002c611  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002c61a  mov     [rsp+78h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002c622  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c62a  xor     r9d, r9d; lpSecurityAttributes
0x18002c62d  lea     r12d, [r9+7]
0x18002c631  mov     r8d, r12d; dwShareMode
0x18002c634  mov     edx, 10180h; dwDesiredAccess
0x18002c639  mov     rcx, [rcx]; lpFileName
0x18002c63c  call    cs:__imp_CreateFileW
0x18002c643  nop     dword ptr [rax+rax+00h]
0x18002c648  mov     rbx, rax
0x18002c64b  mov     [rbp+var_28], rax
0x18002c64f  inc     rax
0x18002c652  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002c658  jnz     short loc_18002C6BE
0x18002c65a  call    cs:__imp_GetLastError
0x18002c661  nop     dword ptr [rax+rax+00h]
0x18002c666  add     eax, 0FFFFFFFEh
0x18002c669  cmp     eax, 1
0x18002c66c  lea     rax, [rbx-1]
0x18002c670  jbe     short loc_18002C681
0x18002c672  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c676  ja      loc_18002C765
0x18002c67c  jmp     loc_18002C74D
0x18002c681  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c685  ja      short loc_18002C69F
0x18002c687  mov     rcx, rbx; Handle
0x18002c68a  call    cs:__imp_NtClose
0x18002c691  nop     dword ptr [rax+rax+00h]
0x18002c696  test    eax, eax
0x18002c698  jns     short loc_18002C69F
0x18002c69a  mov     rcx, r12
0x18002c69d  int     29h; Win8: RtlFailFast(ecx)
0x18002c69f  mov     eax, 1
0x18002c6a4  mov     rcx, [rbp+var_18]
0x18002c6a8  xor     rcx, rsp; StackCookie
0x18002c6ab  call    __security_check_cookie
0x18002c6b0  add     rsp, 78h
0x18002c6b4  pop     r14
0x18002c6b6  pop     r12
0x18002c6b8  pop     rdi
0x18002c6b9  pop     rsi
0x18002c6ba  pop     rbx
0x18002c6bb  pop     rbp
0x18002c6bc  retn
0x18002c6be  mov     [rbp+var_20], 0
0x18002c6c2  mov     [rbp+FileInformation], 0
0x18002c6c9  mov     [rbp+var_38], 0
0x18002c6cd  mov     r9d, 383Ah; unsigned __int16
0x18002c6d3  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18002c6d8  test    al, al
0x18002c6da  jz      short loc_18002C71D
0x18002c6dc  lea     r8, [rbp+var_38]
0x18002c6e0  mov     rdx, rdi
0x18002c6e3  mov     rcx, rbx
0x18002c6e6  call    ?IsPathFAT@@YAJPEAXAEBV?$basic_zstring_view@_W@wil@@PEA_N@Z; IsPathFAT(void *,wil::basic_zstring_view<wchar_t> const &,bool *)
0x18002c6eb  test    eax, eax
0x18002c6ed  js      short loc_18002C71D
0x18002c6ef  cmp     [rbp+var_38], 0
0x18002c6f3  jnz     short loc_18002C71D
0x18002c6f5  mov     esi, 15h
0x18002c6fa  lea     r14, [rbp+FileInformation]
0x18002c6fe  lea     edi, [rsi-11h]
0x18002c701  mov     [rbp+FileInformation], 3
0x18002c708  mov     r9d, 4563h; unsigned __int16
0x18002c70e  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18002c713  test    al, al
0x18002c715  jz      short loc_18002C72D
0x18002c717  or      [rbp+FileInformation], 10h
0x18002c71b  jmp     short loc_18002C72D
0x18002c71d  mov     esi, 4
0x18002c722  mov     [rbp+var_20], 1
0x18002c726  lea     r14, [rbp+var_20]
0x18002c72a  lea     edi, [rsi-3]
0x18002c72d  mov     r9d, edi; dwBufferSize
0x18002c730  mov     r8, r14; lpFileInformation
0x18002c733  mov     edx, esi; FileInformationClass
0x18002c735  mov     rcx, rbx; hFile
0x18002c738  call    cs:__imp_SetFileInformationByHandle
0x18002c73f  nop     dword ptr [rax+rax+00h]
0x18002c744  nop
0x18002c745  test    eax, eax
0x18002c747  jnz     loc_18002C687
0x18002c74d  mov     rcx, rbx; Handle
0x18002c750  call    cs:__imp_NtClose
0x18002c757  nop     dword ptr [rax+rax+00h]
0x18002c75c  test    eax, eax
0x18002c75e  jns     short loc_18002C765
0x18002c760  mov     rcx, r12
0x18002c763  int     29h; Win8: RtlFailFast(ecx)
0x18002c765  xor     eax, eax
0x18002c767  jmp     loc_18002C6A4
```
