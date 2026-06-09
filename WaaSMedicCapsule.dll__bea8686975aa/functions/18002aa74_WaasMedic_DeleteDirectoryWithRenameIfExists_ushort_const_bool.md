# WaasMedic::DeleteDirectoryWithRenameIfExists(ushort const *,bool)

- ea: `0x18002aa74`
- end: `0x18002acd2`
- name: `?DeleteDirectoryWithRenameIfExists@WaasMedic@@YAJPEBG_N@Z`
- size: `606`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x18003a4f4`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x18000a4ac`
- `0x18000b308`
- `0x18002543c`
- `0x180026920`
- `0x18002a870`
- `0x18002aa74`
- `0x18002c238`
- `0x18002c2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ab9f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002aada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002ab41`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002aada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18002ab41`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002ab95`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002ac6a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002ab95`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002ac6a`

## string_xrefs

- `0x18002ab10`: `Unable to delete %ws`
- `0x18002abc0`: `Failed to rename %s to %s, hr = 0x%08X.`
- `0x18002ab32`: `Directory %s does not exists. Nothing to delete`
- `0x18002ab4e`: `Directory %s does not exists. Nothing to delete`
- `0x18002ac85`: `Failed to rename %ws to %ws`

## pseudocode

```c
__int64 __fastcall WaasMedic::DeleteDirectoryWithRenameIfExists(WaasMedic *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  const unsigned __int16 *v5; // rdx
  bool v6; // r8
  unsigned int v7; // eax
  const unsigned __int16 *v9; // rdx
  bool v10; // r8
  signed int LastError; // eax
  int v12; // ebx
  __int64 v13; // rax
  char *v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  LPWSTR v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  memset_0(pszPath, 0, 0x208u);
  StringCchCatW(pszPath, v3, (const unsigned __int16 *)this);
  StringCchCatW(pszPath, v4, L".bak");
  if ( PathFileExistsW(pszPath) )
  {
    v7 = WaasMedic::DeleteDirectory((WaasMedic *)pszPath, v5, v6);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
      (const char *)v7,
      (int)"Unable to delete %ws",
      (const char *)pszPath);
  }
  else
  {
    LogLevelW(4u, L"Directory %s does not exists. Nothing to delete", pszPath);
  }
  if ( !PathFileExistsW((LPCWSTR)this) )
  {
    LogLevelW(4u, L"Directory %s does not exists. Nothing to delete", this);
    return 0;
  }
  if ( MoveFileExW((LPCWSTR)this, pszPath, 8u) )
    goto LABEL_23;
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  LODWORD(v14) = v12;
  LogLevelW(2u, L"Failed to rename %s to %s, hr = 0x%08X.", this, pszPath, v14);
  if ( !v12 )
    goto LABEL_23;
  if ( v12 != -2147024891 )
  {
    if ( v12 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
        (const char *)(unsigned int)v12,
        v15);
    return (unsigned int)v12;
  }
  v16[0] = (LPWSTR)this;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)this + v13) );
  v16[1] = (LPWSTR)v13;
  v12 = WaasMedic::TakeOwnership(v16);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
      (const char *)(unsigned int)v12,
      (int)"Unable to take ownership of: %ws",
      (const char *)this,
      v16[0]);
    return (unsigned int)v12;
  }
  if ( MoveFileExW((LPCWSTR)this, pszPath, 8u) )
  {
LABEL_23:
    v12 = WaasMedic::DeleteDirectory((WaasMedic *)pszPath, v9, v10);
    if ( v12 >= 0 )
      return 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
      (const char *)(unsigned int)v12,
      (int)"Folder name: %ws",
      (const char *)pszPath,
      v16[0]);
    return (unsigned int)v12;
  }
  return wil::details::in1diag3::Return_GetLastErrorMsg(
           retaddr,
           (void *)0x101,
           (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
           "Failed to rename %ws to %ws",
           (const char *)this,
           pszPath,
           v16[0]);
}

```

## disassembly

```asm
0x18002aa74  mov     [rsp-8+arg_8], rbx
0x18002aa79  mov     [rsp-8+arg_10], rsi
0x18002aa7e  push    rbp
0x18002aa7f  push    rdi
0x18002aa80  push    r14
0x18002aa82  lea     rbp, [rsp-160h]
0x18002aa8a  sub     rsp, 260h
0x18002aa91  mov     rax, cs:__security_cookie
0x18002aa98  xor     rax, rsp
0x18002aa9b  mov     [rbp+170h+var_20], rax
0x18002aaa2  mov     rdi, rcx
0x18002aaa5  xor     edx, edx; Val
0x18002aaa7  lea     rcx, [rsp+270h+pszPath]; void *
0x18002aaac  mov     r8d, 208h; Size
0x18002aab2  call    memset_0
0x18002aab7  mov     r8, rdi; unsigned __int16 *
0x18002aaba  lea     rcx, [rsp+270h+pszPath]; unsigned __int16 *
0x18002aabf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002aac4  lea     r8, aBak; ".bak"
0x18002aacb  lea     rcx, [rsp+270h+pszPath]; unsigned __int16 *
0x18002aad0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002aad5  lea     rcx, [rsp+270h+pszPath]; pszPath
0x18002aada  call    cs:__imp_PathFileExistsW
0x18002aae0  xor     esi, esi
0x18002aae2  lea     r14, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002aae9  mov     ebx, 4
0x18002aaee  test    eax, eax
0x18002aaf0  jz      short loc_18002AB2B
0x18002aaf2  lea     rcx, [rsp+270h+pszPath]; this
0x18002aaf7  call    ?DeleteDirectory@WaasMedic@@YAJPEBG_N@Z; WaasMedic::DeleteDirectory(ushort const *,bool)
0x18002aafc  mov     rcx, [rbp+178h]; this
0x18002ab03  lea     rdx, [rsp+270h+pszPath]
0x18002ab08  mov     [rsp+270h+var_248], rdx; char *
0x18002ab0d  mov     r9d, eax; char *
0x18002ab10  lea     rdx, aUnableToDelete; "Unable to delete %ws"
0x18002ab17  mov     r8, r14; unsigned int
0x18002ab1a  mov     [rsp+270h+var_250], rdx; int
0x18002ab1f  mov     edx, 0E5h; void *
0x18002ab24  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ab29  jmp     short loc_18002AB3E
0x18002ab2b  lea     r8, [rsp+270h+pszPath]
0x18002ab30  mov     ecx, ebx; unsigned __int8
0x18002ab32  lea     rdx, aDirectorySDoes; "Directory %s does not exists. Nothing t"...
0x18002ab39  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ab3e  mov     rcx, rdi; pszPath
0x18002ab41  call    cs:__imp_PathFileExistsW
0x18002ab47  test    eax, eax
0x18002ab49  jnz     short loc_18002AB85
0x18002ab4b  mov     r8, rdi
0x18002ab4e  lea     rdx, aDirectorySDoes; "Directory %s does not exists. Nothing t"...
0x18002ab55  mov     ecx, ebx; unsigned __int8
0x18002ab57  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002ab5c  xor     eax, eax
0x18002ab5e  mov     rcx, [rbp+170h+var_20]
0x18002ab65  xor     rcx, rsp; StackCookie
0x18002ab68  call    __security_check_cookie
0x18002ab6d  lea     r11, [rsp+270h+var_10]
0x18002ab75  mov     rbx, [r11+28h]
0x18002ab79  mov     rsi, [r11+30h]
0x18002ab7d  mov     rsp, r11
0x18002ab80  pop     r14
0x18002ab82  pop     rdi
0x18002ab83  pop     rbp
0x18002ab84  retn
0x18002ab85  mov     r8d, 8; dwFlags
0x18002ab8b  lea     rdx, [rsp+270h+pszPath]; lpNewFileName
0x18002ab90  mov     rcx, rdi; lpExistingFileName
0x18002ab93  mov     ebx, esi
0x18002ab95  call    cs:__imp_MoveFileExW
0x18002ab9b  test    eax, eax
0x18002ab9d  jnz     short loc_18002ABFF
0x18002ab9f  call    cs:__imp_GetLastError
0x18002aba5  mov     ebx, eax
0x18002aba7  test    eax, eax
0x18002aba9  jle     short loc_18002ABB4
0x18002abab  movzx   ebx, ax
0x18002abae  or      ebx, 80070000h
0x18002abb4  lea     r9, [rsp+270h+pszPath]
0x18002abb9  mov     dword ptr [rsp+270h+var_250], ebx; int
0x18002abbd  mov     r8, rdi
0x18002abc0  lea     rdx, aFailedToRename; "Failed to rename %s to %s, hr = 0x%08X."
0x18002abc7  mov     ecx, 2; unsigned __int8
0x18002abcc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002abd1  test    ebx, ebx
0x18002abd3  jz      short loc_18002ABFF
0x18002abd5  cmp     ebx, 80070005h
0x18002abdb  jz      short loc_18002AC0B
0x18002abdd  test    ebx, ebx
0x18002abdf  jns     short loc_18002ABF8
0x18002abe1  mov     rcx, [rbp+178h]; this
0x18002abe8  mov     r9d, ebx; char *
0x18002abeb  mov     r8, r14; unsigned int
0x18002abee  mov     edx, 0F9h; void *
0x18002abf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002abf8  mov     eax, ebx
0x18002abfa  jmp     loc_18002AB5E
0x18002abff  cmp     ebx, 80070005h
0x18002ac05  jnz     loc_18002ACA3
0x18002ac0b  mov     [rsp+270h+var_240], rdi
0x18002ac10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ac14  inc     rax
0x18002ac17  cmp     [rdi+rax*2], si
0x18002ac1b  jnz     short loc_18002AC14
0x18002ac1d  lea     rcx, [rsp+270h+var_240]
0x18002ac22  mov     [rsp+270h+var_238], rax
0x18002ac27  call    ?TakeOwnership@WaasMedic@@YAJAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::TakeOwnership(std::basic_string_view<ushort> const &)
0x18002ac2c  mov     ebx, eax
0x18002ac2e  test    eax, eax
0x18002ac30  jns     short loc_18002AC5C
0x18002ac32  mov     [rsp+270h+var_248], rdi; char *
0x18002ac37  lea     rax, aUnableToTakeOw; "Unable to take ownership of: %ws"
0x18002ac3e  mov     edx, 0FDh; void *
0x18002ac43  mov     rcx, [rbp+178h]; this
0x18002ac4a  mov     r8, r14; unsigned int
0x18002ac4d  mov     r9d, ebx; char *
0x18002ac50  mov     [rsp+270h+var_250], rax; int
0x18002ac55  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002ac5a  jmp     short loc_18002ABF8
0x18002ac5c  mov     r8d, 8; dwFlags
0x18002ac62  lea     rdx, [rsp+270h+pszPath]; lpNewFileName
0x18002ac67  mov     rcx, rdi; lpExistingFileName
0x18002ac6a  call    cs:__imp_MoveFileExW
0x18002ac70  test    eax, eax
0x18002ac72  jnz     short loc_18002ACA3
0x18002ac74  mov     rcx, [rbp+178h]; this
0x18002ac7b  lea     rax, [rsp+270h+pszPath]
0x18002ac80  mov     [rsp+270h+var_248], rax
0x18002ac85  lea     r9, aFailedToRename_0; "Failed to rename %ws to %ws"
0x18002ac8c  mov     r8, r14; unsigned int
0x18002ac8f  mov     [rsp+270h+var_250], rdi; char *
0x18002ac94  mov     edx, 101h; void *
0x18002ac99  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002ac9e  jmp     loc_18002AB5E
0x18002aca3  lea     rcx, [rsp+270h+pszPath]; this
0x18002aca8  call    ?DeleteDirectory@WaasMedic@@YAJPEBG_N@Z; WaasMedic::DeleteDirectory(ushort const *,bool)
0x18002acad  mov     ebx, eax
0x18002acaf  test    eax, eax
0x18002acb1  jns     loc_18002AB5C
0x18002acb7  lea     rax, [rsp+270h+pszPath]
0x18002acbc  mov     edx, 104h
0x18002acc1  mov     [rsp+270h+var_248], rax
0x18002acc6  lea     rax, aFolderNameWs; "Folder name: %ws"
0x18002accd  jmp     loc_18002AC43
```
