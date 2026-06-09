# EnumeratePathEx

- ea: `0x1800616e8`
- end: `0x180061cbd`
- name: `EnumeratePathEx`
- size: `1493`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, int)`
- caller_count: `4`
- callee_count: `14`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180060aa0`
- `0x180060be8`
- `0x180060f20`
- `0x1800611b8`

## callees

- `0x18005eea8`
- `0x18005ef38`
- `0x18005f9f8`
- `0x18005fd24`
- `0x1800616e8`
- `0x180061cc4`
- `0x180061d40`
- `0x180061e8c`
- `0x180061f0c`
- `0x180061f64`
- `0x18006213c`
- `0x180066db2`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800619e1`
- `msvcrt!wcsrchr` at `0x1800619e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061c72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061aeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061aeb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800617cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800617cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061c2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800617c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061acb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061c92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800617c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061acb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061c92`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061a5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061a85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061a5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180061a85`
- `ntdll!RtlFreeHeap` at `0x180061c12`
- `ntdll!RtlFreeHeap` at `0x180061c12`
- `ntdll!RtlAllocateHeap` at `0x180061869`
- `ntdll!RtlAllocateHeap` at `0x180061869`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180061957`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180061957`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180061b38`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180061b38`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180061b99`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180061b99`

## string_xrefs

- `0x180061b73`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x180061b64`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x1800617f1`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x180061bde`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`
- `0x180061bad`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x180061c33`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`

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
0x1800616e8  push    rbp
0x1800616ea  push    rbx
0x1800616eb  push    rsi
0x1800616ec  push    rdi
0x1800616ed  push    r12
0x1800616ef  push    r13
0x1800616f1  push    r14
0x1800616f3  push    r15
0x1800616f5  lea     rbp, [rsp-218h]
0x1800616fd  sub     rsp, 318h
0x180061704  mov     rax, cs:__security_cookie
0x18006170b  xor     rax, rsp
0x18006170e  mov     [rbp+250h+var_50], rax
0x180061715  mov     [rsp+350h+var_300], r8
0x18006171a  mov     r14, rcx
0x18006171d  mov     [rbp+250h+var_2B0], rdx
0x180061721  lea     rcx, [rbp+250h+FindFileData]; void *
0x180061725  xor     edx, edx; Val
0x180061727  mov     [rsp+350h+var_2F8], r9
0x18006172c  mov     r8d, 250h; Size
0x180061732  call    memset_0
0x180061737  xor     esi, esi
0x180061739  mov     dword ptr [rsp+350h+pszDest], esi
0x18006173d  test    r14, r14
0x180061740  jz      loc_180061C8D
0x180061746  cmp     si, [r14]
0x18006174a  jz      loc_180061C8D
0x180061750  lea     rdx, [rsp+350h+pszDest]
0x180061755  mov     rcx, r14
0x180061758  call    ReparsePointExists
0x18006175d  lea     r13d, [rsi+1]
0x180061761  test    eax, eax
0x180061763  jz      loc_180061810
0x180061769  cmp     dword ptr [rsp+350h+pszDest], esi
0x18006176d  jz      loc_180061810
0x180061773  mov     ebx, [rbp+250h+arg_20]
0x180061779  mov     dword ptr [rsp+350h+cchDest], esi
0x18006177d  test    bl, 2
0x180061780  jnz     short loc_1800617BF
0x180061782  lea     rdx, [rsp+350h+cchDest]
0x180061787  mov     rcx, r14
0x18006178a  call    ShouldEnumerateReparsePoint
0x18006178f  test    eax, eax
0x180061791  jz      short loc_180061799
0x180061793  cmp     dword ptr [rsp+350h+cchDest], esi
0x180061797  jnz     short loc_180061810
0x180061799  and     ebx, r13d
0x18006179c  mov     dword ptr [rsp+350h+cchDest], esi
0x1800617a0  test    bl, bl
0x1800617a2  jnz     short loc_1800617BF
0x1800617a4  lea     rdx, [rsp+350h+cchDest]
0x1800617a9  mov     rcx, r14; lpFileName
0x1800617ac  call    GetReparseTag
0x1800617b1  test    eax, eax
0x1800617b3  jz      short loc_1800617CF
0x1800617b5  cmp     dword ptr [rsp+350h+cchDest], 80000008h
0x1800617bd  jz      short loc_180061810
0x1800617bf  xor     ecx, ecx; dwErrCode
0x1800617c1  call    cs:__imp_SetLastError
0x1800617c7  mov     eax, r13d
0x1800617ca  jmp     loc_180061C9A
0x1800617cf  call    cs:__imp_GetLastError
0x1800617d5  lea     rdx, [rsp+350h+pszDest]
0x1800617da  mov     rcx, r14
0x1800617dd  mov     ebx, eax
0x1800617df  call    ReparsePointExists
0x1800617e4  test    eax, eax
0x1800617e6  jz      short loc_180061810
0x1800617e8  cmp     dword ptr [rsp+350h+pszDest], esi
0x1800617ec  jz      short loc_180061810
0x1800617ee  mov     r9d, ebx
0x1800617f1  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x1800617f8  mov     edx, 2000000h
0x1800617fd  lea     rcx, g_WdsLibLog
0x180061804  call    LibLog
0x180061809  mov     ecx, ebx
0x18006180b  jmp     loc_180061C92
0x180061810  or      r12, 0FFFFFFFFFFFFFFFFh
0x180061814  mov     [rsp+350h+pszDest], rsi
0x180061819  mov     rdi, r12
0x18006181c  mov     [rsp+350h+cchDest], rsi
0x180061821  mov     rbx, rsi
0x180061824  mov     r15d, esi
0x180061827  inc     rdi
0x18006182a  cmp     [r14+rdi*2], si
0x18006182f  jnz     short loc_180061827
0x180061831  mov     edx, 5Ch ; '\'
0x180061836  test    edi, edi
0x180061838  jz      short loc_180061846
0x18006183a  lea     eax, [rdi-1]
0x18006183d  cmp     dx, [r14+rax*2]
0x180061842  cmovnz  r15d, r13d
0x180061846  mov     rcx, gs:60h
0x18006184f  lea     eax, [r15+2]
0x180061853  add     eax, edi
0x180061855  mov     edx, 8; Flags
0x18006185a  mov     r13d, eax
0x18006185d  mov     rcx, [rcx+30h]; HeapHandle
0x180061861  lea     r8, ds:0[rax*2]; Size
0x180061869  call    cs:__imp_RtlAllocateHeap
0x18006186f  mov     rsi, rax
0x180061872  test    rax, rax
0x180061875  jnz     short loc_18006188F
0x180061877  mov     rax, gs:30h
0x180061880  xor     r15d, r15d
0x180061883  mov     dword ptr [rax+68h], 8
0x18006188a  jmp     loc_180061C27
0x18006188f  lea     rax, [rsp+350h+cchDest]
0x180061894  mov     r9d, edi; cchToCopy
0x180061897  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x18006189c  mov     r8, r14; pszSrc
0x18006189f  lea     rax, [rsp+350h+pszDest]
0x1800618a4  mov     rdx, r13; cchDest
0x1800618a7  mov     rcx, rsi; pszDest
0x1800618aa  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x1800618af  call    StringCchCopyNExW
0x1800618b4  mov     edi, eax
0x1800618b6  test    eax, eax
0x1800618b8  js      loc_180061BFD
0x1800618be  test    r15d, r15d
0x1800618c1  jz      short loc_180061901
0x1800618c3  mov     rdx, [rsp+350h+cchDest]; cchDest
0x1800618c8  lea     rax, [rsp+350h+cchDest]
0x1800618cd  mov     rcx, [rsp+350h+pszDest]; pszDest
0x1800618d2  lea     r8, pszSrc; "\\"
0x1800618d9  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x1800618de  mov     r9d, 1; cchToCopy
0x1800618e4  lea     rax, [rsp+350h+pszDest]
0x1800618e9  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x1800618ee  call    StringCchCopyNExW
0x1800618f3  xor     r15d, r15d
0x1800618f6  mov     edi, eax
0x1800618f8  test    eax, eax
0x1800618fa  jns     short loc_180061904
0x1800618fc  jmp     loc_180061C00
0x180061901  xor     r15d, r15d
0x180061904  mov     rdx, [rsp+350h+cchDest]; cchDest
0x180061909  lea     r8, pszMore; "*"
0x180061910  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180061915  mov     r9d, 1; cchToCopy
0x18006191b  call    StringCchCopyNW
0x180061920  mov     edi, eax
0x180061922  test    eax, eax
0x180061924  js      loc_180061C00
0x18006192a  mov     rax, gs:30h
0x180061933  xor     edx, edx
0x180061935  mov     rcx, rsi; unsigned __int16 *
0x180061938  mov     [rax+68h], r15d
0x18006193c  call    PrepareUnicodePathEx
0x180061941  mov     rbx, rax
0x180061944  test    rax, rax
0x180061947  jz      loc_180061C2A
0x18006194d  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180061951  mov     rcx, rax; lpFileName
0x180061954  mov     r13d, r15d
0x180061957  call    cs:__imp_FindFirstFileW
0x18006195d  mov     [rsp+350h+cchDest], rax
0x180061962  cmp     rax, r12
0x180061965  jz      loc_180061BA4
0x18006196b  xor     edx, edx; Val
0x18006196d  lea     rcx, [rsp+350h+var_2F0]; void *
0x180061972  lea     r8d, [rdx+40h]; Size
0x180061976  call    memset_0
0x18006197b  cmp     r15w, [r14]
0x18006197f  jz      loc_180061AC6
0x180061985  mov     eax, [rbp+250h+FindFileData.dwFileAttributes]
0x180061988  lea     rdx, [rbp+250h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x18006198c  mov     [rsp+350h+var_2F0], eax
0x180061990  xorps   xmm0, xmm0
0x180061993  mov     rax, qword ptr [rbp+250h+FindFileData.ftCreationTime.dwLowDateTime]
0x180061997  mov     rcx, r14; pszSrc
0x18006199a  mov     [rsp+350h+var_2EC], rax
0x18006199f  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x1800619a3  mov     [rsp+350h+var_2E4], rax
0x1800619a8  mov     rax, qword ptr [rbp+250h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800619ac  mov     [rsp+350h+var_2DC], rax
0x1800619b1  mov     eax, [rbp+250h+FindFileData.nFileSizeLow]
0x1800619b4  mov     [rbp+250h+var_2D0], eax
0x1800619b7  mov     eax, [rbp+250h+FindFileData.nFileSizeHigh]
0x1800619ba  mov     [rbp+250h+var_2CC], eax
0x1800619bd  mov     [rsp+350h+var_2D4], r15d
0x1800619c2  mov     [rbp+250h+lpMem], r15
0x1800619c6  movdqa  xmmword ptr [rbp+250h+lpString2], xmm0
0x1800619cb  call    BuildPath
0x1800619d0  mov     [rbp+250h+lpMem], rax
0x1800619d4  test    rax, rax
0x1800619d7  jz      short loc_180061A12
0x1800619d9  mov     edx, 5Ch ; '\'; Ch
0x1800619de  mov     rcx, rax; Str
0x1800619e1  call    cs:__imp_wcsrchr
0x1800619e7  mov     rcx, [rbp+250h+lpMem]; lpFileName
0x1800619eb  test    rax, rax
0x1800619ee  jz      short loc_1800619F6
0x1800619f0  add     rax, 2
0x1800619f4  jmp     short loc_1800619F9
0x1800619f6  mov     rax, rcx
0x1800619f9  mov     [rbp+250h+lpString2], rax
0x1800619fd  call    FormFullPathName
0x180061a02  mov     [rbp+250h+lpString2+8], rax
0x180061a06  test    rax, rax
0x180061a09  jz      short loc_180061A12
0x180061a0b  mov     edi, 1
0x180061a10  jmp     short loc_180061A1F
0x180061a12  lea     rcx, [rsp+350h+var_2F0]; void *
0x180061a17  mov     edi, r15d
0x180061a1a  call    FreeWdslibFindData
0x180061a1f  cmp     edi, 1
0x180061a22  jnz     loc_180061AD4
0x180061a28  test    byte ptr [rsp+350h+var_2F0], 10h
0x180061a2d  jz      short loc_180061AAB
0x180061a2f  mov     r15, [rbp+250h+var_2B0]
0x180061a33  test    r15, r15
0x180061a36  jz      loc_180061AD4
0x180061a3c  mov     rax, [rbp+250h+lpString2]
0x180061a40  lea     r8, asc_18007E4DC; "."
0x180061a47  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180061a4c  mov     r9d, r12d; cchCount1
0x180061a4f  mov     edx, edi; dwCmpFlags
0x180061a51  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180061a56  mov     ecx, 409h; Locale
0x180061a5b  call    cs:__imp_CompareStringW
0x180061a61  cmp     eax, 2
0x180061a64  jz      short loc_180061AD4
0x180061a66  mov     rax, [rbp+250h+lpString2]
0x180061a6a  lea     r8, asc_18007D9DC; ".."
0x180061a71  mov     dword ptr [rsp+350h+pcchRemaining], r12d; cchCount2
0x180061a76  mov     r9d, r12d; cchCount1
0x180061a79  mov     edx, edi; dwCmpFlags
0x180061a7b  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180061a80  mov     ecx, 409h; Locale
0x180061a85  call    cs:__imp_CompareStringW
0x180061a8b  cmp     eax, 2
0x180061a8e  jz      short loc_180061AD4
0x180061a90  mov     r8, [rsp+350h+var_2F8]
0x180061a95  lea     rcx, [rsp+350h+var_2F0]
0x180061a9a  mov     rdx, [rsp+350h+var_300]
0x180061a9f  mov     rax, r15
0x180061aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061aa7  mov     edi, eax
0x180061aa9  jmp     short loc_180061AD4
0x180061aab  mov     rax, [rsp+350h+var_300]
0x180061ab0  test    rax, rax
0x180061ab3  jz      short loc_180061AD4
0x180061ab5  mov     rdx, [rsp+350h+var_2F8]
0x180061aba  lea     rcx, [rsp+350h+var_2F0]
0x180061abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ac4  jmp     short loc_180061AA7
0x180061ac6  mov     ecx, 57h ; 'W'; dwErrCode
0x180061acb  call    cs:__imp_SetLastError
0x180061ad1  mov     edi, r15d
0x180061ad4  mov     r15, [rbp+250h+lpMem]
0x180061ad8  test    r15, r15
0x180061adb  jz      short loc_180061AFD
0x180061add  call    cs:__imp_GetProcessHeap
0x180061ae3  mov     r8, r15; lpMem
0x180061ae6  xor     edx, edx; dwFlags
0x180061ae8  mov     rcx, rax; hHeap
0x180061aeb  call    cs:__imp_HeapFree
0x180061af1  test    eax, eax
0x180061af3  jz      short loc_180061AFD
0x180061af5  mov     [rbp+250h+lpMem], 0
0x180061afd  mov     r15, [rbp+250h+lpString2+8]
0x180061b01  test    r15, r15
0x180061b04  jz      short loc_180061B1A
0x180061b06  call    cs:__imp_GetProcessHeap
0x180061b0c  mov     r8, r15; lpMem
0x180061b0f  xor     edx, edx; dwFlags
0x180061b11  mov     rcx, rax; hHeap
0x180061b14  call    cs:__imp_HeapFree
0x180061b1a  xor     edx, edx; Val
0x180061b1c  lea     rcx, [rsp+350h+var_2F0]; void *
0x180061b21  lea     r8d, [rdx+40h]; Size
0x180061b25  call    memset_0
0x180061b2a  cmp     edi, 1
0x180061b2d  jnz     short loc_180061B6D
0x180061b2f  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x180061b34  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180061b38  call    cs:__imp_FindNextFileW
0x180061b3e  lea     r15d, [rdi-1]
0x180061b42  cmp     eax, edi
0x180061b44  jz      loc_18006197B
0x180061b4a  call    cs:__imp_GetLastError
0x180061b50  cmp     eax, 12h
0x180061b53  jnz     short loc_180061B5E
0x180061b55  mov     edi, r15d
0x180061b58  lea     r13d, [r15+1]
0x180061b5c  jmp     short loc_180061B94
0x180061b5e  call    cs:__imp_GetLastError
0x180061b64  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x180061b6b  jmp     short loc_180061B7A
0x180061b6d  call    cs:__imp_GetLastError
0x180061b73  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x180061b7a  mov     r9, rbx
0x180061b7d  mov     dword ptr [rsp+350h+ppszDestEnd], eax
0x180061b81  mov     edx, 2000000h
0x180061b86  lea     rcx, g_WdsLibLog
0x180061b8d  mov     edi, eax
0x180061b8f  call    LibLog
0x180061b94  mov     rcx, [rsp+350h+cchDest]; hFindFile
0x180061b99  call    cs:__imp_FindClose
  ... truncated ...
```
