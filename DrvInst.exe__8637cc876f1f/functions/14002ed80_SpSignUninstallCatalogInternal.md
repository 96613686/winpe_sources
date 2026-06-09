# SpSignUninstallCatalogInternal

- ea: `0x14002ed80`
- end: `0x14002ee82`
- name: `SpSignUninstallCatalogInternal`
- size: `258`
- prototype: `__int64 __fastcall(LPCWSTR pwszCatalogFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x140014d40`

## callees

- `0x140013d70`
- `0x14002ed80`
- `0x14002ee88`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002edec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ee1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ee49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002edec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ee1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ee49`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002ee3f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14002ee3f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14002ee32`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14002ee32`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14002edcb`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x14002edcb`
- `WINTRUST!CryptCATAdminRemoveCatalog` at `0x14002ede2`
- `WINTRUST!CryptCATAdminRemoveCatalog` at `0x14002ede2`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002ee00`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x14002ee00`

## pseudocode

```c
__int64 __fastcall SpSignUninstallCatalogInternal(LPCWSTR pwszCatalogFile, __int64 a2)
{
  DWORD LastError; // ebx
  DWORD v5; // ebx
  HCATADMIN phCatAdmin; // [rsp+20h] [rbp-238h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !(unsigned int)SpSignSkipValidation() )
  {
    phCatAdmin = 0;
    if ( !CryptCATAdminAcquireContext(&phCatAdmin, &SpSignDriverVerifyGuid, 0)
      || (LastError = 0, !CryptCATAdminRemoveCatalog(phCatAdmin, pwszCatalogFile, 0)) )
    {
      LastError = GetLastError();
    }
    if ( phCatAdmin )
      CryptCATAdminReleaseContext(phCatAdmin, 0);
    if ( !LastError )
      return 0;
  }
  if ( !(unsigned int)pSpSignBuildCatalogFilename(pwszCatalogFile, a2, FileName) )
    return GetLastError();
  SetFileAttributesW(FileName, 0x80u);
  v5 = 0;
  if ( !DeleteFileW(FileName) )
  {
    v5 = GetLastError();
    if ( v5 - 2 <= 1 )
      return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x14002ed80  mov     [rsp+arg_10], rbx
0x14002ed85  mov     [rsp+arg_18], rsi
0x14002ed8a  push    rdi
0x14002ed8b  sub     rsp, 250h
0x14002ed92  mov     rax, cs:__security_cookie
0x14002ed99  xor     rax, rsp
0x14002ed9c  mov     [rsp+258h+var_18], rax
0x14002eda4  mov     rsi, rdx
0x14002eda7  mov     rdi, rcx
0x14002edaa  call    SpSignSkipValidation
0x14002edaf  test    eax, eax
0x14002edb1  jnz     short loc_14002EE0A
0x14002edb3  xor     r8d, r8d; dwFlags
0x14002edb6  mov     [rsp+258h+phCatAdmin], 0
0x14002edbf  lea     rdx, SpSignDriverVerifyGuid; pgSubsystem
0x14002edc6  lea     rcx, [rsp+258h+phCatAdmin]; phCatAdmin
0x14002edcb  call    cs:__imp_CryptCATAdminAcquireContext
0x14002edd1  test    eax, eax
0x14002edd3  jz      short loc_14002EDEC
0x14002edd5  mov     rcx, [rsp+258h+phCatAdmin]; hCatAdmin
0x14002edda  xor     r8d, r8d; dwFlags
0x14002eddd  mov     rdx, rdi; pwszCatalogFile
0x14002ede0  xor     ebx, ebx
0x14002ede2  call    cs:__imp_CryptCATAdminRemoveCatalog
0x14002ede8  test    eax, eax
0x14002edea  jnz     short loc_14002EDF4
0x14002edec  call    cs:__imp_GetLastError
0x14002edf2  mov     ebx, eax
0x14002edf4  mov     rcx, [rsp+258h+phCatAdmin]; hCatAdmin
0x14002edf9  test    rcx, rcx
0x14002edfc  jz      short loc_14002EE06
0x14002edfe  xor     edx, edx; dwFlags
0x14002ee00  call    cs:__imp_CryptCATAdminReleaseContext
0x14002ee06  test    ebx, ebx
0x14002ee08  jz      short loc_14002EE59
0x14002ee0a  lea     r8, [rsp+258h+FileName]
0x14002ee0f  mov     rdx, rsi
0x14002ee12  mov     rcx, rdi
0x14002ee15  call    pSpSignBuildCatalogFilename
0x14002ee1a  test    eax, eax
0x14002ee1c  jnz     short loc_14002EE28
0x14002ee1e  call    cs:__imp_GetLastError
0x14002ee24  mov     ebx, eax
0x14002ee26  jmp     short loc_14002EE5B
0x14002ee28  mov     edx, 80h; dwFileAttributes
0x14002ee2d  lea     rcx, [rsp+258h+FileName]; lpFileName
0x14002ee32  call    cs:__imp_SetFileAttributesW
0x14002ee38  lea     rcx, [rsp+258h+FileName]; lpFileName
0x14002ee3d  xor     ebx, ebx
0x14002ee3f  call    cs:__imp_DeleteFileW
0x14002ee45  test    eax, eax
0x14002ee47  jnz     short loc_14002EE5B
0x14002ee49  call    cs:__imp_GetLastError
0x14002ee4f  mov     ebx, eax
0x14002ee51  add     eax, 0FFFFFFFEh
0x14002ee54  cmp     eax, 1
0x14002ee57  ja      short loc_14002EE5B
0x14002ee59  xor     ebx, ebx
0x14002ee5b  mov     eax, ebx
0x14002ee5d  mov     rcx, [rsp+258h+var_18]
0x14002ee65  xor     rcx, rsp; StackCookie
0x14002ee68  call    __security_check_cookie
0x14002ee6d  lea     r11, [rsp+258h+var_8]
0x14002ee75  mov     rbx, [r11+20h]
0x14002ee79  mov     rsi, [r11+28h]
0x14002ee7d  mov     rsp, r11
0x14002ee80  pop     rdi
0x14002ee81  retn
```
