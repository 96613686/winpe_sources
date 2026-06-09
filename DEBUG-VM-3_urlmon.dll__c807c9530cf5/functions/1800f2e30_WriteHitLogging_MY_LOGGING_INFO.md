# _WriteHitLogging(_MY_LOGGING_INFO *)

- ea: `0x1800f2e30`
- end: `0x1800f2ffa`
- name: `?_WriteHitLogging@@YAHPEAU_MY_LOGGING_INFO@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(struct _MY_LOGGING_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f2730`

## callees

- `0x1800f2898`
- `0x1800f2934`
- `0x1800f2a00`
- `0x1800f2bf4`
- `0x1800f2e30`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f2e89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f2e89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f69`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2ea9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2ece`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f1f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f28`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f72`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2fc1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2fca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2ea9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2ece`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f1f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f28`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2f72`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2fc1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800f2fca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f2f5e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800f2f5e`
- `WININET!CommitUrlCacheEntryA` at `0x1800f2fb6`
- `WININET!CommitUrlCacheEntryA` at `0x1800f2fb6`
- `WININET!GetUrlCacheEntryInfoExA` at `0x1800f2f02`
- `WININET!GetUrlCacheEntryInfoExA` at `0x1800f2f02`

## pseudocode

```c
__int64 __fastcall _WriteHitLogging(struct _MY_LOGGING_INFO *a1)
{
  __int64 v2; // rcx
  char *v3; // rbx
  DWORD v4; // ecx
  struct _INTERNET_CACHE_ENTRY_INFOA *CacheEntry; // rax
  struct _INTERNET_CACHE_ENTRY_INFOA *v7; // rdi
  char *v8; // rcx
  void *LogFile; // rsi
  char *LogString; // rax
  char *v11; // r14
  __int64 v12; // r8
  unsigned int v13; // ebp
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-148h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-140h] BYREF
  CHAR szLocalFileName[272]; // [rsp+60h] [rbp-138h] BYREF

  NumberOfBytesWritten = 0;
  v2 = *(_QWORD *)a1;
  hMem = 0;
  ConvertToPrefixedURL(*(const char **)(v2 + 8), (char **)&hMem);
  v3 = (char *)hMem;
  if ( !hMem )
  {
    v4 = 8;
LABEL_3:
    SetLastError(v4);
    return 0;
  }
  CacheEntry = QueryCacheEntry((LPCSTR)hMem);
  v7 = CacheEntry;
  v8 = v3;
  if ( !CacheEntry )
  {
LABEL_6:
    GlobalFree(v8);
    v4 = 2;
    goto LABEL_3;
  }
  LogFile = GetLogFile(v3, CacheEntry, szLocalFileName);
  if ( !LogFile )
  {
    GlobalFree(v3);
    v8 = (char *)v7;
    goto LABEL_6;
  }
  *((_DWORD *)a1 + 2) = GetUrlCacheEntryInfoExA(*(LPCSTR *)(*(_QWORD *)a1 + 8LL), 0, 0, 0, 0, 0, 0);
  LogString = GetLogString(a1);
  v11 = LogString;
  if ( !LogString )
  {
    GlobalFree(v3);
    GlobalFree(v7);
    CloseHandle(LogFile);
    return 0;
  }
  v12 = -1;
  do
    ++v12;
  while ( LogString[v12] );
  v13 = WriteFile(LogFile, LogString, v12, &NumberOfBytesWritten, 0);
  CloseHandle(LogFile);
  GlobalFree(v11);
  if ( v13 )
    v13 = CommitUrlCacheEntryA(
            v3,
            szLocalFileName,
            v7->ExpireTime,
            v7->LastModifiedTime,
            v7->CacheEntryType,
            0,
            0,
            0,
            0);
  GlobalFree(v7);
  GlobalFree(v3);
  return v13;
}

```

## disassembly

```asm
0x1800f2e30  mov     [rsp+arg_8], rbx
0x1800f2e35  mov     [rsp+arg_10], rbp
0x1800f2e3a  push    rsi
0x1800f2e3b  push    rdi
0x1800f2e3c  push    r14
0x1800f2e3e  sub     rsp, 180h
0x1800f2e45  mov     rax, cs:__security_cookie
0x1800f2e4c  xor     rax, rsp
0x1800f2e4f  mov     [rsp+198h+var_28], rax
0x1800f2e57  mov     r14, rcx
0x1800f2e5a  mov     [rsp+198h+NumberOfBytesWritten], 0
0x1800f2e62  mov     rcx, [rcx]
0x1800f2e65  lea     rdx, [rsp+198h+hMem]; char **
0x1800f2e6a  mov     [rsp+198h+hMem], 0
0x1800f2e73  mov     rcx, [rcx+8]; char *
0x1800f2e77  call    ?ConvertToPrefixedURL@@YAHPEBDPEAPEAD@Z; ConvertToPrefixedURL(char const *,char * *)
0x1800f2e7c  mov     rbx, [rsp+198h+hMem]
0x1800f2e81  test    rbx, rbx
0x1800f2e84  jnz     short loc_1800F2E96
0x1800f2e86  lea     ecx, [rbx+8]; dwErrCode
0x1800f2e89  call    cs:__imp_SetLastError
0x1800f2e8f  xor     eax, eax
0x1800f2e91  jmp     loc_1800F2FD2
0x1800f2e96  mov     rcx, rbx; lpszUrlName
0x1800f2e99  call    ?QueryCacheEntry@@YAPEAU_INTERNET_CACHE_ENTRY_INFOA@@PEBD@Z; QueryCacheEntry(char const *)
0x1800f2e9e  mov     rdi, rax
0x1800f2ea1  mov     rcx, rbx; char *
0x1800f2ea4  test    rax, rax
0x1800f2ea7  jnz     short loc_1800F2EB6
0x1800f2ea9  call    cs:__imp_GlobalFree
0x1800f2eaf  mov     ecx, 2
0x1800f2eb4  jmp     short loc_1800F2E89
0x1800f2eb6  lea     r8, [rsp+198h+szLocalFileName]; char *
0x1800f2ebb  mov     rdx, rdi; struct _INTERNET_CACHE_ENTRY_INFOA *
0x1800f2ebe  call    ?GetLogFile@@YAPEAXPEBDPEAU_INTERNET_CACHE_ENTRY_INFOA@@PEAD@Z; GetLogFile(char const *,_INTERNET_CACHE_ENTRY_INFOA *,char *)
0x1800f2ec3  mov     rsi, rax
0x1800f2ec6  test    rax, rax
0x1800f2ec9  jnz     short loc_1800F2ED9
0x1800f2ecb  mov     rcx, rbx; hMem
0x1800f2ece  call    cs:__imp_GlobalFree
0x1800f2ed4  mov     rcx, rdi
0x1800f2ed7  jmp     short loc_1800F2EA9
0x1800f2ed9  mov     rcx, [r14]
0x1800f2edc  xor     r9d, r9d; lpszRedirectUrl
0x1800f2edf  mov     [rsp+198h+dwFlags], 0; dwFlags
0x1800f2ee7  xor     r8d, r8d; lpcbCacheEntryInfo
0x1800f2eea  mov     [rsp+198h+lpReserved], 0; lpReserved
0x1800f2ef3  xor     edx, edx; lpCacheEntryInfo
0x1800f2ef5  mov     [rsp+198h+lpcbRedirectUrl], 0; lpcbRedirectUrl
0x1800f2efe  mov     rcx, [rcx+8]; lpszUrl
0x1800f2f02  call    cs:__imp_GetUrlCacheEntryInfoExA
0x1800f2f08  mov     rcx, r14; struct _MY_LOGGING_INFO *
0x1800f2f0b  mov     [r14+8], eax
0x1800f2f0f  call    ?GetLogString@@YAPEADPEAU_MY_LOGGING_INFO@@@Z; GetLogString(_MY_LOGGING_INFO *)
0x1800f2f14  mov     r14, rax
0x1800f2f17  test    rax, rax
0x1800f2f1a  jnz     short loc_1800F2F3C
0x1800f2f1c  mov     rcx, rbx; hMem
0x1800f2f1f  call    cs:__imp_GlobalFree
0x1800f2f25  mov     rcx, rdi; hMem
0x1800f2f28  call    cs:__imp_GlobalFree
0x1800f2f2e  mov     rcx, rsi; hObject
0x1800f2f31  call    cs:__imp_CloseHandle
0x1800f2f37  jmp     loc_1800F2E8F
0x1800f2f3c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f2f40  inc     r8; nNumberOfBytesToWrite
0x1800f2f43  cmp     byte ptr [rax+r8], 0
0x1800f2f48  jnz     short loc_1800F2F40
0x1800f2f4a  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800f2f4f  mov     [rsp+198h+lpcbRedirectUrl], 0; lpOverlapped
0x1800f2f58  mov     rdx, r14; lpBuffer
0x1800f2f5b  mov     rcx, rsi; hFile
0x1800f2f5e  call    cs:__imp_WriteFile
0x1800f2f64  mov     rcx, rsi; hObject
0x1800f2f67  mov     ebp, eax
0x1800f2f69  call    cs:__imp_CloseHandle
0x1800f2f6f  mov     rcx, r14; hMem
0x1800f2f72  call    cs:__imp_GlobalFree
0x1800f2f78  test    ebp, ebp
0x1800f2f7a  jz      short loc_1800F2FBE
0x1800f2f7c  mov     eax, [rdi+18h]
0x1800f2f7f  lea     rdx, [rsp+198h+szLocalFileName]; lpszLocalFileName
0x1800f2f84  mov     r9, [rdi+2Ch]; LastModifiedTime
0x1800f2f88  mov     rcx, rbx; lpszUrlName
0x1800f2f8b  mov     r8, [rdi+34h]; ExpireTime
0x1800f2f8f  mov     [rsp+198h+lpszOriginalUrl], 0; lpszOriginalUrl
0x1800f2f98  mov     [rsp+198h+lpszFileExtension], 0; lpszFileExtension
0x1800f2fa1  mov     [rsp+198h+dwFlags], 0; cchHeaderInfo
0x1800f2fa9  mov     [rsp+198h+lpReserved], 0; lpHeaderInfo
0x1800f2fb2  mov     dword ptr [rsp+198h+lpcbRedirectUrl], eax; CacheEntryType
0x1800f2fb6  call    cs:__imp_CommitUrlCacheEntryA
0x1800f2fbc  mov     ebp, eax
0x1800f2fbe  mov     rcx, rdi; hMem
0x1800f2fc1  call    cs:__imp_GlobalFree
0x1800f2fc7  mov     rcx, rbx; hMem
0x1800f2fca  call    cs:__imp_GlobalFree
0x1800f2fd0  mov     eax, ebp
0x1800f2fd2  mov     rcx, [rsp+198h+var_28]
0x1800f2fda  xor     rcx, rsp; StackCookie
0x1800f2fdd  call    __security_check_cookie
0x1800f2fe2  lea     r11, [rsp+198h+var_18]
0x1800f2fea  mov     rbx, [r11+28h]
0x1800f2fee  mov     rbp, [r11+30h]
0x1800f2ff2  mov     rsp, r11
0x1800f2ff5  pop     r14
0x1800f2ff7  pop     rdi
0x1800f2ff8  pop     rsi
0x1800f2ff9  retn
```
