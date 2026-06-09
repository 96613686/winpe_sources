# EnumeratePathEx

- ea: `0x18002dbac`
- end: `0x18002e180`
- name: `EnumeratePathEx`
- size: `1492`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180010d7c`
- `0x18002dae0`
- `0x18002db30`

## callees

- `0x180002ee7`
- `0x18002d79c`
- `0x18002d974`
- `0x18002da5c`
- `0x18002dbac`
- `0x18002e1c8`
- `0x18002e2c4`
- `0x18002e410`
- `0x18002e4a0`
- `0x18002e520`
- `0x18002eed8`
- `0x18002f238`
- `0x1800322d2`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e155`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dc85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002df8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0ed`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002e05c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002e05c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002de1b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002de1b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002dffb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002dffb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e11c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e135`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dfc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e11c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e12a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e143`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dfd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e12a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e143`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002df1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002df48`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002df1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002df48`
- `ntdll!RtlFreeHeap` at `0x18002e0d5`
- `ntdll!RtlFreeHeap` at `0x18002e0d5`
- `ntdll!RtlAllocateHeap` at `0x18002dd2d`
- `ntdll!RtlAllocateHeap` at `0x18002dd2d`

## string_xrefs

- `0x18002dcb5`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x18002e027`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18002e036`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x18002e0f6`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18002e070`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x18002e0a1`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

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
      && ((v22 = wcsrchr_0((const wchar_t *)v21, 0x5Cu)) == 0 ? (v23 = (const WCHAR *)lpMem) : (v23 = v22 + 1),
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
0x18002dbac  push    rbp
0x18002dbae  push    rbx
0x18002dbaf  push    rsi
0x18002dbb0  push    rdi
0x18002dbb1  push    r12
0x18002dbb3  push    r13
0x18002dbb5  push    r14
0x18002dbb7  push    r15
0x18002dbb9  lea     rbp, [rsp-218h]
0x18002dbc1  sub     rsp, 318h
0x18002dbc8  mov     rax, cs:__security_cookie
0x18002dbcf  xor     rax, rsp
0x18002dbd2  mov     [rbp+250h+var_50], rax
0x18002dbd9  mov     [rsp+350h+var_300], r8
0x18002dbde  mov     r14, rcx
0x18002dbe1  mov     [rbp+250h+var_2B0], rdx
0x18002dbe5  lea     rcx, [rbp+250h+FindFileData]; void *
0x18002dbe9  xor     edx, edx; Val
0x18002dbeb  mov     [rsp+350h+var_2F8], r9
0x18002dbf0  mov     r8d, 250h; Size
0x18002dbf6  call    memset_0
0x18002dbfb  xor     esi, esi
0x18002dbfd  mov     dword ptr [rsp+350h+pszDest], esi
0x18002dc01  test    r14, r14
0x18002dc04  jz      loc_18002E150
0x18002dc0a  cmp     si, [r14]
0x18002dc0e  jz      loc_18002E150
0x18002dc14  lea     rdx, [rsp+350h+pszDest]
0x18002dc19  mov     rcx, r14
0x18002dc1c  call    ReparsePointExists
0x18002dc21  lea     r13d, [rsi+1]
0x18002dc25  test    eax, eax
0x18002dc27  jz      loc_18002DCD4
0x18002dc2d  cmp     dword ptr [rsp+350h+pszDest], esi
0x18002dc31  jz      loc_18002DCD4
0x18002dc37  mov     ebx, [rbp+250h+arg_20]
0x18002dc3d  mov     dword ptr [rsp+350h+cchDest], esi
0x18002dc41  test    bl, 2
0x18002dc44  jnz     short loc_18002DC83
0x18002dc46  lea     rdx, [rsp+350h+cchDest]
0x18002dc4b  mov     rcx, r14
0x18002dc4e  call    ShouldEnumerateReparsePoint
0x18002dc53  test    eax, eax
0x18002dc55  jz      short loc_18002DC5D
0x18002dc57  cmp     dword ptr [rsp+350h+cchDest], esi
0x18002dc5b  jnz     short loc_18002DCD4
0x18002dc5d  and     ebx, r13d
0x18002dc60  mov     dword ptr [rsp+350h+cchDest], esi
0x18002dc64  test    bl, bl
0x18002dc66  jnz     short loc_18002DC83
0x18002dc68  lea     rdx, [rsp+350h+cchDest]
0x18002dc6d  mov     rcx, r14; lpFileName
0x18002dc70  call    GetReparseTag
0x18002dc75  test    eax, eax
0x18002dc77  jz      short loc_18002DC93
0x18002dc79  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x18002dc81  jz      short loc_18002DCD4
0x18002dc83  xor     ecx, ecx; dwErrCode
0x18002dc85  call    cs:__imp_SetLastError
0x18002dc8b  mov     eax, r13d
0x18002dc8e  jmp     loc_18002E15D
0x18002dc93  call    cs:__imp_GetLastError
0x18002dc99  lea     rdx, [rsp+350h+pszDest]
0x18002dc9e  mov     rcx, r14
0x18002dca1  mov     ebx, eax
0x18002dca3  call    ReparsePointExists
0x18002dca8  test    eax, eax
0x18002dcaa  jz      short loc_18002DCD4
0x18002dcac  cmp     dword ptr [rsp+350h+pszDest], esi
0x18002dcb0  jz      short loc_18002DCD4
0x18002dcb2  mov     r9d, ebx
0x18002dcb5  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x18002dcbc  mov     edx, 2000000h
0x18002dcc1  lea     rcx, g_WdsLibLog
0x18002dcc8  call    LibLog
0x18002dccd  mov     ecx, ebx
0x18002dccf  jmp     loc_18002E155
0x18002dcd4  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002dcd8  mov     [rsp+350h+pszDest], rsi
0x18002dcdd  mov     rdi, r12
0x18002dce0  mov     [rsp+350h+cchDest], rsi
0x18002dce5  mov     rbx, rsi
0x18002dce8  mov     r15d, esi
0x18002dceb  inc     rdi
0x18002dcee  cmp     [r14+rdi*2], si
0x18002dcf3  jnz     short loc_18002DCEB
0x18002dcf5  mov     edx, 5Ch ; '\'
0x18002dcfa  test    edi, edi
0x18002dcfc  jz      short loc_18002DD0A
0x18002dcfe  lea     eax, [rdi-1]
0x18002dd01  cmp     dx, [r14+rax*2]
0x18002dd06  cmovnz  r15d, r13d
0x18002dd0a  mov     rcx, gs:60h
0x18002dd13  lea     eax, [r15+2]
0x18002dd17  add     eax, edi
0x18002dd19  mov     edx, 8; Flags
0x18002dd1e  mov     r13d, eax
0x18002dd21  mov     rcx, [rcx+30h]; HeapHandle
0x18002dd25  lea     r8, ds:0[rax*2]; Size
0x18002dd2d  call    cs:__imp_RtlAllocateHeap
0x18002dd33  mov     rsi, rax
0x18002dd36  test    rax, rax
0x18002dd39  jnz     short loc_18002DD53
0x18002dd3b  mov     rax, gs:30h
0x18002dd44  xor     r15d, r15d
0x18002dd47  mov     dword ptr [rax+68h], 8
0x18002dd4e  jmp     loc_18002E0EA
0x18002dd53  lea     rax, [rsp+350h+cchDest]
0x18002dd58  mov     r9d, edi; cchToCopy
0x18002dd5b  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18002dd60  mov     r8, r14; pszSrc
0x18002dd63  lea     rax, [rsp+350h+pszDest]
0x18002dd68  mov     rdx, r13; cchDest
0x18002dd6b  mov     rcx, rsi; pszDest
0x18002dd6e  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18002dd73  call    StringCchCopyNExW
0x18002dd78  mov     edi, eax
0x18002dd7a  test    eax, eax
0x18002dd7c  js      loc_18002E0C0
0x18002dd82  test    r15d, r15d
0x18002dd85  jz      short loc_18002DDC5
0x18002dd87  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18002dd8c  lea     rax, [rsp+350h+cchDest]
0x18002dd91  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18002dd96  lea     r8, pszSrc; "\\"
0x18002dd9d  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18002dda2  mov     r9d, 1; cchToCopy
0x18002dda8  lea     rax, [rsp+350h+pszDest]
0x18002ddad  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x18002ddb2  call    StringCchCopyNExW
0x18002ddb7  xor     r15d, r15d
0x18002ddba  mov     edi, eax
0x18002ddbc  test    eax, eax
0x18002ddbe  jns     short loc_18002DDC8
0x18002ddc0  jmp     loc_18002E0C3
0x18002ddc5  xor     r15d, r15d
0x18002ddc8  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18002ddcd  lea     r8, asc_18003D8D4; "*"
0x18002ddd4  mov     rcx, [rsp+350h+pszDest]; pszDest
0x18002ddd9  mov     r9d, 1; cchToCopy
0x18002dddf  call    StringCchCopyNW
0x18002dde4  mov     edi, eax
0x18002dde6  test    eax, eax
0x18002dde8  js      loc_18002E0C3
0x18002ddee  mov     rax, gs:30h
0x18002ddf7  xor     edx, edx
0x18002ddf9  mov     rcx, rsi; unsigned __int16 *
0x18002ddfc  mov     [rax+68h], r15d
0x18002de00  call    PrepareUnicodePathEx
0x18002de05  mov     rbx, rax
0x18002de08  test    rax, rax
0x18002de0b  jz      loc_18002E0ED
0x18002de11  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18002de15  mov     rcx, rax; lpFileName
0x18002de18  mov     r13d, r15d
0x18002de1b  call    cs:__imp_FindFirstFileW
0x18002de21  mov     [rsp+350h+cchDest], rax
0x18002de26  cmp     rax, r12
0x18002de29  jz      loc_18002E067
0x18002de2f  xor     edx, edx; Val
0x18002de31  lea     rcx, [rsp+350h+var_2F0]; void *
0x18002de36  lea     r8d, [rdx+40h]; Size
0x18002de3a  call    memset_0
0x18002de3f  cmp     r15w, [r14]
0x18002de43  jz      loc_18002DF89
0x18002de49  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x18002de4c  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18002de50  mov     [rsp+350h+var_2F0], eax
0x18002de54  xorps   xmm0, xmm0
0x18002de57  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x18002de5b  mov     rcx, r14; pszSrc
0x18002de5e  mov     [rsp+350h+var_2EC], rax
0x18002de63  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x18002de67  mov     [rsp+350h+var_2E4], rax
0x18002de6c  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18002de70  mov     [rsp+350h+var_2DC], rax
0x18002de75  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x18002de78  mov     [rbp+250h+var_2D0], eax
0x18002de7b  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x18002de7e  mov     [rbp+250h+var_2CC], eax
0x18002de81  mov     [rsp+350h+var_2D4], r15d
0x18002de86  mov     [rbp+250h+lpMem], r15
0x18002de8a  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x18002de8f  call    BuildPath
0x18002de94  mov     [rbp+250h+lpMem], rax
0x18002de98  test    rax, rax
0x18002de9b  jz      short loc_18002DED5
0x18002de9d  mov     edx, 5Ch ; '\'; Ch
0x18002dea2  mov     rcx, rax; Str
0x18002dea5  call    wcsrchr_0
0x18002deaa  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x18002deae  test    rax, rax
0x18002deb1  jz      short loc_18002DEB9
0x18002deb3  add     rax, 2
0x18002deb7  jmp     short loc_18002DEBC
0x18002deb9  mov     rax, rcx
0x18002debc  mov     [rbp+250h+lpString2], rax
0x18002dec0  call    FormFullPathName
0x18002dec5  mov     [rbp+250h+lpString2+8], rax
0x18002dec9  test    rax, rax
0x18002decc  jz      short loc_18002DED5
0x18002dece  mov     edi, 1
0x18002ded3  jmp     short loc_18002DEE2
0x18002ded5  lea     rcx, [rsp+350h+var_2F0]; void *
0x18002deda  mov     edi, r15d
0x18002dedd  call    FreeWdslibFindData
0x18002dee2  cmp     edi, 1
0x18002dee5  jnz     loc_18002DF97
0x18002deeb  test    byte ptr [rsp+350h+var_2F0], 10h
0x18002def0  jz      short loc_18002DF6E
0x18002def2  mov     r15, [rbp+250h+var_2B0]
0x18002def6  test    r15, r15
0x18002def9  jz      loc_18002DF97
0x18002deff  mov     rax, [rbp+250h+lpString2]
0x18002df03  lea     r8, asc_18003D8D8; "."
0x18002df0a  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18002df0f  mov     r9d, r12d; cchCount1
0x18002df12  mov     edx, edi; dwCmpFlags
0x18002df14  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18002df19  mov     ecx, 409h; Locale
0x18002df1e  call    cs:__imp_CompareStringW
0x18002df24  cmp     eax, 2
0x18002df27  jz      short loc_18002DF97
0x18002df29  mov     rax, [rbp+250h+lpString2]
0x18002df2d  lea     r8, asc_18003D8DC; ".."
0x18002df34  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x18002df39  mov     r9d, r12d; cchCount1
0x18002df3c  mov     edx, edi; dwCmpFlags
0x18002df3e  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x18002df43  mov     ecx, 409h; Locale
0x18002df48  call    cs:__imp_CompareStringW
0x18002df4e  cmp     eax, 2
0x18002df51  jz      short loc_18002DF97
0x18002df53  mov     r8, [rsp+350h+var_2F8]
0x18002df58  lea     rcx, [rsp+350h+var_2F0]
0x18002df5d  mov     rdx, [rsp+350h+var_300]
0x18002df62  mov     rax, r15
0x18002df65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df6a  mov     edi, eax
0x18002df6c  jmp     short loc_18002DF97
0x18002df6e  mov     rax, [rsp+350h+var_300]
0x18002df73  test    rax, rax
0x18002df76  jz      short loc_18002DF97
0x18002df78  mov     rdx, [rsp+350h+var_2F8]
0x18002df7d  lea     rcx, [rsp+350h+var_2F0]
0x18002df82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df87  jmp     short loc_18002DF6A
0x18002df89  mov     ecx, 57h ; 'W'; dwErrCode
0x18002df8e  call    cs:__imp_SetLastError
0x18002df94  mov     edi, r15d
0x18002df97  mov     r15, [rbp+250h+lpMem]
0x18002df9b  test    r15, r15
0x18002df9e  jz      short loc_18002DFC0
0x18002dfa0  call    cs:__imp_GetProcessHeap
0x18002dfa6  mov     r8, r15; lpMem
0x18002dfa9  xor     edx, edx; dwFlags
0x18002dfab  mov     rcx, rax; hHeap
0x18002dfae  call    cs:__imp_HeapFree
0x18002dfb4  test    eax, eax
0x18002dfb6  jz      short loc_18002DFC0
0x18002dfb8  mov     [rbp+250h+lpMem], 0
0x18002dfc0  mov     r15, [rbp+250h+lpString2+8]
0x18002dfc4  test    r15, r15
0x18002dfc7  jz      short loc_18002DFDD
0x18002dfc9  call    cs:__imp_GetProcessHeap
0x18002dfcf  mov     r8, r15; lpMem
0x18002dfd2  xor     edx, edx; dwFlags
0x18002dfd4  mov     rcx, rax; hHeap
0x18002dfd7  call    cs:__imp_HeapFree
0x18002dfdd  xor     edx, edx; Val
0x18002dfdf  lea     rcx, [rsp+350h+var_2F0]; void *
0x18002dfe4  lea     r8d, [rdx+40h]; Size
0x18002dfe8  call    memset_0
0x18002dfed  cmp     edi, 1
0x18002dff0  jnz     short loc_18002E030
0x18002dff2  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18002dff7  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x18002dffb  call    cs:__imp_FindNextFileW
0x18002e001  lea     r15d, [rdi-1]
0x18002e005  cmp     eax, edi
0x18002e007  jz      loc_18002DE3F
0x18002e00d  call    cs:__imp_GetLastError
0x18002e013  cmp     eax, 12h
0x18002e016  jnz     short loc_18002E021
0x18002e018  mov     edi, r15d
0x18002e01b  lea     r13d, [r15+1]
0x18002e01f  jmp     short loc_18002E057
0x18002e021  call    cs:__imp_GetLastError
0x18002e027  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x18002e02e  jmp     short loc_18002E03D
0x18002e030  call    cs:__imp_GetLastError
0x18002e036  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x18002e03d  mov     r9, rbx
0x18002e040  mov     dword ptr [rsp+350h+ppszDestEnd], eax
0x18002e044  mov     edx, 2000000h
0x18002e049  lea     rcx, g_WdsLibLog
0x18002e050  mov     edi, eax
0x18002e052  call    LibLog
0x18002e057  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x18002e05c  call    cs:__imp_FindClose
  ... truncated ...
```
