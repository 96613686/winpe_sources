# DmCopyDirectoryRecursive(ushort const *,ushort const *)

- ea: `0x18005d830`
- end: `0x18005daa5`
- name: `?DmCopyDirectoryRecursive@@YAJPEBG0@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18005d830`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180058420`
- `0x18005d830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005da24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d97a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005da6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d97a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005da6f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005da47`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005da47`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d9ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005d9ba`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005da5e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005da5e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d8c3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d8c3`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18005d996`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18005d996`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18005d95f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18005d95f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18005da14`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18005da14`

## pseudocode

```c
__int64 __fastcall DmCopyDirectoryRecursive(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  HANDLE FirstFileW; // rsi
  signed int v6; // eax
  int v7; // edx
  int v8; // edx
  signed int LastError; // eax
  signed int v10; // eax
  HLOCAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(FileName, 0, 0x208u);
  hMem = 0;
  v4 = StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", a1);
  if ( v4 >= 0 )
  {
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        v7 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v7 = FindFileData.cFileName[1];
        if ( v7 )
        {
          v8 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v8 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v8 = FindFileData.cFileName[2];
          }
          if ( v8 )
          {
            v4 = PathCchCombine(FileName, 0x104u, a1, FindFileData.cFileName);
            if ( v4 >= 0 )
            {
              LocalFree(hMem);
              v4 = PathAllocCombine(a2, FindFileData.cFileName, 0, (PWSTR *)&hMem);
              if ( v4 >= 0 )
              {
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  if ( !CreateDirectoryW((LPCWSTR)hMem, 0) )
                  {
                    LastError = GetLastError();
                    v4 = LastError;
                    if ( LastError > 0 )
                      v4 = (unsigned __int16)LastError | 0x80070000;
                    if ( v4 != -2147024713 )
                    {
LABEL_27:
                      FindClose(FirstFileW);
                      goto LABEL_28;
                    }
                  }
                  v4 = DmCopyDirectoryRecursive(FileName, (const unsigned __int16 *)hMem);
                }
                else if ( !CopyFileW(FileName, (LPCWSTR)hMem, 1) )
                {
                  v10 = GetLastError();
                  v4 = v10;
                  if ( v10 > 0 )
                    v4 = (unsigned __int16)v10 | 0x80070000;
                }
              }
            }
          }
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          goto LABEL_27;
      }
    }
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v4 = 0;
    if ( v6 != -2147024894 )
      v4 = v6;
  }
LABEL_28:
  LocalFree(hMem);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005d830  mov     [rsp-8+arg_10], rbx
0x18005d835  push    rbp
0x18005d836  push    rsi
0x18005d837  push    r12
0x18005d839  push    r14
0x18005d83b  push    r15
0x18005d83d  lea     rbp, [rsp-3A0h]
0x18005d845  sub     rsp, 4A0h
0x18005d84c  mov     rax, cs:__security_cookie
0x18005d853  xor     rax, rsp
0x18005d856  mov     [rbp+3C0h+var_30], rax
0x18005d85d  mov     r15, rdx
0x18005d860  mov     r14, rcx
0x18005d863  xor     edx, edx; Val
0x18005d865  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x18005d86a  mov     r8d, 250h; Size
0x18005d870  call    memset_0
0x18005d875  xor     edx, edx; Val
0x18005d877  lea     rcx, [rbp+3C0h+FileName]; void *
0x18005d87e  mov     r8d, 208h; Size
0x18005d884  call    memset_0
0x18005d889  mov     r9, r14
0x18005d88c  mov     [rsp+4C0h+hMem], 0
0x18005d895  lea     r8, aS; "%s\\*.*"
0x18005d89c  mov     edx, 104h; unsigned __int64
0x18005d8a1  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x18005d8a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d8ad  mov     ebx, eax
0x18005d8af  test    eax, eax
0x18005d8b1  js      loc_18005DA6A
0x18005d8b7  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18005d8bc  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x18005d8c3  call    cs:__imp_FindFirstFileW
0x18005d8ca  nop     dword ptr [rax+rax+00h]
0x18005d8cf  mov     rsi, rax
0x18005d8d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d8d6  jnz     short loc_18005D8FF
0x18005d8d8  call    cs:__imp_GetLastError
0x18005d8df  nop     dword ptr [rax+rax+00h]
0x18005d8e4  test    eax, eax
0x18005d8e6  jle     short loc_18005D8F0
0x18005d8e8  movzx   eax, ax
0x18005d8eb  or      eax, 80070000h
0x18005d8f0  xor     ebx, ebx
0x18005d8f2  cmp     eax, 80070002h
0x18005d8f7  cmovnz  ebx, eax
0x18005d8fa  jmp     loc_18005DA6A
0x18005d8ff  mov     r12d, 2Eh ; '.'
0x18005d905  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x18005d90a  sub     edx, r12d
0x18005d90d  jnz     short loc_18005D91B
0x18005d90f  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x18005d914  xor     eax, eax
0x18005d916  movzx   ecx, ax
0x18005d919  sub     edx, ecx
0x18005d91b  test    edx, edx
0x18005d91d  jz      loc_18005DA3F
0x18005d923  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x18005d928  sub     edx, r12d
0x18005d92b  jnz     short loc_18005D943
0x18005d92d  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x18005d932  sub     edx, r12d
0x18005d935  jnz     short loc_18005D943
0x18005d937  movzx   edx, [rsp+4C0h+FindFileData.cFileName+4]
0x18005d93c  xor     eax, eax
0x18005d93e  movzx   ecx, ax
0x18005d941  sub     edx, ecx
0x18005d943  test    edx, edx
0x18005d945  jz      loc_18005DA3F
0x18005d94b  lea     r9, [rsp+4C0h+FindFileData.cFileName]; pszMore
0x18005d950  mov     r8, r14; pszPathIn
0x18005d953  mov     edx, 104h; cchPathOut
0x18005d958  lea     rcx, [rbp+3C0h+FileName]; pszPathOut
0x18005d95f  call    cs:__imp_PathCchCombine
0x18005d966  nop     dword ptr [rax+rax+00h]
0x18005d96b  mov     ebx, eax
0x18005d96d  test    eax, eax
0x18005d96f  js      loc_18005DA3F
0x18005d975  mov     rcx, [rsp+4C0h+hMem]; hMem
0x18005d97a  call    cs:__imp_LocalFree
0x18005d981  nop     dword ptr [rax+rax+00h]
0x18005d986  lea     r9, [rsp+4C0h+hMem]; ppszPathOut
0x18005d98b  xor     r8d, r8d; dwFlags
0x18005d98e  lea     rdx, [rsp+4C0h+FindFileData.cFileName]; pszMore
0x18005d993  mov     rcx, r15; pszPathIn
0x18005d996  call    cs:__imp_PathAllocCombine
0x18005d99d  nop     dword ptr [rax+rax+00h]
0x18005d9a2  mov     ebx, eax
0x18005d9a4  test    eax, eax
0x18005d9a6  js      loc_18005DA3F
0x18005d9ac  test    byte ptr [rsp+4C0h+FindFileData.dwFileAttributes], 10h
0x18005d9b1  jz      short loc_18005DA02
0x18005d9b3  mov     rcx, [rsp+4C0h+hMem]; lpPathName
0x18005d9b8  xor     edx, edx; lpSecurityAttributes
0x18005d9ba  call    cs:__imp_CreateDirectoryW
0x18005d9c1  nop     dword ptr [rax+rax+00h]
0x18005d9c6  test    eax, eax
0x18005d9c8  jnz     short loc_18005D9ED
0x18005d9ca  call    cs:__imp_GetLastError
0x18005d9d1  nop     dword ptr [rax+rax+00h]
0x18005d9d6  mov     ebx, eax
0x18005d9d8  test    eax, eax
0x18005d9da  jle     short loc_18005D9E5
0x18005d9dc  movzx   ebx, ax
0x18005d9df  or      ebx, 80070000h
0x18005d9e5  cmp     ebx, 800700B7h
0x18005d9eb  jnz     short loc_18005DA5B
0x18005d9ed  mov     rdx, [rsp+4C0h+hMem]; unsigned __int16 *
0x18005d9f2  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x18005d9f9  call    ?DmCopyDirectoryRecursive@@YAJPEBG0@Z; DmCopyDirectoryRecursive(ushort const *,ushort const *)
0x18005d9fe  mov     ebx, eax
0x18005da00  jmp     short loc_18005DA3F
0x18005da02  mov     rdx, [rsp+4C0h+hMem]; lpNewFileName
0x18005da07  lea     rcx, [rbp+3C0h+FileName]; lpExistingFileName
0x18005da0e  mov     r8d, 1; bFailIfExists
0x18005da14  call    cs:__imp_CopyFileW
0x18005da1b  nop     dword ptr [rax+rax+00h]
0x18005da20  test    eax, eax
0x18005da22  jnz     short loc_18005DA3F
0x18005da24  call    cs:__imp_GetLastError
0x18005da2b  nop     dword ptr [rax+rax+00h]
0x18005da30  mov     ebx, eax
0x18005da32  test    eax, eax
0x18005da34  jle     short loc_18005DA3F
0x18005da36  movzx   ebx, ax
0x18005da39  or      ebx, 80070000h
0x18005da3f  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18005da44  mov     rcx, rsi; hFindFile
0x18005da47  call    cs:__imp_FindNextFileW
0x18005da4e  nop     dword ptr [rax+rax+00h]
0x18005da53  test    eax, eax
0x18005da55  jnz     loc_18005D905
0x18005da5b  mov     rcx, rsi; hFindFile
0x18005da5e  call    cs:__imp_FindClose
0x18005da65  nop     dword ptr [rax+rax+00h]
0x18005da6a  mov     rcx, [rsp+4C0h+hMem]; hMem
0x18005da6f  call    cs:__imp_LocalFree
0x18005da76  nop     dword ptr [rax+rax+00h]
0x18005da7b  mov     eax, ebx
0x18005da7d  mov     rcx, [rbp+3C0h+var_30]
0x18005da84  xor     rcx, rsp; StackCookie
0x18005da87  call    __security_check_cookie
0x18005da8c  mov     rbx, [rsp+4C0h+arg_10]
0x18005da94  add     rsp, 4A0h
0x18005da9b  pop     r15
0x18005da9d  pop     r14
0x18005da9f  pop     r12
0x18005daa1  pop     rsi
0x18005daa2  pop     rbp
0x18005daa3  retn
```
