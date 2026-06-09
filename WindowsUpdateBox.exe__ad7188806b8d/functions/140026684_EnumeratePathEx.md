# EnumeratePathEx

- ea: `0x140026684`
- end: `0x140026da7`
- name: `EnumeratePathEx`
- size: `1827`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64), __int64 (__fastcall *)(DWORD *, __int64), __int64, char)`
- caller_count: `7`
- callee_count: `13`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140025770`
- `0x1400258e4`
- `0x140025c80`
- `0x140025f90`
- `0x1400265f0`
- `0x140055684`
- `0x140057a08`

## callees

- `0x140002116`
- `0x1400222e8`
- `0x140022960`
- `0x140022c14`
- `0x140026684`
- `0x140026df0`
- `0x140026e88`
- `0x14002732c`
- `0x1400273e4`
- `0x140027f0c`
- `0x140028144`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140026b4e`
- `KERNEL32!HeapFree` at `0x140026b7f`
- `KERNEL32!HeapFree` at `0x140026c44`
- `KERNEL32!HeapFree` at `0x140026c69`
- `KERNEL32!HeapFree` at `0x140026b4e`
- `KERNEL32!HeapFree` at `0x140026b7f`
- `KERNEL32!HeapFree` at `0x140026c44`
- `KERNEL32!HeapFree` at `0x140026c69`
- `KERNEL32!GetProcessHeap` at `0x140026b3a`
- `KERNEL32!GetProcessHeap` at `0x140026b6b`
- `KERNEL32!GetProcessHeap` at `0x140026c30`
- `KERNEL32!GetProcessHeap` at `0x140026c55`
- `KERNEL32!GetProcessHeap` at `0x140026b3a`
- `KERNEL32!GetProcessHeap` at `0x140026b6b`
- `KERNEL32!GetProcessHeap` at `0x140026c30`
- `KERNEL32!GetProcessHeap` at `0x140026c55`
- `KERNEL32!GetLastError` at `0x14002677d`
- `KERNEL32!GetLastError` at `0x140026bbe`
- `KERNEL32!GetLastError` at `0x140026bd5`
- `KERNEL32!GetLastError` at `0x140026bea`
- `KERNEL32!GetLastError` at `0x140026c8b`
- `KERNEL32!GetLastError` at `0x140026d2e`
- `KERNEL32!GetLastError` at `0x14002677d`
- `KERNEL32!GetLastError` at `0x140026bbe`
- `KERNEL32!GetLastError` at `0x140026bd5`
- `KERNEL32!GetLastError` at `0x140026bea`
- `KERNEL32!GetLastError` at `0x140026c8b`
- `KERNEL32!GetLastError` at `0x140026d2e`
- `KERNEL32!FindFirstFileW` at `0x140026963`
- `KERNEL32!FindFirstFileW` at `0x140026963`
- `KERNEL32!FindClose` at `0x140026c1b`
- `KERNEL32!FindClose` at `0x140026c1b`
- `KERNEL32!FindNextFileW` at `0x140026baa`
- `KERNEL32!FindNextFileW` at `0x140026baa`
- `KERNEL32!SetLastError` at `0x14002676a`
- `KERNEL32!SetLastError` at `0x140026b25`
- `KERNEL32!SetLastError` at `0x140026c78`
- `KERNEL32!SetLastError` at `0x140026d75`
- `KERNEL32!SetLastError` at `0x14002676a`
- `KERNEL32!SetLastError` at `0x140026b25`
- `KERNEL32!SetLastError` at `0x140026c78`
- `KERNEL32!SetLastError` at `0x140026d75`
- `KERNEL32!CompareStringW` at `0x140026aa8`
- `KERNEL32!CompareStringW` at `0x140026adb`
- `KERNEL32!CompareStringW` at `0x140026aa8`
- `KERNEL32!CompareStringW` at `0x140026adb`
- `msvcrt!wcsrchr` at `0x140026a20`
- `msvcrt!wcsrchr` at `0x140026a20`
- `ntdll!RtlFreeHeap` at `0x140026d0a`
- `ntdll!RtlFreeHeap` at `0x140026d0a`
- `ntdll!RtlAllocateHeap` at `0x140026818`
- `ntdll!RtlAllocateHeap` at `0x140026818`

## string_xrefs

- `0x1400267a5`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x140026be1`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x140026bf6`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x140026d3d`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x140026c9a`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x140026cd3`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

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
  const WCHAR *v6; // r13
  DWORD v7; // r15d
  DWORD LastError; // ebx
  DWORD v10; // ecx
  unsigned __int64 v11; // r12
  __int64 v12; // rbx
  int v13; // esi
  wchar_t *Heap; // rdi
  HRESULT v15; // eax
  unsigned __int16 v16; // bx
  HRESULT v17; // eax
  size_t v18; // rcx
  STRSAFE_LPWSTR v19; // rdx
  size_t v20; // r8
  signed __int64 v21; // r9
  wchar_t v22; // ax
  STRSAFE_LPWSTR v23; // rax
  signed int v24; // eax
  const WCHAR *v25; // rax
  WCHAR *v26; // rbx
  void *v27; // r13
  int v28; // edi
  void *v29; // rax
  wchar_t *v30; // rax
  const WCHAR *v31; // rax
  __int64 (__fastcall *v32)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // rsi
  int v33; // eax
  void *v34; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v36; // rsi
  HANDLE v37; // rax
  DWORD v38; // eax
  const wchar_t *v39; // r8
  void *v40; // rsi
  unsigned int v41; // edi
  HANDLE v42; // rax
  HANDLE v43; // rax
  STRSAFE_LPWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  DWORD v45; // [rsp+30h] [rbp-D0h]
  DWORD v46; // [rsp+30h] [rbp-D0h]
  STRSAFE_LPWSTR pszDest; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcchRemaining; // [rsp+48h] [rbp-B8h] BYREF
  int v49; // [rsp+50h] [rbp-B0h]
  size_t cchDest; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall *v51)(DWORD *, __int64); // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v53)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+70h] [rbp-90h]
  DWORD dwFileAttributes; // [rsp+80h] [rbp-80h] BYREF
  FILETIME ftCreationTime; // [rsp+84h] [rbp-7Ch]
  FILETIME ftLastAccessTime; // [rsp+8Ch] [rbp-74h]
  FILETIME ftLastWriteTime; // [rsp+94h] [rbp-6Ch]
  int v58; // [rsp+9Ch] [rbp-64h]
  unsigned __int64 v59; // [rsp+A0h] [rbp-60h]
  LPVOID lpMem; // [rsp+A8h] [rbp-58h]
  PCNZWCH lpString2[2]; // [rsp+B0h] [rbp-50h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  v51 = a3;
  v53 = a2;
  v52 = a4;
  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v49 = 0;
  v7 = 0;
  LODWORD(pcchRemaining) = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 87;
    goto LABEL_84;
  }
  if ( !(unsigned int)ReparsePointExists(lpFileName, &pcchRemaining) || !(_DWORD)pcchRemaining )
    goto LABEL_15;
  LODWORD(pszDest) = 0;
  if ( (a5 & 2) != 0 )
    goto LABEL_11;
  if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &pszDest) && (_DWORD)pszDest )
    goto LABEL_15;
  LODWORD(pszDest) = 0;
  if ( (a5 & 1) != 0 )
  {
LABEL_11:
    SetLastError(0);
    return 1;
  }
  if ( !(unsigned int)GetReparseTag(lpFileName) )
  {
    LastError = GetLastError();
    if ( !(unsigned int)ReparsePointExists(lpFileName, &pcchRemaining) || !(_DWORD)pcchRemaining )
      goto LABEL_15;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
      LastError);
    v10 = LastError;
LABEL_84:
    SetLastError(v10);
    return 0;
  }
  if ( (_DWORD)pszDest != -2147483640 )
    goto LABEL_11;
LABEL_15:
  v11 = -1;
  pszDest = 0;
  v12 = -1;
  pcchRemaining = 0;
  v13 = 0;
  do
    ++v12;
  while ( lpFileName[v12] );
  if ( (_DWORD)v12 && lpFileName[(unsigned int)(v12 - 1)] != 92 )
    v13 = 1;
  cchDest = (unsigned int)(v12 + v13 + 2);
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * cchDest);
  if ( !Heap )
  {
    Heap = 0;
    NtCurrentTeb()->LastErrorValue = 8;
    goto LABEL_81;
  }
  v15 = StringCchCopyNExW(Heap, cchDest, lpFileName, (unsigned int)v12, &pszDest, &pcchRemaining, v45);
  v16 = v15;
  if ( v15 < 0 )
    goto LABEL_80;
  if ( v13 )
  {
    v17 = StringCchCopyNExW(pszDest, pcchRemaining, L"\\", 1u, &pszDest, &pcchRemaining, v46);
    v16 = v17;
    if ( v17 < 0 )
      goto LABEL_80;
  }
  v18 = pcchRemaining;
  if ( pcchRemaining - 1 > 0x7FFFFFFE )
  {
    v16 = 87;
    v24 = -2147024809;
    if ( pcchRemaining )
    {
      *pszDest = 0;
      goto LABEL_80;
    }
  }
  else
  {
    v19 = pszDest;
    if ( pcchRemaining )
    {
      v20 = 1 - pcchRemaining;
      v21 = (char *)L"*" - (char *)pszDest;
      do
      {
        if ( !(v20 + v18) )
          break;
        v22 = *(STRSAFE_LPWSTR)((char *)v19 + v21);
        if ( !v22 )
          break;
        *v19++ = v22;
        --v18;
      }
      while ( v18 );
    }
    v23 = v19 - 1;
    if ( v18 )
      v23 = v19;
    *v23 = 0;
    v24 = v18 == 0 ? 0x8007007A : 0;
  }
  v16 = v24;
  if ( v24 < 0 )
  {
LABEL_80:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    Heap = 0;
    NtCurrentTeb()->LastErrorValue = v16;
LABEL_81:
    v26 = (WCHAR *)v6;
    v40 = Heap;
    LODWORD(ppszDestEnd) = GetLastError();
    v7 = (unsigned int)ppszDestEnd;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      ppszDestEnd);
    v41 = 0;
    if ( v40 )
      goto LABEL_72;
    goto LABEL_73;
  }
  pcchRemaining = (size_t)Heap;
  NtCurrentTeb()->LastErrorValue = 0;
  v25 = (const WCHAR *)PrepareUnicodePathEx(Heap);
  v26 = (WCHAR *)v25;
  v6 = v25;
  if ( !v25 )
    goto LABEL_81;
  cchDest = (size_t)FindFirstFileW(v25, &FindFileData);
  if ( cchDest == -1 )
  {
    LODWORD(ppszDestEnd) = GetLastError();
    v7 = (unsigned int)ppszDestEnd;
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v6, ppszDestEnd);
    do
      ++v11;
    while ( v26[v11] );
    v40 = Heap;
    if ( v11 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v7 = 206;
    }
    goto LABEL_71;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  v27 = (void *)cchDest;
  do
  {
    v28 = 0;
    pszDest = 0;
    if ( !*lpFileName )
    {
      SetLastError(0x57u);
      goto LABEL_58;
    }
    dwFileAttributes = FindFileData.dwFileAttributes;
    ftCreationTime = FindFileData.ftCreationTime;
    ftLastAccessTime = FindFileData.ftLastAccessTime;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    pszDest = (STRSAFE_LPWSTR)__PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
    v59 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
    v58 = 0;
    lpMem = 0;
    *(_OWORD *)lpString2 = 0;
    v29 = (void *)BuildPath(lpFileName);
    lpMem = v29;
    if ( v29
      && ((v30 = wcsrchr((const wchar_t *)v29, 0x5Cu)) == 0 ? (v31 = (const WCHAR *)lpMem) : (v31 = v30 + 1),
          lpString2[0] = v31,
          (lpString2[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem, 0)) != 0) )
    {
      v28 = 1;
    }
    else
    {
      FreeWdslibFindData(&dwFileAttributes);
    }
    if ( v28 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v51 )
          goto LABEL_58;
        v33 = v51(&dwFileAttributes, v52);
        goto LABEL_54;
      }
      v32 = v53;
      if ( v53
        && CompareStringW(0x409u, 1u, L".", -1, lpString2[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, lpString2[0], -1) != 2 )
      {
        v33 = v32(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v51, v52);
LABEL_54:
        v28 = v33;
      }
    }
LABEL_58:
    v34 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      if ( HeapFree(ProcessHeap, 0, v34) )
        lpMem = 0;
    }
    v36 = (WCHAR *)lpString2[1];
    if ( lpString2[1] )
    {
      v37 = GetProcessHeap();
      HeapFree(v37, 0, v36);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v28 != 1 )
    {
      v38 = GetLastError();
      v39 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_69;
    }
  }
  while ( FindNextFileW(v27, &FindFileData) );
  if ( GetLastError() == 18 )
  {
    v49 = 1;
    goto LABEL_70;
  }
  v38 = GetLastError();
  v39 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_69:
  LODWORD(ppszDestEnd) = v38;
  v7 = v38;
  LibLog(&g_WdsLibLog, 0x2000000, v39, v26, ppszDestEnd);
LABEL_70:
  FindClose(v27);
  v40 = (void *)pcchRemaining;
LABEL_71:
  v41 = v49;
LABEL_72:
  v42 = GetProcessHeap();
  HeapFree(v42, 0, v40);
LABEL_73:
  if ( v26 )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v26);
  }
  SetLastError(v7);
  return v41;
}

```

## disassembly

```asm
0x140026684  push    rbp
0x140026686  push    rbx
0x140026687  push    rsi
0x140026688  push    rdi
0x140026689  push    r12
0x14002668b  push    r13
0x14002668d  push    r14
0x14002668f  push    r15
0x140026691  lea     rbp, [rsp-228h]
0x140026699  sub     rsp, 328h
0x1400266a0  mov     rax, cs:__security_cookie
0x1400266a7  xor     rax, rsp
0x1400266aa  mov     [rbp+260h+var_50], rax
0x1400266b1  mov     [rsp+360h+var_300], r8
0x1400266b6  mov     r14, rcx
0x1400266b9  mov     [rsp+360h+var_2F0], rdx
0x1400266be  lea     rcx, [rbp+260h+FindFileData]; void *
0x1400266c2  xor     edi, edi
0x1400266c4  mov     [rsp+360h+var_2F8], r9
0x1400266c9  xor     edx, edx; Val
0x1400266cb  mov     r8d, 250h; Size
0x1400266d1  mov     r13d, edi
0x1400266d4  call    memset_0
0x1400266d9  mov     [rsp+360h+var_310], edi
0x1400266dd  mov     r15d, edi
0x1400266e0  mov     dword ptr [rsp+360h+var_318], edi
0x1400266e4  test    r14, r14
0x1400266e7  jz      loc_140026D70
0x1400266ed  cmp     di, [r14]
0x1400266f1  jz      loc_140026D70
0x1400266f7  lea     rdx, [rsp+360h+var_318]
0x1400266fc  mov     rcx, r14
0x1400266ff  call    ReparsePointExists
0x140026704  lea     esi, [rdi+1]
0x140026707  test    eax, eax
0x140026709  jz      loc_1400267C4
0x14002670f  cmp     dword ptr [rsp+360h+var_318], edi
0x140026713  jz      loc_1400267C4
0x140026719  mov     ebx, [rbp+260h+arg_20]
0x14002671f  mov     dword ptr [rsp+360h+pszDest], edi
0x140026723  test    bl, 2
0x140026726  jnz     short loc_140026768
0x140026728  lea     rdx, [rsp+360h+pszDest]
0x14002672d  mov     rcx, r14
0x140026730  call    ShouldEnumerateReparsePoint
0x140026735  test    eax, eax
0x140026737  jz      short loc_140026743
0x140026739  cmp     dword ptr [rsp+360h+pszDest], edi
0x14002673d  jnz     loc_1400267C4
0x140026743  and     ebx, esi
0x140026745  mov     dword ptr [rsp+360h+pszDest], edi
0x140026749  test    bl, bl
0x14002674b  jnz     short loc_140026768
0x14002674d  lea     rdx, [rsp+360h+pszDest]
0x140026752  mov     rcx, r14; lpFileName
0x140026755  call    GetReparseTag
0x14002675a  test    eax, eax
0x14002675c  jz      short loc_14002677D
0x14002675e  cmp     dword ptr [rsp+360h+pszDest], 80000008h
0x140026766  jz      short loc_1400267C4
0x140026768  xor     ecx, ecx; dwErrCode
0x14002676a  call    cs:__imp_SetLastError
0x140026771  nop     dword ptr [rax+rax+00h]
0x140026776  mov     eax, esi
0x140026778  jmp     loc_140026D83
0x14002677d  call    cs:__imp_GetLastError
0x140026784  nop     dword ptr [rax+rax+00h]
0x140026789  lea     rdx, [rsp+360h+var_318]
0x14002678e  mov     rcx, r14
0x140026791  mov     ebx, eax
0x140026793  call    ReparsePointExists
0x140026798  test    eax, eax
0x14002679a  jz      short loc_1400267C4
0x14002679c  cmp     dword ptr [rsp+360h+var_318], edi
0x1400267a0  jz      short loc_1400267C4
0x1400267a2  mov     r9d, ebx
0x1400267a5  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x1400267ac  mov     edx, 2000000h
0x1400267b1  lea     rcx, g_WdsLibLog
0x1400267b8  call    LibLog
0x1400267bd  mov     ecx, ebx
0x1400267bf  jmp     loc_140026D75
0x1400267c4  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400267c8  mov     [rsp+360h+pszDest], rdi
0x1400267cd  mov     rbx, r12
0x1400267d0  mov     [rsp+360h+var_318], rdi
0x1400267d5  mov     esi, edi
0x1400267d7  inc     rbx
0x1400267da  cmp     [r14+rbx*2], di
0x1400267df  jnz     short loc_1400267D7
0x1400267e1  mov     edx, 5Ch ; '\'
0x1400267e6  test    ebx, ebx
0x1400267e8  jz      short loc_1400267F8
0x1400267ea  lea     eax, [rbx-1]
0x1400267ed  cmp     dx, [r14+rax*2]
0x1400267f2  lea     eax, [rdx-5Bh]
0x1400267f5  cmovnz  esi, eax
0x1400267f8  mov     rcx, gs:60h
0x140026801  lea     eax, [rsi+2]
0x140026804  add     eax, ebx
0x140026806  mov     edx, 8; Flags
0x14002680b  mov     [rsp+360h+cchDest], rax
0x140026810  mov     rcx, [rcx+30h]; HeapHandle
0x140026814  lea     r8, [rax+rax]; Size
0x140026818  call    cs:__imp_RtlAllocateHeap
0x14002681f  nop     dword ptr [rax+rax+00h]
0x140026824  xor     ecx, ecx
0x140026826  mov     rdi, rax
0x140026829  test    rax, rax
0x14002682c  jnz     short loc_140026845
0x14002682e  mov     rax, gs:30h
0x140026837  mov     edi, ecx
0x140026839  mov     dword ptr [rax+68h], 8
0x140026840  jmp     loc_140026D28
0x140026845  mov     rdx, [rsp+360h+cchDest]; cchDest
0x14002684a  lea     rax, [rsp+360h+var_318]
0x14002684f  mov     [rsp+360h+pcchRemaining], rax; pcchRemaining
0x140026854  mov     r8, r14; pszSrc
0x140026857  lea     rax, [rsp+360h+pszDest]
0x14002685c  mov     r9d, ebx; cchToCopy
0x14002685f  mov     rcx, rdi; pszDest
0x140026862  mov     [rsp+360h+ppszDestEnd], rax; ppszDestEnd
0x140026867  call    StringCchCopyNExW
0x14002686c  mov     ebx, eax
0x14002686e  test    eax, eax
0x140026870  js      loc_140026CF6
0x140026876  test    esi, esi
0x140026878  jz      short loc_1400268B8
0x14002687a  mov     rdx, [rsp+360h+var_318]; cchDest
0x14002687f  lea     rax, [rsp+360h+var_318]
0x140026884  mov     rcx, [rsp+360h+pszDest]; pszDest
0x140026889  lea     r8, pszSrc; "\\"
0x140026890  mov     [rsp+360h+pcchRemaining], rax; pcchRemaining
0x140026895  mov     r9d, 1; cchToCopy
0x14002689b  lea     rax, [rsp+360h+pszDest]
0x1400268a0  mov     [rsp+360h+ppszDestEnd], rax; ppszDestEnd
0x1400268a5  call    StringCchCopyNExW
0x1400268aa  xor     esi, esi
0x1400268ac  mov     ebx, eax
0x1400268ae  test    eax, eax
0x1400268b0  js      loc_140026CF8
0x1400268b6  jmp     short loc_1400268BA
0x1400268b8  xor     esi, esi
0x1400268ba  mov     rcx, [rsp+360h+var_318]
0x1400268bf  lea     rax, [rcx-1]
0x1400268c3  cmp     rax, 7FFFFFFEh
0x1400268c9  ja      loc_140026993
0x1400268cf  mov     rdx, [rsp+360h+pszDest]
0x1400268d4  test    rcx, rcx
0x1400268d7  jz      short loc_14002690E
0x1400268d9  mov     r10d, 1
0x1400268df  lea     r9, asc_140088250; "*"
0x1400268e6  mov     r8d, r10d
0x1400268e9  sub     r8, rcx
0x1400268ec  sub     r9, rdx
0x1400268ef  lea     rax, [r8+rcx]
0x1400268f3  test    rax, rax
0x1400268f6  jz      short loc_14002690E
0x1400268f8  movzx   eax, word ptr [r9+rdx]
0x1400268fd  test    ax, ax
0x140026900  jz      short loc_14002690E
0x140026902  mov     [rdx], ax
0x140026905  add     rdx, 2
0x140026909  sub     rcx, r10
0x14002690c  jnz     short loc_1400268EF
0x14002690e  test    rcx, rcx
0x140026911  lea     rax, [rdx-2]
0x140026915  cmovnz  rax, rdx
0x140026919  neg     rcx
0x14002691c  mov     [rax], si
0x14002691f  sbb     eax, eax
0x140026921  not     eax
0x140026923  and     eax, 8007007Ah
0x140026928  mov     ebx, eax
0x14002692a  test    eax, eax
0x14002692c  js      loc_140026CF8
0x140026932  mov     rax, gs:30h
0x14002693b  xor     edx, edx
0x14002693d  mov     rcx, rdi; unsigned __int16 *
0x140026940  mov     [rsp+360h+var_318], rdi
0x140026945  mov     [rax+68h], esi
0x140026948  call    PrepareUnicodePathEx
0x14002694d  mov     rbx, rax
0x140026950  mov     r13, rax
0x140026953  test    rax, rax
0x140026956  jz      loc_140026D28
0x14002695c  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x140026960  mov     rcx, rax; lpFileName
0x140026963  call    cs:__imp_FindFirstFileW
0x14002696a  nop     dword ptr [rax+rax+00h]
0x14002696f  mov     [rsp+360h+cchDest], rax
0x140026974  cmp     rax, r12
0x140026977  jz      loc_140026C8B
0x14002697d  xor     edx, edx; Val
0x14002697f  lea     rcx, [rbp+260h+var_2E0]; void *
0x140026983  lea     r8d, [rdx+40h]; Size
0x140026987  call    memset_0
0x14002698c  mov     r13, [rsp+360h+cchDest]
0x140026991  jmp     short loc_1400269AE
0x140026993  mov     ebx, 80070057h
0x140026998  mov     eax, ebx
0x14002699a  test    rcx, rcx
0x14002699d  jz      short loc_140026928
0x14002699f  mov     rax, [rsp+360h+pszDest]
0x1400269a4  mov     [rax], si
0x1400269a7  jmp     loc_140026CF8
0x1400269ac  xor     esi, esi
0x1400269ae  mov     edi, esi
0x1400269b0  mov     [rsp+360h+pszDest], rsi
0x1400269b5  cmp     si, [r14]
0x1400269b9  jz      loc_140026B20
0x1400269bf  mov     eax, [rbp+260h+FindFileData.dwFileAttributes]
0x1400269c2  lea     rdx, [rbp+260h+FindFileData.cFileName]
0x1400269c6  mov     [rbp+260h+var_2E0], eax
0x1400269c9  xorps   xmm0, xmm0
0x1400269cc  mov     rax, qword ptr [rbp+260h+FindFileData.ftCreationTime.dwLowDateTime]
0x1400269d0  mov     rcx, r14; pszSrc
0x1400269d3  mov     [rbp+260h+var_2DC], rax
0x1400269d7  mov     rax, qword ptr [rbp+260h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x1400269db  mov     [rbp+260h+var_2D4], rax
0x1400269df  mov     rax, qword ptr [rbp+260h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1400269e3  mov     [rbp+260h+var_2CC], rax
0x1400269e7  mov     eax, [rbp+260h+FindFileData.nFileSizeHigh]
0x1400269ea  mov     dword ptr [rsp+360h+pszDest+4], eax
0x1400269ee  mov     eax, [rbp+260h+FindFileData.nFileSizeLow]
0x1400269f1  mov     dword ptr [rsp+360h+pszDest], eax
0x1400269f5  mov     rax, [rsp+360h+pszDest]
0x1400269fa  mov     [rbp+260h+var_2C0], rax
0x1400269fe  mov     [rbp+260h+var_2C4], esi
0x140026a01  mov     [rbp+260h+lpMem], rsi
0x140026a05  movdqa  xmmword ptr [rbp+260h+lpString2], xmm0
0x140026a0a  call    BuildPath
0x140026a0f  mov     [rbp+260h+lpMem], rax
0x140026a13  test    rax, rax
0x140026a16  jz      short loc_140026A5B
0x140026a18  mov     edx, 5Ch ; '\'; Ch
0x140026a1d  mov     rcx, rax; Str
0x140026a20  call    cs:__imp_wcsrchr
0x140026a27  nop     dword ptr [rax+rax+00h]
0x140026a2c  mov     rcx, [rbp+260h+lpMem]; lpFileName
0x140026a30  test    rax, rax
0x140026a33  jz      short loc_140026A3B
0x140026a35  add     rax, 2
0x140026a39  jmp     short loc_140026A3E
0x140026a3b  mov     rax, rcx
0x140026a3e  xor     edx, edx; lpFilePart
0x140026a40  mov     [rbp+260h+lpString2], rax
0x140026a44  call    FormFullPathName
0x140026a49  mov     [rbp+260h+lpString2+8], rax
0x140026a4d  test    rax, rax
0x140026a50  jz      short loc_140026A5B
0x140026a52  mov     ecx, 1
0x140026a57  mov     edi, ecx
0x140026a59  jmp     short loc_140026A69
0x140026a5b  lea     rcx, [rbp+260h+var_2E0]; void *
0x140026a5f  call    FreeWdslibFindData
0x140026a64  mov     ecx, 1
0x140026a69  cmp     edi, ecx
0x140026a6b  jnz     loc_140026B31
0x140026a71  test    byte ptr [rbp+260h+var_2E0], 10h
0x140026a75  jz      loc_140026B06
0x140026a7b  mov     rsi, [rsp+360h+var_2F0]
0x140026a80  test    rsi, rsi
0x140026a83  jz      loc_140026B31
0x140026a89  mov     rax, [rbp+260h+lpString2]
0x140026a8d  lea     r8, asc_1400865F4; "."
0x140026a94  mov     edx, ecx; dwCmpFlags
0x140026a96  mov     dword ptr [rsp+360h+pcchRemaining], r12d; cchCount2
0x140026a9b  mov     ecx, 409h; Locale
0x140026aa0  mov     [rsp+360h+ppszDestEnd], rax; lpString2
0x140026aa5  mov     r9d, r12d; cchCount1
0x140026aa8  call    cs:__imp_CompareStringW
0x140026aaf  nop     dword ptr [rax+rax+00h]
0x140026ab4  cmp     eax, 2
0x140026ab7  jz      short loc_140026B31
0x140026ab9  mov     rax, [rbp+260h+lpString2]
0x140026abd  lea     r8, asc_140088254; ".."
0x140026ac4  mov     dword ptr [rsp+360h+pcchRemaining], r12d; cchCount2
0x140026ac9  mov     r9d, r12d; cchCount1
0x140026acc  mov     edx, 1; dwCmpFlags
0x140026ad1  mov     [rsp+360h+ppszDestEnd], rax; lpString2
0x140026ad6  mov     ecx, 409h; Locale
0x140026adb  call    cs:__imp_CompareStringW
0x140026ae2  nop     dword ptr [rax+rax+00h]
0x140026ae7  cmp     eax, 2
0x140026aea  jz      short loc_140026B31
0x140026aec  mov     r8, [rsp+360h+var_2F8]
0x140026af1  lea     rcx, [rbp+260h+var_2E0]
0x140026af5  mov     rdx, [rsp+360h+var_300]
0x140026afa  mov     rax, rsi
0x140026afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b02  mov     edi, eax
0x140026b04  jmp     short loc_140026B31
0x140026b06  mov     rax, [rsp+360h+var_300]
0x140026b0b  test    rax, rax
0x140026b0e  jz      short loc_140026B31
0x140026b10  mov     rdx, [rsp+360h+var_2F8]
0x140026b15  lea     rcx, [rbp+260h+var_2E0]
0x140026b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b1e  jmp     short loc_140026B02
  ... truncated ...
```
