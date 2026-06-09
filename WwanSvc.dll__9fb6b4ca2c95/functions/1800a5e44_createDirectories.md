# _createDirectories

- ea: `0x1800a5e44`
- end: `0x1800a600f`
- name: `_createDirectories`
- size: `459`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800a5c88`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180019f24`
- `0x180074758`
- `0x180074cec`
- `0x1800a5e44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5e6d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5e93`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5f2a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5e6d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5e93`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800a5f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5fa8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a5ef6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a5fcf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a5ef6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800a5fcf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5ed0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5edd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5f5b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5fba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5ed0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5edd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5f5b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a5fba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a5eaf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a5f41`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a5eaf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a5f41`

## string_xrefs

- `0x1800a5f6f`: `CreateDirectory failed, errCode (0x%8x)`
- `0x1800a5e56`: `_createDirectories`
- `0x1800a5e99`: `Path %s already exists with attributes 0x%x`
- `0x1800a5f04`: `Path %s created and set with attributes 0x%x`
- `0x1800a5fd9`: `Path %s created and set with attributes 0x%x`
- `0x1800a5f9b`: `SetFileAttributes failed, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall createDirectories(wchar_t *lpFileName)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rax
  const unsigned __int16 *v4; // rbp
  const unsigned __int16 *v5; // r14
  DWORD v6; // esi
  DWORD FileAttributesW; // esi
  wchar_t *v8; // rdi
  DWORD v9; // edi
  DWORD LastError; // eax
  const unsigned __int16 *v11; // r8
  DWORD v12; // ebx
  DWORD v14; // edi
  __int64 v15; // [rsp+20h] [rbp-48h]

  WwanLog::Enter("_createDirectories");
  v2 = wcschr(lpFileName, 0x3Au);
  if ( v2 )
  {
    do
      ++v2;
    while ( *v2 == 92 );
  }
  else
  {
    v2 = lpFileName;
  }
  v3 = wcschr(v2, 0x5Cu);
  v4 = L"Path %s already exists with attributes 0x%x";
  while ( 1 )
  {
    v8 = v3;
    if ( !v3 )
      break;
    *v3 = 0;
    if ( CreateDirectoryW(lpFileName, 0) )
    {
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
      {
        *v8 = 92;
        goto LABEL_23;
      }
      v6 = FileAttributesW | 2;
      if ( !SetFileAttributesW(lpFileName, v6) )
      {
        *v8 = 92;
        goto LABEL_21;
      }
      v5 = L"Path %s created and set with attributes 0x%x";
    }
    else
    {
      if ( GetLastError() != 183 )
      {
        *v8 = 92;
LABEL_18:
        LastError = GetLastError();
        v11 = L"CreateDirectory failed, errCode (0x%8x)";
LABEL_19:
        v12 = LastError;
        WwanLog::Error("_createDirectories", 0, v11, LastError);
        WwanLog::Exit("_createDirectories");
        return v12;
      }
      v5 = L"Path %s already exists with attributes 0x%x";
      v6 = GetFileAttributesW(lpFileName);
    }
    LODWORD(v15) = v6;
    WwanLog::Info("_createDirectories", 0, v5, lpFileName, v15);
    *v8 = 92;
    v3 = wcschr(v8 + 1, 0x5Cu);
  }
  if ( CreateDirectoryW(lpFileName, 0) )
  {
    v14 = GetFileAttributesW(lpFileName);
    if ( v14 == -1 )
    {
LABEL_23:
      LastError = GetLastError();
      v11 = L"GetFileAttributes failed, errCode (0x%8x)";
      goto LABEL_19;
    }
    v9 = v14 | 2;
    if ( !SetFileAttributesW(lpFileName, v9) )
    {
LABEL_21:
      LastError = GetLastError();
      v11 = L"SetFileAttributes failed, errCode (0x%8x)";
      goto LABEL_19;
    }
    v4 = L"Path %s created and set with attributes 0x%x";
  }
  else
  {
    if ( GetLastError() != 183 )
      goto LABEL_18;
    v9 = GetFileAttributesW(lpFileName);
  }
  LODWORD(v15) = v9;
  WwanLog::Info("_createDirectories", 0, v4, lpFileName, v15);
  WwanLog::ExitWithStatus("_createDirectories", 0);
  return 0;
}

```

## disassembly

```asm
0x1800a5e44  push    rbx
0x1800a5e46  push    rbp
0x1800a5e47  push    rsi
0x1800a5e48  push    rdi
0x1800a5e49  push    r12
0x1800a5e4b  push    r14
0x1800a5e4d  push    r15
0x1800a5e4f  sub     rsp, 30h
0x1800a5e53  mov     rbx, rcx
0x1800a5e56  lea     r15, aCreatedirector_0; "_createDirectories"
0x1800a5e5d  mov     rcx, r15; char *
0x1800a5e60  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a5e65  mov     edx, 3Ah ; ':'; Ch
0x1800a5e6a  mov     rcx, rbx; Str
0x1800a5e6d  call    cs:__imp_wcschr
0x1800a5e73  mov     r12d, 5Ch ; '\'
0x1800a5e79  test    rax, rax
0x1800a5e7c  jz      short loc_1800A5E8A
0x1800a5e7e  add     rax, 2
0x1800a5e82  cmp     [rax], r12w
0x1800a5e86  jz      short loc_1800A5E7E
0x1800a5e88  jmp     short loc_1800A5E8D
0x1800a5e8a  mov     rax, rbx
0x1800a5e8d  mov     edx, r12d; Ch
0x1800a5e90  mov     rcx, rax; Str
0x1800a5e93  call    cs:__imp_wcschr
0x1800a5e99  lea     rbp, aPathSAlreadyEx; "Path %s already exists with attributes "...
0x1800a5ea0  jmp     loc_1800A5F30
0x1800a5ea5  xor     ecx, ecx
0x1800a5ea7  xor     edx, edx; lpSecurityAttributes
0x1800a5ea9  mov     [rdi], cx
0x1800a5eac  mov     rcx, rbx; lpPathName
0x1800a5eaf  call    cs:__imp_CreateDirectoryW
0x1800a5eb5  test    eax, eax
0x1800a5eb7  jnz     short loc_1800A5EDA
0x1800a5eb9  call    cs:__imp_GetLastError
0x1800a5ebf  cmp     eax, 0B7h
0x1800a5ec4  jnz     loc_1800A5F65
0x1800a5eca  mov     rcx, rbx; lpFileName
0x1800a5ecd  mov     r14, rbp
0x1800a5ed0  call    cs:__imp_GetFileAttributesW
0x1800a5ed6  mov     esi, eax
0x1800a5ed8  jmp     short loc_1800A5F0B
0x1800a5eda  mov     rcx, rbx; lpFileName
0x1800a5edd  call    cs:__imp_GetFileAttributesW
0x1800a5ee3  mov     esi, eax
0x1800a5ee5  cmp     eax, 0FFFFFFFFh
0x1800a5ee8  jz      loc_1800A5FA4
0x1800a5eee  or      esi, 2
0x1800a5ef1  mov     rcx, rbx; lpFileName
0x1800a5ef4  mov     edx, esi; dwFileAttributes
0x1800a5ef6  call    cs:__imp_SetFileAttributesW
0x1800a5efc  test    eax, eax
0x1800a5efe  jz      loc_1800A5F91
0x1800a5f04  lea     r14, aPathSCreatedAn; "Path %s created and set with attributes"...
0x1800a5f0b  mov     r9, rbx
0x1800a5f0e  mov     dword ptr [rsp+68h+var_48], esi
0x1800a5f12  mov     r8, r14; unsigned __int16 *
0x1800a5f15  xor     edx, edx; struct _GUID *
0x1800a5f17  mov     rcx, r15; char *
0x1800a5f1a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a5f1f  mov     edx, r12d; Ch
0x1800a5f22  mov     [rdi], r12w
0x1800a5f26  lea     rcx, [rdi+2]; Str
0x1800a5f2a  call    cs:__imp_wcschr
0x1800a5f30  mov     rdi, rax
0x1800a5f33  test    rax, rax
0x1800a5f36  jnz     loc_1800A5EA5
0x1800a5f3c  xor     edx, edx; lpSecurityAttributes
0x1800a5f3e  mov     rcx, rbx; lpPathName
0x1800a5f41  call    cs:__imp_CreateDirectoryW
0x1800a5f47  test    eax, eax
0x1800a5f49  jnz     short loc_1800A5FB7
0x1800a5f4b  call    cs:__imp_GetLastError
0x1800a5f51  cmp     eax, 0B7h
0x1800a5f56  jnz     short loc_1800A5F69
0x1800a5f58  mov     rcx, rbx; lpFileName
0x1800a5f5b  call    cs:__imp_GetFileAttributesW
0x1800a5f61  mov     edi, eax
0x1800a5f63  jmp     short loc_1800A5FE0
0x1800a5f65  mov     [rdi], r12w
0x1800a5f69  call    cs:__imp_GetLastError
0x1800a5f6f  lea     r8, aCreatedirector; "CreateDirectory failed, errCode (0x%8x)"
0x1800a5f76  mov     r9d, eax
0x1800a5f79  xor     edx, edx; struct _GUID *
0x1800a5f7b  mov     rcx, r15; char *
0x1800a5f7e  mov     ebx, eax
0x1800a5f80  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a5f85  mov     rcx, r15; char *
0x1800a5f88  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a5f8d  mov     eax, ebx
0x1800a5f8f  jmp     short loc_1800A6000
0x1800a5f91  mov     [rdi], r12w
0x1800a5f95  call    cs:__imp_GetLastError
0x1800a5f9b  lea     r8, aSetfileattribu; "SetFileAttributes failed, errCode (0x%8"...
0x1800a5fa2  jmp     short loc_1800A5F76
0x1800a5fa4  mov     [rdi], r12w
0x1800a5fa8  call    cs:__imp_GetLastError
0x1800a5fae  lea     r8, aGetfileattribu; "GetFileAttributes failed, errCode (0x%8"...
0x1800a5fb5  jmp     short loc_1800A5F76
0x1800a5fb7  mov     rcx, rbx; lpFileName
0x1800a5fba  call    cs:__imp_GetFileAttributesW
0x1800a5fc0  mov     edi, eax
0x1800a5fc2  cmp     eax, 0FFFFFFFFh
0x1800a5fc5  jz      short loc_1800A5FA8
0x1800a5fc7  or      edi, 2
0x1800a5fca  mov     rcx, rbx; lpFileName
0x1800a5fcd  mov     edx, edi; dwFileAttributes
0x1800a5fcf  call    cs:__imp_SetFileAttributesW
0x1800a5fd5  test    eax, eax
0x1800a5fd7  jz      short loc_1800A5F95
0x1800a5fd9  lea     rbp, aPathSCreatedAn; "Path %s created and set with attributes"...
0x1800a5fe0  mov     r9, rbx
0x1800a5fe3  mov     dword ptr [rsp+68h+var_48], edi
0x1800a5fe7  mov     r8, rbp; unsigned __int16 *
0x1800a5fea  xor     edx, edx; struct _GUID *
0x1800a5fec  mov     rcx, r15; char *
0x1800a5fef  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a5ff4  xor     edx, edx; unsigned int
0x1800a5ff6  mov     rcx, r15; char *
0x1800a5ff9  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800a5ffe  xor     eax, eax
0x1800a6000  add     rsp, 30h
0x1800a6004  pop     r15
0x1800a6006  pop     r14
0x1800a6008  pop     r12
0x1800a600a  pop     rdi
0x1800a600b  pop     rsi
0x1800a600c  pop     rbp
0x1800a600d  pop     rbx
0x1800a600e  retn
```
