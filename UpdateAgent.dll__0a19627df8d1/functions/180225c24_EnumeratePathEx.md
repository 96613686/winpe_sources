# EnumeratePathEx

- ea: `0x180225c24`
- end: `0x18022629c`
- name: `EnumeratePathEx`
- size: `1656`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64), __int64 (__fastcall *)(DWORD *, __int64), __int64, char)`
- caller_count: `7`
- callee_count: `14`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180224b80`
- `0x180224cf4`
- `0x1802252d0`
- `0x1802255bc`
- `0x180225ba0`
- `0x180226388`
- `0x1802266e4`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x180093308`
- `0x1802222e4`
- `0x180222764`
- `0x1802227f8`
- `0x180225c24`
- `0x1802262f0`
- `0x1802264ac`
- `0x180226a18`
- `0x180226ab4`
- `0x180226ea0`
- `0x180227084`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180225f39`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180225f39`
- `ntdll!RtlAllocateHeap` at `0x180225db5`
- `ntdll!RtlAllocateHeap` at `0x180225db5`
- `ntdll!RtlFreeHeap` at `0x1802261c6`
- `ntdll!RtlFreeHeap` at `0x1802261c6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802260c4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802260c4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180225ea9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180225ea9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18022613d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18022613d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180225fbd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180225fed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180225fbd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180225fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022623e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180226219`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022623e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180226065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022609a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022622d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180226252`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180226065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022609a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022622d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180226252`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180226039`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18022626a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180225d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180226039`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18022626a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180225d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802260dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802260f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022610b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022614e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802261e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180225d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802260dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802260f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022610b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022614e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802261e4`

## string_xrefs

- `0x1802261f3`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18022615d`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x180226192`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`
- `0x180225d3d`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x180226102`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x180226117`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180225c24  push    rbp
0x180225c26  push    rbx
0x180225c27  push    rsi
0x180225c28  push    rdi
0x180225c29  push    r12
0x180225c2b  push    r13
0x180225c2d  push    r14
0x180225c2f  push    r15
0x180225c31  lea     rbp, [rsp-218h]
0x180225c39  sub     rsp, 318h
0x180225c40  mov     rax, cs:__security_cookie
0x180225c47  xor     rax, rsp
0x180225c4a  mov     [rbp+250h+var_50], rax
0x180225c51  mov     [rsp+350h+var_300], r8
0x180225c56  mov     r14, rcx
0x180225c59  mov     [rbp+250h+var_2B0], rdx
0x180225c5d  lea     rcx, [rbp+250h+FindFileData]; void *
0x180225c61  xor     edx, edx; Val
0x180225c63  mov     [rsp+350h+var_2F8], r9
0x180225c68  mov     r8d, 250h; Size
0x180225c6e  call    memset_0
0x180225c73  xor     esi, esi
0x180225c75  mov     dword ptr [rsp+350h+pszDest], esi
0x180225c79  test    r14, r14
0x180225c7c  jz      loc_180226265
0x180225c82  cmp     si, [r14]
0x180225c86  jz      loc_180226265
0x180225c8c  lea     rdx, [rsp+350h+pszDest]
0x180225c91  mov     rcx, r14
0x180225c94  call    ReparsePointExists
0x180225c99  lea     r13d, [rsi+1]
0x180225c9d  test    eax, eax
0x180225c9f  jz      loc_180225D5C
0x180225ca5  cmp     dword ptr [rsp+350h+pszDest], esi
0x180225ca9  jz      loc_180225D5C
0x180225caf  mov     ebx, [rbp+250h+arg_20]
0x180225cb5  mov     dword ptr [rsp+350h+cchDest], esi
0x180225cb9  test    bl, 2
0x180225cbc  jnz     short loc_180225CFF
0x180225cbe  lea     rdx, [rsp+350h+cchDest]
0x180225cc3  mov     rcx, r14
0x180225cc6  call    ShouldEnumerateReparsePoint
0x180225ccb  test    eax, eax
0x180225ccd  jz      short loc_180225CD9
0x180225ccf  cmp     dword ptr [rsp+350h+cchDest], esi
0x180225cd3  jnz     loc_180225D5C
0x180225cd9  and     ebx, r13d
0x180225cdc  mov     dword ptr [rsp+350h+cchDest], esi
0x180225ce0  test    bl, bl
0x180225ce2  jnz     short loc_180225CFF
0x180225ce4  lea     rdx, [rsp+350h+cchDest]
0x180225ce9  mov     rcx, r14; lpFileName
0x180225cec  call    GetReparseTag
0x180225cf1  test    eax, eax
0x180225cf3  jz      short loc_180225D15
0x180225cf5  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x180225cfd  jz      short loc_180225D5C
0x180225cff  xor     ecx, ecx; dwErrCode
0x180225d01  call    cs:__imp_SetLastError
0x180225d08  nop     dword ptr [rax+rax+00h]
0x180225d0d  mov     eax, r13d
0x180225d10  jmp     loc_180226278
0x180225d15  call    cs:__imp_GetLastError
0x180225d1c  nop     dword ptr [rax+rax+00h]
0x180225d21  lea     rdx, [rsp+350h+pszDest]
0x180225d26  mov     rcx, r14
0x180225d29  mov     ebx, eax
0x180225d2b  call    ReparsePointExists
0x180225d30  test    eax, eax
0x180225d32  jz      short loc_180225D5C
0x180225d34  cmp     dword ptr [rsp+350h+pszDest], esi
0x180225d38  jz      short loc_180225D5C
0x180225d3a  mov     r9d, ebx
0x180225d3d  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x180225d44  mov     edx, 2000000h
0x180225d49  lea     rcx, g_WdsLibLog
0x180225d50  call    LibLog
0x180225d55  mov     ecx, ebx
0x180225d57  jmp     loc_18022626A
0x180225d5c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180225d60  mov     [rsp+350h+pszDest], rsi
0x180225d65  mov     rdi, r12
0x180225d68  mov     [rsp+350h+cchDest], rsi
0x180225d6d  mov     rbx, rsi
0x180225d70  mov     r15d, esi
0x180225d73  inc     rdi
0x180225d76  cmp     [r14+rdi*2], si
0x180225d7b  jnz     short loc_180225D73
0x180225d7d  mov     edx, 5Ch ; '\'
0x180225d82  test    edi, edi
0x180225d84  jz      short loc_180225D92
0x180225d86  lea     eax, [rdi-1]
0x180225d89  cmp     dx, [r14+rax*2]
0x180225d8e  cmovnz  r15d, r13d
0x180225d92  mov     rcx, gs:60h
0x180225d9b  lea     eax, [r15+2]
0x180225d9f  add     eax, edi
0x180225da1  mov     edx, 8; Flags
0x180225da6  mov     r13d, eax
0x180225da9  mov     rcx, [rcx+30h]; HeapHandle
0x180225dad  lea     r8, ds:0[rax*2]; Size
0x180225db5  call    cs:__imp_RtlAllocateHeap
0x180225dbc  nop     dword ptr [rax+rax+00h]
0x180225dc1  mov     rsi, rax
0x180225dc4  test    rax, rax
0x180225dc7  jnz     short loc_180225DE1
0x180225dc9  mov     rax, gs:30h
0x180225dd2  xor     r15d, r15d
0x180225dd5  mov     dword ptr [rax+68h], 8
0x180225ddc  jmp     loc_1802261E1
0x180225de1  lea     rax, [rsp+350h+cchDest]
0x180225de6  mov     r9d, edi; cchToCopy
0x180225de9  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x180225dee  mov     r8, r14; pszSrc
0x180225df1  lea     rax, [rsp+350h+pszDest]
0x180225df6  mov     rdx, r13; cchDest
0x180225df9  mov     rcx, rsi; pszDest
0x180225dfc  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x180225e01  call    StringCchCopyNExW
0x180225e06  mov     edi, eax
0x180225e08  test    eax, eax
0x180225e0a  js      loc_1802261B1
0x180225e10  test    r15d, r15d
0x180225e13  jz      short loc_180225E53
0x180225e15  mov     rdx, [rsp+350h+cchDest]; cchDest
0x180225e1a  lea     rax, [rsp+350h+cchDest]
0x180225e1f  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180225e24  lea     r8, pszSrc; "\\"
0x180225e2b  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x180225e30  mov     r9d, 1; cchToCopy
0x180225e36  lea     rax, [rsp+350h+pszDest]
0x180225e3b  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x180225e40  call    StringCchCopyNExW
0x180225e45  xor     r15d, r15d
0x180225e48  mov     edi, eax
0x180225e4a  test    eax, eax
0x180225e4c  jns     short loc_180225E56
0x180225e4e  jmp     loc_1802261B4
0x180225e53  xor     r15d, r15d
0x180225e56  mov     rdx, [rsp+350h+cchDest]; cchDest
0x180225e5b  lea     r8, asc_1802D0F50; "*"
0x180225e62  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180225e67  mov     r9d, 1; cchToCopy
0x180225e6d  call    StringCchCopyNW
0x180225e72  mov     edi, eax
0x180225e74  test    eax, eax
0x180225e76  js      loc_1802261B4
0x180225e7c  mov     rax, gs:30h
0x180225e85  xor     edx, edx
0x180225e87  mov     rcx, rsi; wchar_t *
0x180225e8a  mov     [rax+68h], r15d
0x180225e8e  call    PrepareUnicodePathEx
0x180225e93  mov     rbx, rax
0x180225e96  test    rax, rax
0x180225e99  jz      loc_1802261E4
0x180225e9f  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180225ea3  mov     rcx, rax; lpFileName
0x180225ea6  mov     r13d, r15d
0x180225ea9  call    cs:__imp_FindFirstFileW
0x180225eb0  nop     dword ptr [rax+rax+00h]
0x180225eb5  mov     [rsp+350h+cchDest], rax
0x180225eba  cmp     rax, r12
0x180225ebd  jz      loc_18022614E
0x180225ec3  xor     edx, edx; Val
0x180225ec5  lea     rcx, [rsp+350h+var_2F0]; void *
0x180225eca  lea     r8d, [rdx+40h]; Size
0x180225ece  call    memset_0
0x180225ed3  cmp     r15w, [r14]
0x180225ed7  jz      loc_180226034
0x180225edd  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x180225ee0  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x180225ee4  mov     [rsp+350h+var_2F0], eax
0x180225ee8  xorps   xmm0, xmm0
0x180225eeb  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x180225eef  mov     rcx, r14; pszSrc
0x180225ef2  mov     [rsp+350h+var_2EC], rax
0x180225ef7  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x180225efb  mov     [rsp+350h+var_2E4], rax
0x180225f00  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180225f04  mov     [rsp+350h+var_2DC], rax
0x180225f09  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x180225f0c  mov     [rbp+250h+var_2D0], eax
0x180225f0f  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x180225f12  mov     [rbp+250h+var_2CC], eax
0x180225f15  mov     [rsp+350h+var_2D4], r15d
0x180225f1a  mov     [rbp+250h+lpMem], r15
0x180225f1e  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x180225f23  call    BuildPath
0x180225f28  mov     [rbp+250h+lpMem], rax
0x180225f2c  test    rax, rax
0x180225f2f  jz      short loc_180225F70
0x180225f31  mov     edx, 5Ch ; '\'; Ch
0x180225f36  mov     rcx, rax; Str
0x180225f39  call    cs:__imp_wcsrchr
0x180225f40  nop     dword ptr [rax+rax+00h]
0x180225f45  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x180225f49  test    rax, rax
0x180225f4c  jz      short loc_180225F54
0x180225f4e  add     rax, 2
0x180225f52  jmp     short loc_180225F57
0x180225f54  mov     rax, rcx
0x180225f57  mov     [rbp+250h+lpString2], rax
0x180225f5b  call    FormFullPathName
0x180225f60  mov     [rbp+250h+lpString2+8], rax
0x180225f64  test    rax, rax
0x180225f67  jz      short loc_180225F70
0x180225f69  mov     edi, 1
0x180225f6e  jmp     short loc_180225F7D
0x180225f70  lea     rcx, [rsp+350h+var_2F0]; void *
0x180225f75  mov     edi, r15d
0x180225f78  call    FreeWdslibFindData
0x180225f7d  cmp     edi, 1
0x180225f80  jnz     loc_180226048
0x180225f86  test    byte ptr [rsp+350h+var_2F0], 10h
0x180225f8b  jz      loc_180226019
0x180225f91  mov     r15, [rbp+250h+var_2B0]
0x180225f95  test    r15, r15
0x180225f98  jz      loc_180226048
0x180225f9e  mov     rax, [rbp+250h+lpString2]
0x180225fa2  lea     r8, S; "."
0x180225fa9  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180225fae  mov     r9d, r12d; cchCount1
0x180225fb1  mov     edx, edi; dwCmpFlags
0x180225fb3  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180225fb8  mov     ecx, 409h; Locale
0x180225fbd  call    cs:__imp_CompareStringW
0x180225fc4  nop     dword ptr [rax+rax+00h]
0x180225fc9  cmp     eax, 2
0x180225fcc  jz      short loc_180226048
0x180225fce  mov     rax, [rbp+250h+lpString2]
0x180225fd2  lea     r8, asc_1802D0F48; ".."
0x180225fd9  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180225fde  mov     r9d, r12d; cchCount1
0x180225fe1  mov     edx, edi; dwCmpFlags
0x180225fe3  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180225fe8  mov     ecx, 409h; Locale
0x180225fed  call    cs:__imp_CompareStringW
0x180225ff4  nop     dword ptr [rax+rax+00h]
0x180225ff9  cmp     eax, 2
0x180225ffc  jz      short loc_180226048
0x180225ffe  mov     r8, [rsp+350h+var_2F8]
0x180226003  lea     rcx, [rsp+350h+var_2F0]
0x180226008  mov     rdx, [rsp+350h+var_300]
0x18022600d  mov     rax, r15
0x180226010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180226015  mov     edi, eax
0x180226017  jmp     short loc_180226048
0x180226019  mov     rax, [rsp+350h+var_300]
0x18022601e  test    rax, rax
0x180226021  jz      short loc_180226048
0x180226023  mov     rdx, [rsp+350h+var_2F8]
0x180226028  lea     rcx, [rsp+350h+var_2F0]
0x18022602d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180226032  jmp     short loc_180226015
0x180226034  mov     ecx, 57h ; 'W'; dwErrCode
0x180226039  call    cs:__imp_SetLastError
0x180226040  nop     dword ptr [rax+rax+00h]
0x180226045  mov     edi, r15d
0x180226048  mov     r15, [rbp+250h+lpMem]
0x18022604c  test    r15, r15
0x18022604f  jz      short loc_18022607D
0x180226051  call    cs:__imp_GetProcessHeap
0x180226058  nop     dword ptr [rax+rax+00h]
0x18022605d  mov     r8, r15; lpMem
0x180226060  xor     edx, edx; dwFlags
0x180226062  mov     rcx, rax; hHeap
0x180226065  call    cs:__imp_HeapFree
0x18022606c  nop     dword ptr [rax+rax+00h]
0x180226071  test    eax, eax
0x180226073  jz      short loc_18022607D
0x180226075  mov     [rbp+250h+lpMem], 0
0x18022607d  mov     r15, [rbp+250h+lpString2+8]
0x180226081  test    r15, r15
0x180226084  jz      short loc_1802260A6
0x180226086  call    cs:__imp_GetProcessHeap
0x18022608d  nop     dword ptr [rax+rax+00h]
0x180226092  mov     r8, r15; lpMem
0x180226095  xor     edx, edx; dwFlags
0x180226097  mov     rcx, rax; hHeap
0x18022609a  call    cs:__imp_HeapFree
0x1802260a1  nop     dword ptr [rax+rax+00h]
0x1802260a6  xor     edx, edx; Val
0x1802260a8  lea     rcx, [rsp+350h+var_2F0]; void *
0x1802260ad  lea     r8d, [rdx+40h]; Size
0x1802260b1  call    memset_0
0x1802260b6  cmp     edi, 1
0x1802260b9  jnz     short loc_18022610B
0x1802260bb  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x1802260c0  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1802260c4  call    cs:__imp_FindNextFileW
0x1802260cb  nop     dword ptr [rax+rax+00h]
0x1802260d0  lea     r15d, [rdi-1]
0x1802260d4  cmp     eax, edi
0x1802260d6  jz      loc_180225ED3
0x1802260dc  call    cs:__imp_GetLastError
0x1802260e3  nop     dword ptr [rax+rax+00h]
0x1802260e8  cmp     eax, 12h
0x1802260eb  jnz     short loc_1802260F6
0x1802260ed  mov     edi, r15d
0x1802260f0  lea     r13d, [r15+1]
  ... truncated ...
```
