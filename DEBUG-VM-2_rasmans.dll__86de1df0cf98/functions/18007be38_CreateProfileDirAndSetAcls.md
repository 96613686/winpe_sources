# CreateProfileDirAndSetAcls

- ea: `0x18007be38`
- end: `0x18007bf88`
- name: `CreateProfileDirAndSetAcls`
- size: `336`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800074c8`
- `0x18006d96c`

## callees

- `0x18005b9cc`
- `0x18005d454`
- `0x18007a880`
- `0x18007be38`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bf45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007bf45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007bf60`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007bea6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18007bea6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007bee2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007bf56`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007bee2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007bf56`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007bf32`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18007bf32`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007bf20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007bf20`

## pseudocode

```c
__int64 __fastcall CreateProfileDirAndSetAcls(char *hToken, __int64 a2, int a3, __int64 a4, int a5)
{
  unsigned int DirectoriesOnPath; // ebx
  int v9; // edi
  HANDLE FileW; // rax
  void *v11; // rsi
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x20Au);
  DirectoriesOnPath = StringCchCopyWrapW(FileName, 261, a2);
  if ( DirectoriesOnPath )
    return DirectoriesOnPath;
  v9 = 0;
  if ( a3 != 4 && (unsigned __int64)(hToken - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( !ImpersonateLoggedOnUser(hToken) )
      return GetLastError();
    v9 = 1;
  }
  DirectoriesOnPath = CreateDirectoriesOnPath(FileName);
  if ( !DirectoriesOnPath )
  {
    if ( !a3 )
      UpdateAclsOnPhonebookFolder(FileName);
    if ( v9 )
    {
      v9 = 0;
      if ( !RevertToSelf() )
        return GetLastError();
    }
    if ( !a5 )
      return DirectoriesOnPath;
    FileW = CreateFileW(FileName, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      DirectoriesOnPath = 621;
    }
    else
    {
      if ( GetFileType(FileW) != 1 )
        DirectoriesOnPath = 621;
      CloseHandle(v11);
    }
  }
  if ( v9 && !RevertToSelf() )
    return GetLastError();
  return DirectoriesOnPath;
}

```

## disassembly

```asm
0x18007be38  push    rbx
0x18007be3a  push    rbp
0x18007be3b  push    rsi
0x18007be3c  push    rdi
0x18007be3d  push    r14
0x18007be3f  sub     rsp, 270h
0x18007be46  mov     rax, cs:__security_cookie
0x18007be4d  xor     rax, rsp
0x18007be50  mov     [rsp+298h+var_38], rax
0x18007be58  mov     esi, r8d
0x18007be5b  mov     rbx, rdx
0x18007be5e  mov     rbp, rcx
0x18007be61  xor     edx, edx; Val
0x18007be63  mov     r8d, 20Ah; Size
0x18007be69  lea     rcx, [rsp+298h+FileName]; void *
0x18007be6e  mov     r14d, r9d
0x18007be71  call    memset_0
0x18007be76  mov     r8, rbx
0x18007be79  lea     rcx, [rsp+298h+FileName]
0x18007be7e  mov     edx, 105h
0x18007be83  call    StringCchCopyWrapW
0x18007be88  mov     ebx, eax
0x18007be8a  test    eax, eax
0x18007be8c  jnz     loc_18007BF68
0x18007be92  xor     edi, edi
0x18007be94  cmp     esi, 4
0x18007be97  jz      short loc_18007BEB7
0x18007be99  lea     rax, [rbp-1]
0x18007be9d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007bea1  ja      short loc_18007BEB7
0x18007bea3  mov     rcx, rbp; hToken
0x18007bea6  call    cs:__imp_ImpersonateLoggedOnUser
0x18007beac  test    eax, eax
0x18007beae  jz      loc_18007BF60
0x18007beb4  lea     edi, [rbx+1]
0x18007beb7  lea     rcx, [rsp+298h+FileName]; lpPathName
0x18007bebc  call    CreateDirectoriesOnPath
0x18007bec1  mov     ebx, eax
0x18007bec3  test    eax, eax
0x18007bec5  jnz     loc_18007BF52
0x18007becb  test    esi, esi
0x18007becd  jnz     short loc_18007BEDC
0x18007becf  mov     r8d, r14d
0x18007bed2  lea     rcx, [rsp+298h+FileName]; pszSrc
0x18007bed7  call    UpdateAclsOnPhonebookFolder
0x18007bedc  test    edi, edi
0x18007bede  jz      short loc_18007BEEC
0x18007bee0  xor     edi, edi
0x18007bee2  call    cs:__imp_RevertToSelf
0x18007bee8  test    eax, eax
0x18007beea  jz      short loc_18007BF60
0x18007beec  cmp     [rsp+298h+arg_20], 0
0x18007bef4  jz      short loc_18007BF68
0x18007bef6  xor     r9d, r9d; lpSecurityAttributes
0x18007bef9  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18007bf02  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18007bf0a  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18007bf0f  mov     edx, 0C0000000h; dwDesiredAccess
0x18007bf14  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x18007bf1c  lea     r8d, [r9+1]; dwShareMode
0x18007bf20  call    cs:__imp_CreateFileW
0x18007bf26  mov     rsi, rax
0x18007bf29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007bf2d  jz      short loc_18007BF4D
0x18007bf2f  mov     rcx, rax; hFile
0x18007bf32  call    cs:__imp_GetFileType
0x18007bf38  cmp     eax, 1
0x18007bf3b  jz      short loc_18007BF42
0x18007bf3d  mov     ebx, 26Dh
0x18007bf42  mov     rcx, rsi; hObject
0x18007bf45  call    cs:__imp_CloseHandle
0x18007bf4b  jmp     short loc_18007BF52
0x18007bf4d  mov     ebx, 26Dh
0x18007bf52  test    edi, edi
0x18007bf54  jz      short loc_18007BF68
0x18007bf56  call    cs:__imp_RevertToSelf
0x18007bf5c  test    eax, eax
0x18007bf5e  jnz     short loc_18007BF68
0x18007bf60  call    cs:__imp_GetLastError
0x18007bf66  mov     ebx, eax
0x18007bf68  mov     eax, ebx
0x18007bf6a  mov     rcx, [rsp+298h+var_38]
0x18007bf72  xor     rcx, rsp; StackCookie
0x18007bf75  call    __security_check_cookie
0x18007bf7a  add     rsp, 270h
0x18007bf81  pop     r14
0x18007bf83  pop     rdi
0x18007bf84  pop     rsi
0x18007bf85  pop     rbp
0x18007bf86  pop     rbx
0x18007bf87  retn
```
