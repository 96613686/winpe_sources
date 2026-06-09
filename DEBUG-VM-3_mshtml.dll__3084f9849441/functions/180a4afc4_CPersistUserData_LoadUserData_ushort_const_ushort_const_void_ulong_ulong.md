# CPersistUserData::LoadUserData(ushort const *,ushort const *,void * *,ulong *,ulong)

- ea: `0x180a4afc4`
- end: `0x180a4b287`
- name: `?LoadUserData@CPersistUserData@@AEAAJPEBG0PEAPEAXPEAKK@Z`
- size: `707`
- prototype: `int(CPersistUserData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, void **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180a4c380`

## callees

- `0x1801bf528`
- `0x1801c0b08`
- `0x180a4a3d0`
- `0x180a4a7c4`
- `0x180a4afc4`
- `0x180b440b8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a4b137`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a4b137`
- `KERNEL32!CompareFileTime` at `0x180a4b148`
- `KERNEL32!CompareFileTime` at `0x180a4b159`
- `KERNEL32!CompareFileTime` at `0x180a4b224`
- `KERNEL32!CompareFileTime` at `0x180a4b148`
- `KERNEL32!CompareFileTime` at `0x180a4b159`
- `KERNEL32!CompareFileTime` at `0x180a4b224`
- `KERNEL32!GetLastError` at `0x180a4b0b2`
- `KERNEL32!GetLastError` at `0x180a4b10f`
- `KERNEL32!GetLastError` at `0x180a4b1be`
- `KERNEL32!GetLastError` at `0x180a4b0b2`
- `KERNEL32!GetLastError` at `0x180a4b10f`
- `KERNEL32!GetLastError` at `0x180a4b1be`
- `WININET!UnlockUrlCacheEntryStream` at `0x180a4b267`
- `WININET!UnlockUrlCacheEntryStream` at `0x180a4b267`
- `WININET!ReadUrlCacheEntryStream` at `0x180a4b1b4`
- `WININET!ReadUrlCacheEntryStream` at `0x180a4b213`
- `WININET!ReadUrlCacheEntryStream` at `0x180a4b1b4`
- `WININET!ReadUrlCacheEntryStream` at `0x180a4b213`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a4b0a4`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a4b101`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a4b0a4`
- `WININET!RetrieveUrlCacheEntryStreamW` at `0x180a4b101`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180a4b1e3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180a4b1e3`
- `OLEAUT32!__imp_SysFreeString` at `0x180a4b081`
- `OLEAUT32!__imp_SysFreeString` at `0x180a4b081`

## pseudocode

```c
__int64 __fastcall CPersistUserData::LoadUserData(
        CPersistUserData *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        BSTR *a4,
        unsigned int *dwLen,
        __int16 Buffer)
{
  unsigned int *v6; // r13
  struct _INTERNET_CACHE_ENTRY_INFOW *v7; // rsi
  WCHAR *v8; // rdi
  BSTR v9; // r15
  HANDLE v10; // r14
  signed int CacheUrlFromDirPath; // ebx
  __int64 result; // rax
  struct _INTERNET_CACHE_ENTRY_INFOW *v15; // rax
  void *v16; // r8
  void *v17; // r8
  struct _INTERNET_CACHE_ENTRY_INFOW *v18; // rax
  unsigned int dwSizeLow; // eax
  signed int LastError; // eax
  BSTR v21; // rax
  unsigned int v22; // eax
  DWORD cbCacheEntryInfo; // [rsp+30h] [rbp-20h] BYREF
  int v24; // [rsp+34h] [rbp-1Ch]
  LPCWSTR lpszUrlName; // [rsp+38h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-8h] BYREF

  v6 = dwLen;
  v7 = 0;
  v8 = 0;
  FileTime1 = 0;
  v9 = 0;
  lpszUrlName = 0;
  v10 = 0;
  v24 = 0;
  if ( dwLen )
  {
    result = CPersistUserData::EnsureCacheContainer(this);
    if ( (_DWORD)result )
      return result;
    CacheUrlFromDirPath = CPersistUserData::GetCacheUrlFromDirPath(a2, a3, (unsigned __int16 **)&lpszUrlName);
    if ( CacheUrlFromDirPath )
      goto LABEL_7;
    v15 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 1396);
    v7 = v15;
    if ( !v15 )
    {
      CacheUrlFromDirPath = -2147024882;
LABEL_7:
      v8 = (WCHAR *)lpszUrlName;
      goto LABEL_8;
    }
    v8 = (WCHAR *)lpszUrlName;
    cbCacheEntryInfo = 1396;
    v10 = RetrieveUrlCacheEntryStreamW(lpszUrlName, v15, &cbCacheEntryInfo, 0, 0);
    if ( !v10 )
    {
      CacheUrlFromDirPath = GetLastError();
      if ( CacheUrlFromDirPath == 122 )
      {
        MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v7, a3);
        v18 = (struct _INTERNET_CACHE_ENTRY_INFOW *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, cbCacheEntryInfo);
        v7 = v18;
        if ( !v18 )
        {
LABEL_13:
          CacheUrlFromDirPath = -2147024882;
          goto LABEL_8;
        }
        v10 = RetrieveUrlCacheEntryStreamW(v8, v18, &cbCacheEntryInfo, 0, 0);
        if ( v10 )
          goto LABEL_20;
        CacheUrlFromDirPath = GetLastError();
      }
      if ( CacheUrlFromDirPath )
      {
        if ( CacheUrlFromDirPath <= 0 )
          goto LABEL_8;
        CacheUrlFromDirPath = (unsigned __int16)CacheUrlFromDirPath;
        goto LABEL_19;
      }
    }
LABEL_20:
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &v7->ExpireTime) && CompareFileTime(&SystemTimeAsFileTime, &v7->ExpireTime) > 0 )
    {
      DeleteUrlCacheEntryBugW(v8);
      CacheUrlFromDirPath = -2147024894;
      goto LABEL_8;
    }
    LODWORD(dwLen) = 0;
    dwSizeLow = v7->dwSizeLow;
    LODWORD(dwLen) = dwSizeLow;
    if ( !a4 )
    {
      *v6 = dwSizeLow;
      CacheUrlFromDirPath = -2147024774;
      goto LABEL_8;
    }
    LODWORD(lpszUrlName) = 2;
    Buffer = 0;
    if ( ReadUrlCacheEntryStream(v10, 0, &Buffer, (LPDWORD)&lpszUrlName, 0) )
    {
      LODWORD(dwLen) = (_DWORD)dwLen - 2;
      v21 = SysAllocStringLen(0, (unsigned int)dwLen >> 1);
      v24 = 1;
      v9 = v21;
      if ( !v21 )
        goto LABEL_13;
      if ( ReadUrlCacheEntryStream(v10, 2u, v21, (LPDWORD)&dwLen, 0) )
      {
        if ( CompareFileTime(&FileTime1, &v7->ExpireTime) )
          *((_QWORD *)this + 6) = v7->ExpireTime;
        v22 = (unsigned int)dwLen;
        *a4 = v9;
        v9 = 0;
        CacheUrlFromDirPath = 0;
        *v6 = v22;
        goto LABEL_8;
      }
    }
    LastError = GetLastError();
    CacheUrlFromDirPath = LastError;
    if ( LastError <= 0 )
      goto LABEL_8;
    CacheUrlFromDirPath = (unsigned __int16)LastError;
LABEL_19:
    CacheUrlFromDirPath |= 0x80070000;
    goto LABEL_8;
  }
  CacheUrlFromDirPath = -2147467261;
LABEL_8:
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v8, a3);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v7, v16);
  if ( v24 )
    SysFreeString(v9);
  else
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v9, v17);
  if ( v10 )
    UnlockUrlCacheEntryStream(v10, 0);
  return (unsigned int)CacheUrlFromDirPath;
}

```

## disassembly

```asm
0x180a4afc4  mov     [rsp-38h+arg_8], rbx
0x180a4afc9  mov     [rsp-38h+arg_18], r9
0x180a4afce  mov     [rsp-38h+arg_0], rcx
0x180a4afd3  push    rbp
0x180a4afd4  push    rsi
0x180a4afd5  push    rdi
0x180a4afd6  push    r12
0x180a4afd8  push    r13
0x180a4afda  push    r14
0x180a4afdc  push    r15
0x180a4afde  mov     rbp, rsp
0x180a4afe1  sub     rsp, 50h
0x180a4afe5  mov     r13, [rbp+dwLen]
0x180a4afe9  xor     esi, esi
0x180a4afeb  xor     edi, edi
0x180a4afed  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rsi
0x180a4aff1  xor     r15d, r15d
0x180a4aff4  mov     [rbp+lpszUrlName], rdi
0x180a4aff8  xor     r14d, r14d
0x180a4affb  mov     [rbp+var_1C], esi
0x180a4affe  mov     rbx, r8
0x180a4b001  mov     r12, rdx
0x180a4b004  test    r13, r13
0x180a4b007  jnz     short loc_180A4B010
0x180a4b009  mov     ebx, 80004003h
0x180a4b00e  jmp     short loc_180A4B056
0x180a4b010  call    ?EnsureCacheContainer@CPersistUserData@@AEAAJXZ; CPersistUserData::EnsureCacheContainer(void)
0x180a4b015  test    eax, eax
0x180a4b017  jnz     loc_180A4B26F
0x180a4b01d  lea     r8, [rbp+lpszUrlName]; unsigned __int16 **
0x180a4b021  mov     rdx, rbx; Source
0x180a4b024  mov     rcx, r12; pcszURL
0x180a4b027  call    ?GetCacheUrlFromDirPath@CPersistUserData@@CAJPEBG0PEAPEAG@Z; CPersistUserData::GetCacheUrlFromDirPath(ushort const *,ushort const *,ushort * *)
0x180a4b02c  mov     ebx, eax
0x180a4b02e  test    eax, eax
0x180a4b030  jnz     short loc_180A4B052
0x180a4b032  mov     rcx, cs:g_hProcessHeap
0x180a4b039  mov     ebx, 574h
0x180a4b03e  mov     edx, ebx
0x180a4b040  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a4b045  mov     rsi, rax
0x180a4b048  test    rax, rax
0x180a4b04b  jnz     short loc_180A4B08C
0x180a4b04d  mov     ebx, 8007000Eh
0x180a4b052  mov     rdi, [rbp+lpszUrlName]
0x180a4b056  mov     rcx, cs:g_hProcessHeap; this
0x180a4b05d  mov     rdx, rdi; void *
0x180a4b060  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a4b065  mov     rcx, cs:g_hProcessHeap; this
0x180a4b06c  mov     rdx, rsi; void *
0x180a4b06f  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a4b074  cmp     [rbp+var_1C], 0
0x180a4b078  jz      loc_180A4B24E
0x180a4b07e  mov     rcx, r15; bstrString
0x180a4b081  call    cs:__imp_SysFreeString
0x180a4b087  jmp     loc_180A4B25D
0x180a4b08c  mov     [rsp+50h+dwReserved], edi; dwReserved
0x180a4b090  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a4b094  mov     rdi, [rbp+lpszUrlName]
0x180a4b098  xor     r9d, r9d; fRandomRead
0x180a4b09b  mov     rcx, rdi; lpszUrlName
0x180a4b09e  mov     [rbp+cbCacheEntryInfo], ebx
0x180a4b0a1  mov     rdx, rsi; lpCacheEntryInfo
0x180a4b0a4  call    cs:__imp_RetrieveUrlCacheEntryStreamW
0x180a4b0aa  mov     r14, rax
0x180a4b0ad  test    rax, rax
0x180a4b0b0  jnz     short loc_180A4B12F
0x180a4b0b2  call    cs:__imp_GetLastError
0x180a4b0b8  mov     ebx, eax
0x180a4b0ba  cmp     eax, 7Ah ; 'z'
0x180a4b0bd  jnz     short loc_180A4B117
0x180a4b0bf  mov     rcx, cs:g_hProcessHeap; this
0x180a4b0c6  mov     rdx, rsi; void *
0x180a4b0c9  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a4b0ce  mov     edx, [rbp+cbCacheEntryInfo]
0x180a4b0d1  mov     rcx, cs:g_hProcessHeap
0x180a4b0d8  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a4b0dd  mov     rsi, rax
0x180a4b0e0  test    rax, rax
0x180a4b0e3  jnz     short loc_180A4B0EF
0x180a4b0e5  mov     ebx, 8007000Eh
0x180a4b0ea  jmp     loc_180A4B056
0x180a4b0ef  xor     r9d, r9d; fRandomRead
0x180a4b0f2  mov     [rsp+50h+dwReserved], r15d; dwReserved
0x180a4b0f7  lea     r8, [rbp+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a4b0fb  mov     rdx, rax; lpCacheEntryInfo
0x180a4b0fe  mov     rcx, rdi; lpszUrlName
0x180a4b101  call    cs:__imp_RetrieveUrlCacheEntryStreamW
0x180a4b107  mov     r14, rax
0x180a4b10a  test    rax, rax
0x180a4b10d  jnz     short loc_180A4B12F
0x180a4b10f  call    cs:__imp_GetLastError
0x180a4b115  mov     ebx, eax
0x180a4b117  test    ebx, ebx
0x180a4b119  jz      short loc_180A4B12F
0x180a4b11b  jle     loc_180A4B056
0x180a4b121  movzx   ebx, bx
0x180a4b124  or      ebx, 80070000h
0x180a4b12a  jmp     loc_180A4B056
0x180a4b12f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180a4b133  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x180a4b137  call    cs:__imp_GetSystemTimeAsFileTime
0x180a4b13d  lea     rbx, [rsi+34h]
0x180a4b141  mov     rdx, rbx; lpFileTime2
0x180a4b144  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180a4b148  call    cs:__imp_CompareFileTime
0x180a4b14e  test    eax, eax
0x180a4b150  jz      short loc_180A4B175
0x180a4b152  mov     rdx, rbx; lpFileTime2
0x180a4b155  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x180a4b159  call    cs:__imp_CompareFileTime
0x180a4b15f  test    eax, eax
0x180a4b161  jle     short loc_180A4B175
0x180a4b163  mov     rcx, rdi; unsigned __int16 *
0x180a4b166  call    ?DeleteUrlCacheEntryBugW@@YAHPEBG@Z; DeleteUrlCacheEntryBugW(ushort const *)
0x180a4b16b  mov     ebx, 80070002h
0x180a4b170  jmp     loc_180A4B056
0x180a4b175  mov     r12, [rbp+arg_18]
0x180a4b179  mov     dword ptr [rbp+dwLen], r15d
0x180a4b17d  mov     eax, [rsi+24h]
0x180a4b180  mov     dword ptr [rbp+dwLen], eax
0x180a4b183  test    r12, r12
0x180a4b186  jnz     short loc_180A4B196
0x180a4b188  mov     [r13+0], eax
0x180a4b18c  mov     ebx, 8007007Ah
0x180a4b191  jmp     loc_180A4B056
0x180a4b196  xor     eax, eax
0x180a4b198  mov     dword ptr [rbp+lpszUrlName], 2
0x180a4b19f  lea     r9, [rbp+lpszUrlName]; lpdwLen
0x180a4b1a3  mov     [rbp+Buffer], ax
0x180a4b1a7  lea     r8, [rbp+Buffer]; lpBuffer
0x180a4b1ab  mov     [rsp+50h+dwReserved], eax; Reserved
0x180a4b1af  xor     edx, edx; dwLocation
0x180a4b1b1  mov     rcx, r14; hUrlCacheStream
0x180a4b1b4  call    cs:__imp_ReadUrlCacheEntryStream
0x180a4b1ba  test    eax, eax
0x180a4b1bc  jnz     short loc_180A4B1D6
0x180a4b1be  call    cs:__imp_GetLastError
0x180a4b1c4  mov     ebx, eax
0x180a4b1c6  test    eax, eax
0x180a4b1c8  jle     loc_180A4B056
0x180a4b1ce  movzx   ebx, ax
0x180a4b1d1  jmp     loc_180A4B124
0x180a4b1d6  mov     edx, dword ptr [rbp+dwLen]
0x180a4b1d9  xor     ecx, ecx; strIn
0x180a4b1db  add     edx, 0FFFFFFFEh
0x180a4b1de  mov     dword ptr [rbp+dwLen], edx
0x180a4b1e1  shr     edx, 1; ui
0x180a4b1e3  call    cs:__imp_SysAllocStringLen
0x180a4b1e9  mov     [rbp+var_1C], 1
0x180a4b1f0  mov     r15, rax
0x180a4b1f3  test    rax, rax
0x180a4b1f6  jz      loc_180A4B0E5
0x180a4b1fc  lea     r9, [rbp+dwLen]; lpdwLen
0x180a4b200  mov     [rsp+50h+dwReserved], 0; Reserved
0x180a4b208  mov     r8, rax; lpBuffer
0x180a4b20b  mov     edx, 2; dwLocation
0x180a4b210  mov     rcx, r14; hUrlCacheStream
0x180a4b213  call    cs:__imp_ReadUrlCacheEntryStream
0x180a4b219  test    eax, eax
0x180a4b21b  jz      short loc_180A4B1BE
0x180a4b21d  mov     rdx, rbx; lpFileTime2
0x180a4b220  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180a4b224  call    cs:__imp_CompareFileTime
0x180a4b22a  test    eax, eax
0x180a4b22c  jz      short loc_180A4B239
0x180a4b22e  mov     rcx, [rbp+arg_0]
0x180a4b232  mov     rax, [rbx]
0x180a4b235  mov     [rcx+30h], rax
0x180a4b239  mov     eax, dword ptr [rbp+dwLen]
0x180a4b23c  mov     [r12], r15
0x180a4b240  xor     r15d, r15d
0x180a4b243  xor     ebx, ebx
0x180a4b245  mov     [r13+0], eax
0x180a4b249  jmp     loc_180A4B056
0x180a4b24e  mov     rcx, cs:g_hProcessHeap; this
0x180a4b255  mov     rdx, r15; void *
0x180a4b258  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180a4b25d  test    r14, r14
0x180a4b260  jz      short loc_180A4B26D
0x180a4b262  xor     edx, edx; Reserved
0x180a4b264  mov     rcx, r14; hUrlCacheStream
0x180a4b267  call    cs:__imp_UnlockUrlCacheEntryStream
0x180a4b26d  mov     eax, ebx
0x180a4b26f  mov     rbx, [rsp+50h+arg_8]
0x180a4b277  add     rsp, 50h
0x180a4b27b  pop     r15
0x180a4b27d  pop     r14
0x180a4b27f  pop     r13
0x180a4b281  pop     r12
0x180a4b283  pop     rdi
0x180a4b284  pop     rsi
0x180a4b285  pop     rbp
0x180a4b286  retn
```
