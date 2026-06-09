# TfsInitStore

- ea: `0x18002b8f8`
- end: `0x18002bb68`
- name: `TfsInitStore`
- size: `624`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800118c0`

## callees

- `0x18000b5f0`
- `0x18000b6b4`
- `0x18000b7dc`
- `0x18000b81c`
- `0x18002b680`
- `0x18002b8f8`
- `0x18002c814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b96f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b96f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bb12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bb12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bace`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002ba80`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002ba80`
- `KERNEL32!LocalFree` at `0x18002ba63`
- `KERNEL32!LocalFree` at `0x18002ba63`
- `KERNEL32!LocalAlloc` at `0x18002b961`
- `KERNEL32!LocalAlloc` at `0x18002b961`
- `KERNEL32!CreateDirectoryW` at `0x18002ba15`
- `KERNEL32!CreateDirectoryW` at `0x18002ba15`

## pseudocode

```c
_QWORD *TfsInitStore()
{
  unsigned int v0; // edi
  __int64 v1; // rax
  unsigned __int64 v2; // rax
  unsigned int v3; // esi
  char *v4; // rax
  _QWORD *v5; // rbx
  DWORD LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  wchar_t *v10; // rcx
  size_t v11; // rdx
  DWORD v12; // eax
  __int64 i; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rax

  if ( (unsigned int)TfsInit() )
    return 0;
  v0 = TfsStorePathLen + 8;
  if ( TfsStorePathLen + 8 < (unsigned int)TfsStorePathLen
    || (v1 = (unsigned int)(TfsStorePathLen + 9), (unsigned int)v1 < v0)
    || (v2 = 2 * v1, v2 > 0xFFFFFFFF)
    || (int)v2 + 8 < (unsigned int)v2
    || (v3 = v2 + 8304, (int)v2 + 8304 < (unsigned int)(v2 + 8)) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v8 = 17;
    v9 = 534;
    goto LABEL_28;
  }
  v4 = (char *)LocalAlloc(0x40u, v3);
  v5 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v8 = 18;
    v9 = LastError;
LABEL_28:
    WPP_SF_d(v7[2], v8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v9);
LABEL_29:
    TfsShutdown();
    return 0;
  }
  *((_DWORD *)v4 + 4) = v3;
  *((_DWORD *)v4 + 10) = v0;
  *((_DWORD *)v4 + 7) = 3;
  *((_QWORD *)v4 + 4) = v4 + 8296;
  StringCchCopyW((STRSAFE_LPWSTR)v4 + 4148, 4u, L"DAV");
  v10 = (wchar_t *)(v5[4] + 8LL);
  v11 = (unsigned int)(*((_DWORD *)v5 + 10) + 1);
  v5[6] = v10;
  StringCchCopyW(v10, v11, &TfsStorePath);
  StringCchCatW((STRSAFE_LPWSTR)v5[6], (unsigned int)(*((_DWORD *)v5 + 10) + 1), L"\\Tfs_");
  StringCchCatW((STRSAFE_LPWSTR)v5[6], (unsigned int)(*((_DWORD *)v5 + 10) + 1), L"DAV");
  if ( CreateDirectoryW((LPCWSTR)v5[6], 0) )
  {
    *((_DWORD *)v5 + 5) = 0;
    *((_DWORD *)v5 + 6) = 1;
  }
  else
  {
    v12 = GetLastError();
    if ( v12 != 183 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
          v12,
          (__int64)L"DAV");
      LocalFree(v5);
      goto LABEL_29;
    }
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 7));
  for ( i = 0; i != 512; ++i )
  {
    v14 = (__int64)&v5[2 * i + 12];
    v5[2 * i + 13] = v14;
    v15 = 2 * (i + 6);
    v5[v15] = v14;
  }
  *((_DWORD *)v5 + 2073) = 100;
  *((_DWORD *)v5 + 2072) = 600000000;
  EnterCriticalSection(&TfsGlobalLock);
  if ( (unsigned int)TfsScavengerThreadInterval > 0x23C34600 )
    TfsScavengerThreadInterval = 600000000;
  v16 = (_QWORD *)qword_180039358;
  if ( *(__int64 **)qword_180039358 != &TfsStoreList )
    __fastfail(3u);
  *v5 = &TfsStoreList;
  v5[1] = v16;
  *v16 = v5;
  qword_180039358 = (__int64)v5;
  LeaveCriticalSection(&TfsGlobalLock);
  return v5;
}

```

## disassembly

```asm
0x18002b8f8  mov     [rsp+arg_0], rbx
0x18002b8fd  mov     [rsp+arg_8], rsi
0x18002b902  push    rdi
0x18002b903  sub     rsp, 30h
0x18002b907  call    TfsInit
0x18002b90c  test    eax, eax
0x18002b90e  jnz     loc_18002BB56
0x18002b914  mov     eax, cs:TfsStorePathLen
0x18002b91a  lea     edi, [rax+8]
0x18002b91d  cmp     edi, eax
0x18002b91f  jb      loc_18002BB1D
0x18002b925  lea     eax, [rdi+1]
0x18002b928  cmp     eax, edi
0x18002b92a  jb      loc_18002BB1D
0x18002b930  add     rax, rax
0x18002b933  mov     ecx, 0FFFFFFFFh
0x18002b938  cmp     rax, rcx
0x18002b93b  ja      loc_18002BB1D
0x18002b941  lea     ecx, [rax+8]
0x18002b944  cmp     ecx, eax
0x18002b946  jb      loc_18002BB1D
0x18002b94c  lea     esi, [rcx+2068h]
0x18002b952  cmp     esi, ecx
0x18002b954  jb      loc_18002BB1D
0x18002b95a  mov     edx, esi; uBytes
0x18002b95c  mov     ecx, 40h ; '@'; uFlags
0x18002b961  call    cs:__imp_LocalAlloc
0x18002b967  mov     rbx, rax
0x18002b96a  test    rax, rax
0x18002b96d  jnz     short loc_18002B9A1
0x18002b96f  call    cs:__imp_GetLastError
0x18002b975  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b97c  lea     rdx, WPP_GLOBAL_Control
0x18002b983  cmp     rcx, rdx
0x18002b986  jz      loc_18002BB51
0x18002b98c  test    byte ptr [rcx+1Ch], 1
0x18002b990  jz      loc_18002BB51
0x18002b996  lea     edx, [rbx+12h]
0x18002b999  mov     r9d, eax
0x18002b99c  jmp     loc_18002BB41
0x18002b9a1  mov     [rax+10h], esi
0x18002b9a4  lea     rcx, [rax+2068h]; pszDest
0x18002b9ab  mov     esi, 3
0x18002b9b0  mov     [rax+28h], edi
0x18002b9b3  lea     rdi, aDav; "DAV"
0x18002b9ba  mov     [rax+1Ch], esi
0x18002b9bd  mov     r8, rdi; pszSrc
0x18002b9c0  mov     [rax+20h], rcx
0x18002b9c4  lea     edx, [rsi+1]; cchDest
0x18002b9c7  call    StringCchCopyW
0x18002b9cc  mov     rcx, [rbx+20h]
0x18002b9d0  lea     r8, TfsStorePath; pszSrc
0x18002b9d7  mov     edx, [rbx+28h]
0x18002b9da  add     rcx, 8; pszDest
0x18002b9de  inc     edx; cchDest
0x18002b9e0  mov     [rbx+30h], rcx
0x18002b9e4  call    StringCchCopyW
0x18002b9e9  mov     edx, [rbx+28h]
0x18002b9ec  lea     r8, aTfs; "\\Tfs_"
0x18002b9f3  mov     rcx, [rbx+30h]; pszDest
0x18002b9f7  inc     edx; cchDest
0x18002b9f9  call    StringCchCatW
0x18002b9fe  mov     edx, [rbx+28h]
0x18002ba01  mov     r8, rdi; pszSrc
0x18002ba04  mov     rcx, [rbx+30h]; pszDest
0x18002ba08  inc     edx; cchDest
0x18002ba0a  call    StringCchCatW
0x18002ba0f  mov     rcx, [rbx+30h]; lpPathName
0x18002ba13  xor     edx, edx; lpSecurityAttributes
0x18002ba15  call    cs:__imp_CreateDirectoryW
0x18002ba1b  test    eax, eax
0x18002ba1d  jnz     short loc_18002BA6E
0x18002ba1f  call    cs:__imp_GetLastError
0x18002ba25  cmp     eax, 0B7h
0x18002ba2a  jz      short loc_18002BA7C
0x18002ba2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba33  lea     rdx, WPP_GLOBAL_Control
0x18002ba3a  cmp     rcx, rdx
0x18002ba3d  jz      short loc_18002BA60
0x18002ba3f  test    byte ptr [rcx+1Ch], 1
0x18002ba43  jz      short loc_18002BA60
0x18002ba45  mov     rcx, [rcx+10h]
0x18002ba49  lea     edx, [rsi+10h]
0x18002ba4c  mov     r9d, eax
0x18002ba4f  mov     [rsp+38h+var_18], rdi
0x18002ba54  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002ba5b  call    WPP_SF_dS
0x18002ba60  mov     rcx, rbx; hMem
0x18002ba63  call    cs:__imp_LocalFree
0x18002ba69  jmp     loc_18002BB51
0x18002ba6e  mov     dword ptr [rbx+14h], 0
0x18002ba75  mov     dword ptr [rbx+18h], 1
0x18002ba7c  lea     rcx, [rbx+38h]; lpCriticalSection
0x18002ba80  call    cs:__imp_InitializeCriticalSection
0x18002ba86  xor     edx, edx
0x18002ba88  mov     rax, rdx
0x18002ba8b  lea     rcx, [rbx+60h]
0x18002ba8f  shl     rax, 4
0x18002ba93  add     rcx, rax
0x18002ba96  mov     [rax+rbx+68h], rcx
0x18002ba9b  lea     rax, [rdx+6]
0x18002ba9f  add     rax, rax
0x18002baa2  inc     rdx
0x18002baa5  mov     [rbx+rax*8], rcx
0x18002baa9  cmp     rdx, 200h
0x18002bab0  jnz     short loc_18002BA88
0x18002bab2  mov     edi, 23C34600h
0x18002bab7  mov     dword ptr [rbx+2064h], 64h ; 'd'
0x18002bac1  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002bac8  mov     [rbx+2060h], edi
0x18002bace  call    cs:__imp_EnterCriticalSection
0x18002bad4  cmp     cs:TfsScavengerThreadInterval, edi
0x18002bada  jbe     short loc_18002BAE2
0x18002badc  mov     cs:TfsScavengerThreadInterval, edi
0x18002bae2  mov     rax, cs:qword_180039358
0x18002bae9  lea     rdx, TfsStoreList
0x18002baf0  cmp     [rax], rdx
0x18002baf3  jz      short loc_18002BAFA
0x18002baf5  mov     rcx, rsi
0x18002baf8  int     29h; Win8: RtlFailFast(ecx)
0x18002bafa  mov     [rbx], rdx
0x18002bafd  lea     rcx, TfsGlobalLock; lpCriticalSection
0x18002bb04  mov     [rbx+8], rax
0x18002bb08  mov     [rax], rbx
0x18002bb0b  mov     cs:qword_180039358, rbx
0x18002bb12  call    cs:__imp_LeaveCriticalSection
0x18002bb18  mov     rax, rbx
0x18002bb1b  jmp     short loc_18002BB58
0x18002bb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb24  lea     rdx, WPP_GLOBAL_Control
0x18002bb2b  cmp     rcx, rdx
0x18002bb2e  jz      short loc_18002BB51
0x18002bb30  test    byte ptr [rcx+1Ch], 1
0x18002bb34  jz      short loc_18002BB51
0x18002bb36  mov     edx, 11h
0x18002bb3b  mov     r9d, 216h
0x18002bb41  mov     rcx, [rcx+10h]
0x18002bb45  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002bb4c  call    WPP_SF_d
0x18002bb51  call    TfsShutdown
0x18002bb56  xor     eax, eax
0x18002bb58  mov     rbx, [rsp+38h+arg_0]
0x18002bb5d  mov     rsi, [rsp+38h+arg_8]
0x18002bb62  add     rsp, 30h
0x18002bb66  pop     rdi
0x18002bb67  retn
```
