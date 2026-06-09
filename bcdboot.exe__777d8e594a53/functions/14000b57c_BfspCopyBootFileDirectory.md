# BfspCopyBootFileDirectory

- ea: `0x14000b57c`
- end: `0x14000bd21`
- name: `BfspCopyBootFileDirectory`
- size: `1957`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, const wchar_t *, int, int, int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140009fd4`
- `0x14000b57c`
- `0x14000cc78`

## callees

- `0x140002b7c`
- `0x140002ec8`
- `0x140003884`
- `0x140003bf8`
- `0x14000b57c`
- `0x14000bd28`
- `0x14000d2b4`
- `0x14000d3c4`
- `0x14000dba4`
- `0x14000e628`
- `0x14000ec18`
- `0x1400116f4`
- `0x1400265fa`
- `0x140026650`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000ba7f`
- `msvcrt!_wcsicmp` at `0x14000ba96`
- `msvcrt!_wcsicmp` at `0x14000bbda`
- `msvcrt!_wcsicmp` at `0x14000bbef`
- `msvcrt!_wcsicmp` at `0x14000ba7f`
- `msvcrt!_wcsicmp` at `0x14000ba96`
- `msvcrt!_wcsicmp` at `0x14000bbda`
- `msvcrt!_wcsicmp` at `0x14000bbef`
- `KERNEL32!SetLastError` at `0x14000b890`
- `KERNEL32!SetLastError` at `0x14000b890`
- `KERNEL32!GetLastError` at `0x14000b7d7`
- `KERNEL32!GetLastError` at `0x14000b826`
- `KERNEL32!GetLastError` at `0x14000bac6`
- `KERNEL32!GetLastError` at `0x14000bcb1`
- `KERNEL32!GetLastError` at `0x14000bcd2`
- `KERNEL32!GetLastError` at `0x14000bd11`
- `KERNEL32!GetLastError` at `0x14000b7d7`
- `KERNEL32!GetLastError` at `0x14000b826`
- `KERNEL32!GetLastError` at `0x14000bac6`
- `KERNEL32!GetLastError` at `0x14000bcb1`
- `KERNEL32!GetLastError` at `0x14000bcd2`
- `KERNEL32!GetLastError` at `0x14000bd11`
- `KERNEL32!HeapFree` at `0x14000b841`
- `KERNEL32!HeapFree` at `0x14000b857`
- `KERNEL32!HeapFree` at `0x14000b875`
- `KERNEL32!HeapFree` at `0x14000b841`
- `KERNEL32!HeapFree` at `0x14000b857`
- `KERNEL32!HeapFree` at `0x14000b875`
- `KERNEL32!HeapAlloc` at `0x14000b5fe`
- `KERNEL32!HeapAlloc` at `0x14000b647`
- `KERNEL32!HeapAlloc` at `0x14000b697`
- `KERNEL32!HeapAlloc` at `0x14000b5fe`
- `KERNEL32!HeapAlloc` at `0x14000b647`
- `KERNEL32!HeapAlloc` at `0x14000b697`
- `KERNEL32!GetProcessHeap` at `0x14000b5eb`
- `KERNEL32!GetProcessHeap` at `0x14000b639`
- `KERNEL32!GetProcessHeap` at `0x14000b689`
- `KERNEL32!GetProcessHeap` at `0x14000b833`
- `KERNEL32!GetProcessHeap` at `0x14000b847`
- `KERNEL32!GetProcessHeap` at `0x14000b867`
- `KERNEL32!GetProcessHeap` at `0x14000b5eb`
- `KERNEL32!GetProcessHeap` at `0x14000b639`
- `KERNEL32!GetProcessHeap` at `0x14000b689`
- `KERNEL32!GetProcessHeap` at `0x14000b833`
- `KERNEL32!GetProcessHeap` at `0x14000b847`
- `KERNEL32!GetProcessHeap` at `0x14000b867`
- `KERNEL32!FindFirstFileW` at `0x14000b7b5`
- `KERNEL32!FindFirstFileW` at `0x14000b7b5`
- `KERNEL32!FindNextFileW` at `0x14000bc99`
- `KERNEL32!FindNextFileW` at `0x14000bc99`
- `KERNEL32!FindClose` at `0x14000b884`
- `KERNEL32!FindClose` at `0x14000b884`

## string_xrefs

- `0x14000bcba`: `Error copying %s to %s. Last Error = %#x`
- `0x14000b7e0`: `Error creating %s path! Last Error = %#x`
- `0x14000bc12`: `Source, %s, is older than destination, %s, will not update`

## pseudocode

```c
__int64 __fastcall BfspCopyBootFileDirectory(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const wchar_t *a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v11; // r12
  __int64 v12; // rax
  unsigned __int64 v13; // r15
  SIZE_T v14; // rbx
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int Path; // edi
  __int64 v18; // rax
  unsigned __int64 v19; // rdi
  SIZE_T v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // r12
  SIZE_T v24; // rbx
  HANDLE v25; // rax
  wchar_t *v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rdi
  WCHAR *v30; // r14
  __int64 v31; // rbx
  const wchar_t *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  const wchar_t *v35; // r8
  wchar_t *v36; // rax
  wchar_t *v37; // rcx
  HANDLE v38; // rax
  HANDLE v39; // rax
  HANDLE v40; // rax
  WCHAR *v42; // r10
  WCHAR *cFileName; // r8
  wchar_t *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  wchar_t *v47; // rcx
  __int64 v48; // r8
  WCHAR *v49; // r9
  __int64 v50; // rdx
  WCHAR *v51; // rax
  WCHAR *v52; // rcx
  STRSAFE_LPWSTR v53; // rax
  WCHAR *v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rdx
  STRSAFE_LPWSTR v57; // rcx
  __int64 v58; // rax
  unsigned int v59; // edx
  unsigned __int64 v60; // rcx
  unsigned __int64 v61; // r10
  WCHAR *v62; // rbx
  __int64 v63; // rdx
  STRSAFE_LPWSTR v64; // rax
  __int64 v65; // r8
  WCHAR *v66; // r9
  wchar_t *v67; // rdx
  __int64 v68; // rax
  wchar_t *v69; // rcx
  unsigned int ThreadPagePriority; // ebx
  __int64 v71; // [rsp+20h] [rbp-E0h]
  HANDLE hFindFile; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *lpFileName; // [rsp+50h] [rbp-B0h]
  STRSAFE_LPWSTR pszDest; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v76; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *lpMem; // [rsp+70h] [rbp-90h]
  int lpMema; // [rsp+70h] [rbp-90h]
  wchar_t *String1; // [rsp+78h] [rbp-88h]
  WCHAR *i; // [rsp+80h] [rbp-80h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF

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
    goto LABEL_45;
  }
  if ( a2 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(a2 + 2 * v18) );
    v19 = v18 + 262;
    v20 = 2 * (v18 + 262);
    v21 = GetProcessHeap();
    v76 = (unsigned __int16 *)HeapAlloc(v21, 8u, v20);
    if ( !v76 )
    {
      Path = 0;
      goto LABEL_40;
    }
  }
  else
  {
    v76 = 0;
    v19 = 0;
  }
  v22 = -1;
  do
    ++v22;
  while ( a3[v22] );
  v23 = v22 + 262;
  v24 = 2 * (v22 + 262);
  v25 = GetProcessHeap();
  lpMem = (unsigned __int16 *)HeapAlloc(v25, 8u, v24);
  if ( !lpMem )
  {
    v11 = -1;
    Path = 0;
    goto LABEL_40;
  }
  v26 = lpFileName;
  pszDest = 0;
  StringCchPrintfW(lpFileName, v13, L"%s\\", a1);
  v27 = -1;
  do
    ++v27;
  while ( lpFileName[v27] );
  String1 = &lpFileName[v27];
  if ( a2 )
  {
    StringCchPrintfW(v76, v19, L"%s\\", a2);
    v28 = -1;
    do
      ++v28;
    while ( v76[v28] );
    pszDest = &v76[v28];
  }
  v29 = a3;
  v30 = lpMem;
  StringCchPrintfW(lpMem, v23, L"%s\\", a3);
  v31 = -1;
  do
    ++v31;
  while ( lpMem[v31] );
  v32 = L"*";
  v33 = 2147483646;
  v34 = 261;
  if ( a4 )
    v32 = a4;
  lpMema = (int)v32;
  v35 = v32;
  v36 = String1;
  do
  {
    if ( !v33 )
      break;
    if ( !*v35 )
      break;
    *v36++ = *v35++;
    --v33;
    --v34;
  }
  while ( v34 );
  v37 = v36 - 1;
  if ( v34 )
    v37 = v36;
  *v37 = 0;
  hFindFile = FindFirstFileW(lpFileName, &FindFileData);
  v11 = (__int64)hFindFile;
  if ( hFindFile != (HANDLE)-1LL )
  {
    Path = CreatePath(a3);
    if ( !Path )
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"Error creating %s path! Last Error = %#x", v30, LastError);
      goto LABEL_39;
    }
    v29 = a3;
  }
  if ( a6 && (Path = BfspSetFileDirectorySecurityDescriptor(v29)) == 0 || (Path = BfspSetAttributes(a3)) == 0 )
  {
LABEL_37:
    LODWORD(LastError) = GetLastError();
    goto LABEL_38;
  }
  v42 = &v30[v31];
  for ( i = v42; ; v42 = i )
  {
    cFileName = FindFileData.cFileName;
    v44 = String1;
    v45 = 261;
    v46 = 2147483646;
    do
    {
      if ( !v46 )
        break;
      if ( !*cFileName )
        break;
      *v44++ = *cFileName++;
      --v46;
      --v45;
    }
    while ( v45 );
    v47 = v44 - 1;
    v48 = 2147483646;
    v49 = FindFileData.cFileName;
    if ( v45 )
      v47 = v44;
    v50 = 261;
    v51 = v42;
    *v47 = 0;
    do
    {
      if ( !v48 )
        break;
      if ( !*v49 )
        break;
      *v51++ = *v49++;
      --v48;
      --v50;
    }
    while ( v50 );
    v52 = v51 - 1;
    if ( v50 )
      v52 = v51;
    *v52 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      break;
    if ( a2 )
    {
      v53 = pszDest;
      v54 = FindFileData.cFileName;
      v55 = 2147483646;
      v56 = 261;
      do
      {
        if ( !v55 )
          break;
        if ( !*v54 )
          break;
        *v53++ = *v54++;
        --v55;
        --v56;
      }
      while ( v56 );
      v57 = v53 - 1;
      if ( v56 )
        v57 = v53;
      *v57 = 0;
    }
    if ( a8
      && (FindFileData.cFileName[0] != 46
       || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
    {
      Path = BfspCopyBootFileDirectory((_DWORD)v26, (_DWORD)v76, (_DWORD)v30, lpMema, a5, a6, a7, a8);
      if ( !Path )
        goto LABEL_123;
    }
LABEL_120:
    Path = FindNextFileW(hFindFile, &FindFileData);
    if ( !Path )
      goto LABEL_123;
  }
  if ( a2 )
    *pszDest = 0;
  if ( a7 )
  {
    v58 = -1;
    do
      ++v58;
    while ( String1[v58] );
    if ( (unsigned int)v58 < 4 || _wcsicmp(&String1[(unsigned int)v58 - 4], L".mui") )
    {
      if ( _wcsicmp(String1, L"bootfix.bin") )
        goto LABEL_120;
    }
  }
  if ( a6 )
  {
    Path = BfspSetFileDirectorySecurityDescriptor(v30);
    if ( !Path && GetLastError() != 2 )
      goto LABEL_123;
  }
  if ( a2 )
  {
    v59 = 0;
    v60 = -1;
    do
      ++v60;
    while ( FindFileData.cFileName[v60] );
    if ( v60 )
    {
      while ( 1 )
      {
        v61 = v59;
        v62 = &FindFileData.cFileName[v59];
        if ( *v62 == 46 )
          break;
        if ( ++v59 >= v60 )
          goto LABEL_108;
      }
      v63 = 261;
      v64 = pszDest;
      do
      {
        if ( !*v64 )
          break;
        ++v64;
        --v63;
      }
      while ( v63 );
      v65 = (261 - v63) & -(__int64)(v63 != 0);
      if ( v63 && v61 <= 0x7FFFFFFE )
      {
        v66 = FindFileData.cFileName;
        v67 = &pszDest[v65];
        v68 = 261 - v65;
        if ( v65 != 261 )
        {
          do
          {
            if ( !v61 )
              break;
            if ( !*v66 )
              break;
            *v67++ = *v66++;
            --v61;
            --v68;
          }
          while ( v68 );
        }
        v69 = v67 - 1;
        if ( v68 )
          v69 = v67;
        *v69 = 0;
      }
      StringCchCatW(pszDest, 0x105u, L"_EX");
      StringCchCatW(pszDest, 0x105u, v62);
    }
LABEL_108:
    if ( (unsigned int)BfspFileExists(v76) )
      v26 = v76;
  }
  if ( !_wcsicmp(FindFileData.cFileName, L"boot.stl") || !_wcsicmp(FindFileData.cFileName, L"boot.pnd.stl") )
    goto LABEL_115;
  if ( !(unsigned int)BfspShouldFileBeCopied(v26) )
  {
    BfspLogMessage(3, L"Source, %s, is older than destination, %s, will not update", v26, v30);
    goto LABEL_115;
  }
  ThreadPagePriority = BfspGetThreadPagePriority();
  BfspSetThreadPagePriority(1);
  Path = BfspCopyFile(v26, v30);
  BfspSetThreadPagePriority(ThreadPagePriority);
  if ( Path )
  {
LABEL_115:
    if ( (unsigned int)BfspFileExists(v30) )
    {
      Path = BfspSetAttributes(v30);
      if ( !Path )
        goto LABEL_123;
      if ( a6 )
      {
        Path = BfspSetFileDirectorySecurityDescriptor(v30);
        if ( !Path )
          goto LABEL_123;
      }
    }
    v26 = lpFileName;
    goto LABEL_120;
  }
  LODWORD(v71) = GetLastError();
  BfspLogMessage(4, L"Error copying %s to %s. Last Error = %#x", v26, v30, v71);
LABEL_123:
  if ( GetLastError() == 18 )
  {
    Path = 1;
    LODWORD(LastError) = 0;
    if ( a6 )
    {
      Path = BfspSetFileDirectorySecurityDescriptor(a3);
      if ( !Path )
        goto LABEL_37;
    }
LABEL_38:
    v11 = (__int64)hFindFile;
  }
  else
  {
    LODWORD(LastError) = GetLastError();
    v11 = (__int64)hFindFile;
  }
LABEL_39:
  v38 = GetProcessHeap();
  HeapFree(v38, 0, v30);
LABEL_40:
  v39 = GetProcessHeap();
  HeapFree(v39, 0, lpFileName);
  if ( v76 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v76);
  }
  if ( v11 != -1 )
    FindClose((HANDLE)v11);
  if ( !Path )
LABEL_45:
    SetLastError(LastError);
  return Path;
}

```

## disassembly

```asm
0x14000b57c  push    rbp
0x14000b57e  push    rbx
0x14000b57f  push    rsi
0x14000b580  push    rdi
0x14000b581  push    r12
0x14000b583  push    r13
0x14000b585  push    r14
0x14000b587  push    r15
0x14000b589  lea     rbp, [rsp-1F8h]
0x14000b591  sub     rsp, 2F8h
0x14000b598  mov     rax, cs:__security_cookie
0x14000b59f  xor     rax, rsp
0x14000b5a2  mov     [rbp+230h+var_50], rax
0x14000b5a9  mov     [rsp+330h+var_2E8], r8
0x14000b5ae  mov     rdi, rdx
0x14000b5b1  mov     [rsp+330h+var_2C8], rdx
0x14000b5b6  mov     r14, rcx
0x14000b5b9  xor     edx, edx; Val
0x14000b5bb  lea     rcx, [rbp+230h+FindFileData]; void *
0x14000b5bf  mov     r8d, 250h; Size
0x14000b5c5  mov     r13, r9
0x14000b5c8  call    memset_0
0x14000b5cd  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000b5d1  mov     rax, r12
0x14000b5d4  xor     ecx, ecx
0x14000b5d6  inc     rax
0x14000b5d9  cmp     [r14+rax*2], cx
0x14000b5de  jnz     short loc_14000B5D6
0x14000b5e0  lea     r15, [rax+106h]
0x14000b5e7  lea     rbx, [r15+r15]
0x14000b5eb  call    cs:__imp_GetProcessHeap
0x14000b5f1  mov     esi, 8
0x14000b5f6  mov     r8, rbx; dwBytes
0x14000b5f9  mov     rcx, rax; hHeap
0x14000b5fc  mov     edx, esi; dwFlags
0x14000b5fe  call    cs:__imp_HeapAlloc
0x14000b604  xor     edx, edx
0x14000b606  mov     [rsp+330h+lpFileName], rax
0x14000b60b  test    rax, rax
0x14000b60e  jnz     short loc_14000B617
0x14000b610  mov     edi, edx
0x14000b612  jmp     loc_14000B88E
0x14000b617  mov     [rsp+330h+hFindFile], r12
0x14000b61c  test    rdi, rdi
0x14000b61f  jz      short loc_14000B664
0x14000b621  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b625  inc     rax
0x14000b628  cmp     [rdi+rax*2], dx
0x14000b62c  jnz     short loc_14000B625
0x14000b62e  lea     rdi, [rax+106h]
0x14000b635  lea     rbx, [rdi+rdi]
0x14000b639  call    cs:__imp_GetProcessHeap
0x14000b63f  mov     r8, rbx; dwBytes
0x14000b642  mov     edx, esi; dwFlags
0x14000b644  mov     rcx, rax; hHeap
0x14000b647  call    cs:__imp_HeapAlloc
0x14000b64d  xor     edx, edx
0x14000b64f  mov     [rsp+330h+var_2D0], rax
0x14000b654  test    rax, rax
0x14000b657  jnz     short loc_14000B66C
0x14000b659  xor     r13d, r13d
0x14000b65c  mov     edi, r13d
0x14000b65f  jmp     loc_14000B847
0x14000b664  mov     [rsp+330h+var_2D0], rdx
0x14000b669  mov     rdi, rdx
0x14000b66c  mov     rcx, [rsp+330h+var_2E8]
0x14000b671  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b675  inc     rax
0x14000b678  cmp     [rcx+rax*2], dx
0x14000b67c  jnz     short loc_14000B675
0x14000b67e  lea     r12, [rax+106h]
0x14000b685  lea     rbx, [r12+r12]
0x14000b689  call    cs:__imp_GetProcessHeap
0x14000b68f  mov     r8, rbx; dwBytes
0x14000b692  mov     edx, esi; dwFlags
0x14000b694  mov     rcx, rax; hHeap
0x14000b697  call    cs:__imp_HeapAlloc
0x14000b69d  xor     ebx, ebx
0x14000b69f  mov     [rsp+330h+lpMem], rax
0x14000b6a4  test    rax, rax
0x14000b6a7  jnz     short loc_14000B6B9
0x14000b6a9  mov     r12, [rsp+330h+hFindFile]
0x14000b6ae  xor     r13d, r13d
0x14000b6b1  mov     edi, r13d
0x14000b6b4  jmp     loc_14000B847
0x14000b6b9  mov     rsi, [rsp+330h+lpFileName]
0x14000b6be  mov     r9, r14
0x14000b6c1  lea     r14, aS_1; "%s\\"
0x14000b6c8  mov     [rsp+330h+pszDest], rbx
0x14000b6cd  mov     r8, r14; unsigned __int16 *
0x14000b6d0  mov     rdx, r15; unsigned __int64
0x14000b6d3  mov     rcx, rsi; unsigned __int16 *
0x14000b6d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b6db  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b6df  inc     rax
0x14000b6e2  cmp     [rsi+rax*2], bx
0x14000b6e6  jnz     short loc_14000B6DF
0x14000b6e8  mov     r15, [rsp+330h+var_2D0]
0x14000b6ed  lea     rax, [rsi+rax*2]
0x14000b6f1  mov     [rsp+330h+String1], rax
0x14000b6f6  mov     rax, [rsp+330h+var_2C8]
0x14000b6fb  test    rax, rax
0x14000b6fe  jz      short loc_14000B728
0x14000b700  mov     r9, rax
0x14000b703  mov     r8, r14; unsigned __int16 *
0x14000b706  mov     rdx, rdi; unsigned __int64
0x14000b709  mov     rcx, r15; unsigned __int16 *
0x14000b70c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b711  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000b715  inc     rax
0x14000b718  cmp     [r15+rax*2], bx
0x14000b71d  jnz     short loc_14000B715
0x14000b71f  lea     rax, [r15+rax*2]
0x14000b723  mov     [rsp+330h+pszDest], rax
0x14000b728  mov     rdi, [rsp+330h+var_2E8]
0x14000b72d  mov     r8, r14; unsigned __int16 *
0x14000b730  mov     r14, [rsp+330h+lpMem]
0x14000b735  mov     r9, rdi
0x14000b738  mov     rcx, r14; unsigned __int16 *
0x14000b73b  mov     rdx, r12; unsigned __int64
0x14000b73e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b743  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000b747  xor     ecx, ecx
0x14000b749  inc     rbx
0x14000b74c  cmp     [r14+rbx*2], cx
0x14000b751  jnz     short loc_14000B749
0x14000b753  test    r13, r13
0x14000b756  lea     rax, asc_14002FBE8; "*"
0x14000b75d  mov     ecx, 7FFFFFFEh
0x14000b762  mov     edx, 105h
0x14000b767  cmovnz  rax, r13
0x14000b76b  xor     r13d, r13d
0x14000b76e  mov     [rsp+330h+lpMem], rax
0x14000b773  mov     r8, rax
0x14000b776  mov     rax, [rsp+330h+String1]
0x14000b77b  test    rcx, rcx
0x14000b77e  jz      short loc_14000B79F
0x14000b780  movzx   r9d, word ptr [r8]
0x14000b784  test    r9w, r9w
0x14000b788  jz      short loc_14000B79F
0x14000b78a  mov     [rax], r9w
0x14000b78e  add     r8, 2
0x14000b792  add     rax, 2
0x14000b796  dec     rcx
0x14000b799  sub     rdx, 1
0x14000b79d  jnz     short loc_14000B77B
0x14000b79f  test    rdx, rdx
0x14000b7a2  lea     rcx, [rax-2]
0x14000b7a6  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x14000b7aa  cmovnz  rcx, rax
0x14000b7ae  mov     [rcx], r13w
0x14000b7b2  mov     rcx, rsi; lpFileName
0x14000b7b5  call    cs:__imp_FindFirstFileW
0x14000b7bb  mov     [rsp+330h+hFindFile], rax
0x14000b7c0  mov     r12, rax
0x14000b7c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b7c7  jz      short loc_14000B7FB
0x14000b7c9  mov     rcx, rdi
0x14000b7cc  call    CreatePath
0x14000b7d1  mov     edi, eax
0x14000b7d3  test    eax, eax
0x14000b7d5  jnz     short loc_14000B7F6
0x14000b7d7  call    cs:__imp_GetLastError
0x14000b7dd  mov     r8, r14
0x14000b7e0  lea     rdx, aErrorCreatingS; "Error creating %s path! Last Error = %#"...
0x14000b7e7  mov     r9d, eax
0x14000b7ea  lea     ecx, [rdi+4]
0x14000b7ed  mov     esi, eax
0x14000b7ef  call    BfspLogMessage
0x14000b7f4  jmp     short loc_14000B833
0x14000b7f6  mov     rdi, [rsp+330h+var_2E8]
0x14000b7fb  mov     r12d, [rbp+230h+arg_28]
0x14000b802  test    r12d, r12d
0x14000b805  jz      loc_14000B8BB
0x14000b80b  lea     r8, aOSgSdPACiGaSA0; "O:%sG:%sD:P(A;CI;GA;;;%s)(A;;0x1201bf;;"...
0x14000b812  xor     edx, edx
0x14000b814  mov     rcx, rdi; lpFileName
0x14000b817  call    BfspSetFileDirectorySecurityDescriptor
0x14000b81c  mov     edi, eax
0x14000b81e  test    eax, eax
0x14000b820  jnz     loc_14000B8BB
0x14000b826  call    cs:__imp_GetLastError
0x14000b82c  mov     esi, eax
0x14000b82e  mov     r12, [rsp+330h+hFindFile]
0x14000b833  call    cs:__imp_GetProcessHeap
0x14000b839  mov     r8, r14; lpMem
0x14000b83c  xor     edx, edx; dwFlags
0x14000b83e  mov     rcx, rax; hHeap
0x14000b841  call    cs:__imp_HeapFree
0x14000b847  call    cs:__imp_GetProcessHeap
0x14000b84d  mov     r8, [rsp+330h+lpFileName]; lpMem
0x14000b852  xor     edx, edx; dwFlags
0x14000b854  mov     rcx, rax; hHeap
0x14000b857  call    cs:__imp_HeapFree
0x14000b85d  mov     rbx, [rsp+330h+var_2D0]
0x14000b862  test    rbx, rbx
0x14000b865  jz      short loc_14000B87B
0x14000b867  call    cs:__imp_GetProcessHeap
0x14000b86d  mov     r8, rbx; lpMem
0x14000b870  xor     edx, edx; dwFlags
0x14000b872  mov     rcx, rax; hHeap
0x14000b875  call    cs:__imp_HeapFree
0x14000b87b  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14000b87f  jz      short loc_14000B88A
0x14000b881  mov     rcx, r12; hFindFile
0x14000b884  call    cs:__imp_FindClose
0x14000b88a  test    edi, edi
0x14000b88c  jnz     short loc_14000B896
0x14000b88e  mov     ecx, esi; dwErrCode
0x14000b890  call    cs:__imp_SetLastError
0x14000b896  mov     eax, edi
0x14000b898  mov     rcx, [rbp+230h+var_50]
0x14000b89f  xor     rcx, rsp; StackCookie
0x14000b8a2  call    __security_check_cookie
0x14000b8a7  add     rsp, 2F8h
0x14000b8ae  pop     r15
0x14000b8b0  pop     r14
0x14000b8b2  pop     r13
0x14000b8b4  pop     r12
0x14000b8b6  pop     rdi
0x14000b8b7  pop     rsi
0x14000b8b8  pop     rbx
0x14000b8b9  pop     rbp
0x14000b8ba  retn
0x14000b8bb  mov     rcx, [rsp+330h+var_2E8]; lpFileName
0x14000b8c0  mov     edx, 80h
0x14000b8c5  call    BfspSetAttributes
0x14000b8ca  xor     r11d, r11d
0x14000b8cd  mov     edi, eax
0x14000b8cf  test    eax, eax
0x14000b8d1  jz      loc_14000B826
0x14000b8d7  mov     r13, [rsp+330h+hFindFile]
0x14000b8dc  lea     r10, [r14+rbx*2]
0x14000b8e0  mov     [rbp+230h+var_2B0], r10
0x14000b8e4  mov     rdi, [rsp+330h+String1]
0x14000b8e9  lea     r8, [rbp+230h+FindFileData.cFileName]
0x14000b8ed  mov     ebx, 105h
0x14000b8f2  mov     rax, rdi
0x14000b8f5  mov     edx, ebx
0x14000b8f7  mov     ecx, 7FFFFFFEh
0x14000b8fc  test    rcx, rcx
0x14000b8ff  jz      short loc_14000B920
0x14000b901  movzx   r9d, word ptr [r8]
0x14000b905  test    r9w, r9w
0x14000b909  jz      short loc_14000B920
0x14000b90b  mov     [rax], r9w
0x14000b90f  add     r8, 2
0x14000b913  add     rax, 2
0x14000b917  dec     rcx
0x14000b91a  sub     rdx, 1
0x14000b91e  jnz     short loc_14000B8FC
0x14000b920  test    rdx, rdx
0x14000b923  lea     rcx, [rax-2]
0x14000b927  mov     r8d, 7FFFFFFEh
0x14000b92d  lea     r9, [rbp+230h+FindFileData.cFileName]
0x14000b931  cmovnz  rcx, rax
0x14000b935  mov     rdx, rbx
0x14000b938  mov     rax, r10
0x14000b93b  mov     [rcx], r11w
0x14000b93f  test    r8, r8
0x14000b942  jz      short loc_14000B961
0x14000b944  movzx   ecx, word ptr [r9]
0x14000b948  test    cx, cx
0x14000b94b  jz      short loc_14000B961
0x14000b94d  mov     [rax], cx
0x14000b950  add     r9, 2
0x14000b954  add     rax, 2
0x14000b958  dec     r8
0x14000b95b  sub     rdx, 1
0x14000b95f  jnz     short loc_14000B93F
0x14000b961  test    rdx, rdx
0x14000b964  lea     rcx, [rax-2]
0x14000b968  cmovnz  rcx, rax
0x14000b96c  mov     [rcx], r11w
0x14000b970  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x14000b974  jz      loc_14000BA3F
0x14000b97a  cmp     [rsp+330h+var_2C8], 0
0x14000b980  jz      short loc_14000B9C6
0x14000b982  mov     rax, [rsp+330h+pszDest]
0x14000b987  lea     r8, [rbp+230h+FindFileData.cFileName]
0x14000b98b  mov     ecx, 7FFFFFFEh
0x14000b990  mov     rdx, rbx
0x14000b993  test    rcx, rcx
0x14000b996  jz      short loc_14000B9B7
0x14000b998  movzx   r9d, word ptr [r8]
0x14000b99c  test    r9w, r9w
0x14000b9a0  jz      short loc_14000B9B7
0x14000b9a2  mov     [rax], r9w
0x14000b9a6  add     r8, 2
0x14000b9aa  add     rax, 2
0x14000b9ae  dec     rcx
0x14000b9b1  sub     rdx, 1
0x14000b9b5  jnz     short loc_14000B993
0x14000b9b7  test    rdx, rdx
0x14000b9ba  lea     rcx, [rax-2]
0x14000b9be  cmovnz  rcx, rax
0x14000b9c2  mov     [rcx], r11w
0x14000b9c6  mov     ecx, [rbp+230h+arg_38]
0x14000b9cc  test    ecx, ecx
0x14000b9ce  jz      loc_14000BC92
  ... truncated ...
```
