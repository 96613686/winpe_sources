# SpSignInstallCatalogInternal

- ea: `0x14002e91c`
- end: `0x14002ea08`
- name: `SpSignInstallCatalogInternal`
- size: `236`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x1400143b8`

## callees

- `0x14000c8bc`
- `0x140013d70`
- `0x14002e91c`
- `0x14002ee88`
- `0x14002ef38`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e9db`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14002e997`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14002e997`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14002e9ac`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14002e9ac`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x14002e9d1`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x14002e9d1`

## pseudocode

```c
__int64 __fastcall SpSignInstallCatalogInternal(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  DWORD SurePathExists; // ebx
  WCHAR FileName[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( a3 )
  {
    if ( (unsigned int)SpSignSkipValidation() || (SurePathExists = pSpSignInstallCatalog(a1, a3)) != 0 )
    {
      if ( !(unsigned int)pSpSignBuildCatalogFilename(a3, a2, FileName) )
        return GetLastError();
      SurePathExists = pSetupMakeSurePathExists(FileName);
      if ( !SurePathExists )
      {
        if ( GetFileAttributesW(FileName) != -1 )
          SetFileAttributesW(FileName, 0x80u);
        if ( !CopyFileExW(a1, FileName, 0, 0, 0, 0) )
          return GetLastError();
      }
    }
  }
  else
  {
    return 87;
  }
  return SurePathExists;
}

```

## disassembly

```asm
0x14002e91c  mov     [rsp+arg_18], rbx
0x14002e921  push    rbp
0x14002e922  push    rsi
0x14002e923  push    rdi
0x14002e924  sub     rsp, 250h
0x14002e92b  mov     rax, cs:__security_cookie
0x14002e932  xor     rax, rsp
0x14002e935  mov     [rsp+268h+var_28], rax
0x14002e93d  mov     rdi, r8
0x14002e940  mov     rbp, rdx
0x14002e943  mov     rsi, rcx
0x14002e946  test    r8, r8
0x14002e949  jnz     short loc_14002E954
0x14002e94b  lea     ebx, [r8+57h]
0x14002e94f  jmp     loc_14002E9E3
0x14002e954  call    SpSignSkipValidation
0x14002e959  test    eax, eax
0x14002e95b  jnz     short loc_14002E96E
0x14002e95d  mov     rdx, rdi; unsigned __int16 *
0x14002e960  mov     rcx, rsi; unsigned __int16 *
0x14002e963  call    pSpSignInstallCatalog
0x14002e968  mov     ebx, eax
0x14002e96a  test    eax, eax
0x14002e96c  jz      short loc_14002E9E3
0x14002e96e  lea     r8, [rsp+268h+FileName]
0x14002e973  mov     rdx, rbp
0x14002e976  mov     rcx, rdi
0x14002e979  call    pSpSignBuildCatalogFilename
0x14002e97e  test    eax, eax
0x14002e980  jz      short loc_14002E9DB
0x14002e982  lea     rcx, [rsp+268h+FileName]
0x14002e987  call    pSetupMakeSurePathExists
0x14002e98c  mov     ebx, eax
0x14002e98e  test    eax, eax
0x14002e990  jnz     short loc_14002E9E3
0x14002e992  lea     rcx, [rsp+268h+FileName]; lpFileName
0x14002e997  call    cs:__imp_GetFileAttributesW
0x14002e99d  cmp     eax, 0FFFFFFFFh
0x14002e9a0  jz      short loc_14002E9B2
0x14002e9a2  mov     edx, 80h; dwFileAttributes
0x14002e9a7  lea     rcx, [rsp+268h+FileName]; lpFileName
0x14002e9ac  call    cs:__imp_SetFileAttributesW
0x14002e9b2  mov     [rsp+268h+dwCopyFlags], 0; dwCopyFlags
0x14002e9ba  lea     rdx, [rsp+268h+FileName]; lpNewFileName
0x14002e9bf  xor     r9d, r9d; lpData
0x14002e9c2  mov     [rsp+268h+pbCancel], 0; pbCancel
0x14002e9cb  xor     r8d, r8d; lpProgressRoutine
0x14002e9ce  mov     rcx, rsi; lpExistingFileName
0x14002e9d1  call    cs:__imp_CopyFileExW
0x14002e9d7  test    eax, eax
0x14002e9d9  jnz     short loc_14002E9E3
0x14002e9db  call    cs:__imp_GetLastError
0x14002e9e1  mov     ebx, eax
0x14002e9e3  mov     eax, ebx
0x14002e9e5  mov     rcx, [rsp+268h+var_28]
0x14002e9ed  xor     rcx, rsp; StackCookie
0x14002e9f0  call    __security_check_cookie
0x14002e9f5  mov     rbx, [rsp+268h+arg_18]
0x14002e9fd  add     rsp, 250h
0x14002ea04  pop     rdi
0x14002ea05  pop     rsi
0x14002ea06  pop     rbp
0x14002ea07  retn
```
