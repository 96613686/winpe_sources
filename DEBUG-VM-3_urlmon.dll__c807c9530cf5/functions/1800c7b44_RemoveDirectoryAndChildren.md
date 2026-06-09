# RemoveDirectoryAndChildren

- ea: `0x1800c7b44`
- end: `0x1800c7db3`
- name: `RemoveDirectoryAndChildren`
- size: `623`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800c7b44`
- `0x1800cdf30`

## callees

- `0x180058270`
- `0x180058738`
- `0x18005cc10`
- `0x1800c7b44`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c7c18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c7c32`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c7c18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpA` at `0x1800c7c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7d75`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800c7ce8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800c7d07`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800c7ce8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800c7d07`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1800c7d26`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1800c7d26`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c7d57`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c7d62`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c7d57`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800c7d62`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x1800c7bf9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x1800c7bf9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800c7b9d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800c7d6b`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800c7b9d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800c7d6b`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800c7d14`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800c7d14`

## pseudocode

```c
__int64 __fastcall RemoveDirectoryAndChildren(const char *a1)
{
  signed int v2; // ebx
  HANDLE FirstFileA; // rsi
  signed int LastError; // eax
  signed int v5; // eax
  unsigned __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  STRSAFE_LPSTR pszDest; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  CHAR PathName[272]; // [rsp+180h] [rbp+80h] BYREF

  v2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( a1 )
  {
    if ( *a1 )
    {
      if ( !RemoveDirectoryA(a1) )
      {
        v2 = StringCchCopyA(PathName, 0x104u, a1);
        if ( v2 >= 0 )
        {
          v2 = StringCchCatA(PathName, 0x104u, "\\*");
          if ( v2 >= 0 )
          {
            FirstFileA = FindFirstFileA(PathName, &FindFileData);
            if ( FirstFileA == (HANDLE)-1LL )
              goto LABEL_22;
            do
            {
              if ( lstrcmpA(FindFileData.cFileName, ".") && lstrcmpA(FindFileData.cFileName, "..") )
              {
                pszDest = PathName;
                v7 = 260;
                v2 = StringCchCopyExA(PathName, 0x104u, a1, &pszDest, &v7, 0);
                if ( v2 < 0 )
                  goto LABEL_20;
                v2 = StringCchCopyExA(pszDest, v7, "\\", &pszDest, &v7, 0);
                if ( v2 < 0 )
                  goto LABEL_20;
                v2 = StringCchCopyA(pszDest, v7, FindFileData.cFileName);
                if ( v2 < 0 )
                  goto LABEL_20;
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  SetFileAttributesA(PathName, 0x90u);
                  v2 = RemoveDirectoryAndChildren(PathName);
                  if ( v2 < 0 )
                    goto LABEL_20;
                }
                else
                {
                  SetFileAttributesA(PathName, 0x80u);
                  if ( !DeleteFileA(PathName) )
                    goto LABEL_18;
                }
              }
            }
            while ( FindNextFileA(FirstFileA, &FindFileData) );
            if ( GetLastError() != 18 )
            {
LABEL_18:
              LastError = GetLastError();
              v2 = LastError;
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
              FindClose(FirstFileA);
              return (unsigned int)v2;
            }
            FindClose(FirstFileA);
            if ( !RemoveDirectoryA(a1) )
            {
LABEL_22:
              v5 = GetLastError();
              v2 = v5;
              if ( v5 > 0 )
                return (unsigned __int16)v5 | 0x80070000;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800c7b44  mov     [rsp-8+arg_8], rbx
0x1800c7b49  mov     [rsp-8+arg_10], rsi
0x1800c7b4e  push    rbp
0x1800c7b4f  push    rdi
0x1800c7b50  push    r15
0x1800c7b52  lea     rbp, [rsp-1A0h]
0x1800c7b5a  sub     rsp, 2A0h
0x1800c7b61  mov     rax, cs:__security_cookie
0x1800c7b68  xor     rax, rsp
0x1800c7b6b  mov     [rbp+1B0h+var_20], rax
0x1800c7b72  mov     rdi, rcx
0x1800c7b75  xor     edx, edx; Val
0x1800c7b77  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x1800c7b7c  mov     r8d, 140h; Size
0x1800c7b82  xor     ebx, ebx
0x1800c7b84  call    memset_0
0x1800c7b89  test    rdi, rdi
0x1800c7b8c  jz      loc_1800C7D8A
0x1800c7b92  cmp     [rdi], bl
0x1800c7b94  jz      loc_1800C7D8A
0x1800c7b9a  mov     rcx, rdi; lpPathName
0x1800c7b9d  call    cs:__imp_RemoveDirectoryA
0x1800c7ba3  test    eax, eax
0x1800c7ba5  jnz     loc_1800C7D8A
0x1800c7bab  mov     r15d, 104h
0x1800c7bb1  lea     rcx, [rbp+1B0h+PathName]; char *
0x1800c7bb8  mov     edx, r15d; unsigned __int64
0x1800c7bbb  mov     r8, rdi; char *
0x1800c7bbe  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c7bc3  mov     ebx, eax
0x1800c7bc5  test    eax, eax
0x1800c7bc7  js      loc_1800C7D8A
0x1800c7bcd  lea     r8, asc_180134D4C; "\\*"
0x1800c7bd4  mov     edx, r15d; unsigned __int64
0x1800c7bd7  lea     rcx, [rbp+1B0h+PathName]; char *
0x1800c7bde  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800c7be3  mov     ebx, eax
0x1800c7be5  test    eax, eax
0x1800c7be7  js      loc_1800C7D8A
0x1800c7bed  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800c7bf2  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800c7bf9  call    cs:__imp_FindFirstFileA
0x1800c7bff  mov     rsi, rax
0x1800c7c02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c7c06  jz      loc_1800C7D75
0x1800c7c0c  lea     rdx, asc_180134D50; "."
0x1800c7c13  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x1800c7c18  call    cs:__imp_lstrcmpA
0x1800c7c1e  test    eax, eax
0x1800c7c20  jz      loc_1800C7D1E
0x1800c7c26  lea     rdx, asc_180134D54; ".."
0x1800c7c2d  lea     rcx, [rsp+2B0h+FindFileData.cFileName]; lpString1
0x1800c7c32  call    cs:__imp_lstrcmpA
0x1800c7c38  test    eax, eax
0x1800c7c3a  jz      loc_1800C7D1E
0x1800c7c40  lea     rax, [rbp+1B0h+PathName]
0x1800c7c47  mov     [rsp+2B0h+var_288], 0; unsigned int
0x1800c7c4f  mov     [rsp+2B0h+pszDest], rax
0x1800c7c54  lea     r9, [rsp+2B0h+pszDest]; char **
0x1800c7c59  lea     rax, [rsp+2B0h+var_280]
0x1800c7c5e  mov     [rsp+2B0h+var_280], r15
0x1800c7c63  mov     r8, rdi; char *
0x1800c7c66  mov     [rsp+2B0h+var_290], rax; unsigned __int64 *
0x1800c7c6b  mov     rdx, r15; unsigned __int64
0x1800c7c6e  lea     rcx, [rbp+1B0h+PathName]; pszDest
0x1800c7c75  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x1800c7c7a  mov     ebx, eax
0x1800c7c7c  test    eax, eax
0x1800c7c7e  js      loc_1800C7D54
0x1800c7c84  mov     rdx, [rsp+2B0h+var_280]; unsigned __int64
0x1800c7c89  lea     rax, [rsp+2B0h+var_280]
0x1800c7c8e  mov     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800c7c93  lea     r9, [rsp+2B0h+pszDest]; char **
0x1800c7c98  mov     [rsp+2B0h+var_288], 0; unsigned int
0x1800c7ca0  lea     r8, asc_18012AFD0; "\\"
0x1800c7ca7  mov     [rsp+2B0h+var_290], rax; unsigned __int64 *
0x1800c7cac  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x1800c7cb1  mov     ebx, eax
0x1800c7cb3  test    eax, eax
0x1800c7cb5  js      loc_1800C7D54
0x1800c7cbb  mov     rdx, [rsp+2B0h+var_280]; unsigned __int64
0x1800c7cc0  lea     r8, [rsp+2B0h+FindFileData.cFileName]; char *
0x1800c7cc5  mov     rcx, [rsp+2B0h+pszDest]; char *
0x1800c7cca  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800c7ccf  mov     ebx, eax
0x1800c7cd1  test    eax, eax
0x1800c7cd3  js      short loc_1800C7D54
0x1800c7cd5  test    byte ptr [rsp+2B0h+FindFileData.dwFileAttributes], 10h
0x1800c7cda  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800c7ce1  jz      short loc_1800C7D02
0x1800c7ce3  mov     edx, 90h; dwFileAttributes
0x1800c7ce8  call    cs:__imp_SetFileAttributesA
0x1800c7cee  lea     rcx, [rbp+1B0h+PathName]
0x1800c7cf5  call    RemoveDirectoryAndChildren
0x1800c7cfa  mov     ebx, eax
0x1800c7cfc  test    eax, eax
0x1800c7cfe  js      short loc_1800C7D54
0x1800c7d00  jmp     short loc_1800C7D1E
0x1800c7d02  mov     edx, 80h; dwFileAttributes
0x1800c7d07  call    cs:__imp_SetFileAttributesA
0x1800c7d0d  lea     rcx, [rbp+1B0h+PathName]; lpFileName
0x1800c7d14  call    cs:__imp_DeleteFileA
0x1800c7d1a  test    eax, eax
0x1800c7d1c  jz      short loc_1800C7D3F
0x1800c7d1e  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x1800c7d23  mov     rcx, rsi; hFindFile
0x1800c7d26  call    cs:__imp_FindNextFileA
0x1800c7d2c  test    eax, eax
0x1800c7d2e  jnz     loc_1800C7C0C
0x1800c7d34  call    cs:__imp_GetLastError
0x1800c7d3a  cmp     eax, 12h
0x1800c7d3d  jz      short loc_1800C7D5F
0x1800c7d3f  call    cs:__imp_GetLastError
0x1800c7d45  mov     ebx, eax
0x1800c7d47  test    eax, eax
0x1800c7d49  jle     short loc_1800C7D54
0x1800c7d4b  movzx   ebx, ax
0x1800c7d4e  or      ebx, 80070000h
0x1800c7d54  mov     rcx, rsi; hFindFile
0x1800c7d57  call    cs:__imp_FindClose
0x1800c7d5d  jmp     short loc_1800C7D8A
0x1800c7d5f  mov     rcx, rsi; hFindFile
0x1800c7d62  call    cs:__imp_FindClose
0x1800c7d68  mov     rcx, rdi; lpPathName
0x1800c7d6b  call    cs:__imp_RemoveDirectoryA
0x1800c7d71  test    eax, eax
0x1800c7d73  jnz     short loc_1800C7D8A
0x1800c7d75  call    cs:__imp_GetLastError
0x1800c7d7b  mov     ebx, eax
0x1800c7d7d  test    eax, eax
0x1800c7d7f  jle     short loc_1800C7D8A
0x1800c7d81  movzx   ebx, ax
0x1800c7d84  or      ebx, 80070000h
0x1800c7d8a  mov     eax, ebx
0x1800c7d8c  mov     rcx, [rbp+1B0h+var_20]
0x1800c7d93  xor     rcx, rsp; StackCookie
0x1800c7d96  call    __security_check_cookie
0x1800c7d9b  lea     r11, [rsp+2B0h+var_10]
0x1800c7da3  mov     rbx, [r11+28h]
0x1800c7da7  mov     rsi, [r11+30h]
0x1800c7dab  mov     rsp, r11
0x1800c7dae  pop     r15
0x1800c7db0  pop     rdi
0x1800c7db1  pop     rbp
0x1800c7db2  retn
```
