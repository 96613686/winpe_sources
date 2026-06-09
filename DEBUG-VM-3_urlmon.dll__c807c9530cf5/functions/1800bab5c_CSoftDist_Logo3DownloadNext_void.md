# CSoftDist::Logo3DownloadNext(void)

- ea: `0x1800bab5c`
- end: `0x1800bae02`
- name: `?Logo3DownloadNext@CSoftDist@@QEAAJXZ`
- size: `678`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800ccd30`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x18005cc10`
- `0x1800763a8`
- `0x1800ba8f4`
- `0x1800bab5c`
- `0x1800c7954`
- `0x18011baa0`
- `0x18011bb60`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x1800bad10`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionA` at `0x1800bad10`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800bac9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800bacbd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800bac9e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x1800bacbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bac52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bac52`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x1800bad3f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x1800bad3f`
- `WININET!CommitUrlCacheEntryA` at `0x1800bad6e`
- `WININET!CommitUrlCacheEntryA` at `0x1800bad6e`
- `WININET!CreateUrlCacheEntryA` at `0x1800bad2b`
- `WININET!CreateUrlCacheEntryA` at `0x1800bad2b`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800babf6`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800bad00`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800babf6`
- `WININET!GetUrlCacheEntryInfoA` at `0x1800bad00`

## pseudocode

```c
__int64 __fastcall CSoftDist::Logo3DownloadNext(CSoftDist *this)
{
  __int64 v1; // rax
  CHAR *v3; // rdi
  LPCWCH *v4; // r15
  CHAR *v5; // r14
  int v6; // ebx
  __int64 v7; // rax
  size_t v8; // rbx
  char *v9; // rax
  _QWORD *v10; // rsi
  int v11; // r13d
  __int64 v12; // rdi
  const CHAR *lpszFileExtension; // rsi
  CSoftDist *v14; // rsi
  _QWORD *v15; // r8
  __int64 v16; // rdx
  _QWORD *v17; // r9
  DWORD cbCacheEntryInfo; // [rsp+50h] [rbp-B0h] BYREF
  LPCSTR lpszUrlName; // [rsp+58h] [rbp-A8h]
  LPCSTR pszPath; // [rsp+60h] [rbp-A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  LPCWCH lpWideCharStr; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v24; // [rsp+78h] [rbp-88h]
  CSoftDist *v25; // [rsp+80h] [rbp-80h]
  CHAR szFileName[272]; // [rsp+90h] [rbp-70h] BYREF
  _INTERNET_CACHE_ENTRY_INFOA CacheEntryInfo; // [rsp+1A0h] [rbp+A0h] BYREF

  v1 = *((_QWORD *)this + 17);
  v25 = this;
  SystemTimeAsFileTime = 0;
  cbCacheEntryInfo = 0;
  v3 = 0;
  v4 = *(LPCWCH **)(v1 + 16);
  v5 = 0;
  lpWideCharStr = 0;
  lpszUrlName = 0;
  pszPath = 0;
  v6 = Unicode2Ansi(*v4);
  if ( v6 >= 0 )
  {
    cbCacheEntryInfo = 4096;
    if ( GetUrlCacheEntryInfoA(lpszUrlName, &CacheEntryInfo, &cbCacheEntryInfo) )
    {
      v7 = -1;
      do
        ++v7;
      while ( CacheEntryInfo.lpszLocalFileName[v7] );
      v8 = (unsigned int)(v7 + 1);
      v9 = (char *)operator new(v8);
      v5 = v9;
      if ( v9 )
      {
        StringCchCopyA(v9, v8, CacheEntryInfo.lpszLocalFileName);
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v10 = (_QWORD *)*((_QWORD *)this + 11);
        v6 = 1;
        lpszUrlName = 0;
        v11 = 1;
        while ( v10 )
        {
          v24 = (_QWORD *)*v10;
          v12 = v10[2];
          if ( (*(_BYTE *)(v12 + 24) & 2) != 0 )
          {
            if ( (int)Unicode2Ansi(*(LPCWCH *)v12) < 0 )
            {
              v3 = (CHAR *)pszPath;
              v6 = -2147467259;
              goto LABEL_27;
            }
            if ( (LPCWCH *)v12 == v4 || StrCmpW(*(PCWSTR *)(v12 + 16), v4[2]) )
              v11 = 0;
          }
          v10 = v24;
          if ( (LPCWCH *)v12 != v4 && !StrCmpW(v4[2], *(PCWSTR *)(v12 + 16)) )
            *(_DWORD *)(v12 + 24) |= 1u;
        }
        v3 = (CHAR *)pszPath;
        if ( v11 )
        {
          cbCacheEntryInfo = 4096;
          if ( !GetUrlCacheEntryInfoA(pszPath, &CacheEntryInfo, &cbCacheEntryInfo) )
          {
            lpszFileExtension = PathFindExtensionA(v3) + 1;
            if ( CreateUrlCacheEntryA(v3, 0, lpszFileExtension, szFileName, 0) )
            {
              CopyFileA(v5, szFileName, 0);
              CommitUrlCacheEntryA(
                v3,
                szFileName,
                (FILETIME)lpszUrlName,
                SystemTimeAsFileTime,
                1u,
                0,
                0,
                lpszFileExtension,
                0);
            }
          }
        }
        v14 = v25;
        v15 = (_QWORD *)*((_QWORD *)v25 + 11);
        while ( v15 )
        {
          v16 = v15[2];
          v17 = v15;
          v15 = (_QWORD *)*v15;
          if ( (*(_BYTE *)(v16 + 24) & 1) == 0 )
          {
            *((_QWORD *)v25 + 17) = v17;
            *(_DWORD *)(v16 + 24) |= 1u;
            CDLDupWStr(&lpWideCharStr, *(_QWORD *)v16, v15);
            v6 = CSoftDist::Logo3Download(v14, lpWideCharStr);
            break;
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
    else
    {
      v6 = -2147467259;
    }
  }
LABEL_27:
  if ( v5 )
    operator delete(v5);
  if ( v3 )
    operator delete(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800bab5c  push    rbp
0x1800bab5e  push    rbx
0x1800bab5f  push    rsi
0x1800bab60  push    rdi
0x1800bab61  push    r12
0x1800bab63  push    r13
0x1800bab65  push    r14
0x1800bab67  push    r15
0x1800bab69  lea     rbp, [rsp-10B8h]
0x1800bab71  mov     eax, 11B8h
0x1800bab76  call    _alloca_probe
0x1800bab7b  sub     rsp, rax
0x1800bab7e  mov     rax, cs:__security_cookie
0x1800bab85  xor     rax, rsp
0x1800bab88  mov     [rbp+10F0h+var_50], rax
0x1800bab8f  mov     rax, [rcx+88h]
0x1800bab96  lea     rdx, [rsp+11F0h+lpszUrlName]
0x1800bab9b  xor     r13d, r13d
0x1800bab9e  mov     [rbp+10F0h+var_1170], rcx
0x1800baba2  mov     qword ptr [rsp+11F0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800baba7  mov     rsi, rcx
0x1800babaa  mov     [rsp+11F0h+cbCacheEntryInfo], r13d
0x1800babaf  mov     edi, r13d
0x1800babb2  mov     r15, [rax+10h]
0x1800babb6  mov     r14d, r13d
0x1800babb9  mov     [rsp+11F0h+lpWideCharStr], r13
0x1800babbe  mov     [rsp+11F0h+lpszUrlName], r13
0x1800babc3  mov     [rsp+11F0h+pszPath], r13
0x1800babc8  mov     rcx, [r15]; lpWideCharStr
0x1800babcb  call    Unicode2Ansi
0x1800babd0  mov     r12, [rsp+11F0h+lpszUrlName]
0x1800babd5  mov     ebx, eax
0x1800babd7  test    eax, eax
0x1800babd9  js      loc_1800BADB6
0x1800babdf  lea     r8, [rsp+11F0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800babe4  mov     [rsp+11F0h+cbCacheEntryInfo], 1000h
0x1800babec  lea     rdx, [rbp+10F0h+CacheEntryInfo]; lpCacheEntryInfo
0x1800babf3  mov     rcx, r12; lpszUrlName
0x1800babf6  call    cs:__imp_GetUrlCacheEntryInfoA
0x1800babfc  test    eax, eax
0x1800babfe  jnz     short loc_1800BAC0A
0x1800bac00  mov     ebx, 80004005h
0x1800bac05  jmp     loc_1800BADB6
0x1800bac0a  mov     rcx, [rbp+10F0h+CacheEntryInfo.lpszLocalFileName]
0x1800bac11  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bac15  inc     rax
0x1800bac18  cmp     [rcx+rax], r13b
0x1800bac1c  jnz     short loc_1800BAC15
0x1800bac1e  inc     eax
0x1800bac20  mov     ecx, eax; Size
0x1800bac22  mov     ebx, eax
0x1800bac24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bac29  mov     r14, rax
0x1800bac2c  test    rax, rax
0x1800bac2f  jnz     short loc_1800BAC3B
0x1800bac31  mov     ebx, 8007000Eh
0x1800bac36  jmp     loc_1800BADB6
0x1800bac3b  mov     r8, [rbp+10F0h+CacheEntryInfo.lpszLocalFileName]; char *
0x1800bac42  mov     rdx, rbx; unsigned __int64
0x1800bac45  mov     rcx, r14; char *
0x1800bac48  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800bac4d  lea     rcx, [rsp+11F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800bac52  call    cs:__imp_GetSystemTimeAsFileTime
0x1800bac58  mov     rsi, [rsi+58h]
0x1800bac5c  mov     ebx, 1
0x1800bac61  mov     [rsp+11F0h+lpszUrlName], r13
0x1800bac66  mov     r13d, ebx
0x1800bac69  test    rsi, rsi
0x1800bac6c  jz      short loc_1800BACDB
0x1800bac6e  mov     rdi, [rsi]
0x1800bac71  mov     [rsp+11F0h+var_1178], rdi
0x1800bac76  mov     rdi, [rsi+10h]
0x1800bac7a  test    byte ptr [rdi+18h], 2
0x1800bac7e  jz      short loc_1800BACAB
0x1800bac80  mov     rcx, [rdi]; lpWideCharStr
0x1800bac83  lea     rdx, [rsp+11F0h+pszPath]
0x1800bac88  call    Unicode2Ansi
0x1800bac8d  test    eax, eax
0x1800bac8f  js      short loc_1800BACCC
0x1800bac91  cmp     rdi, r15
0x1800bac94  jz      short loc_1800BACA8
0x1800bac96  mov     rdx, [r15+10h]; psz2
0x1800bac9a  mov     rcx, [rdi+10h]; psz1
0x1800bac9e  call    cs:__imp_StrCmpW
0x1800baca4  test    eax, eax
0x1800baca6  jz      short loc_1800BACAB
0x1800baca8  xor     r13d, r13d
0x1800bacab  mov     rsi, [rsp+11F0h+var_1178]
0x1800bacb0  cmp     rdi, r15
0x1800bacb3  jz      short loc_1800BAC69
0x1800bacb5  mov     rdx, [rdi+10h]; psz2
0x1800bacb9  mov     rcx, [r15+10h]; psz1
0x1800bacbd  call    cs:__imp_StrCmpW
0x1800bacc3  test    eax, eax
0x1800bacc5  jnz     short loc_1800BAC69
0x1800bacc7  or      [rdi+18h], ebx
0x1800bacca  jmp     short loc_1800BAC69
0x1800baccc  mov     rdi, [rsp+11F0h+pszPath]
0x1800bacd1  mov     ebx, 80004005h
0x1800bacd6  jmp     loc_1800BADB6
0x1800bacdb  mov     rdi, [rsp+11F0h+pszPath]
0x1800bace0  test    r13d, r13d
0x1800bace3  jz      loc_1800BAD74
0x1800bace9  lea     r8, [rsp+11F0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800bacee  mov     [rsp+11F0h+cbCacheEntryInfo], 1000h
0x1800bacf6  lea     rdx, [rbp+10F0h+CacheEntryInfo]; lpCacheEntryInfo
0x1800bacfd  mov     rcx, rdi; lpszUrlName
0x1800bad00  call    cs:__imp_GetUrlCacheEntryInfoA
0x1800bad06  xor     r13d, r13d
0x1800bad09  test    eax, eax
0x1800bad0b  jnz     short loc_1800BAD74
0x1800bad0d  mov     rcx, rdi; pszPath
0x1800bad10  call    cs:__imp_PathFindExtensionA
0x1800bad16  lea     r9, [rbp+10F0h+szFileName]; lpszFileName
0x1800bad1a  mov     [rsp+11F0h+dwReserved], r13d; dwReserved
0x1800bad1f  xor     edx, edx; dwExpectedFileSize
0x1800bad21  mov     rcx, rdi; lpszUrlName
0x1800bad24  lea     rsi, [rax+1]
0x1800bad28  mov     r8, rsi; lpszFileExtension
0x1800bad2b  call    cs:__imp_CreateUrlCacheEntryA
0x1800bad31  test    eax, eax
0x1800bad33  jz      short loc_1800BAD74
0x1800bad35  xor     r8d, r8d; bFailIfExists
0x1800bad38  lea     rdx, [rbp+10F0h+szFileName]; lpNewFileName
0x1800bad3c  mov     rcx, r14; lpExistingFileName
0x1800bad3f  call    cs:__imp_CopyFileA
0x1800bad45  mov     r9, qword ptr [rsp+11F0h+SystemTimeAsFileTime.dwLowDateTime]; LastModifiedTime
0x1800bad4a  lea     rdx, [rbp+10F0h+szFileName]; lpszLocalFileName
0x1800bad4e  mov     r8, [rsp+11F0h+lpszUrlName]; ExpireTime
0x1800bad53  mov     rcx, rdi; lpszUrlName
0x1800bad56  mov     [rsp+11F0h+lpszOriginalUrl], r12; lpszOriginalUrl
0x1800bad5b  mov     [rsp+11F0h+lpszFileExtension], rsi; lpszFileExtension
0x1800bad60  mov     [rsp+11F0h+cchHeaderInfo], r13d; cchHeaderInfo
0x1800bad65  mov     [rsp+11F0h+lpHeaderInfo], r13; lpHeaderInfo
0x1800bad6a  mov     [rsp+11F0h+dwReserved], ebx; CacheEntryType
0x1800bad6e  call    cs:__imp_CommitUrlCacheEntryA
0x1800bad74  mov     rsi, [rbp+10F0h+var_1170]
0x1800bad78  mov     r8, [rsi+58h]
0x1800bad7c  test    r8, r8
0x1800bad7f  jz      short loc_1800BADB6
0x1800bad81  mov     rdx, [r8+10h]
0x1800bad85  mov     r9, r8
0x1800bad88  mov     r8, [r8]
0x1800bad8b  test    [rdx+18h], bl
0x1800bad8e  jnz     short loc_1800BAD7C
0x1800bad90  mov     [rsi+88h], r9
0x1800bad97  lea     rcx, [rsp+11F0h+lpWideCharStr]
0x1800bad9c  or      [rdx+18h], ebx
0x1800bad9f  mov     rdx, [rdx]
0x1800bada2  call    CDLDupWStr
0x1800bada7  mov     rdx, [rsp+11F0h+lpWideCharStr]; lpWideCharStr
0x1800badac  mov     rcx, rsi; this
0x1800badaf  call    ?Logo3Download@CSoftDist@@QEAAJPEAG@Z; CSoftDist::Logo3Download(ushort *)
0x1800badb4  mov     ebx, eax
0x1800badb6  test    r12, r12
0x1800badb9  jz      short loc_1800BADC3
0x1800badbb  mov     rcx, r12; void *
0x1800badbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800badc3  test    r14, r14
0x1800badc6  jz      short loc_1800BADD0
0x1800badc8  mov     rcx, r14; void *
0x1800badcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800badd0  test    rdi, rdi
0x1800badd3  jz      short loc_1800BADDD
0x1800badd5  mov     rcx, rdi; void *
0x1800badd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800baddd  mov     eax, ebx
0x1800baddf  mov     rcx, [rbp+10F0h+var_50]
0x1800bade6  xor     rcx, rsp; StackCookie
0x1800bade9  call    __security_check_cookie
0x1800badee  add     rsp, 11B8h
0x1800badf5  pop     r15
0x1800badf7  pop     r14
0x1800badf9  pop     r13
0x1800badfb  pop     r12
0x1800badfd  pop     rdi
0x1800badfe  pop     rsi
0x1800badff  pop     rbx
0x1800bae00  pop     rbp
0x1800bae01  retn
```
