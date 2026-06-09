# Wallet::ServerUtils::HideAndRestrictFolder(ushort const *)

- ea: `0x18001d50c`
- end: `0x18001d597`
- name: `?HideAndRestrictFolder@ServerUtils@Wallet@@YAJPEBG@Z`
- size: `139`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800110f0`

## callees

- `0x18001d50c`
- `0x18001d5cc`
- `0x18001d83c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d53f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001d535`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001d535`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d523`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001d523`

## pseudocode

```c
__int64 __fastcall Wallet::ServerUtils::HideAndRestrictFolder(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  bool v6; // sf
  int v7; // eax
  bool v9; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  if ( !g_fUnitTestContext )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( (FileAttributesW & 2) == 0 && !SetFileAttributesW(lpFileName, FileAttributesW | 2) )
    {
      LastError = GetLastError();
      v6 = LastError < 0;
      if ( !LastError )
        return (unsigned int)-2143748092;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = LastError < 0;
      }
      if ( v6 )
        return (unsigned int)LastError;
    }
    v9 = 0;
    LastError = IsFolderRestricted(lpFileName, &v9);
    if ( LastError >= 0 )
    {
      if ( !v9 )
      {
        v7 = RestrictFolder(lpFileName);
        if ( v7 < 0 )
          return (unsigned int)v7;
      }
    }
    else
    {
      return (unsigned int)LastError;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001d50c  mov     [rsp+arg_0], rbx
0x18001d511  push    rdi
0x18001d512  sub     rsp, 20h
0x18001d516  xor     ebx, ebx
0x18001d518  mov     rdi, rcx
0x18001d51b  cmp     cs:?g_fUnitTestContext@@3HA, ebx; int g_fUnitTestContext
0x18001d521  jnz     short loc_18001D58A
0x18001d523  call    cs:__imp_GetFileAttributesW
0x18001d529  test    al, 2
0x18001d52b  jnz     short loc_18001D557
0x18001d52d  or      eax, 2
0x18001d530  mov     rcx, rdi; lpFileName
0x18001d533  mov     edx, eax; dwFileAttributes
0x18001d535  call    cs:__imp_SetFileAttributesW
0x18001d53b  test    eax, eax
0x18001d53d  jnz     short loc_18001D557
0x18001d53f  call    cs:__imp_GetLastError
0x18001d545  test    eax, eax
0x18001d547  jz      short loc_18001D570
0x18001d549  jle     short loc_18001D555
0x18001d54b  movzx   eax, ax
0x18001d54e  or      eax, 80070000h
0x18001d553  test    eax, eax
0x18001d555  js      short loc_18001D56C
0x18001d557  lea     rdx, [rsp+28h+arg_8]; bool *
0x18001d55c  mov     [rsp+28h+arg_8], bl
0x18001d560  mov     rcx, rdi; lpFileName
0x18001d563  call    ?IsFolderRestricted@@YAJPEBGAEA_N@Z; IsFolderRestricted(ushort const *,bool &)
0x18001d568  test    eax, eax
0x18001d56a  jns     short loc_18001D577
0x18001d56c  mov     ebx, eax
0x18001d56e  jmp     short loc_18001D58A
0x18001d570  mov     ebx, 80390004h
0x18001d575  jmp     short loc_18001D58A
0x18001d577  cmp     [rsp+28h+arg_8], bl
0x18001d57b  jnz     short loc_18001D58A
0x18001d57d  mov     rcx, rdi; lpFileName
0x18001d580  call    ?RestrictFolder@@YAJPEBG@Z; RestrictFolder(ushort const *)
0x18001d585  test    eax, eax
0x18001d587  cmovs   ebx, eax
0x18001d58a  mov     eax, ebx
0x18001d58c  mov     rbx, [rsp+28h+arg_0]
0x18001d591  add     rsp, 20h
0x18001d595  pop     rdi
0x18001d596  retn
```
