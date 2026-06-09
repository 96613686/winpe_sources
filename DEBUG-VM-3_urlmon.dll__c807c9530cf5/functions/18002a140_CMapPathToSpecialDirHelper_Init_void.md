# CMapPathToSpecialDirHelper::Init(void)

- ea: `0x18002a140`
- end: `0x18002a48c`
- name: `?Init@CMapPathToSpecialDirHelper@@QEAAJXZ`
- size: `844`
- prototype: `__int64 __fastcall(CMapPathToSpecialDirHelper *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029a90`
- `0x180029e90`
- `0x18002a730`

## callees

- `0x1800150e0`
- `0x18001e340`
- `0x18002a140`
- `0x1800fd830`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `iertutil!__imp_GetValue` at `0x18002a1d8`
- `iertutil!__imp_GetValue` at `0x18002a1d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a349`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a349`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a1a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a1a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002a2a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002a32b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002a2a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002a32b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18002a28a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18002a31a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18002a28a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x18002a31a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002a24c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002a2ea`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002a24c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002a2ea`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002a230`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002a2ce`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002a230`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002a2ce`
- `WININET!GetUrlCacheConfigInfoW` at `0x18002a37a`
- `WININET!GetUrlCacheConfigInfoW` at `0x18002a413`
- `WININET!GetUrlCacheConfigInfoW` at `0x18002a37a`
- `WININET!GetUrlCacheConfigInfoW` at `0x18002a413`

## pseudocode

```c
__int64 __fastcall CMapPathToSpecialDirHelper::Init(CMapPathToSpecialDirHelper *this)
{
  unsigned int Error; // ebx
  __int64 v4; // rsi
  void *v5; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rax
  __int64 v8; // rax
  WCHAR *i; // rcx
  WCHAR *j; // rcx
  _INTERNET_CACHE_CONFIG_INFOW CacheConfigInfo; // [rsp+40h] [rbp-C0h] BYREF
  struct _INTERNET_CACHE_CONFIG_INFOW v12; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszSrch[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  Error = 0;
  if ( !*((_BYTE *)this + 24) )
  {
    EnterCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
    if ( *((_BYTE *)this + 24) )
      goto LABEL_16;
    GetValue(SettingStore::IEVALUE_urlmon_SpecialFoldersCacheSize, 1, 1, (char *)this + 20, 4, 0, 0);
    v4 = -1;
    v5 = operator new(saturated_mul(*((unsigned int *)this + 5), 8u));
    *((_QWORD *)this + 4) = v5;
    if ( !v5 )
      goto LABEL_17;
    memset_0(v5, 0, 8LL * *((unsigned int *)this + 5));
    Error = SHGetFolderPathW(0, 32, 0, 0, pszSrch);
    InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
    if ( byte_18015DE34 )
      goto LABEL_18;
    if ( Error )
      goto LABEL_16;
    if ( !pszSrch[0] )
    {
LABEL_18:
      memset_0(&CacheConfigInfo, 0, sizeof(CacheConfigInfo));
      CacheConfigInfo.dwStructSize = 560;
      if ( GetUrlCacheConfigInfoW(&CacheConfigInfo, 0, 0x40u) && CacheConfigInfo.CachePath[0] )
      {
        v8 = -1;
        do
          ++v8;
        while ( CacheConfigInfo.CachePath[v8] );
        for ( i = (WCHAR *)&CacheConfigInfo.dwNumCachePaths + v8; i >= CacheConfigInfo.CachePath && *i != 92; --i )
          ;
        i[1] = 0;
        StringCchCopyW(pszSrch, 0x104u, CacheConfigInfo.CachePath);
LABEL_9:
        v6 = StrDupW(pszSrch);
        *((_QWORD *)this + 1) = v6;
        if ( !v6 )
          goto LABEL_17;
        *((_BYTE *)this + 25) = PathIsUNCW(v6);
        Error = SHGetFolderPathW(0, 33, 0, 0, pszSrch);
        InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
        if ( byte_18015DE34 )
          goto LABEL_28;
        if ( Error )
          goto LABEL_16;
        if ( !pszSrch[0] )
        {
LABEL_28:
          memset_0(&v12, 0, sizeof(v12));
          v12.dwStructSize = 560;
          if ( GetUrlCacheConfigInfoW(&v12, 0, 0x200u) && v12.CachePath[0] )
          {
            do
              ++v4;
            while ( v12.CachePath[v4] );
            for ( j = (WCHAR *)&v12.dwNumCachePaths + v4; j >= v12.CachePath && *j != 92; --j )
              ;
            j[1] = 0;
            StringCchCopyW(pszSrch, 0x104u, v12.CachePath);
            Error = 0;
LABEL_14:
            v7 = StrDupW(pszSrch);
            *(_QWORD *)this = v7;
            if ( v7 )
            {
              *((_BYTE *)this + 26) = PathIsUNCW(v7);
              *((_BYTE *)this + 24) = 1;
              goto LABEL_16;
            }
LABEL_17:
            Error = -2147024882;
            goto LABEL_16;
          }
          Error = ResultFromLastError();
        }
        if ( !Error )
          goto LABEL_14;
LABEL_16:
        LeaveCriticalSection(&CMapPathToSpecialDirHelper::s_csPathToSpecialDirHelper);
        return Error;
      }
      Error = ResultFromLastError();
    }
    if ( Error )
      goto LABEL_16;
    goto LABEL_9;
  }
  return Error;
}

```

## disassembly

```asm
0x18002a140  push    rbp
0x18002a142  push    rbx
0x18002a143  push    rsi
0x18002a144  push    rdi
0x18002a145  push    r12
0x18002a147  push    r14
0x18002a149  lea     rbp, [rsp-5C8h]
0x18002a151  sub     rsp, 6C8h
0x18002a158  mov     rax, cs:__security_cookie
0x18002a15f  xor     rax, rsp
0x18002a162  mov     [rbp+5F0h+var_40], rax
0x18002a169  xor     r14d, r14d
0x18002a16c  mov     rdi, rcx
0x18002a16f  mov     ebx, r14d
0x18002a172  cmp     [rcx+18h], r14b
0x18002a176  jz      short loc_18002A199
0x18002a178  mov     eax, ebx
0x18002a17a  mov     rcx, [rbp+5F0h+var_40]
0x18002a181  xor     rcx, rsp; StackCookie
0x18002a184  call    __security_check_cookie
0x18002a189  add     rsp, 6C8h
0x18002a190  pop     r14
0x18002a192  pop     r12
0x18002a194  pop     rdi
0x18002a195  pop     rsi
0x18002a196  pop     rbx
0x18002a197  pop     rbp
0x18002a198  retn
0x18002a199  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a1a0  call    cs:__imp_EnterCriticalSection
0x18002a1a6  cmp     [rdi+18h], r14b
0x18002a1aa  jnz     loc_18002A342
0x18002a1b0  mov     rcx, cs:?IEVALUE_urlmon_SpecialFoldersCacheSize@SettingStore@@3U?$VALUEID@K@1@B; SettingStore::VALUEID<ulong> const SettingStore::IEVALUE_urlmon_SpecialFoldersCacheSize
0x18002a1b7  lea     rbx, [rdi+14h]
0x18002a1bb  mov     edx, 1
0x18002a1c0  mov     [rsp+6F0h+var_6C0], r14
0x18002a1c5  mov     r9, rbx
0x18002a1c8  mov     [rsp+6F0h+var_6C8], r14
0x18002a1cd  mov     r8d, edx
0x18002a1d0  mov     dword ptr [rsp+6F0h+pszPath], 4
0x18002a1d8  call    cs:__imp_GetValue
0x18002a1de  mov     ecx, [rbx]
0x18002a1e0  mov     eax, 8
0x18002a1e5  mul     rcx
0x18002a1e8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002a1ef  cmovb   rax, rsi
0x18002a1f3  mov     rcx, rax; Size
0x18002a1f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a1fb  mov     [rdi+20h], rax
0x18002a1ff  test    rax, rax
0x18002a202  jz      loc_18002A354
0x18002a208  mov     r8d, [rbx]
0x18002a20b  xor     edx, edx; Val
0x18002a20d  shl     r8, 3; Size
0x18002a211  mov     rcx, rax; void *
0x18002a214  call    memset_0
0x18002a219  lea     rax, [rbp+5F0h+pszSrch]
0x18002a220  xor     r9d, r9d; dwFlags
0x18002a223  xor     r8d, r8d; hToken
0x18002a226  mov     [rsp+6F0h+pszPath], rax; pszPath
0x18002a22b  lea     edx, [rsi+21h]; csidl
0x18002a22e  xor     ecx, ecx; hwnd
0x18002a230  call    cs:__imp_SHGetFolderPathW
0x18002a236  xor     r9d, r9d; Context
0x18002a239  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002a240  xor     r8d, r8d; Parameter
0x18002a243  lea     rcx, stru_18015EA38; InitOnce
0x18002a24a  mov     ebx, eax
0x18002a24c  call    cs:__imp_InitOnceExecuteOnce
0x18002a252  cmp     cs:byte_18015DE34, r14b
0x18002a259  mov     r12d, 230h
0x18002a25f  jnz     loc_18002A35B
0x18002a265  test    ebx, ebx
0x18002a267  jnz     loc_18002A342
0x18002a26d  cmp     [rbp+5F0h+pszSrch], r14w
0x18002a275  jz      loc_18002A35B
0x18002a27b  test    ebx, ebx
0x18002a27d  jnz     loc_18002A342
0x18002a283  lea     rcx, [rbp+5F0h+pszSrch]; pszSrch
0x18002a28a  call    cs:__imp_StrDupW
0x18002a290  mov     [rdi+8], rax
0x18002a294  test    rax, rax
0x18002a297  jz      loc_18002A354
0x18002a29d  mov     rcx, rax; pszPath
0x18002a2a0  call    cs:__imp_PathIsUNCW
0x18002a2a6  cmp     eax, 1
0x18002a2a9  setz    al
0x18002a2ac  mov     [rdi+19h], al
0x18002a2af  test    ebx, ebx
0x18002a2b1  jnz     loc_18002A342
0x18002a2b7  lea     rax, [rbp+5F0h+pszSrch]
0x18002a2be  xor     r9d, r9d; dwFlags
0x18002a2c1  xor     r8d, r8d; hToken
0x18002a2c4  mov     [rsp+6F0h+pszPath], rax; pszPath
0x18002a2c9  lea     edx, [rbx+21h]; csidl
0x18002a2cc  xor     ecx, ecx; hwnd
0x18002a2ce  call    cs:__imp_SHGetFolderPathW
0x18002a2d4  xor     r9d, r9d; Context
0x18002a2d7  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002a2de  xor     r8d, r8d; Parameter
0x18002a2e1  lea     rcx, stru_18015EA38; InitOnce
0x18002a2e8  mov     ebx, eax
0x18002a2ea  call    cs:__imp_InitOnceExecuteOnce
0x18002a2f0  cmp     cs:byte_18015DE34, r14b
0x18002a2f7  jnz     loc_18002A3EC
0x18002a2fd  test    ebx, ebx
0x18002a2ff  jnz     short loc_18002A342
0x18002a301  cmp     [rbp+5F0h+pszSrch], r14w
0x18002a309  jz      loc_18002A3EC
0x18002a30f  test    ebx, ebx
0x18002a311  jnz     short loc_18002A342
0x18002a313  lea     rcx, [rbp+5F0h+pszSrch]; pszSrch
0x18002a31a  call    cs:__imp_StrDupW
0x18002a320  mov     [rdi], rax
0x18002a323  test    rax, rax
0x18002a326  jz      short loc_18002A354
0x18002a328  mov     rcx, rax; pszPath
0x18002a32b  call    cs:__imp_PathIsUNCW
0x18002a331  cmp     eax, 1
0x18002a334  setz    al
0x18002a337  mov     [rdi+1Ah], al
0x18002a33a  test    ebx, ebx
0x18002a33c  jnz     short loc_18002A342
0x18002a33e  mov     byte ptr [rdi+18h], 1
0x18002a342  lea     rcx, ?s_csPathToSpecialDirHelper@CMapPathToSpecialDirHelper@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a349  call    cs:__imp_LeaveCriticalSection
0x18002a34f  jmp     loc_18002A178
0x18002a354  mov     ebx, 8007000Eh
0x18002a359  jmp     short loc_18002A342
0x18002a35b  mov     r8, r12; Size
0x18002a35e  lea     rcx, [rsp+6F0h+CacheConfigInfo]; void *
0x18002a363  xor     edx, edx; Val
0x18002a365  call    memset_0
0x18002a36a  xor     edx, edx; lpcbCacheConfigInfo
0x18002a36c  mov     [rsp+6F0h+CacheConfigInfo.dwStructSize], r12d
0x18002a371  lea     rcx, [rsp+6F0h+CacheConfigInfo]; lpCacheConfigInfo
0x18002a376  lea     r8d, [rdx+40h]; dwFieldControl
0x18002a37a  call    cs:__imp_GetUrlCacheConfigInfoW
0x18002a380  test    eax, eax
0x18002a382  jz      short loc_18002A3E0
0x18002a384  cmp     word ptr [rsp+6F0h+CacheConfigInfo.1Ch], r14w
0x18002a38a  jz      short loc_18002A3E0
0x18002a38c  lea     rcx, [rsp+6F0h+CacheConfigInfo.1Ch]
0x18002a391  mov     rax, rsi
0x18002a394  inc     rax
0x18002a397  cmp     [rcx+rax*2], r14w
0x18002a39c  jnz     short loc_18002A394
0x18002a39e  lea     rcx, [rsp+6F0h+CacheConfigInfo.dwNumCachePaths]
0x18002a3a3  lea     rcx, [rcx+rax*2]
0x18002a3a7  jmp     short loc_18002A3B3
0x18002a3a9  cmp     word ptr [rcx], 5Ch ; '\'
0x18002a3ad  jz      short loc_18002A3BD
0x18002a3af  sub     rcx, 2
0x18002a3b3  lea     rax, [rsp+6F0h+CacheConfigInfo.1Ch]
0x18002a3b8  cmp     rcx, rax
0x18002a3bb  jnb     short loc_18002A3A9
0x18002a3bd  mov     [rcx+2], r14w
0x18002a3c2  lea     r8, [rsp+6F0h+CacheConfigInfo.1Ch]; unsigned __int16 *
0x18002a3c7  lea     rcx, [rbp+5F0h+pszSrch]; unsigned __int16 *
0x18002a3ce  mov     edx, 104h; unsigned __int64
0x18002a3d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a3d8  mov     ebx, r14d
0x18002a3db  jmp     loc_18002A283
0x18002a3e0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002a3e5  mov     ebx, eax
0x18002a3e7  jmp     loc_18002A27B
0x18002a3ec  mov     r8, r12; Size
0x18002a3ef  lea     rcx, [rbp+5F0h+var_480]; void *
0x18002a3f6  xor     edx, edx; Val
0x18002a3f8  call    memset_0
0x18002a3fd  xor     edx, edx; lpcbCacheConfigInfo
0x18002a3ff  mov     [rbp+5F0h+var_480.dwStructSize], r12d
0x18002a406  mov     r8d, 200h; dwFieldControl
0x18002a40c  lea     rcx, [rbp+5F0h+var_480]; lpCacheConfigInfo
0x18002a413  call    cs:__imp_GetUrlCacheConfigInfoW
0x18002a419  test    eax, eax
0x18002a41b  jz      short loc_18002A480
0x18002a41d  cmp     word ptr [rbp+5F0h+var_480.1Ch], r14w
0x18002a425  jz      short loc_18002A480
0x18002a427  lea     rax, [rbp+5F0h+var_480.1Ch]
0x18002a42e  inc     rsi
0x18002a431  cmp     [rax+rsi*2], r14w
0x18002a436  jnz     short loc_18002A42E
0x18002a438  lea     rcx, [rbp+5F0h+var_480.dwNumCachePaths]
0x18002a43f  lea     rcx, [rcx+rsi*2]
0x18002a443  jmp     short loc_18002A44F
0x18002a445  cmp     word ptr [rcx], 5Ch ; '\'
0x18002a449  jz      short loc_18002A45B
0x18002a44b  sub     rcx, 2
0x18002a44f  lea     rax, [rbp+5F0h+var_480.1Ch]
0x18002a456  cmp     rcx, rax
0x18002a459  jnb     short loc_18002A445
0x18002a45b  mov     [rcx+2], r14w
0x18002a460  lea     r8, [rbp+5F0h+var_480.1Ch]; unsigned __int16 *
0x18002a467  lea     rcx, [rbp+5F0h+pszSrch]; unsigned __int16 *
0x18002a46e  mov     edx, 104h; unsigned __int64
0x18002a473  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a478  mov     ebx, r14d
0x18002a47b  jmp     loc_18002A313
0x18002a480  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002a485  mov     ebx, eax
0x18002a487  jmp     loc_18002A30F
```
