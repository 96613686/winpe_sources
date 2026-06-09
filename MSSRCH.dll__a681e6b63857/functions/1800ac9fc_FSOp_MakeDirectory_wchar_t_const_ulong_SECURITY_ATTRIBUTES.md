# FSOp::MakeDirectory(wchar_t const *,ulong &,_SECURITY_ATTRIBUTES *)

- ea: `0x1800ac9fc`
- end: `0x1800acabc`
- name: `?MakeDirectory@FSOp@@YAHPEB_WAEAKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(wchar_t *this, wchar_t *, struct _SECURITY_ATTRIBUTES *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800abe78`

## callees

- `0x18004e5d8`
- `0x1800ac9fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aca73`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aca9b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800aca9b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aca8c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800aca8c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aca17`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800aca17`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800aca69`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800aca69`

## string_xrefs

- `0x1800aca48`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\fsutil.cxx"`
- `0x1800aca35`: `[UtilFileSystem] CreateDirectory %ls failed. 0x%08x`
- `0x1800aca7b`: `[UtilFileSystem] SetFileSecurity %ls failed. 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FSOp::MakeDirectory(
        wchar_t *this,
        wchar_t *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  DWORD LastError; // eax
  const wchar_t *v8; // r8
  __int64 v9; // rdx
  __int64 result; // rax
  DWORD FileAttributesW; // eax
  DWORD v12; // [rsp+20h] [rbp-18h]

  if ( !CreateDirectoryW(this, a3) )
  {
    LastError = GetLastError();
    *(_DWORD *)a2 = LastError;
    if ( LastError != 80 && LastError != 183 )
    {
      v8 = (const wchar_t *)L"[UtilFileSystem] CreateDirectory %ls failed. 0x%08x";
      v9 = 99;
LABEL_5:
      v12 = LastError;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\fsutil.cxx\"",
        (const wchar_t *)v9,
        (unsigned int)v8,
        this,
        v12);
      return 0;
    }
    if ( a3 && !SetFileSecurityW(this, 4u, a3->lpSecurityDescriptor) )
    {
      LastError = GetLastError();
      *(_DWORD *)a2 = LastError;
      v8 = L"[UtilFileSystem] SetFileSecurity %ls failed. 0x%08x";
      v9 = 109;
      goto LABEL_5;
    }
  }
  FileAttributesW = GetFileAttributesW(this);
  SetFileAttributesW(this, FileAttributesW | 0x2000);
  result = 1;
  *(_DWORD *)a2 = 0;
  return result;
}

```

## disassembly

```asm
0x1800ac9fc  mov     [rsp+arg_0], rbx
0x1800aca01  mov     [rsp+arg_8], rsi
0x1800aca06  push    rdi
0x1800aca07  sub     rsp, 30h
0x1800aca0b  mov     rdi, rdx
0x1800aca0e  mov     rsi, r8
0x1800aca11  mov     rdx, r8; lpSecurityAttributes
0x1800aca14  mov     rbx, rcx
0x1800aca17  call    cs:__imp_CreateDirectoryW
0x1800aca1d  test    eax, eax
0x1800aca1f  jnz     short loc_1800ACA89
0x1800aca21  call    cs:__imp_GetLastError
0x1800aca27  mov     [rdi], eax
0x1800aca29  cmp     eax, 50h ; 'P'
0x1800aca2c  jz      short loc_1800ACA58
0x1800aca2e  cmp     eax, 0B7h
0x1800aca33  jz      short loc_1800ACA58
0x1800aca35  lea     r8, aUtilfilesystem_1; "[UtilFileSystem] CreateDirectory %ls fa"...
0x1800aca3c  mov     edx, 63h ; 'c'; wchar_t *
0x1800aca41  mov     r9, rbx; wchar_t *
0x1800aca44  mov     [rsp+38h+var_18], eax
0x1800aca48  lea     rcx, aOnecoreuapBase_174; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800aca4f  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800aca54  xor     eax, eax
0x1800aca56  jmp     short loc_1800ACAAC
0x1800aca58  test    rsi, rsi
0x1800aca5b  jz      short loc_1800ACA89
0x1800aca5d  mov     r8, [rsi+8]; pSecurityDescriptor
0x1800aca61  mov     edx, 4; SecurityInformation
0x1800aca66  mov     rcx, rbx; lpFileName
0x1800aca69  call    cs:__imp_SetFileSecurityW
0x1800aca6f  test    eax, eax
0x1800aca71  jnz     short loc_1800ACA89
0x1800aca73  call    cs:__imp_GetLastError
0x1800aca79  mov     [rdi], eax
0x1800aca7b  lea     r8, aUtilfilesystem_2; "[UtilFileSystem] SetFileSecurity %ls fa"...
0x1800aca82  mov     edx, 6Dh ; 'm'
0x1800aca87  jmp     short loc_1800ACA41
0x1800aca89  mov     rcx, rbx; lpFileName
0x1800aca8c  call    cs:__imp_GetFileAttributesW
0x1800aca92  bts     eax, 0Dh
0x1800aca96  mov     rcx, rbx; lpFileName
0x1800aca99  mov     edx, eax; dwFileAttributes
0x1800aca9b  call    cs:__imp_SetFileAttributesW
0x1800acaa1  mov     eax, 1
0x1800acaa6  mov     dword ptr [rdi], 0
0x1800acaac  mov     rbx, [rsp+38h+arg_0]
0x1800acab1  mov     rsi, [rsp+38h+arg_8]
0x1800acab6  add     rsp, 30h
0x1800acaba  pop     rdi
0x1800acabb  retn
```
