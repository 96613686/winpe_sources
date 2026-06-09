# EnumeratePathEx

- ea: `0x180065c98`
- end: `0x180066145`
- name: `EnumeratePathEx`
- size: `1197`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64), __int64 (__fastcall *)(DWORD *, __int64), __int64, char)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800654d0`
- `0x180065748`

## callees

- `0x1800037c1`
- `0x180065c98`
- `0x18006614c`
- `0x1800661e8`
- `0x18006631c`
- `0x1800663ac`
- `0x18006642c`
- `0x180066f58`
- `0x1800673b0`
- `0x18006865c`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180065f09`
- `KERNEL32!CompareStringW` at `0x180065f33`
- `KERNEL32!CompareStringW` at `0x180065f09`
- `KERNEL32!CompareStringW` at `0x180065f33`
- `KERNEL32!SetLastError` at `0x180065d74`
- `KERNEL32!SetLastError` at `0x180065f77`
- `KERNEL32!SetLastError` at `0x18006610a`
- `KERNEL32!SetLastError` at `0x18006611a`
- `KERNEL32!SetLastError` at `0x180065d74`
- `KERNEL32!SetLastError` at `0x180065f77`
- `KERNEL32!SetLastError` at `0x18006610a`
- `KERNEL32!SetLastError` at `0x18006611a`
- `KERNEL32!GetLastError` at `0x180065d84`
- `KERNEL32!GetLastError` at `0x180065ff4`
- `KERNEL32!GetLastError` at `0x18006600b`
- `KERNEL32!GetLastError` at `0x18006601a`
- `KERNEL32!GetLastError` at `0x180066051`
- `KERNEL32!GetLastError` at `0x1800660ac`
- `KERNEL32!GetLastError` at `0x180065d84`
- `KERNEL32!GetLastError` at `0x180065ff4`
- `KERNEL32!GetLastError` at `0x18006600b`
- `KERNEL32!GetLastError` at `0x18006601a`
- `KERNEL32!GetLastError` at `0x180066051`
- `KERNEL32!GetLastError` at `0x1800660ac`
- `KERNEL32!HeapFree` at `0x180065f95`
- `KERNEL32!HeapFree` at `0x180065fbe`
- `KERNEL32!HeapFree` at `0x1800660e9`
- `KERNEL32!HeapFree` at `0x180066102`
- `KERNEL32!HeapFree` at `0x180065f95`
- `KERNEL32!HeapFree` at `0x180065fbe`
- `KERNEL32!HeapFree` at `0x1800660e9`
- `KERNEL32!HeapFree` at `0x180066102`
- `KERNEL32!GetProcessHeap` at `0x180065f87`
- `KERNEL32!GetProcessHeap` at `0x180065fb0`
- `KERNEL32!GetProcessHeap` at `0x1800660db`
- `KERNEL32!GetProcessHeap` at `0x1800660f4`
- `KERNEL32!GetProcessHeap` at `0x180065f87`
- `KERNEL32!GetProcessHeap` at `0x180065fb0`
- `KERNEL32!GetProcessHeap` at `0x1800660db`
- `KERNEL32!GetProcessHeap` at `0x1800660f4`
- `KERNEL32!FindClose` at `0x180066046`
- `KERNEL32!FindClose` at `0x180066046`
- `KERNEL32!FindFirstFileW` at `0x180065e04`
- `KERNEL32!FindFirstFileW` at `0x180065e04`
- `KERNEL32!FindNextFileW` at `0x180065fe2`
- `KERNEL32!FindNextFileW` at `0x180065fe2`

## string_xrefs

- `0x180065da7`: `EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x`
- `0x180066020`: `EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x`
- `0x180066011`: `EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x`
- `0x18006605a`: `EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x`
- `0x1800660b5`: `EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x`
- `0x18006608d`: `EnumeratePathEx: Failed search path is >= MAX_PATH!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnumeratePathEx(
        LPCWSTR lpFileName,
        __int64 (__fastcall *a2)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64),
        __int64 (__fastcall *a3)(DWORD *, __int64),
        __int64 a4,
        char a5)
{
  __int64 (__fastcall *v5)(DWORD *, __int64); // r15
  DWORD LastError; // ebx
  DWORD v9; // ecx
  WCHAR *v10; // rdi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r12
  const WCHAR *v13; // rax
  unsigned int v14; // r13d
  unsigned __int64 v15; // r14
  int v16; // ebx
  void *v17; // rax
  wchar_t *v18; // rax
  const WCHAR *v19; // rax
  int v20; // eax
  void *v21; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v23; // r15
  HANDLE v24; // rax
  BOOL NextFileW; // eax
  DWORD v26; // ebx
  DWORD v27; // eax
  const wchar_t *v28; // r8
  HANDLE v29; // rax
  HANDLE v30; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall *v34)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64); // [rsp+40h] [rbp-C0h]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  DWORD dwFileAttributes; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME ftCreationTime; // [rsp+54h] [rbp-ACh]
  FILETIME ftLastAccessTime; // [rsp+5Ch] [rbp-A4h]
  FILETIME ftLastWriteTime; // [rsp+64h] [rbp-9Ch]
  int v40; // [rsp+6Ch] [rbp-94h]
  DWORD nFileSizeLow; // [rsp+70h] [rbp-90h]
  DWORD nFileSizeHigh; // [rsp+74h] [rbp-8Ch]
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  PCNZWCH v44[2]; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v45)(DWORD *, __int64); // [rsp+90h] [rbp-70h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v5 = a3;
  v45 = a3;
  v34 = a2;
  v35 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v32 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v9 = 87;
    goto LABEL_60;
  }
  if ( (unsigned int)ReparsePointExists(lpFileName, &v32) && v32 )
  {
    LODWORD(hFindFile) = 0;
    if ( (a5 & 2) != 0 )
      goto LABEL_11;
    if ( (unsigned int)ShouldEnumerateReparsePoint(lpFileName, &hFindFile) && (_DWORD)hFindFile )
      goto LABEL_15;
    LODWORD(hFindFile) = 0;
    if ( (a5 & 1) != 0 )
    {
LABEL_11:
      SetLastError(0);
      return 1;
    }
    if ( (unsigned int)GetReparseTag(lpFileName) )
    {
      if ( (_DWORD)hFindFile != -2147483640 )
        goto LABEL_11;
      goto LABEL_15;
    }
    LastError = GetLastError();
    if ( (unsigned int)ReparsePointExists(lpFileName, &v32) && v32 )
    {
      LibLog(
        &g_WdsLibLog,
        0x2000000,
        L"EnumeratePathEx: Unable to get reparse tag for persistent reparse point; GLE = 0x%x",
        LastError);
      v9 = LastError;
LABEL_60:
      SetLastError(v9);
      return 0;
    }
  }
LABEL_15:
  v10 = 0;
  v11 = (unsigned __int16 *)BuildPath(lpFileName, L"*");
  v12 = v11;
  if ( !v11 || (v13 = (const WCHAR *)PrepareUnicodePathEx(v11), (v10 = (WCHAR *)v13) == 0) )
  {
    v26 = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"EnumeratePathEx: Unable to construct path under [%s]; GLE = 0x%x",
      lpFileName,
      v26);
    v14 = 0;
    if ( v12 )
      goto LABEL_55;
    goto LABEL_56;
  }
  v14 = 0;
  v15 = -1;
  hFindFile = FindFirstFileW(v13, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v26 = GetLastError();
    LibLog(&g_WdsLibLog, 0x2000000, L"EnumeratePathEx: FindFirstFile failed for [%s]; GLE = 0x%x", v10, v26);
    do
      ++v15;
    while ( v10[v15] );
    if ( v15 >= 0x104 )
    {
      LibLog(&g_WdsLibLog, 50331648, L"EnumeratePathEx: Failed search path is >= MAX_PATH!");
      v26 = 206;
    }
    goto LABEL_55;
  }
  memset_0(&dwFileAttributes, 0, 0x40u);
  do
  {
    v16 = 0;
    if ( !*lpFileName )
    {
      SetLastError(0x57u);
      goto LABEL_37;
    }
    dwFileAttributes = FindFileData.dwFileAttributes;
    ftCreationTime = FindFileData.ftCreationTime;
    ftLastAccessTime = FindFileData.ftLastAccessTime;
    ftLastWriteTime = FindFileData.ftLastWriteTime;
    nFileSizeLow = FindFileData.nFileSizeLow;
    nFileSizeHigh = FindFileData.nFileSizeHigh;
    v40 = 0;
    lpMem = 0;
    *(_OWORD *)v44 = 0;
    v17 = (void *)BuildPath(lpFileName, FindFileData.cFileName);
    lpMem = v17;
    if ( v17
      && ((v18 = wcsrchr_0((const wchar_t *)v17, 0x5Cu)) == 0 ? (v19 = (const WCHAR *)lpMem) : (v19 = v18 + 1),
          v44[0] = v19,
          (v44[1] = (PCNZWCH)FormFullPathName((LPCWSTR)lpMem)) != 0) )
    {
      v16 = 1;
    }
    else
    {
      FreeWdslibFindData(&dwFileAttributes);
    }
    if ( v16 == 1 )
    {
      if ( (dwFileAttributes & 0x10) == 0 )
      {
        if ( !v5 )
          goto LABEL_37;
        v20 = v5(&dwFileAttributes, v35);
        goto LABEL_33;
      }
      if ( v34
        && CompareStringW(0x409u, 1u, L".", -1, v44[0], -1) != 2
        && CompareStringW(0x409u, 1u, L"..", -1, v44[0], -1) != 2 )
      {
        v20 = v34(&dwFileAttributes, (__int64 (__fastcall *)(_QWORD, _QWORD))v5, v35);
LABEL_33:
        v16 = v20;
      }
    }
LABEL_37:
    v21 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      if ( HeapFree(ProcessHeap, 0, v21) )
        lpMem = 0;
    }
    v23 = (WCHAR *)v44[1];
    if ( v44[1] )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
    }
    memset_0(&dwFileAttributes, 0, 0x40u);
    if ( v16 != 1 )
    {
      v27 = GetLastError();
      v28 = L"EnumeratePathEx: Callback requested enumeration interruption or hit internal enumeration failure on [%s]; GLE = 0x%x";
      goto LABEL_48;
    }
    NextFileW = FindNextFileW(hFindFile, &FindFileData);
    v5 = v45;
  }
  while ( NextFileW );
  if ( GetLastError() == 18 )
  {
    v14 = 1;
    v26 = 0;
    goto LABEL_49;
  }
  v27 = GetLastError();
  v28 = L"EnumeratePathEx: Unable to enumerate [%s]; GLE = 0x%x";
LABEL_48:
  LODWORD(lpString2) = v27;
  v26 = v27;
  LibLog(&g_WdsLibLog, 0x2000000, v28, v10, lpString2);
LABEL_49:
  FindClose(hFindFile);
LABEL_55:
  v29 = GetProcessHeap();
  HeapFree(v29, 0, v12);
LABEL_56:
  if ( v10 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v10);
  }
  SetLastError(v26);
  return v14;
}

```

## disassembly

```asm
0x180065c98  push    rbp
0x180065c9a  push    rbx
0x180065c9b  push    rsi
0x180065c9c  push    rdi
0x180065c9d  push    r12
0x180065c9f  push    r13
0x180065ca1  push    r14
0x180065ca3  push    r15
0x180065ca5  lea     rbp, [rsp-208h]
0x180065cad  sub     rsp, 308h
0x180065cb4  mov     rax, cs:__security_cookie
0x180065cbb  xor     rax, rsp
0x180065cbe  mov     [rbp+240h+var_50], rax
0x180065cc5  mov     r15, r8
0x180065cc8  mov     [rbp+240h+var_2B0], r8
0x180065ccc  mov     [rsp+340h+var_300], rdx
0x180065cd1  mov     rsi, rcx
0x180065cd4  xor     edx, edx; Val
0x180065cd6  mov     [rsp+340h+var_2F8], r9
0x180065cdb  mov     r8d, 250h; Size
0x180065ce1  lea     rcx, [rbp+240h+FindFileData]; void *
0x180065ce5  call    memset_0
0x180065cea  xor     r14d, r14d
0x180065ced  mov     [rsp+340h+var_310], r14d
0x180065cf2  test    rsi, rsi
0x180065cf5  jz      loc_180066115
0x180065cfb  cmp     r14w, [rsi]
0x180065cff  jz      loc_180066115
0x180065d05  lea     rdx, [rsp+340h+var_310]
0x180065d0a  mov     rcx, rsi
0x180065d0d  call    ReparsePointExists
0x180065d12  test    eax, eax
0x180065d14  jz      loc_180065DC6
0x180065d1a  cmp     [rsp+340h+var_310], r14d
0x180065d1f  jz      loc_180065DC6
0x180065d25  mov     ebx, [rbp+240h+arg_20]
0x180065d2b  mov     dword ptr [rsp+340h+hFindFile], r14d
0x180065d30  test    bl, 2
0x180065d33  jnz     short loc_180065D72
0x180065d35  lea     rdx, [rsp+340h+hFindFile]
0x180065d3a  mov     rcx, rsi
0x180065d3d  call    ShouldEnumerateReparsePoint
0x180065d42  test    eax, eax
0x180065d44  jz      short loc_180065D4D
0x180065d46  cmp     dword ptr [rsp+340h+hFindFile], r14d
0x180065d4b  jnz     short loc_180065DC6
0x180065d4d  mov     dword ptr [rsp+340h+hFindFile], r14d
0x180065d52  test    bl, 1
0x180065d55  jnz     short loc_180065D72
0x180065d57  lea     rdx, [rsp+340h+hFindFile]
0x180065d5c  mov     rcx, rsi; lpFileName
0x180065d5f  call    GetReparseTag
0x180065d64  test    eax, eax
0x180065d66  jz      short loc_180065D84
0x180065d68  cmp     dword ptr [rsp+340h+hFindFile], 80000008h
0x180065d70  jz      short loc_180065DC6
0x180065d72  xor     ecx, ecx; dwErrCode
0x180065d74  call    cs:__imp_SetLastError
0x180065d7a  mov     eax, 1
0x180065d7f  jmp     loc_180066122
0x180065d84  call    cs:__imp_GetLastError
0x180065d8a  lea     rdx, [rsp+340h+var_310]
0x180065d8f  mov     rcx, rsi
0x180065d92  mov     ebx, eax
0x180065d94  call    ReparsePointExists
0x180065d99  test    eax, eax
0x180065d9b  jz      short loc_180065DC6
0x180065d9d  cmp     [rsp+340h+var_310], r14d
0x180065da2  jz      short loc_180065DC6
0x180065da4  mov     r9d, ebx
0x180065da7  lea     r8, aEnumeratepathe_0; "EnumeratePathEx: Unable to get reparse "...
0x180065dae  mov     edx, 2000000h
0x180065db3  lea     rcx, g_WdsLibLog
0x180065dba  call    LibLog
0x180065dbf  mov     ecx, ebx
0x180065dc1  jmp     loc_18006611A
0x180065dc6  lea     rdx, asc_1800913DC; "*"
0x180065dcd  mov     rcx, rsi; pszSrc
0x180065dd0  mov     rdi, r14
0x180065dd3  call    BuildPath
0x180065dd8  mov     r12, rax
0x180065ddb  test    rax, rax
0x180065dde  jz      loc_1800660AC
0x180065de4  xor     edx, edx
0x180065de6  mov     rcx, rax; unsigned __int16 *
0x180065de9  call    PrepareUnicodePathEx
0x180065dee  mov     rdi, rax
0x180065df1  test    rax, rax
0x180065df4  jz      loc_1800660AC
0x180065dfa  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x180065dfe  mov     rcx, rax; lpFileName
0x180065e01  mov     r13d, r14d
0x180065e04  call    cs:__imp_FindFirstFileW
0x180065e0a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180065e0e  mov     [rsp+340h+hFindFile], rax
0x180065e13  cmp     rax, r14
0x180065e16  jz      loc_180066051
0x180065e1c  xor     edx, edx; Val
0x180065e1e  lea     r8d, [r14+41h]; Size
0x180065e22  lea     rcx, [rsp+340h+var_2F0]; void *
0x180065e27  call    memset_0
0x180065e2c  xor     ebx, ebx
0x180065e2e  cmp     bx, [rsi]
0x180065e31  jz      loc_180065F72
0x180065e37  mov     eax, [rbp+240h+FindFileData.dwFileAttributes]
0x180065e3a  lea     rdx, [rbp+240h+FindFileData.cFileName]; STRSAFE_PCNZWCH
0x180065e3e  mov     [rsp+340h+var_2F0], eax
0x180065e42  xorps   xmm0, xmm0
0x180065e45  mov     rax, qword ptr [rbp+240h+FindFileData.ftCreationTime.dwLowDateTime]
0x180065e49  mov     rcx, rsi; pszSrc
0x180065e4c  mov     [rsp+340h+var_2EC], rax
0x180065e51  mov     rax, qword ptr [rbp+240h+FindFileData.ftLastAccessTime.dwLowDateTime]
0x180065e55  mov     [rsp+340h+var_2E4], rax
0x180065e5a  mov     rax, qword ptr [rbp+240h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180065e5e  mov     [rsp+340h+var_2DC], rax
0x180065e63  mov     eax, [rbp+240h+FindFileData.nFileSizeLow]
0x180065e66  mov     [rsp+340h+var_2D0], eax
0x180065e6a  mov     eax, [rbp+240h+FindFileData.nFileSizeHigh]
0x180065e6d  mov     [rsp+340h+var_2CC], eax
0x180065e71  mov     [rsp+340h+var_2D4], ebx
0x180065e75  mov     [rsp+340h+lpMem], rbx
0x180065e7a  movdqa  xmmword ptr [rbp+240h+var_2C0], xmm0
0x180065e7f  call    BuildPath
0x180065e84  mov     [rsp+340h+lpMem], rax
0x180065e89  test    rax, rax
0x180065e8c  jz      short loc_180065EC5
0x180065e8e  lea     edx, [rbx+5Ch]; Ch
0x180065e91  mov     rcx, rax; Str
0x180065e94  call    wcsrchr_0
0x180065e99  mov     rcx, [rsp+340h+lpMem]; lpFileName
0x180065e9e  test    rax, rax
0x180065ea1  jz      short loc_180065EA9
0x180065ea3  add     rax, 2
0x180065ea7  jmp     short loc_180065EAC
0x180065ea9  mov     rax, rcx
0x180065eac  mov     [rbp+240h+var_2C0], rax
0x180065eb0  call    FormFullPathName
0x180065eb5  mov     [rbp+240h+var_2C0+8], rax
0x180065eb9  test    rax, rax
0x180065ebc  jz      short loc_180065EC5
0x180065ebe  mov     ebx, 1
0x180065ec3  jmp     short loc_180065ECF
0x180065ec5  lea     rcx, [rsp+340h+var_2F0]; void *
0x180065eca  call    FreeWdslibFindData
0x180065ecf  cmp     ebx, 1
0x180065ed2  jnz     loc_180065F7D
0x180065ed8  test    byte ptr [rsp+340h+var_2F0], 10h
0x180065edd  jz      short loc_180065F59
0x180065edf  cmp     [rsp+340h+var_300], r13
0x180065ee4  jz      loc_180065F7D
0x180065eea  mov     rax, [rbp+240h+var_2C0]
0x180065eee  lea     r8, asc_180091504; "."
0x180065ef5  mov     [rsp+340h+cchCount2], r14d; cchCount2
0x180065efa  mov     r9d, r14d; cchCount1
0x180065efd  mov     edx, ebx; dwCmpFlags
0x180065eff  mov     [rsp+340h+lpString2], rax; lpString2
0x180065f04  mov     ecx, 409h; Locale
0x180065f09  call    cs:__imp_CompareStringW
0x180065f0f  cmp     eax, 2
0x180065f12  jz      short loc_180065F7D
0x180065f14  mov     rax, [rbp+240h+var_2C0]
0x180065f18  lea     r8, asc_180091508; ".."
0x180065f1f  mov     [rsp+340h+cchCount2], r14d; cchCount2
0x180065f24  mov     r9d, r14d; cchCount1
0x180065f27  mov     edx, ebx; dwCmpFlags
0x180065f29  mov     [rsp+340h+lpString2], rax; lpString2
0x180065f2e  mov     ecx, 409h; Locale
0x180065f33  call    cs:__imp_CompareStringW
0x180065f39  cmp     eax, 2
0x180065f3c  jz      short loc_180065F7D
0x180065f3e  mov     r8, [rsp+340h+var_2F8]
0x180065f43  lea     rcx, [rsp+340h+var_2F0]
0x180065f48  mov     rax, [rsp+340h+var_300]
0x180065f4d  mov     rdx, r15
0x180065f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f55  mov     ebx, eax
0x180065f57  jmp     short loc_180065F7D
0x180065f59  test    r15, r15
0x180065f5c  jz      short loc_180065F7D
0x180065f5e  mov     rdx, [rsp+340h+var_2F8]
0x180065f63  lea     rcx, [rsp+340h+var_2F0]
0x180065f68  mov     rax, r15
0x180065f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f70  jmp     short loc_180065F55
0x180065f72  mov     ecx, 57h ; 'W'; dwErrCode
0x180065f77  call    cs:__imp_SetLastError
0x180065f7d  mov     r15, [rsp+340h+lpMem]
0x180065f82  test    r15, r15
0x180065f85  jz      short loc_180065FA7
0x180065f87  call    cs:__imp_GetProcessHeap
0x180065f8d  mov     r8, r15; lpMem
0x180065f90  xor     edx, edx; dwFlags
0x180065f92  mov     rcx, rax; hHeap
0x180065f95  call    cs:__imp_HeapFree
0x180065f9b  xor     r15d, r15d
0x180065f9e  test    eax, eax
0x180065fa0  jz      short loc_180065FA7
0x180065fa2  mov     [rsp+340h+lpMem], r15
0x180065fa7  mov     r15, [rbp+240h+var_2C0+8]
0x180065fab  test    r15, r15
0x180065fae  jz      short loc_180065FC4
0x180065fb0  call    cs:__imp_GetProcessHeap
0x180065fb6  mov     r8, r15; lpMem
0x180065fb9  xor     edx, edx; dwFlags
0x180065fbb  mov     rcx, rax; hHeap
0x180065fbe  call    cs:__imp_HeapFree
0x180065fc4  xor     edx, edx; Val
0x180065fc6  lea     rcx, [rsp+340h+var_2F0]; void *
0x180065fcb  lea     r8d, [rdx+40h]; Size
0x180065fcf  call    memset_0
0x180065fd4  cmp     ebx, 1
0x180065fd7  jnz     short loc_18006601A
0x180065fd9  mov     rcx, [rsp+340h+hFindFile]; hFindFile
0x180065fde  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x180065fe2  call    cs:__imp_FindNextFileW
0x180065fe8  mov     r15, [rbp+240h+var_2B0]
0x180065fec  cmp     eax, ebx
0x180065fee  jz      loc_180065E2C
0x180065ff4  call    cs:__imp_GetLastError
0x180065ffa  cmp     eax, 12h
0x180065ffd  jnz     short loc_18006600B
0x180065fff  xor     r14d, r14d
0x180066002  lea     r13d, [rax-11h]
0x180066006  mov     ebx, r14d
0x180066009  jmp     short loc_180066041
0x18006600b  call    cs:__imp_GetLastError
0x180066011  lea     r8, aEnumeratepathe_4; "EnumeratePathEx: Unable to enumerate [%"...
0x180066018  jmp     short loc_180066027
0x18006601a  call    cs:__imp_GetLastError
0x180066020  lea     r8, aEnumeratepathe_1; "EnumeratePathEx: Callback requested enu"...
0x180066027  mov     r9, rdi
0x18006602a  mov     dword ptr [rsp+340h+lpString2], eax
0x18006602e  mov     edx, 2000000h
0x180066033  lea     rcx, g_WdsLibLog
0x18006603a  mov     ebx, eax
0x18006603c  call    LibLog
0x180066041  mov     rcx, [rsp+340h+hFindFile]; hFindFile
0x180066046  call    cs:__imp_FindClose
0x18006604c  jmp     loc_1800660DB
0x180066051  call    cs:__imp_GetLastError
0x180066057  mov     r9, rdi
0x18006605a  lea     r8, aEnumeratepathe_3; "EnumeratePathEx: FindFirstFile failed f"...
0x180066061  lea     rcx, g_WdsLibLog
0x180066068  mov     dword ptr [rsp+340h+lpString2], eax
0x18006606c  mov     edx, 2000000h
0x180066071  mov     ebx, eax
0x180066073  call    LibLog
0x180066078  xor     eax, eax
0x18006607a  inc     r14
0x18006607d  cmp     [rdi+r14*2], ax
0x180066082  jnz     short loc_18006607A
0x180066084  cmp     r14, 104h
0x18006608b  jb      short loc_1800660DB
0x18006608d  lea     r8, aEnumeratepathe; "EnumeratePathEx: Failed search path is "...
0x180066094  mov     edx, 3000000h
0x180066099  lea     rcx, g_WdsLibLog
0x1800660a0  call    LibLog
0x1800660a5  mov     ebx, 0CEh
0x1800660aa  jmp     short loc_1800660DB
0x1800660ac  call    cs:__imp_GetLastError
0x1800660b2  mov     r9, rsi
0x1800660b5  lea     r8, aEnumeratepathe_2; "EnumeratePathEx: Unable to construct pa"...
0x1800660bc  lea     rcx, g_WdsLibLog
0x1800660c3  mov     dword ptr [rsp+340h+lpString2], eax
0x1800660c7  mov     edx, 2000000h
0x1800660cc  mov     ebx, eax
0x1800660ce  call    LibLog
0x1800660d3  mov     r13d, r14d
0x1800660d6  test    r12, r12
0x1800660d9  jz      short loc_1800660EF
0x1800660db  call    cs:__imp_GetProcessHeap
0x1800660e1  mov     r8, r12; lpMem
0x1800660e4  xor     edx, edx; dwFlags
0x1800660e6  mov     rcx, rax; hHeap
0x1800660e9  call    cs:__imp_HeapFree
0x1800660ef  test    rdi, rdi
0x1800660f2  jz      short loc_180066108
0x1800660f4  call    cs:__imp_GetProcessHeap
0x1800660fa  mov     r8, rdi; lpMem
0x1800660fd  xor     edx, edx; dwFlags
0x1800660ff  mov     rcx, rax; hHeap
0x180066102  call    cs:__imp_HeapFree
0x180066108  mov     ecx, ebx; dwErrCode
0x18006610a  call    cs:__imp_SetLastError
0x180066110  mov     eax, r13d
0x180066113  jmp     short loc_180066122
0x180066115  mov     ecx, 57h ; 'W'; dwErrCode
0x18006611a  call    cs:__imp_SetLastError
0x180066120  xor     eax, eax
0x180066122  mov     rcx, [rbp+240h+var_50]
0x180066129  xor     rcx, rsp; StackCookie
0x18006612c  call    __security_check_cookie
0x180066131  add     rsp, 308h
0x180066138  pop     r15
0x18006613a  pop     r14
0x18006613c  pop     r13
0x18006613e  pop     r12
0x180066140  pop     rdi
0x180066141  pop     rsi
0x180066142  pop     rbx
  ... truncated ...
```
