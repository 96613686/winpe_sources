# EnumeratePathEx

- ea: `0x18003c3b8`
- end: `0x18003c98d`
- name: `EnumeratePathEx`
- size: `1493`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18003bbe0`
- `0x18003be78`

## callees

- `0x18003a8d8`
- `0x18003b7f4`
- `0x18003c3b8`
- `0x18003c994`
- `0x18003ca10`
- `0x18003cb5c`
- `0x18003cbdc`
- `0x18003ce30`
- `0x18003d238`
- `0x18003df50`
- `0x18003e128`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18003c6b1`
- `msvcrt!wcsrchr` at `0x18003c6b1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003c869`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003c869`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003c627`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003c627`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003c808`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003c808`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c7ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c7d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c7ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c7d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c929`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c942`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c7bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c7e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c950`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c7bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c7e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c950`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c491`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c79b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c962`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c491`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c79b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c72b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c755`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c72b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003c755`
- `ntdll!RtlAllocateHeap` at `0x18003c539`
- `ntdll!RtlAllocateHeap` at `0x18003c539`
- `ntdll!RtlFreeHeap` at `0x18003c8e2`
- `ntdll!RtlFreeHeap` at `0x18003c8e2`

## string_xrefs

- `0x18003c4c1`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x18003c834`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18003c843`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x18003c903`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18003c87d`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x18003c8ae`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

## pseudocode

```c
__int64 __fastcall EnumeratePathEx(
        LPCWSTR lpFileName,
        __int64 (__fastcall *a2)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64),
        __int64 (__fastcall *a3)(DWORD *, __int64),
        __int64 a4,
        char a5)
{
  unsigned int v6; // r13d
  DWORD v7; // ecx
  DWORD LastError; // ebx
  DWORD v10; // ecx
  unsigned __int64 v11; // r12
  __int64 v12; // rdi
  WCHAR *v13; // rbx
  int v14; // r15d
  wchar_t *Heap; // rsi
  HRESULT v16; // eax
  unsigned __int16 v17; // di
  HRESULT v18; // eax
  HRESULT v19; // eax
  const WCHAR *v20; // rax
  void *v21; // rax
  wchar_t *v22; // rax
  const WCHAR *v23; // rax
  int v24; // edi
  __int64 (__fastcall *v25)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // r15
  int v26; // eax
  void *v27; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v29; // r15
  HANDLE v30; // rax
  int v31; // edi
  DWORD v32; // eax
  const wchar_t *v33; // r8
  HANDLE v34; // rax
  HANDLE v35; // rax
  STRSAFE_LPWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  DWORD v37; // [rsp+30h] [rbp-D0h]
  DWORD v38; // [rsp+30h] [rbp-D0h]
  size_t cchDest; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v41)(DWORD *, __int64); // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  DWORD dwFileAttributes; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME ftCreationTime; // [rsp+64h] [rbp-9Ch]
  FILETIME ftLastAccessTime; // [rsp+6Ch] [rbp-94h]
  FILETIME ftLastWriteTime; // [rsp+74h] [rbp-8Ch]
  int v47; // [rsp+7Ch] [rbp-84h]
  DWORD nFileSizeLow; // [rsp+80h] [rbp-80h]
  DWORD nFileSizeHigh; // [rsp+84h] [rbp-7Ch]
  LPVOID lpMem; // [rsp+88h] [rbp-78h]
  PCNZWCH lpString2[2]; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v52)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+A0h] [rbp-60h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  v41 = a3;
  v52 = a2;
  v42 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  LODWORD(pszDest) = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 87;
    goto LABEL_73;
  }
  v6 = 1;
  if ( (unsigned int)ReparsePointExists(lpFileName, &pszDest) && (_DWORD)pszDest )
  {
    LODWORD(cchDest) = 0;
    if ( (a5 & 2) != 0 )
      goto LABEL_11;
    if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &cchDest) && (_DWORD)cchDest )
      goto LABEL_16;
    LODWORD(cchDest) = 0;
    if ( (a5 & 1) != 0 )
    {
LABEL_11:
      v7 = 0;
      goto LABEL_12;
    }
    if ( (unsigned int)GetReparseTag(lpFileName) )
    {
      if ( (_DWORD)cchDest != -2147483640 )
        goto LABEL_11;
      goto LABEL_16;
    }
    LastError = GetLastError();
    if ( (unsigned int)ReparsePointExists(lpFileName, &pszDest) && (_DWORD)pszDest )
    {
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
        LastError);
      v10 = LastError;
LABEL_73:
      SetLastError(v10);
      return 0;
    }
  }
LABEL_16:
  v11 = -1;
  pszDest = 0;
  v12 = -1;
  cchDest = 0;
  v13 = 0;
  v14 = 0;
  do
    ++v12;
  while ( lpFileName[v12] );
  if ( (_DWORD)v12 && lpFileName[(unsigned int)(v12 - 1)] != 92 )
    v14 = 1;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v12 + v14 + 2));
  if ( !Heap )
  {
    NtCurrentTeb()->LastErrorValue = 8;
LABEL_66:
    Heap = 0;
LABEL_67:
    LODWORD(ppszDestEnd) = GetLastError();
    v31 = (int)ppszDestEnd;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      ppszDestEnd);
    v6 = 0;
    if ( Heap )
      goto LABEL_68;
    goto LABEL_69;
  }
  v16 = StringCchCopyNExW(Heap, (unsigned int)(v12 + v14 + 2), lpFileName, (unsigned int)v12, &pszDest, &cchDest, v37);
  v17 = v16;
  if ( v16 < 0
    || v14 && (v18 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v38), v17 = v18, v18 < 0)
    || (v19 = StringCchCopyNW(pszDest, cchDest, L"*", 1u), v17 = v19, v19 < 0) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    NtCurrentTeb()->LastErrorValue = v17;
    goto LABEL_66;
  }
  NtCurrentTeb()->LastErrorValue = 0;
  v20 = (const WCHAR *)PrepareUnicodePathEx(Heap);
  v13 = (WCHAR *)v20;
  if ( !v20 )
    goto LABEL_67;
  v6 = 0;
  cchDest = (size_t)FindFirstFileW(v20, &FindFileData);
  if ( cchDest == -1 )
  {
    LODWORD(ppszDestEnd) = GetLastError();
    v31 = (int)ppszDestEnd;
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v13, ppszDestEnd);
    do
      ++v11;
    while ( v13[v11] );
    if ( v11 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v31 = 206;
    }
    goto LABEL_68;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  do
  {
    if ( !*lpFileName )
    {
      SetLastError(0x57u);
      v24 = 0;
      goto LABEL_48;
    }
    dwFileAttributes = FindFileData.dwFileAttributes;
    ftCreationTime = FindFileData.ftCreationTime;
    ftLastAccessTime = FindFileData.ftLastAccessTime;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    nFileSizeLow = FindFileData.nFileSizeLow;
    nFileSizeHigh = FindFileData.nFileSizeHigh;
    v47 = 0;
    lpMem = 0;
    *(_OWORD *)lpString2 = 0;
    v21 = (void *)BuildPath(lpFileName, FindFileData.cFileName);
    lpMem = v21;
    if ( v21
      && ((v22 = wcsrchr((const wchar_t *)v21, 0x5Cu)) == 0 ? (v23 = (const WCHAR *)lpMem) : (v23 = v22 + 1),
          lpString2[0] = v23,
          (lpString2[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem)) != 0) )
    {
      v24 = 1;
    }
    else
    {
      v24 = 0;
      FreeWdslibFindData(&dwFileAttributes);
    }
    if ( v24 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v41 )
          goto LABEL_48;
        v26 = v41(&dwFileAttributes, v42);
        goto LABEL_44;
      }
      v25 = v52;
      if ( v52
        && CompareStringW(0x409u, 1u, L".", -1, lpString2[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, lpString2[0], -1) != 2 )
      {
        v26 = v25(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v41, v42);
LABEL_44:
        v24 = v26;
      }
    }
LABEL_48:
    v27 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      if ( HeapFree(ProcessHeap, 0, v27) )
        lpMem = 0;
    }
    v29 = (WCHAR *)lpString2[1];
    if ( lpString2[1] )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v24 != 1 )
    {
      v32 = GetLastError();
      v33 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_59;
    }
  }
  while ( FindNextFileW((HANDLE)cchDest, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v31 = 0;
    v6 = 1;
    goto LABEL_60;
  }
  v32 = GetLastError();
  v33 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_59:
  LODWORD(ppszDestEnd) = v32;
  v31 = v32;
  LibLog(&g_WdsLibLog, 0x2000000, v33, v13, ppszDestEnd);
LABEL_60:
  FindClose((HANDLE)cchDest);
LABEL_68:
  v34 = GetProcessHeap();
  HeapFree(v34, 0, Heap);
LABEL_69:
  if ( v13 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v13);
  }
  v7 = v31;
LABEL_12:
  SetLastError(v7);
  return v6;
}

```

## disassembly

```asm
0x18003c3b8  push    rbp
0x18003c3ba  push    rbx
0x18003c3bb  push    rsi
0x18003c3bc  push    rdi
0x18003c3bd  push    r12
0x18003c3bf  push    r13
0x18003c3c1  push    r14
0x18003c3c3  push    r15
0x18003c3c5  lea     rbp, [rsp-218h]
0x18003c3cd  sub     rsp, 318h
0x18003c3d4  mov     rax, cs:__security_cookie
0x18003c3db  xor     rax, rsp
0x18003c3de  mov     [rbp+250h+var_50], rax
0x18003c3e5  mov     [rsp+350h+var_300], r8
0x18003c3ea  mov     r14, rcx
0x18003c3ed  mov     [rbp+250h+var_2B0], rdx
0x18003c3f1  lea     rcx, [rbp+250h+FindFileData]; void *
0x18003c3f5  xor     edx, edx; Val
0x18003c3f7  mov     [rsp+350h+var_2F8], r9
0x18003c3fc  mov     r8d, 250h; Size
0x18003c402  call    memset_0
0x18003c407  xor     esi, esi
0x18003c409  mov     dword ptr [rsp+350h+pszDest], esi
0x18003c40d  test    r14, r14
0x18003c410  jz      loc_18003C95D
0x18003c416  cmp     si, [r14]
0x18003c41a  jz      loc_18003C95D
0x18003c420  lea     rdx, [rsp+350h+pszDest]
0x18003c425  mov     rcx, r14
0x18003c428  call    ReparsePointExists
0x18003c42d  lea     r13d, [rsi+1]
0x18003c431  test    eax, eax
0x18003c433  jz      loc_18003C4E0
0x18003c439  cmp     dword ptr [rsp+350h+pszDest], esi
0x18003c43d  jz      loc_18003C4E0
0x18003c443  mov     ebx, [rbp+250h+arg_20]
0x18003c449  mov     dword ptr [rsp+350h+cchDest], esi
0x18003c44d  test    bl, 2
0x18003c450  jnz     short loc_18003C48F
0x18003c452  lea     rdx, [rsp+350h+cchDest]
0x18003c457  mov     rcx, r14
0x18003c45a  call    ShouldEnumerateReparsePoint
0x18003c45f  test    eax, eax
0x18003c461  jz      short loc_18003C469
0x18003c463  cmp     dword ptr [rsp+350h+cchDest], esi
0x18003c467  jnz     short loc_18003C4E0
0x18003c469  and     ebx, r13d
0x18003c46c  mov     dword ptr [rsp+350h+cchDest], esi
0x18003c470  test    bl, bl
0x18003c472  jnz     short loc_18003C48F
0x18003c474  lea     rdx, [rsp+350h+cchDest]
0x18003c479  mov     rcx, r14; lpFileName
0x18003c47c  call    GetReparseTag
0x18003c481  test    eax, eax
0x18003c483  jz      short loc_18003C49F
0x18003c485  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x18003c48d  jz      short loc_18003C4E0
0x18003c48f  xor     ecx, ecx; dwErrCode
0x18003c491  call    cs:__imp_SetLastError
0x18003c497  mov     eax, r13d
0x18003c49a  jmp     loc_18003C96A
0x18003c49f  call    cs:__imp_GetLastError
0x18003c4a5  lea     rdx, [rsp+350h+pszDest]
0x18003c4aa  mov     rcx, r14
0x18003c4ad  mov     ebx, eax
0x18003c4af  call    ReparsePointExists
0x18003c4b4  test    eax, eax
0x18003c4b6  jz      short loc_18003C4E0
0x18003c4b8  cmp     dword ptr [rsp+350h+pszDest], esi
0x18003c4bc  jz      short loc_18003C4E0
0x18003c4be  mov     r9d, ebx
0x18003c4c1  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x18003c4c8  mov     edx, 2000000h
0x18003c4cd  lea     rcx, g_WdsLibLog
0x18003c4d4  call    LibLog
0x18003c4d9  mov     ecx, ebx
0x18003c4db  jmp     loc_18003C962
0x18003c4e0  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003c4e4  mov     [rsp+350h+pszDest], rsi
0x18003c4e9  mov     rdi, r12
0x18003c4ec  mov     [rsp+350h+cchDest], rsi
0x18003c4f1  mov     rbx, rsi
0x18003c4f4  mov     r15d, esi
0x18003c4f7  inc     rdi
0x18003c4fa  cmp     [r14+rdi*2], si
0x18003c4ff  jnz     short loc_18003C4F7
0x18003c501  mov     edx, 5Ch ; '\'
0x18003c506  test    edi, edi
0x18003c508  jz      short loc_18003C516
0x18003c50a  lea     eax, [rdi-1]
0x18003c50d  cmp     dx, [r14+rax*2]
0x18003c512  cmovnz  r15d, r13d
0x18003c516  mov     rcx, gs:60h
0x18003c51f  lea     eax, [r15+2]
0x18003c523  add     eax, edi
0x18003c525  mov     edx, 8; Flags
0x18003c52a  mov     r13d, eax
0x18003c52d  mov     rcx, [rcx+30h]; HeapHandle
0x18003c531  lea     r8, ds:0[rax*2]; Size
0x18003c539  call    cs:__imp_RtlAllocateHeap
0x18003c53f  mov     rsi, rax
0x18003c542  test    rax, rax
0x18003c545  jnz     short loc_18003C55F
0x18003c547  mov     rax, gs:30h
0x18003c550  xor     r15d, r15d
0x18003c553  mov     dword ptr [rax+68h], 8
0x18003c55a  jmp     loc_18003C8F7
0x18003c55f  lea     rax, [rsp+350h+cchDest]
0x18003c564  mov     r9d, edi; cchToCopy
0x18003c567  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18003c56c  mov     r8, r14; pszSrc
0x18003c56f  lea     rax, [rsp+350h+pszDest]
0x18003c574  mov     rdx, r13; cchDest
0x18003c577  mov     rcx, rsi; pszDest
0x18003c57a  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18003c57f  call    StringCchCopyNExW
0x18003c584  mov     edi, eax
0x18003c586  test    eax, eax
0x18003c588  js      loc_18003C8CD
0x18003c58e  test    r15d, r15d
0x18003c591  jz      short loc_18003C5D1
0x18003c593  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18003c598  lea     rax, [rsp+350h+cchDest]
0x18003c59d  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18003c5a2  lea     r8, pszSrc; "\\"
0x18003c5a9  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18003c5ae  mov     r9d, 1; cchToCopy
0x18003c5b4  lea     rax, [rsp+350h+pszDest]
0x18003c5b9  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18003c5be  call    StringCchCopyNExW
0x18003c5c3  xor     r15d, r15d
0x18003c5c6  mov     edi, eax
0x18003c5c8  test    eax, eax
0x18003c5ca  jns     short loc_18003C5D4
0x18003c5cc  jmp     loc_18003C8D0
0x18003c5d1  xor     r15d, r15d
0x18003c5d4  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18003c5d9  lea     r8, asc_180061A1C; "*"
0x18003c5e0  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18003c5e5  mov     r9d, 1; cchToCopy
0x18003c5eb  call    StringCchCopyNW
0x18003c5f0  mov     edi, eax
0x18003c5f2  test    eax, eax
0x18003c5f4  js      loc_18003C8D0
0x18003c5fa  mov     rax, gs:30h
0x18003c603  xor     edx, edx
0x18003c605  mov     rcx, rsi; unsigned __int16 *
0x18003c608  mov     [rax+68h], r15d
0x18003c60c  call    PrepareUnicodePathEx
0x18003c611  mov     rbx, rax
0x18003c614  test    rax, rax
0x18003c617  jz      loc_18003C8FA
0x18003c61d  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18003c621  mov     rcx, rax; lpFileName
0x18003c624  mov     r13d, r15d
0x18003c627  call    cs:__imp_FindFirstFileW
0x18003c62d  mov     [rsp+350h+cchDest], rax
0x18003c632  cmp     rax, r12
0x18003c635  jz      loc_18003C874
0x18003c63b  xor     edx, edx; Val
0x18003c63d  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003c642  lea     r8d, [rdx+40h]; Size
0x18003c646  call    memset_0
0x18003c64b  cmp     r15w, [r14]
0x18003c64f  jz      loc_18003C796
0x18003c655  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x18003c658  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18003c65c  mov     [rsp+350h+var_2F0], eax
0x18003c660  xorps   xmm0, xmm0
0x18003c663  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x18003c667  mov     rcx, r14; pszSrc
0x18003c66a  mov     [rsp+350h+var_2EC], rax
0x18003c66f  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x18003c673  mov     [rsp+350h+var_2E4], rax
0x18003c678  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18003c67c  mov     [rsp+350h+var_2DC], rax
0x18003c681  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x18003c684  mov     [rbp+250h+var_2D0], eax
0x18003c687  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x18003c68a  mov     [rbp+250h+var_2CC], eax
0x18003c68d  mov     [rsp+350h+var_2D4], r15d
0x18003c692  mov     [rbp+250h+lpMem], r15
0x18003c696  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x18003c69b  call    BuildPath
0x18003c6a0  mov     [rbp+250h+lpMem], rax
0x18003c6a4  test    rax, rax
0x18003c6a7  jz      short loc_18003C6E2
0x18003c6a9  mov     edx, 5Ch ; '\'; Ch
0x18003c6ae  mov     rcx, rax; Str
0x18003c6b1  call    cs:__imp_wcsrchr
0x18003c6b7  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x18003c6bb  test    rax, rax
0x18003c6be  jz      short loc_18003C6C6
0x18003c6c0  add     rax, 2
0x18003c6c4  jmp     short loc_18003C6C9
0x18003c6c6  mov     rax, rcx
0x18003c6c9  mov     [rbp+250h+lpString2], rax
0x18003c6cd  call    FormFullPathName
0x18003c6d2  mov     [rbp+250h+lpString2+8], rax
0x18003c6d6  test    rax, rax
0x18003c6d9  jz      short loc_18003C6E2
0x18003c6db  mov     edi, 1
0x18003c6e0  jmp     short loc_18003C6EF
0x18003c6e2  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003c6e7  mov     edi, r15d
0x18003c6ea  call    FreeWdslibFindData
0x18003c6ef  cmp     edi, 1
0x18003c6f2  jnz     loc_18003C7A4
0x18003c6f8  test    byte ptr [rsp+350h+var_2F0], 10h
0x18003c6fd  jz      short loc_18003C77B
0x18003c6ff  mov     r15, [rbp+250h+var_2B0]
0x18003c703  test    r15, r15
0x18003c706  jz      loc_18003C7A4
0x18003c70c  mov     rax, [rbp+250h+lpString2]
0x18003c710  lea     r8, String1; "."
0x18003c717  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18003c71c  mov     r9d, r12d; cchCount1
0x18003c71f  mov     edx, edi; dwCmpFlags
0x18003c721  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18003c726  mov     ecx, 409h; Locale
0x18003c72b  call    cs:__imp_CompareStringW
0x18003c731  cmp     eax, 2
0x18003c734  jz      short loc_18003C7A4
0x18003c736  mov     rax, [rbp+250h+lpString2]
0x18003c73a  lea     r8, asc_180061A20; ".."
0x18003c741  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18003c746  mov     r9d, r12d; cchCount1
0x18003c749  mov     edx, edi; dwCmpFlags
0x18003c74b  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18003c750  mov     ecx, 409h; Locale
0x18003c755  call    cs:__imp_CompareStringW
0x18003c75b  cmp     eax, 2
0x18003c75e  jz      short loc_18003C7A4
0x18003c760  mov     r8, [rsp+350h+var_2F8]
0x18003c765  lea     rcx, [rsp+350h+var_2F0]
0x18003c76a  mov     rdx, [rsp+350h+var_300]
0x18003c76f  mov     rax, r15
0x18003c772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c777  mov     edi, eax
0x18003c779  jmp     short loc_18003C7A4
0x18003c77b  mov     rax, [rsp+350h+var_300]
0x18003c780  test    rax, rax
0x18003c783  jz      short loc_18003C7A4
0x18003c785  mov     rdx, [rsp+350h+var_2F8]
0x18003c78a  lea     rcx, [rsp+350h+var_2F0]
0x18003c78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c794  jmp     short loc_18003C777
0x18003c796  mov     ecx, 57h ; 'W'; dwErrCode
0x18003c79b  call    cs:__imp_SetLastError
0x18003c7a1  mov     edi, r15d
0x18003c7a4  mov     r15, [rbp+250h+lpMem]
0x18003c7a8  test    r15, r15
0x18003c7ab  jz      short loc_18003C7CD
0x18003c7ad  call    cs:__imp_GetProcessHeap
0x18003c7b3  mov     r8, r15; lpMem
0x18003c7b6  xor     edx, edx; dwFlags
0x18003c7b8  mov     rcx, rax; hHeap
0x18003c7bb  call    cs:__imp_HeapFree
0x18003c7c1  test    eax, eax
0x18003c7c3  jz      short loc_18003C7CD
0x18003c7c5  mov     [rbp+250h+lpMem], 0
0x18003c7cd  mov     r15, [rbp+250h+lpString2+8]
0x18003c7d1  test    r15, r15
0x18003c7d4  jz      short loc_18003C7EA
0x18003c7d6  call    cs:__imp_GetProcessHeap
0x18003c7dc  mov     r8, r15; lpMem
0x18003c7df  xor     edx, edx; dwFlags
0x18003c7e1  mov     rcx, rax; hHeap
0x18003c7e4  call    cs:__imp_HeapFree
0x18003c7ea  xor     edx, edx; Val
0x18003c7ec  lea     rcx, [rsp+350h+var_2F0]; void *
0x18003c7f1  lea     r8d, [rdx+40h]; Size
0x18003c7f5  call    memset_0
0x18003c7fa  cmp     edi, 1
0x18003c7fd  jnz     short loc_18003C83D
0x18003c7ff  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18003c804  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18003c808  call    cs:__imp_FindNextFileW
0x18003c80e  lea     r15d, [rdi-1]
0x18003c812  cmp     eax, edi
0x18003c814  jz      loc_18003C64B
0x18003c81a  call    cs:__imp_GetLastError
0x18003c820  cmp     eax, 12h
0x18003c823  jnz     short loc_18003C82E
0x18003c825  mov     edi, r15d
0x18003c828  lea     r13d, [r15+1]
0x18003c82c  jmp     short loc_18003C864
0x18003c82e  call    cs:__imp_GetLastError
0x18003c834  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x18003c83b  jmp     short loc_18003C84A
0x18003c83d  call    cs:__imp_GetLastError
0x18003c843  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x18003c84a  mov     r9, rbx
0x18003c84d  mov     dword ptr [rsp+350h+ppszDestEnd], eax
0x18003c851  mov     edx, 2000000h
0x18003c856  lea     rcx, g_WdsLibLog
0x18003c85d  mov     edi, eax
0x18003c85f  call    LibLog
0x18003c864  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18003c869  call    cs:__imp_FindClose
  ... truncated ...
```
