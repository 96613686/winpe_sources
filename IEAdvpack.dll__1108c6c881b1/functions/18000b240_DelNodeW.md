# DelNodeW

- ea: `0x18000b240`
- end: `0x18000b4af`
- name: `DelNodeW`
- size: `623`
- prototype: `HRESULT __stdcall(LPCWSTR pszFileOrDirName, DWORD dwFlags)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000b170`
- `0x18000b1d0`
- `0x18000b240`

## callees

- `0x1800022bc`
- `0x1800040bc`
- `0x180005a8c`
- `0x1800082f0`
- `0x18000b240`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000b2ba`
- `KERNEL32!DeleteFileW` at `0x18000b2ba`
- `KERNEL32!GetFileAttributesW` at `0x18000b29f`
- `KERNEL32!GetFileAttributesW` at `0x18000b29f`
- `KERNEL32!lstrcmpW` at `0x18000b3c8`
- `KERNEL32!lstrcmpW` at `0x18000b3de`
- `KERNEL32!lstrcmpW` at `0x18000b3c8`
- `KERNEL32!lstrcmpW` at `0x18000b3de`
- `KERNEL32!SetFileAttributesW` at `0x18000b2b1`
- `KERNEL32!SetFileAttributesW` at `0x18000b2d0`
- `KERNEL32!SetFileAttributesW` at `0x18000b2b1`
- `KERNEL32!SetFileAttributesW` at `0x18000b2d0`
- `KERNEL32!RemoveDirectoryW` at `0x18000b2d9`
- `KERNEL32!RemoveDirectoryW` at `0x18000b2d9`
- `KERNEL32!FindFirstFileW` at `0x18000b391`
- `KERNEL32!FindFirstFileW` at `0x18000b391`
- `KERNEL32!FindNextFileW` at `0x18000b437`
- `KERNEL32!FindNextFileW` at `0x18000b437`
- `KERNEL32!FindClose` at `0x18000b448`
- `KERNEL32!FindClose` at `0x18000b448`
- `SHLWAPI!PathAddBackslashW` at `0x18000b338`
- `SHLWAPI!PathAddBackslashW` at `0x18000b338`

## pseudocode

```c
HRESULT __stdcall DelNodeW(LPCWSTR pszFileOrDirName, DWORD dwFlags)
{
  __int64 v4; // rcx
  DWORD v5; // r14d
  BOOL v6; // eax
  HRESULT v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int16 *v10; // r13
  HANDLE FirstFileW; // r12
  HRESULT v12; // eax
  DWORD v13; // edx
  size_t v15; // [rsp+20h] [rbp-E0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v5 = 0;
  if ( IsFullPath(pszFileOrDirName) && (*(_WORD *)v4 != 92 || *(_WORD *)(v4 + 2) != 92 || (dwFlags & 8) != 0) )
  {
    if ( (GetFileAttributesW((LPCWSTR)v4) & 0x10) != 0 )
    {
      if ( (dwFlags & 1) == 0 )
      {
        v7 = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        if ( (dwFlags & 0x40000000) != 0 || (v7 = DirSafe(pszFileOrDirName), v7 >= 0) )
        {
          StringCchCopyW(FileName, 0x104u, (size_t *)pszFileOrDirName);
          PathAddBackslashW(FileName);
          v9 = -1;
          do
            ++v9;
          while ( FileName[v9] );
          v10 = &FileName[v9];
          v15 = AvailableBufferCch(FileName, v8, v10);
          StringCchCopyW(v10, v15, (size_t *)L"*");
          FirstFileW = FindFirstFileW(FileName, &FindFileData);
          if ( FirstFileW == (HANDLE)-1LL )
            return -2147467259;
          while ( 1 )
          {
            if ( (FindFileData.dwFileAttributes & 0x10) == 0
              || lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") && (dwFlags & 2) == 0 )
            {
              StringCchCopyW(v10, v15, (size_t *)FindFileData.cFileName);
              if ( (dwFlags & 8) != 0 )
              {
                v12 = DelNodeW(FileName, 8u);
                v5 = dwFlags & 8;
              }
              else
              {
                v12 = DelNodeW(FileName, 0);
              }
              v7 = v12;
            }
            else
            {
              v5 = dwFlags & 8;
            }
            if ( v7 < 0 || !FindNextFileW(FirstFileW, &FindFileData) )
              break;
            v5 = 0;
          }
          FindClose(FirstFileW);
          if ( v7 >= 0 && (dwFlags & 4) == 0 )
          {
            v13 = 9;
            if ( !v5 )
              v13 = 1;
            if ( DelNodeW(pszFileOrDirName, v13) < 0 && (dwFlags & 2) == 0 )
              return -2147467259;
          }
        }
        return v7;
      }
      SetFileAttributesW(pszFileOrDirName, 0x80u);
      v6 = RemoveDirectoryW(pszFileOrDirName);
    }
    else
    {
      SetFileAttributesW(pszFileOrDirName, 0x80u);
      v6 = DeleteFileW(pszFileOrDirName);
    }
    return !v6 ? 0x80004005 : 0;
  }
  return -2147467259;
}

```

## disassembly

```asm
0x18000b240  push    rbp
0x18000b242  push    rbx
0x18000b243  push    rsi
0x18000b244  push    rdi
0x18000b245  push    r12
0x18000b247  push    r13
0x18000b249  push    r14
0x18000b24b  push    r15
0x18000b24d  lea     rbp, [rsp-3A8h]
0x18000b255  sub     rsp, 4A8h
0x18000b25c  mov     rax, cs:__security_cookie
0x18000b263  xor     rax, rsp
0x18000b266  mov     [rbp+3E0h+var_50], rax
0x18000b26d  mov     esi, edx
0x18000b26f  mov     [rsp+4E0h+pszFileOrDirName], rcx
0x18000b274  mov     rdi, rcx
0x18000b277  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000b27c  xor     r14d, r14d
0x18000b27f  test    eax, eax
0x18000b281  jz      loc_18000B487
0x18000b287  cmp     word ptr [rcx], 5Ch ; '\'
0x18000b28b  jnz     short loc_18000B29F
0x18000b28d  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000b292  jnz     short loc_18000B29F
0x18000b294  mov     eax, esi
0x18000b296  and     eax, 8
0x18000b299  jz      loc_18000B487
0x18000b29f  call    cs:__imp_GetFileAttributesW
0x18000b2a5  test    al, 10h
0x18000b2a7  jnz     short loc_18000B2C2
0x18000b2a9  mov     edx, 80h; dwFileAttributes
0x18000b2ae  mov     rcx, rdi; lpFileName
0x18000b2b1  call    cs:__imp_SetFileAttributesW
0x18000b2b7  mov     rcx, rdi; lpFileName
0x18000b2ba  call    cs:__imp_DeleteFileW
0x18000b2c0  jmp     short loc_18000B2DF
0x18000b2c2  test    sil, 1
0x18000b2c6  jz      short loc_18000B2F0
0x18000b2c8  mov     edx, 80h; dwFileAttributes
0x18000b2cd  mov     rcx, rdi; lpFileName
0x18000b2d0  call    cs:__imp_SetFileAttributesW
0x18000b2d6  mov     rcx, rdi; lpPathName
0x18000b2d9  call    cs:__imp_RemoveDirectoryW
0x18000b2df  neg     eax
0x18000b2e1  sbb     ebx, ebx
0x18000b2e3  not     ebx
0x18000b2e5  and     ebx, 80004005h
0x18000b2eb  jmp     loc_18000B483
0x18000b2f0  xor     edx, edx; Val
0x18000b2f2  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18000b2f7  mov     r8d, 250h; Size
0x18000b2fd  mov     ebx, r14d
0x18000b300  call    memset_0
0x18000b305  bt      esi, 1Eh
0x18000b309  jb      short loc_18000B31D
0x18000b30b  mov     rcx, rdi; unsigned __int16 *
0x18000b30e  call    ?DirSafe@@YAJPEBG@Z; DirSafe(ushort const *)
0x18000b313  mov     ebx, eax
0x18000b315  test    eax, eax
0x18000b317  js      loc_18000B483
0x18000b31d  mov     r8, rdi; unsigned __int16 *
0x18000b320  lea     rcx, [rbp+3E0h+FileName]; unsigned __int16 *
0x18000b327  mov     edx, 104h; unsigned __int64
0x18000b32c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b331  lea     rcx, [rbp+3E0h+FileName]; pszPath
0x18000b338  call    cs:__imp_PathAddBackslashW
0x18000b33e  lea     rcx, [rbp+3E0h+FileName]
0x18000b345  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b349  inc     rax
0x18000b34c  cmp     [rcx+rax*2], r14w
0x18000b351  jnz     short loc_18000B349
0x18000b353  lea     r13, [rbp+3E0h+FileName]
0x18000b35a  lea     r13, [r13+rax*2+0]
0x18000b35f  mov     r8, r13
0x18000b362  lea     rcx, [rbp+3E0h+FileName]
0x18000b369  call    AvailableBufferCch
0x18000b36e  lea     r8, asc_18001F134; "*"
0x18000b375  mov     [rsp+4E0h+var_4C0], rax
0x18000b37a  mov     rdx, rax; unsigned __int64
0x18000b37d  mov     rcx, r13; unsigned __int16 *
0x18000b380  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b385  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000b38a  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x18000b391  call    cs:__imp_FindFirstFileW
0x18000b397  mov     r12, rax
0x18000b39a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b39e  jz      loc_18000B47E
0x18000b3a4  mov     rdi, [rsp+4E0h+var_4C0]
0x18000b3a9  mov     r15d, esi
0x18000b3ac  and     r15d, 8
0x18000b3b0  jmp     short loc_18000B3B5
0x18000b3b2  xor     r14d, r14d
0x18000b3b5  test    byte ptr [rsp+4E0h+FindFileData.dwFileAttributes], 10h
0x18000b3ba  jz      short loc_18000B3F7
0x18000b3bc  lea     rdx, asc_18001E860; "."
0x18000b3c3  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; lpString1
0x18000b3c8  call    cs:__imp_lstrcmpW
0x18000b3ce  test    eax, eax
0x18000b3d0  jz      short loc_18000B3EE
0x18000b3d2  lea     rdx, asc_18001F138; ".."
0x18000b3d9  lea     rcx, [rsp+4E0h+FindFileData.cFileName]; lpString1
0x18000b3de  call    cs:__imp_lstrcmpW
0x18000b3e4  test    eax, eax
0x18000b3e6  jz      short loc_18000B3EE
0x18000b3e8  test    sil, 2
0x18000b3ec  jz      short loc_18000B3F7
0x18000b3ee  mov     r14d, esi
0x18000b3f1  and     r14d, 8
0x18000b3f5  jmp     short loc_18000B42B
0x18000b3f7  lea     r8, [rsp+4E0h+FindFileData.cFileName]; unsigned __int16 *
0x18000b3fc  mov     rdx, rdi; unsigned __int64
0x18000b3ff  mov     rcx, r13; unsigned __int16 *
0x18000b402  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b407  lea     rcx, [rbp+3E0h+FileName]; pszFileOrDirName
0x18000b40e  test    r15d, r15d
0x18000b411  jz      short loc_18000B422
0x18000b413  mov     edx, 8; dwFlags
0x18000b418  call    DelNodeW
0x18000b41d  mov     r14d, r15d
0x18000b420  jmp     short loc_18000B429
0x18000b422  xor     edx, edx; dwFlags
0x18000b424  call    DelNodeW
0x18000b429  mov     ebx, eax
0x18000b42b  test    ebx, ebx
0x18000b42d  js      short loc_18000B445
0x18000b42f  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000b434  mov     rcx, r12; hFindFile
0x18000b437  call    cs:__imp_FindNextFileW
0x18000b43d  test    eax, eax
0x18000b43f  jnz     loc_18000B3B2
0x18000b445  mov     rcx, r12; hFindFile
0x18000b448  call    cs:__imp_FindClose
0x18000b44e  mov     rdi, [rsp+4E0h+pszFileOrDirName]
0x18000b453  test    ebx, ebx
0x18000b455  js      short loc_18000B483
0x18000b457  test    sil, 4
0x18000b45b  jnz     short loc_18000B483
0x18000b45d  mov     rcx, rdi; pszFileOrDirName
0x18000b460  mov     edx, 9
0x18000b465  test    r14d, r14d
0x18000b468  jnz     short loc_18000B46F
0x18000b46a  mov     edx, 1; dwFlags
0x18000b46f  call    DelNodeW
0x18000b474  test    eax, eax
0x18000b476  jns     short loc_18000B483
0x18000b478  test    sil, 2
0x18000b47c  jnz     short loc_18000B483
0x18000b47e  mov     ebx, 80004005h
0x18000b483  mov     eax, ebx
0x18000b485  jmp     short loc_18000B48C
0x18000b487  mov     eax, 80004005h
0x18000b48c  mov     rcx, [rbp+3E0h+var_50]
0x18000b493  xor     rcx, rsp; StackCookie
0x18000b496  call    __security_check_cookie
0x18000b49b  add     rsp, 4A8h
0x18000b4a2  pop     r15
0x18000b4a4  pop     r14
0x18000b4a6  pop     r13
0x18000b4a8  pop     r12
0x18000b4aa  pop     rdi
0x18000b4ab  pop     rsi
0x18000b4ac  pop     rbx
0x18000b4ad  pop     rbp
0x18000b4ae  retn
```
