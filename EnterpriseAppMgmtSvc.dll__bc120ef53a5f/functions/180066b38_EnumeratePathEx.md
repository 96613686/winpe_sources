# EnumeratePathEx

- ea: `0x180066b38`
- end: `0x1800671b0`
- name: `EnumeratePathEx`
- size: `1656`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `4`
- callee_count: `14`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180065d70`
- `0x180065ee4`
- `0x180066270`
- `0x18006655c`

## callees

- `0x180063df0`
- `0x180063e84`
- `0x180064a7c`
- `0x180064e8c`
- `0x180066b38`
- `0x1800671b8`
- `0x180067250`
- `0x1800673e4`
- `0x180067480`
- `0x1800674d8`
- `0x1800676bc`
- `0x18006c8d2`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180066e4d`
- `msvcrt!wcsrchr` at `0x180066e4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066f9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006712d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066f9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006712d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180067152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066fae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066fae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067141`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180067166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006700a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006701f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006700a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006701f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066f4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006717e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066c15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066f4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006717e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180066ed1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180066f01`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180066ed1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180066f01`
- `ntdll!RtlFreeHeap` at `0x1800670da`
- `ntdll!RtlFreeHeap` at `0x1800670da`
- `ntdll!RtlAllocateHeap` at `0x180066cc9`
- `ntdll!RtlAllocateHeap` at `0x180066cc9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180066dbd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180066dbd`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180066fd8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180066fd8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180067051`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180067051`

## string_xrefs

- `0x180066c51`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x180067071`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x180067107`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18006702b`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x180067016`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x1800670a6`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

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
0x180066b38  push    rbp
0x180066b3a  push    rbx
0x180066b3b  push    rsi
0x180066b3c  push    rdi
0x180066b3d  push    r12
0x180066b3f  push    r13
0x180066b41  push    r14
0x180066b43  push    r15
0x180066b45  lea     rbp, [rsp-218h]
0x180066b4d  sub     rsp, 318h
0x180066b54  mov     rax, cs:__security_cookie
0x180066b5b  xor     rax, rsp
0x180066b5e  mov     [rbp+250h+var_50], rax
0x180066b65  mov     [rsp+350h+var_300], r8
0x180066b6a  mov     r14, rcx
0x180066b6d  mov     [rbp+250h+var_2B0], rdx
0x180066b71  lea     rcx, [rbp+250h+FindFileData]; void *
0x180066b75  xor     edx, edx; Val
0x180066b77  mov     [rsp+350h+var_2F8], r9
0x180066b7c  mov     r8d, 250h; Size
0x180066b82  call    memset_0
0x180066b87  xor     esi, esi
0x180066b89  mov     dword ptr [rsp+350h+pszDest], esi
0x180066b8d  test    r14, r14
0x180066b90  jz      loc_180067179
0x180066b96  cmp     si, [r14]
0x180066b9a  jz      loc_180067179
0x180066ba0  lea     rdx, [rsp+350h+pszDest]
0x180066ba5  mov     rcx, r14
0x180066ba8  call    ReparsePointExists
0x180066bad  lea     r13d, [rsi+1]
0x180066bb1  test    eax, eax
0x180066bb3  jz      loc_180066C70
0x180066bb9  cmp     dword ptr [rsp+350h+pszDest], esi
0x180066bbd  jz      loc_180066C70
0x180066bc3  mov     ebx, [rbp+250h+arg_20]
0x180066bc9  mov     dword ptr [rsp+350h+cchDest], esi
0x180066bcd  test    bl, 2
0x180066bd0  jnz     short loc_180066C13
0x180066bd2  lea     rdx, [rsp+350h+cchDest]
0x180066bd7  mov     rcx, r14
0x180066bda  call    ShouldEnumerateReparsePoint
0x180066bdf  test    eax, eax
0x180066be1  jz      short loc_180066BED
0x180066be3  cmp     dword ptr [rsp+350h+cchDest], esi
0x180066be7  jnz     loc_180066C70
0x180066bed  and     ebx, r13d
0x180066bf0  mov     dword ptr [rsp+350h+cchDest], esi
0x180066bf4  test    bl, bl
0x180066bf6  jnz     short loc_180066C13
0x180066bf8  lea     rdx, [rsp+350h+cchDest]
0x180066bfd  mov     rcx, r14; lpFileName
0x180066c00  call    GetReparseTag
0x180066c05  test    eax, eax
0x180066c07  jz      short loc_180066C29
0x180066c09  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x180066c11  jz      short loc_180066C70
0x180066c13  xor     ecx, ecx; dwErrCode
0x180066c15  call    cs:__imp_SetLastError
0x180066c1c  nop     dword ptr [rax+rax+00h]
0x180066c21  mov     eax, r13d
0x180066c24  jmp     loc_18006718C
0x180066c29  call    cs:__imp_GetLastError
0x180066c30  nop     dword ptr [rax+rax+00h]
0x180066c35  lea     rdx, [rsp+350h+pszDest]
0x180066c3a  mov     rcx, r14
0x180066c3d  mov     ebx, eax
0x180066c3f  call    ReparsePointExists
0x180066c44  test    eax, eax
0x180066c46  jz      short loc_180066C70
0x180066c48  cmp     dword ptr [rsp+350h+pszDest], esi
0x180066c4c  jz      short loc_180066C70
0x180066c4e  mov     r9d, ebx
0x180066c51  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x180066c58  mov     edx, 2000000h
0x180066c5d  lea     rcx, g_WdsLibLog
0x180066c64  call    LibLog
0x180066c69  mov     ecx, ebx
0x180066c6b  jmp     loc_18006717E
0x180066c70  or      r12, 0FFFFFFFFFFFFFFFFh
0x180066c74  mov     [rsp+350h+pszDest], rsi
0x180066c79  mov     rdi, r12
0x180066c7c  mov     [rsp+350h+cchDest], rsi
0x180066c81  mov     rbx, rsi
0x180066c84  mov     r15d, esi
0x180066c87  inc     rdi
0x180066c8a  cmp     [r14+rdi*2], si
0x180066c8f  jnz     short loc_180066C87
0x180066c91  mov     edx, 5Ch ; '\'
0x180066c96  test    edi, edi
0x180066c98  jz      short loc_180066CA6
0x180066c9a  lea     eax, [rdi-1]
0x180066c9d  cmp     dx, [r14+rax*2]
0x180066ca2  cmovnz  r15d, r13d
0x180066ca6  mov     rcx, gs:60h
0x180066caf  lea     eax, [r15+2]
0x180066cb3  add     eax, edi
0x180066cb5  mov     edx, 8; Flags
0x180066cba  mov     r13d, eax
0x180066cbd  mov     rcx, [rcx+30h]; HeapHandle
0x180066cc1  lea     r8, ds:0[rax*2]; Size
0x180066cc9  call    cs:__imp_RtlAllocateHeap
0x180066cd0  nop     dword ptr [rax+rax+00h]
0x180066cd5  mov     rsi, rax
0x180066cd8  test    rax, rax
0x180066cdb  jnz     short loc_180066CF5
0x180066cdd  mov     rax, gs:30h
0x180066ce6  xor     r15d, r15d
0x180066ce9  mov     dword ptr [rax+68h], 8
0x180066cf0  jmp     loc_1800670F5
0x180066cf5  lea     rax, [rsp+350h+cchDest]
0x180066cfa  mov     r9d, edi; cchToCopy
0x180066cfd  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x180066d02  mov     r8, r14; pszSrc
0x180066d05  lea     rax, [rsp+350h+pszDest]
0x180066d0a  mov     rdx, r13; cchDest
0x180066d0d  mov     rcx, rsi; pszDest
0x180066d10  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x180066d15  call    StringCchCopyNExW
0x180066d1a  mov     edi, eax
0x180066d1c  test    eax, eax
0x180066d1e  js      loc_1800670C5
0x180066d24  test    r15d, r15d
0x180066d27  jz      short loc_180066D67
0x180066d29  mov     rdx, [rsp+350h+cchDest]; cchDest
0x180066d2e  lea     rax, [rsp+350h+cchDest]
0x180066d33  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180066d38  lea     r8, pszSrc; "\\"
0x180066d3f  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x180066d44  mov     r9d, 1; cchToCopy
0x180066d4a  lea     rax, [rsp+350h+pszDest]
0x180066d4f  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x180066d54  call    StringCchCopyNExW
0x180066d59  xor     r15d, r15d
0x180066d5c  mov     edi, eax
0x180066d5e  test    eax, eax
0x180066d60  jns     short loc_180066D6A
0x180066d62  jmp     loc_1800670C8
0x180066d67  xor     r15d, r15d
0x180066d6a  mov     rdx, [rsp+350h+cchDest]; cchDest
0x180066d6f  lea     r8, pszMore; "*"
0x180066d76  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180066d7b  mov     r9d, 1; cchToCopy
0x180066d81  call    StringCchCopyNW
0x180066d86  mov     edi, eax
0x180066d88  test    eax, eax
0x180066d8a  js      loc_1800670C8
0x180066d90  mov     rax, gs:30h
0x180066d99  xor     edx, edx
0x180066d9b  mov     rcx, rsi; unsigned __int16 *
0x180066d9e  mov     [rax+68h], r15d
0x180066da2  call    PrepareUnicodePathEx
0x180066da7  mov     rbx, rax
0x180066daa  test    rax, rax
0x180066dad  jz      loc_1800670F8
0x180066db3  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180066db7  mov     rcx, rax; lpFileName
0x180066dba  mov     r13d, r15d
0x180066dbd  call    cs:__imp_FindFirstFileW
0x180066dc4  nop     dword ptr [rax+rax+00h]
0x180066dc9  mov     [rsp+350h+cchDest], rax
0x180066dce  cmp     rax, r12
0x180066dd1  jz      loc_180067062
0x180066dd7  xor     edx, edx; Val
0x180066dd9  lea     rcx, [rsp+350h+var_2F0]; void *
0x180066dde  lea     r8d, [rdx+40h]; Size
0x180066de2  call    memset_0
0x180066de7  cmp     r15w, [r14]
0x180066deb  jz      loc_180066F48
0x180066df1  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x180066df4  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x180066df8  mov     [rsp+350h+var_2F0], eax
0x180066dfc  xorps   xmm0, xmm0
0x180066dff  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x180066e03  mov     rcx, r14; pszSrc
0x180066e06  mov     [rsp+350h+var_2EC], rax
0x180066e0b  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x180066e0f  mov     [rsp+350h+var_2E4], rax
0x180066e14  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180066e18  mov     [rsp+350h+var_2DC], rax
0x180066e1d  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x180066e20  mov     [rbp+250h+var_2D0], eax
0x180066e23  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x180066e26  mov     [rbp+250h+var_2CC], eax
0x180066e29  mov     [rsp+350h+var_2D4], r15d
0x180066e2e  mov     [rbp+250h+lpMem], r15
0x180066e32  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x180066e37  call    BuildPath
0x180066e3c  mov     [rbp+250h+lpMem], rax
0x180066e40  test    rax, rax
0x180066e43  jz      short loc_180066E84
0x180066e45  mov     edx, 5Ch ; '\'; Ch
0x180066e4a  mov     rcx, rax; Str
0x180066e4d  call    cs:__imp_wcsrchr
0x180066e54  nop     dword ptr [rax+rax+00h]
0x180066e59  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x180066e5d  test    rax, rax
0x180066e60  jz      short loc_180066E68
0x180066e62  add     rax, 2
0x180066e66  jmp     short loc_180066E6B
0x180066e68  mov     rax, rcx
0x180066e6b  mov     [rbp+250h+lpString2], rax
0x180066e6f  call    FormFullPathName
0x180066e74  mov     [rbp+250h+lpString2+8], rax
0x180066e78  test    rax, rax
0x180066e7b  jz      short loc_180066E84
0x180066e7d  mov     edi, 1
0x180066e82  jmp     short loc_180066E91
0x180066e84  lea     rcx, [rsp+350h+var_2F0]; void *
0x180066e89  mov     edi, r15d
0x180066e8c  call    FreeWdslibFindData
0x180066e91  cmp     edi, 1
0x180066e94  jnz     loc_180066F5C
0x180066e9a  test    byte ptr [rsp+350h+var_2F0], 10h
0x180066e9f  jz      loc_180066F2D
0x180066ea5  mov     r15, [rbp+250h+var_2B0]
0x180066ea9  test    r15, r15
0x180066eac  jz      loc_180066F5C
0x180066eb2  mov     rax, [rbp+250h+lpString2]
0x180066eb6  lea     r8, asc_1800844FC; "."
0x180066ebd  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180066ec2  mov     r9d, r12d; cchCount1
0x180066ec5  mov     edx, edi; dwCmpFlags
0x180066ec7  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180066ecc  mov     ecx, 409h; Locale
0x180066ed1  call    cs:__imp_CompareStringW
0x180066ed8  nop     dword ptr [rax+rax+00h]
0x180066edd  cmp     eax, 2
0x180066ee0  jz      short loc_180066F5C
0x180066ee2  mov     rax, [rbp+250h+lpString2]
0x180066ee6  lea     r8, asc_180083A24; ".."
0x180066eed  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180066ef2  mov     r9d, r12d; cchCount1
0x180066ef5  mov     edx, edi; dwCmpFlags
0x180066ef7  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180066efc  mov     ecx, 409h; Locale
0x180066f01  call    cs:__imp_CompareStringW
0x180066f08  nop     dword ptr [rax+rax+00h]
0x180066f0d  cmp     eax, 2
0x180066f10  jz      short loc_180066F5C
0x180066f12  mov     r8, [rsp+350h+var_2F8]
0x180066f17  lea     rcx, [rsp+350h+var_2F0]
0x180066f1c  mov     rdx, [rsp+350h+var_300]
0x180066f21  mov     rax, r15
0x180066f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f29  mov     edi, eax
0x180066f2b  jmp     short loc_180066F5C
0x180066f2d  mov     rax, [rsp+350h+var_300]
0x180066f32  test    rax, rax
0x180066f35  jz      short loc_180066F5C
0x180066f37  mov     rdx, [rsp+350h+var_2F8]
0x180066f3c  lea     rcx, [rsp+350h+var_2F0]
0x180066f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f46  jmp     short loc_180066F29
0x180066f48  mov     ecx, 57h ; 'W'; dwErrCode
0x180066f4d  call    cs:__imp_SetLastError
0x180066f54  nop     dword ptr [rax+rax+00h]
0x180066f59  mov     edi, r15d
0x180066f5c  mov     r15, [rbp+250h+lpMem]
0x180066f60  test    r15, r15
0x180066f63  jz      short loc_180066F91
0x180066f65  call    cs:__imp_GetProcessHeap
0x180066f6c  nop     dword ptr [rax+rax+00h]
0x180066f71  mov     r8, r15; lpMem
0x180066f74  xor     edx, edx; dwFlags
0x180066f76  mov     rcx, rax; hHeap
0x180066f79  call    cs:__imp_HeapFree
0x180066f80  nop     dword ptr [rax+rax+00h]
0x180066f85  test    eax, eax
0x180066f87  jz      short loc_180066F91
0x180066f89  mov     [rbp+250h+lpMem], 0
0x180066f91  mov     r15, [rbp+250h+lpString2+8]
0x180066f95  test    r15, r15
0x180066f98  jz      short loc_180066FBA
0x180066f9a  call    cs:__imp_GetProcessHeap
0x180066fa1  nop     dword ptr [rax+rax+00h]
0x180066fa6  mov     r8, r15; lpMem
0x180066fa9  xor     edx, edx; dwFlags
0x180066fab  mov     rcx, rax; hHeap
0x180066fae  call    cs:__imp_HeapFree
0x180066fb5  nop     dword ptr [rax+rax+00h]
0x180066fba  xor     edx, edx; Val
0x180066fbc  lea     rcx, [rsp+350h+var_2F0]; void *
0x180066fc1  lea     r8d, [rdx+40h]; Size
0x180066fc5  call    memset_0
0x180066fca  cmp     edi, 1
0x180066fcd  jnz     short loc_18006701F
0x180066fcf  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x180066fd4  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180066fd8  call    cs:__imp_FindNextFileW
0x180066fdf  nop     dword ptr [rax+rax+00h]
0x180066fe4  lea     r15d, [rdi-1]
0x180066fe8  cmp     eax, edi
0x180066fea  jz      loc_180066DE7
0x180066ff0  call    cs:__imp_GetLastError
0x180066ff7  nop     dword ptr [rax+rax+00h]
0x180066ffc  cmp     eax, 12h
0x180066fff  jnz     short loc_18006700A
0x180067001  mov     edi, r15d
0x180067004  lea     r13d, [r15+1]
  ... truncated ...
```
