# BfspCopyBootFileDirectory

- ea: `0x18004a678`
- end: `0x18004ac98`
- name: `BfspCopyBootFileDirectory`
- size: `1568`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, const unsigned __int16 *, int, int, int, int)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180049234`
- `0x18004a678`
- `0x18004b980`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18001bd50`
- `0x18001bddc`
- `0x18001be20`
- `0x1800466c0`
- `0x180046adc`
- `0x1800472a4`
- `0x18004a678`
- `0x18004aca0`
- `0x18004b5d8`
- `0x18004bf48`
- `0x18004c0c4`
- `0x18004c6bc`
- `0x18004cdd4`
- `0x18004d3e0`
- `0x180052c8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ab88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ab9d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ab88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ab9d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004aa71`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004aa71`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004ac59`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004ac59`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004a883`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004a883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004aa62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a6ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a73a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a78c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a6ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a73a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004a78c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aa54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a6ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a748`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a79a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a6ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a748`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004a79a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004aa7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aa15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aaeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac72`

## string_xrefs

- `0x18004ac7b`: `Error copying %s to %s. Last Error = %#x`
- `0x18004a8ab`: `Error creating %s path! Last Error = %#x`
- `0x18004abc0`: `Source, %s, is older than destination, %s, will not update`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall BfspCopyBootFileDirectory(
        __int64 a1,
        __int64 a2,
        WCHAR *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned __int64 v13; // r12
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int Path; // edi
  __int64 v18; // rax
  unsigned __int64 v19; // rdi
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  unsigned __int16 *v22; // r13
  __int64 v23; // rax
  unsigned __int64 v24; // r13
  SIZE_T v25; // rbx
  HANDLE v26; // rax
  unsigned __int16 *v27; // r14
  __int64 v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rax
  WCHAR *v31; // rdi
  __int64 v32; // rbx
  const unsigned __int16 *v33; // rcx
  DWORD v34; // eax
  unsigned __int16 *v35; // rdi
  int v36; // ebx
  __int64 v37; // r11
  __int16 v38; // r11
  HANDLE v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  wchar_t *v43; // rsi
  size_t v44; // rdx
  unsigned __int64 v45; // rcx
  WCHAR *v46; // rbx
  unsigned int ThreadPagePriority; // ebx
  __int64 v48; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *lpFileName; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *pszDest; // [rsp+50h] [rbp-B0h]
  __int64 hFindFile; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *lpMem; // [rsp+68h] [rbp-98h]
  int v56; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v57; // [rsp+78h] [rbp-88h]
  unsigned __int16 *i; // [rsp+80h] [rbp-80h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(a1 + 2 * v12) );
  v13 = v12 + 262;
  v14 = 2 * (v12 + 262);
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  lpFileName = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v14);
  if ( !lpFileName )
  {
    Path = 0;
    goto LABEL_55;
  }
  hFindFile = -1;
  if ( a2 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(a2 + 2 * v18) );
    v19 = v18 + 262;
    v20 = 2 * (v18 + 262);
    v21 = GetProcessHeap();
    lpMem = (unsigned __int16 *)HeapAlloc(v21, 8u, v20);
    if ( !lpMem )
    {
      v22 = lpFileName;
      Path = 0;
      goto LABEL_50;
    }
  }
  else
  {
    lpMem = 0;
    v19 = 0;
  }
  v23 = -1;
  do
    ++v23;
  while ( a3[v23] );
  v24 = v23 + 262;
  v25 = 2 * (v23 + 262);
  v26 = GetProcessHeap();
  v27 = (unsigned __int16 *)HeapAlloc(v26, 8u, v25);
  if ( !v27 )
  {
    v22 = lpFileName;
    Path = 0;
    goto LABEL_49;
  }
  pszDest = 0;
  StringCchPrintfW(lpFileName, v13, L"%s\\", a1);
  v28 = -1;
  do
    ++v28;
  while ( lpFileName[v28] );
  v29 = a2;
  v57 = &lpFileName[v28];
  if ( a2 )
  {
    StringCchPrintfW(lpMem, v19, L"%s\\", a2);
    v30 = -1;
    do
      ++v30;
    while ( lpMem[v30] );
    pszDest = &lpMem[v30];
  }
  v31 = a3;
  StringCchPrintfW(v27, v24, L"%s\\", a3);
  v32 = -1;
  do
    ++v32;
  while ( v27[v32] );
  v33 = L"*";
  if ( a4 )
    v33 = a4;
  v56 = (int)v33;
  StringCchCopyW(v57, 0x105u, v33);
  hFindFile = (__int64)FindFirstFileW(lpFileName, &FindFileData);
  if ( hFindFile != -1 )
  {
    Path = CreatePath(a3);
    if ( !Path )
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"Error creating %s path! Last Error = %#x", v27, LastError);
      v22 = lpFileName;
      goto LABEL_48;
    }
    v31 = a3;
  }
  if ( a6 && (Path = BfspSetFileDirectorySecurityDescriptor(v31)) == 0 || (Path = BfspSetAttributes(a3)) == 0 )
  {
    v34 = GetLastError();
    v22 = lpFileName;
    goto LABEL_47;
  }
  v22 = lpFileName;
  v35 = &v27[v32];
  v36 = a7;
  for ( i = v35; ; v35 = i )
  {
    StringCchCopyW(v57, 0x105u, FindFileData.cFileName);
    StringCchCopyW(v35, 0x105u, FindFileData.cFileName);
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    v38 = 0;
    if ( v29 )
      StringCchCopyW(pszDest, 0x105u, FindFileData.cFileName);
    if ( a8
      && (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2] != v38)) )
    {
      Path = BfspCopyBootFileDirectory((_DWORD)lpFileName, (_DWORD)lpMem, (_DWORD)v27, v56, a5, a6, v36, a8);
      if ( !Path )
        goto LABEL_43;
    }
LABEL_85:
    Path = FindNextFileW((HANDLE)hFindFile, &FindFileData);
    if ( !Path )
      goto LABEL_43;
  }
  if ( v29 )
    *pszDest = 0;
  if ( a7 && !(unsigned int)BfspIsMuiFile(v37) )
  {
LABEL_84:
    v36 = a7;
    goto LABEL_85;
  }
  if ( a6 )
  {
    Path = BfspSetFileDirectorySecurityDescriptor(v27);
    if ( !Path && GetLastError() != 2 )
      goto LABEL_43;
  }
  v43 = lpFileName;
  if ( a2 )
  {
    v44 = 0;
    v45 = -1;
    do
      ++v45;
    while ( FindFileData.cFileName[v45] );
    if ( v45 )
    {
      while ( 1 )
      {
        v46 = &FindFileData.cFileName[(unsigned int)v44];
        if ( *v46 == 46 )
          break;
        v44 = (unsigned int)(v44 + 1);
        if ( (unsigned int)v44 >= v45 )
          goto LABEL_72;
      }
      StringCchCatNW(pszDest, v44, FindFileData.cFileName, (unsigned int)v44);
      StringCchCatW(pszDest, 0x105u, L"_EX");
      StringCchCatW(pszDest, 0x105u, v46);
    }
LABEL_72:
    if ( (unsigned int)BfspFileExists(lpMem) )
      v43 = lpMem;
  }
  if ( !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"boot.stl")
    || !(unsigned int)_o__wcsicmp(FindFileData.cFileName, L"boot.pnd.stl") )
  {
    goto LABEL_79;
  }
  if ( !(unsigned int)BfspShouldFileBeCopied(v43) )
  {
    BfspLogMessage(3, L"Source, %s, is older than destination, %s, will not update", v43, v27);
    goto LABEL_79;
  }
  ThreadPagePriority = BfspGetThreadPagePriority();
  BfspSetThreadPagePriority(1);
  Path = BfspCopyFile((__int64)v43, v27);
  BfspSetThreadPagePriority(ThreadPagePriority);
  if ( Path )
  {
LABEL_79:
    if ( (unsigned int)BfspFileExists(v27) )
    {
      Path = BfspSetAttributes(v27);
      if ( !Path )
        goto LABEL_43;
      if ( a6 )
      {
        Path = BfspSetFileDirectorySecurityDescriptor(v27);
        if ( !Path )
          goto LABEL_43;
      }
    }
    v29 = a2;
    goto LABEL_84;
  }
  LODWORD(v48) = GetLastError();
  BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v43, v27, v48);
LABEL_43:
  if ( GetLastError() != 18
    || (LODWORD(LastError) = 0, Path = 1, a6) && (Path = BfspSetFileDirectorySecurityDescriptor(a3)) == 0 )
  {
    v34 = GetLastError();
LABEL_47:
    LODWORD(LastError) = v34;
  }
LABEL_48:
  v39 = GetProcessHeap();
  HeapFree(v39, 0, v27);
LABEL_49:
  v11 = hFindFile;
LABEL_50:
  v40 = GetProcessHeap();
  HeapFree(v40, 0, v22);
  if ( lpMem )
  {
    v41 = GetProcessHeap();
    HeapFree(v41, 0, lpMem);
  }
  if ( v11 != -1 )
    FindClose((HANDLE)v11);
  if ( !Path )
LABEL_55:
    SetLastError(LastError);
  return Path;
}

```

## disassembly

```asm
0x18004a678  push    rbp
0x18004a67a  push    rbx
0x18004a67b  push    rsi
0x18004a67c  push    rdi
0x18004a67d  push    r12
0x18004a67f  push    r13
0x18004a681  push    r14
0x18004a683  push    r15
0x18004a685  lea     rbp, [rsp-1F8h]
0x18004a68d  sub     rsp, 2F8h
0x18004a694  mov     rax, cs:__security_cookie
0x18004a69b  xor     rax, rsp
0x18004a69e  mov     [rbp+230h+var_50], rax
0x18004a6a5  mov     r13, r8
0x18004a6a8  mov     [rsp+330h+var_2D8], r8
0x18004a6ad  mov     rdi, rdx
0x18004a6b0  mov     [rsp+330h+var_2E8], rdx
0x18004a6b5  mov     r15, rcx
0x18004a6b8  mov     [rsp+330h+var_2C0], r9
0x18004a6bd  xor     edx, edx; Val
0x18004a6bf  lea     rcx, [rbp+230h+FindFileData]; void *
0x18004a6c3  mov     r8d, 250h; Size
0x18004a6c9  call    memset_0
0x18004a6ce  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004a6d2  mov     rax, r14
0x18004a6d5  xor     ecx, ecx
0x18004a6d7  inc     rax
0x18004a6da  cmp     [r15+rax*2], cx
0x18004a6df  jnz     short loc_18004A6D7
0x18004a6e1  lea     r12, [rax+106h]
0x18004a6e8  lea     rbx, [r12+r12]
0x18004a6ec  call    cs:__imp_GetProcessHeap
0x18004a6f2  mov     esi, 8
0x18004a6f7  mov     r8, rbx; dwBytes
0x18004a6fa  mov     rcx, rax; hHeap
0x18004a6fd  mov     edx, esi; dwFlags
0x18004a6ff  call    cs:__imp_HeapAlloc
0x18004a705  xor     edx, edx
0x18004a707  mov     [rsp+330h+lpFileName], rax
0x18004a70c  test    rax, rax
0x18004a70f  jnz     short loc_18004A718
0x18004a711  mov     edi, edx
0x18004a713  jmp     loc_18004AA7B
0x18004a718  mov     [rsp+330h+hFindFile], r14
0x18004a71d  test    rdi, rdi
0x18004a720  jz      short loc_18004A766
0x18004a722  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a726  inc     rax
0x18004a729  cmp     [rdi+rax*2], dx
0x18004a72d  jnz     short loc_18004A726
0x18004a72f  lea     rdi, [rax+106h]
0x18004a736  lea     rbx, [rdi+rdi]
0x18004a73a  call    cs:__imp_GetProcessHeap
0x18004a740  mov     r8, rbx; dwBytes
0x18004a743  mov     edx, esi; dwFlags
0x18004a745  mov     rcx, rax; hHeap
0x18004a748  call    cs:__imp_HeapAlloc
0x18004a74e  xor     edx, edx
0x18004a750  mov     [rsp+330h+lpMem], rax
0x18004a755  test    rax, rax
0x18004a758  jnz     short loc_18004A76E
0x18004a75a  mov     r13, [rsp+330h+lpFileName]
0x18004a75f  mov     edi, edx
0x18004a761  jmp     loc_18004AA36
0x18004a766  mov     [rsp+330h+lpMem], rdx
0x18004a76b  mov     rdi, rdx
0x18004a76e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a772  inc     rax
0x18004a775  cmp     [r13+rax*2+0], dx
0x18004a77b  jnz     short loc_18004A772
0x18004a77d  lea     r13, [rax+106h]
0x18004a784  lea     rbx, ds:0[r13*2]
0x18004a78c  call    cs:__imp_GetProcessHeap
0x18004a792  mov     r8, rbx; dwBytes
0x18004a795  mov     edx, esi; dwFlags
0x18004a797  mov     rcx, rax; hHeap
0x18004a79a  call    cs:__imp_HeapAlloc
0x18004a7a0  xor     ebx, ebx
0x18004a7a2  mov     r14, rax
0x18004a7a5  test    rax, rax
0x18004a7a8  jnz     short loc_18004A7B6
0x18004a7aa  mov     r13, [rsp+330h+lpFileName]
0x18004a7af  mov     edi, ebx
0x18004a7b1  jmp     loc_18004AA31
0x18004a7b6  mov     rdx, r12; unsigned __int64
0x18004a7b9  mov     [rsp+330h+pszDest], rbx
0x18004a7be  mov     r12, [rsp+330h+lpFileName]
0x18004a7c3  lea     r8, aS_0; "%s\\"
0x18004a7ca  mov     rcx, r12; unsigned __int16 *
0x18004a7cd  mov     r9, r15
0x18004a7d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a7d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a7d9  inc     rax
0x18004a7dc  cmp     [r12+rax*2], bx
0x18004a7e1  jnz     short loc_18004A7D9
0x18004a7e3  mov     rsi, [rsp+330h+var_2E8]
0x18004a7e8  lea     rax, [r12+rax*2]
0x18004a7ec  mov     r15, [rsp+330h+lpMem]
0x18004a7f1  mov     [rsp+330h+var_2B8], rax
0x18004a7f6  test    rsi, rsi
0x18004a7f9  jz      short loc_18004A827
0x18004a7fb  mov     r9, rsi
0x18004a7fe  lea     r8, aS_0; "%s\\"
0x18004a805  mov     rdx, rdi; unsigned __int64
0x18004a808  mov     rcx, r15; unsigned __int16 *
0x18004a80b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a810  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a814  inc     rax
0x18004a817  cmp     [r15+rax*2], bx
0x18004a81c  jnz     short loc_18004A814
0x18004a81e  lea     rax, [r15+rax*2]
0x18004a822  mov     [rsp+330h+pszDest], rax
0x18004a827  mov     rdi, [rsp+330h+var_2D8]
0x18004a82c  lea     r8, aS_0; "%s\\"
0x18004a833  mov     r9, rdi
0x18004a836  mov     rdx, r13; unsigned __int64
0x18004a839  mov     rcx, r14; unsigned __int16 *
0x18004a83c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a841  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004a845  xor     r13d, r13d
0x18004a848  inc     rbx
0x18004a84b  cmp     [r14+rbx*2], r13w
0x18004a850  jnz     short loc_18004A848
0x18004a852  mov     rax, [rsp+330h+var_2C0]
0x18004a857  lea     rcx, asc_1800847B4; "*"
0x18004a85e  test    rax, rax
0x18004a861  mov     edx, 105h; unsigned __int64
0x18004a866  cmovnz  rcx, rax
0x18004a86a  mov     [rsp+330h+var_2C0], rcx
0x18004a86f  mov     r8, rcx; unsigned __int16 *
0x18004a872  mov     rcx, [rsp+330h+var_2B8]; unsigned __int16 *
0x18004a877  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a87c  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18004a880  mov     rcx, r12; lpFileName
0x18004a883  call    cs:__imp_FindFirstFileW
0x18004a889  mov     [rsp+330h+hFindFile], rax
0x18004a88e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a892  jz      short loc_18004A8CC
0x18004a894  mov     rcx, rdi
0x18004a897  call    CreatePath
0x18004a89c  mov     edi, eax
0x18004a89e  test    eax, eax
0x18004a8a0  jnz     short loc_18004A8C7
0x18004a8a2  call    cs:__imp_GetLastError
0x18004a8a8  mov     r8, r14
0x18004a8ab  lea     rdx, aErrorCreatingS; "Error creating %s path! Last Error = %#"...
0x18004a8b2  mov     r9d, eax
0x18004a8b5  lea     ecx, [rdi+4]
0x18004a8b8  mov     esi, eax
0x18004a8ba  call    BfspLogMessage
0x18004a8bf  mov     r13, r12
0x18004a8c2  jmp     loc_18004AA1D
0x18004a8c7  mov     rdi, [rsp+330h+var_2D8]
0x18004a8cc  mov     r12d, [rbp+230h+arg_28]
0x18004a8d3  test    r12d, r12d
0x18004a8d6  jz      short loc_18004A8FF
0x18004a8d8  lea     r8, aOSgSdPACiGaSA0; "O:%sG:%sD:P(A;CI;GA;;;%s)(A;;0x1201bf;;"...
0x18004a8df  xor     edx, edx
0x18004a8e1  mov     rcx, rdi; pObjectName
0x18004a8e4  call    BfspSetFileDirectorySecurityDescriptor
0x18004a8e9  mov     edi, eax
0x18004a8eb  test    eax, eax
0x18004a8ed  jnz     short loc_18004A8FF
0x18004a8ef  call    cs:__imp_GetLastError
0x18004a8f5  mov     r13, [rsp+330h+lpFileName]
0x18004a8fa  jmp     loc_18004AA1B
0x18004a8ff  mov     rcx, [rsp+330h+var_2D8]; lpFileName
0x18004a904  mov     edx, 80h
0x18004a909  call    BfspSetAttributes
0x18004a90e  mov     edi, eax
0x18004a910  test    eax, eax
0x18004a912  jz      short loc_18004A8EF
0x18004a914  mov     r13, [rsp+330h+lpFileName]
0x18004a919  lea     rdi, [r14+rbx*2]
0x18004a91d  mov     ebx, [rbp+230h+arg_30]
0x18004a923  mov     [rbp+230h+var_2B0], rdi
0x18004a927  mov     r11, [rsp+330h+var_2B8]
0x18004a92c  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x18004a930  mov     rcx, r11; unsigned __int16 *
0x18004a933  mov     edx, 105h; unsigned __int64
0x18004a938  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a93d  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x18004a941  mov     edx, 105h; unsigned __int64
0x18004a946  mov     rcx, rdi; unsigned __int16 *
0x18004a949  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a94e  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x18004a952  jz      loc_18004AAA8
0x18004a958  xor     r11d, r11d
0x18004a95b  test    rsi, rsi
0x18004a95e  jz      short loc_18004A973
0x18004a960  mov     rcx, [rsp+330h+pszDest]; unsigned __int16 *
0x18004a965  lea     r8, [rbp+230h+FindFileData.cFileName]; unsigned __int16 *
0x18004a969  mov     edx, 105h; unsigned __int64
0x18004a96e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a973  mov     ecx, [rbp+230h+arg_38]
0x18004a979  test    ecx, ecx
0x18004a97b  jz      loc_18004AC50
0x18004a981  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x18004a986  movzx   eax, [rbp+230h+FindFileData.cFileName+2]
0x18004a98a  jnz     short loc_18004A9AD
0x18004a98c  test    ax, ax
0x18004a98f  jz      loc_18004AC50
0x18004a995  cmp     [rbp+230h+FindFileData.cFileName], 2Eh ; '.'
0x18004a99a  jnz     short loc_18004A9AD
0x18004a99c  cmp     ax, 2Eh ; '.'
0x18004a9a0  jnz     short loc_18004A9AD
0x18004a9a2  cmp     [rbp+230h+FindFileData.cFileName+4], r11w
0x18004a9a7  jz      loc_18004AC50
0x18004a9ad  mov     eax, [rbp+230h+arg_20]
0x18004a9b3  mov     r8, r14
0x18004a9b6  mov     r9, [rsp+330h+var_2C0]
0x18004a9bb  mov     rdx, r15
0x18004a9be  mov     [rsp+330h+var_2F8], ecx
0x18004a9c2  mov     rcx, r13
0x18004a9c5  mov     [rsp+330h+var_300], ebx
0x18004a9c9  mov     [rsp+330h+var_308], r12d
0x18004a9ce  mov     dword ptr [rsp+330h+var_310], eax
0x18004a9d2  call    BfspCopyBootFileDirectory
0x18004a9d7  mov     edi, eax
0x18004a9d9  test    eax, eax
0x18004a9db  jnz     loc_18004AC50
0x18004a9e1  xor     ebx, ebx
0x18004a9e3  call    cs:__imp_GetLastError
0x18004a9e9  cmp     eax, 12h
0x18004a9ec  jnz     short loc_18004AA15
0x18004a9ee  mov     eax, 1
0x18004a9f3  mov     esi, ebx
0x18004a9f5  mov     edi, eax
0x18004a9f7  test    r12d, r12d
0x18004a9fa  jz      short loc_18004AA1D
0x18004a9fc  mov     rcx, [rsp+330h+var_2D8]; pObjectName
0x18004aa01  lea     r8, aOSgSdPACiGaSA0; "O:%sG:%sD:P(A;CI;GA;;;%s)(A;;0x1201bf;;"...
0x18004aa08  mov     edx, eax
0x18004aa0a  call    BfspSetFileDirectorySecurityDescriptor
0x18004aa0f  mov     edi, eax
0x18004aa11  test    eax, eax
0x18004aa13  jnz     short loc_18004AA1D
0x18004aa15  call    cs:__imp_GetLastError
0x18004aa1b  mov     esi, eax
0x18004aa1d  call    cs:__imp_GetProcessHeap
0x18004aa23  mov     r8, r14; lpMem
0x18004aa26  xor     edx, edx; dwFlags
0x18004aa28  mov     rcx, rax; hHeap
0x18004aa2b  call    cs:__imp_HeapFree
0x18004aa31  mov     r14, [rsp+330h+hFindFile]
0x18004aa36  call    cs:__imp_GetProcessHeap
0x18004aa3c  mov     r8, r13; lpMem
0x18004aa3f  xor     edx, edx; dwFlags
0x18004aa41  mov     rcx, rax; hHeap
0x18004aa44  call    cs:__imp_HeapFree
0x18004aa4a  mov     rbx, [rsp+330h+lpMem]
0x18004aa4f  test    rbx, rbx
0x18004aa52  jz      short loc_18004AA68
0x18004aa54  call    cs:__imp_GetProcessHeap
0x18004aa5a  mov     r8, rbx; lpMem
0x18004aa5d  xor     edx, edx; dwFlags
0x18004aa5f  mov     rcx, rax; hHeap
0x18004aa62  call    cs:__imp_HeapFree
0x18004aa68  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18004aa6c  jz      short loc_18004AA77
0x18004aa6e  mov     rcx, r14; hFindFile
0x18004aa71  call    cs:__imp_FindClose
0x18004aa77  test    edi, edi
0x18004aa79  jnz     short loc_18004AA83
0x18004aa7b  mov     ecx, esi; dwErrCode
0x18004aa7d  call    cs:__imp_SetLastError
0x18004aa83  mov     eax, edi
0x18004aa85  mov     rcx, [rbp+230h+var_50]
0x18004aa8c  xor     rcx, rsp; StackCookie
0x18004aa8f  call    __security_check_cookie
0x18004aa94  add     rsp, 2F8h
0x18004aa9b  pop     r15
0x18004aa9d  pop     r14
0x18004aa9f  pop     r13
0x18004aaa1  pop     r12
0x18004aaa3  pop     rdi
0x18004aaa4  pop     rsi
0x18004aaa5  pop     rbx
0x18004aaa6  pop     rbp
0x18004aaa7  retn
0x18004aaa8  xor     ebx, ebx
0x18004aaaa  test    rsi, rsi
0x18004aaad  jz      short loc_18004AAB7
0x18004aaaf  mov     rcx, [rsp+330h+pszDest]
0x18004aab4  mov     [rcx], bx
0x18004aab7  cmp     [rbp+230h+arg_30], ebx
0x18004aabd  jz      short loc_18004AACF
0x18004aabf  mov     rcx, r11
0x18004aac2  call    BfspIsMuiFile
0x18004aac7  test    eax, eax
0x18004aac9  jz      loc_18004AC4A
0x18004aacf  test    r12d, r12d
0x18004aad2  jz      short loc_18004AAFA
0x18004aad4  lea     r8, aOSgSdPAFaSAGrg; "O:%sG:%sD:P(A;;FA;;;%s)(A;;GRGX;;;BA)(A"...
0x18004aadb  xor     edx, edx
0x18004aadd  mov     rcx, r14; pObjectName
0x18004aae0  call    BfspSetFileDirectorySecurityDescriptor
0x18004aae5  mov     edi, eax
0x18004aae7  test    eax, eax
0x18004aae9  jnz     short loc_18004AAFA
  ... truncated ...
```
