# RedirectLogging(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *)

- ea: `0x14001c624`
- end: `0x14001cbab`
- name: `?RedirectLogging@@YAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0@Z`
- size: `1415`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x140013894`

## callees

- `0x1400076c8`
- `0x1400093b8`
- `0x140009700`
- `0x1400135b8`
- `0x140016bb4`
- `0x140018a38`
- `0x14001c624`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x14001c8fb`
- `KERNEL32!DeleteFileW` at `0x14001c9c5`
- `KERNEL32!DeleteFileW` at `0x14001c8fb`
- `KERNEL32!DeleteFileW` at `0x14001c9c5`
- `KERNEL32!CloseHandle` at `0x14001cb28`
- `KERNEL32!CloseHandle` at `0x14001cb28`
- `KERNEL32!CreateSymbolicLinkW` at `0x14001cabd`
- `KERNEL32!CreateSymbolicLinkW` at `0x14001cabd`
- `KERNEL32!HeapFree` at `0x14001c6af`
- `KERNEL32!HeapFree` at `0x14001c794`
- `KERNEL32!HeapFree` at `0x14001cb4f`
- `KERNEL32!HeapFree` at `0x14001cb7d`
- `KERNEL32!HeapFree` at `0x14001c6af`
- `KERNEL32!HeapFree` at `0x14001c794`
- `KERNEL32!HeapFree` at `0x14001cb4f`
- `KERNEL32!HeapFree` at `0x14001cb7d`
- `KERNEL32!GetProcessHeap` at `0x14001c69a`
- `KERNEL32!GetProcessHeap` at `0x14001c77f`
- `KERNEL32!GetProcessHeap` at `0x14001cb3a`
- `KERNEL32!GetProcessHeap` at `0x14001cb68`
- `KERNEL32!GetProcessHeap` at `0x14001c69a`
- `KERNEL32!GetProcessHeap` at `0x14001c77f`
- `KERNEL32!GetProcessHeap` at `0x14001cb3a`
- `KERNEL32!GetProcessHeap` at `0x14001cb68`
- `KERNEL32!GetLastError` at `0x14001c90b`
- `KERNEL32!GetLastError` at `0x14001c90b`
- `KERNEL32!GetFileAttributesW` at `0x14001c705`
- `KERNEL32!GetFileAttributesW` at `0x14001c7e8`
- `KERNEL32!GetFileAttributesW` at `0x14001c873`
- `KERNEL32!GetFileAttributesW` at `0x14001c943`
- `KERNEL32!GetFileAttributesW` at `0x14001c705`
- `KERNEL32!GetFileAttributesW` at `0x14001c7e8`
- `KERNEL32!GetFileAttributesW` at `0x14001c873`
- `KERNEL32!GetFileAttributesW` at `0x14001c943`

## string_xrefs

- `0x14001ca7a`: `Creating soft link from [%s] to [%s]...`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RedirectLogging(__int64 a1, __int64 a2)
{
  WCHAR *v4; // rsi
  WCHAR *v5; // r14
  unsigned int v6; // edi
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // r15d
  HANDLE ProcessHeap; // rax
  __int64 v11; // rax
  unsigned __int16 *v12; // rcx
  int v13; // eax
  DWORD FileAttributesW; // ebx
  int v15; // ebx
  HANDLE v16; // rcx
  int FolderPath; // eax
  HANDLE v18; // rax
  __int64 v19; // rax
  unsigned __int16 *v20; // rcx
  int v21; // eax
  DWORD v22; // ebx
  int v23; // ebx
  HANDLE v24; // rcx
  __int64 v25; // rax
  const WCHAR *v26; // rcx
  DWORD v27; // eax
  BOOL v28; // ebx
  __int64 v29; // r9
  HANDLE v30; // rcx
  __int64 v31; // rax
  const WCHAR *v32; // rcx
  signed int LastError; // eax
  __int64 v34; // rax
  const WCHAR *v35; // rcx
  DWORD v36; // eax
  BOOL v37; // ebx
  __int64 v38; // r9
  HANDLE v39; // rcx
  __int64 v40; // rax
  const WCHAR *v41; // rcx
  __int64 v42; // r9
  HANDLE v43; // rcx
  __int64 v44; // rax
  const WCHAR *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // r10
  HANDLE v49; // rcx
  __int64 v50; // rax
  const WCHAR *v51; // rdx
  __int64 v52; // rax
  const WCHAR *v53; // rcx
  HANDLE v54; // rax
  HANDLE v55; // rax
  HANDLE hObject[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v58; // [rsp+80h] [rbp+40h]
  LPCWSTR v59; // [rsp+90h] [rbp+50h] BYREF
  LPCWSTR lpFileName; // [rsp+98h] [rbp+58h] BYREF

  hObject[1] = (HANDLE)-2LL;
  v4 = 0;
  lpFileName = 0;
  v5 = 0;
  v59 = 0;
  hObject[0] = (HANDLE)-1LL;
  v6 = 0;
  if ( !a1 || !a2 || (v8 = *(_DWORD *)(a1 + 4), v8 != *(_DWORD *)(a2 + 4)) )
  {
    v7 = -2147024809;
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_103;
  }
  v9 = 0;
  v58 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        lpFileName = 0;
      }
      v11 = *(_QWORD *)(a1 + 8);
      if ( !v11 )
        v11 = 0;
      v12 = *(unsigned __int16 **)(v11 + 8LL * (int)v9);
      if ( !v12 )
        v12 = 0;
      v13 = CMiscHelpersT<CEmptyType>::ParseFileName(v12, 0, (unsigned __int16 **)&lpFileName, 0, 0);
      v6 = v13;
      if ( v13 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
        v4 = (WCHAR *)lpFileName;
        goto LABEL_103;
      }
      v4 = (WCHAR *)lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      if ( FileAttributesW == -1 )
        v15 = 0;
      else
        v15 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v15 )
      {
        v16 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v16 = g_shLogFile;
        OutputMsg(v16, g_shLogEvent, L"Creating logging folder [%s]...", v4);
        FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v4);
        v6 = FolderPath;
        if ( FolderPath < 0 )
        {
LABEL_21:
          v7 = FolderPath;
          goto LABEL_3;
        }
      }
      if ( v5 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v5 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v59 = 0;
      }
      v19 = *(_QWORD *)(a2 + 8);
      if ( !v19 )
        v19 = 0;
      v20 = *(unsigned __int16 **)(v19 + 8LL * (int)v9);
      if ( !v20 )
        v20 = 0;
      v21 = CMiscHelpersT<CEmptyType>::ParseFileName(v20, 0, (unsigned __int16 **)&v59, 0, 0);
      v6 = v21;
      if ( v21 < 0 )
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
        v5 = (WCHAR *)v59;
        goto LABEL_103;
      }
      v5 = (WCHAR *)v59;
      v22 = GetFileAttributesW(v59);
      if ( v22 == -1 )
        v23 = 0;
      else
        v23 = (v22 >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v23 )
      {
        v24 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v24 = g_shLogFile;
        OutputMsg(v24, g_shLogEvent, L"Creating redirect folder [%s]...", v5);
        FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v5);
        v6 = FolderPath;
        if ( FolderPath < 0 )
          goto LABEL_21;
      }
      v25 = *(_QWORD *)(a2 + 8);
      if ( !v25 )
        v25 = 0;
      v26 = *(const WCHAR **)(v25 + 8LL * (int)v9);
      if ( !v26 )
        v26 = 0;
      v27 = GetFileAttributesW(v26);
      v28 = v27 != -1 && (v27 & 0x10) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v28 )
      {
        v29 = *(_QWORD *)(a2 + 8);
        if ( !v29 )
          v29 = 0;
        v30 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v30 = g_shLogFile;
        OutputMsg(v30, g_shLogEvent, L"Deleting file [%s]...", *(_QWORD *)(v29 + 8LL * (int)v9));
        v31 = *(_QWORD *)(a2 + 8);
        if ( !v31 )
          v31 = 0;
        v32 = *(const WCHAR **)(v31 + 8LL * (int)v9);
        if ( !v32 )
          v32 = 0;
        if ( !DeleteFileW(v32) )
          break;
      }
      v34 = *(_QWORD *)(a1 + 8);
      if ( !v34 )
        v34 = 0;
      v35 = *(const WCHAR **)(v34 + 8LL * (int)v9);
      if ( !v35 )
        v35 = 0;
      v36 = GetFileAttributesW(v35);
      v37 = v36 != -1 && (v36 & 0x10) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v37 )
      {
        v38 = *(_QWORD *)(a1 + 8);
        if ( !v38 )
          v38 = 0;
        v39 = 0;
        if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          v39 = g_shLogFile;
        OutputMsg(v39, g_shLogEvent, L"Deleting file [%s]...", *(_QWORD *)(v38 + 8LL * (int)v9));
        v40 = *(_QWORD *)(a1 + 8);
        if ( !v40 )
          v40 = 0;
        v41 = *(const WCHAR **)(v40 + 8LL * (int)v9);
        if ( !v41 )
          v41 = 0;
        if ( !DeleteFileW(v41) )
          break;
      }
      v42 = *(_QWORD *)(a2 + 8);
      if ( !v42 )
        v42 = 0;
      v43 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v43 = g_shLogFile;
      OutputMsg(v43, g_shLogEvent, L"Creating file [%s]...", *(_QWORD *)(v42 + 8LL * (int)v9));
      v44 = *(_QWORD *)(a2 + 8);
      if ( !v44 )
        v44 = 0;
      v45 = *(const WCHAR **)(v44 + 8LL * (int)v9);
      if ( !v45 )
        v45 = 0;
      FolderPath = CDlpHelpersT<CEmptyType>::CreateFileWithAcl(v45, (__int64 *)hObject);
      v6 = FolderPath;
      if ( FolderPath < 0 )
        goto LABEL_21;
      v46 = *(_QWORD *)(a2 + 8);
      if ( !v46 )
        v46 = 0;
      v47 = *(_QWORD *)(v46 + 8LL * (int)v9);
      v48 = *(_QWORD *)(a1 + 8);
      if ( !v48 )
        v48 = 0;
      v49 = 0;
      if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        v49 = g_shLogFile;
      OutputMsg(v49, g_shLogEvent, L"Creating soft link from [%s] to [%s]...", *(_QWORD *)(v48 + 8LL * (int)v9), v47);
      v50 = *(_QWORD *)(a2 + 8);
      if ( !v50 )
        v50 = 0;
      v51 = *(const WCHAR **)(v50 + 8LL * (int)v9);
      if ( !v51 )
        v51 = 0;
      v52 = *(_QWORD *)(a1 + 8);
      if ( !v52 )
        v52 = 0;
      v53 = *(const WCHAR **)(v52 + 8LL * (int)v9);
      if ( !v53 )
        v53 = 0;
      if ( !CreateSymbolicLinkW(v53, v51, 0) )
        break;
      v9 = v58 + 1;
      v58 = v9;
      if ( v9 >= *(_DWORD *)(a1 + 4) )
        goto LABEL_103;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    v7 = v6;
    goto LABEL_3;
  }
LABEL_103:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( v5 )
  {
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v5 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v55 = GetProcessHeap();
    HeapFree(v55, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v6;
}

```

## disassembly

```asm
0x14001c624  mov     rax, rsp
0x14001c627  push    rbp
0x14001c628  push    rsi
0x14001c629  push    rdi
0x14001c62a  push    r12
0x14001c62c  push    r13
0x14001c62e  push    r14
0x14001c630  push    r15
0x14001c632  mov     rbp, rsp
0x14001c635  sub     rsp, 40h
0x14001c639  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x14001c641  mov     [rax+10h], rbx
0x14001c645  mov     r12, rdx
0x14001c648  mov     r13, rcx
0x14001c64b  xor     ebx, ebx
0x14001c64d  mov     esi, ebx
0x14001c64f  mov     [rbp+lpFileName], rbx
0x14001c653  mov     r14d, ebx
0x14001c656  mov     [rbp+arg_10], rbx
0x14001c65a  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x14001c662  mov     edi, ebx
0x14001c664  test    rcx, rcx
0x14001c667  jnz     short loc_14001C67A
0x14001c669  mov     ecx, 80070057h
0x14001c66e  mov     edi, ecx
0x14001c670  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001c675  jmp     loc_14001CB12
0x14001c67a  test    r12, r12
0x14001c67d  jz      short loc_14001C669
0x14001c67f  mov     eax, [rcx+4]
0x14001c682  cmp     eax, [rdx+4]
0x14001c685  jnz     short loc_14001C669
0x14001c687  mov     r15d, ebx
0x14001c68a  mov     [rbp+arg_0], ebx
0x14001c68d  test    eax, eax
0x14001c68f  jz      loc_14001CB12
0x14001c695  test    rsi, rsi
0x14001c698  jz      short loc_14001C6C8
0x14001c69a  call    cs:__imp_GetProcessHeap
0x14001c6a1  nop     dword ptr [rax+rax+00h]
0x14001c6a6  mov     rcx, rax; hHeap
0x14001c6a9  lea     r8, [rsi-4]; lpMem
0x14001c6ad  xor     edx, edx; dwFlags
0x14001c6af  call    cs:__imp_HeapFree
0x14001c6b6  nop     dword ptr [rax+rax+00h]
0x14001c6bb  xor     ecx, ecx
0x14001c6bd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c6c2  xor     ebx, ebx
0x14001c6c4  mov     [rbp+lpFileName], rbx
0x14001c6c8  mov     rax, [r13+8]
0x14001c6cc  test    rax, rax
0x14001c6cf  cmovz   rax, rbx
0x14001c6d3  movsxd  r15, r15d
0x14001c6d6  mov     rcx, [rax+r15*8]
0x14001c6da  test    rcx, rcx
0x14001c6dd  cmovz   rcx, rbx; Src
0x14001c6e1  mov     [rsp+40h+var_20], rbx; __int64
0x14001c6e6  xor     r9d, r9d
0x14001c6e9  lea     r8, [rbp+lpFileName]
0x14001c6ed  xor     edx, edx
0x14001c6ef  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x14001c6f4  mov     edi, eax
0x14001c6f6  test    eax, eax
0x14001c6f8  js      loc_14001CB07
0x14001c6fe  mov     rsi, [rbp+lpFileName]
0x14001c702  mov     rcx, rsi; lpFileName
0x14001c705  call    cs:__imp_GetFileAttributesW
0x14001c70c  nop     dword ptr [rax+rax+00h]
0x14001c711  mov     ebx, eax
0x14001c713  cmp     eax, 0FFFFFFFFh
0x14001c716  jz      short loc_14001C720
0x14001c718  shr     ebx, 4
0x14001c71b  and     ebx, 1
0x14001c71e  jmp     short loc_14001C724
0x14001c720  xor     edi, edi
0x14001c722  mov     ebx, edi
0x14001c724  xor     ecx, ecx
0x14001c726  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c72b  xor     ecx, ecx
0x14001c72d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c732  test    ebx, ebx
0x14001c734  jnz     short loc_14001C778
0x14001c736  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001c73d  lea     rax, [r8-1]
0x14001c741  xor     ebx, ebx
0x14001c743  mov     ecx, ebx
0x14001c745  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001c749  cmovbe  rcx, r8; hFile
0x14001c74d  mov     r9, rsi
0x14001c750  lea     r8, aCreatingLoggin; "Creating logging folder [%s]..."
0x14001c757  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001c75e  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001c763  mov     rcx, rsi
0x14001c766  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x14001c76b  mov     edi, eax
0x14001c76d  test    eax, eax
0x14001c76f  jns     short loc_14001C77A
0x14001c771  mov     ecx, eax
0x14001c773  jmp     loc_14001C670
0x14001c778  xor     ebx, ebx
0x14001c77a  test    r14, r14
0x14001c77d  jz      short loc_14001C7AD
0x14001c77f  call    cs:__imp_GetProcessHeap
0x14001c786  nop     dword ptr [rax+rax+00h]
0x14001c78b  mov     rcx, rax; hHeap
0x14001c78e  lea     r8, [r14-4]; lpMem
0x14001c792  xor     edx, edx; dwFlags
0x14001c794  call    cs:__imp_HeapFree
0x14001c79b  nop     dword ptr [rax+rax+00h]
0x14001c7a0  xor     ecx, ecx
0x14001c7a2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c7a7  xor     ebx, ebx
0x14001c7a9  mov     [rbp+arg_10], rbx
0x14001c7ad  mov     rax, [r12+8]
0x14001c7b2  test    rax, rax
0x14001c7b5  cmovz   rax, rbx
0x14001c7b9  mov     rcx, [rax+r15*8]
0x14001c7bd  test    rcx, rcx
0x14001c7c0  cmovz   rcx, rbx; Src
0x14001c7c4  mov     [rsp+40h+var_20], rbx; __int64
0x14001c7c9  xor     r9d, r9d
0x14001c7cc  lea     r8, [rbp+arg_10]
0x14001c7d0  xor     edx, edx
0x14001c7d2  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x14001c7d7  mov     edi, eax
0x14001c7d9  test    eax, eax
0x14001c7db  js      loc_14001CAFA
0x14001c7e1  mov     r14, [rbp+arg_10]
0x14001c7e5  mov     rcx, r14; lpFileName
0x14001c7e8  call    cs:__imp_GetFileAttributesW
0x14001c7ef  nop     dword ptr [rax+rax+00h]
0x14001c7f4  mov     ebx, eax
0x14001c7f6  cmp     eax, 0FFFFFFFFh
0x14001c7f9  jz      short loc_14001C803
0x14001c7fb  shr     ebx, 4
0x14001c7fe  and     ebx, 1
0x14001c801  jmp     short loc_14001C807
0x14001c803  xor     edi, edi
0x14001c805  mov     ebx, edi
0x14001c807  xor     ecx, ecx
0x14001c809  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c80e  xor     ecx, ecx
0x14001c810  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c815  test    ebx, ebx
0x14001c817  jnz     short loc_14001C85A
0x14001c819  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001c820  lea     rax, [r8-1]
0x14001c824  xor     ebx, ebx
0x14001c826  mov     ecx, ebx
0x14001c828  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001c82c  cmovbe  rcx, r8; hFile
0x14001c830  mov     r9, r14
0x14001c833  lea     r8, aCreatingRedire; "Creating redirect folder [%s]..."
0x14001c83a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001c841  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001c846  mov     rcx, r14
0x14001c849  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x14001c84e  mov     edi, eax
0x14001c850  test    eax, eax
0x14001c852  js      loc_14001C771
0x14001c858  jmp     short loc_14001C85C
0x14001c85a  xor     ebx, ebx
0x14001c85c  mov     rax, [r12+8]
0x14001c861  test    rax, rax
0x14001c864  cmovz   rax, rbx
0x14001c868  mov     rcx, [rax+r15*8]
0x14001c86c  test    rcx, rcx
0x14001c86f  cmovz   rcx, rbx; lpFileName
0x14001c873  call    cs:__imp_GetFileAttributesW
0x14001c87a  nop     dword ptr [rax+rax+00h]
0x14001c87f  mov     ebx, eax
0x14001c881  cmp     eax, 0FFFFFFFFh
0x14001c884  jz      short loc_14001C890
0x14001c886  shr     ebx, 4
0x14001c889  not     ebx
0x14001c88b  and     ebx, 1
0x14001c88e  jmp     short loc_14001C894
0x14001c890  xor     edi, edi
0x14001c892  mov     ebx, edi
0x14001c894  xor     ecx, ecx
0x14001c896  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c89b  xor     ecx, ecx
0x14001c89d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c8a2  test    ebx, ebx
0x14001c8a4  jz      loc_14001C92B
0x14001c8aa  mov     r9, [r12+8]
0x14001c8af  xor     ebx, ebx
0x14001c8b1  test    r9, r9
0x14001c8b4  cmovz   r9, rbx
0x14001c8b8  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001c8bf  lea     rax, [r8-1]
0x14001c8c3  mov     ecx, ebx
0x14001c8c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001c8c9  cmovbe  rcx, r8; hFile
0x14001c8cd  mov     r9, [r9+r15*8]
0x14001c8d1  lea     r8, aDeletingFileS; "Deleting file [%s]..."
0x14001c8d8  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001c8df  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001c8e4  mov     rax, [r12+8]
0x14001c8e9  test    rax, rax
0x14001c8ec  cmovz   rax, rbx
0x14001c8f0  mov     rcx, [rax+r15*8]
0x14001c8f4  test    rcx, rcx
0x14001c8f7  cmovz   rcx, rbx; lpFileName
0x14001c8fb  call    cs:__imp_DeleteFileW
0x14001c902  nop     dword ptr [rax+rax+00h]
0x14001c907  test    eax, eax
0x14001c909  jnz     short loc_14001C92D
0x14001c90b  call    cs:__imp_GetLastError
0x14001c912  nop     dword ptr [rax+rax+00h]
0x14001c917  mov     edi, eax
0x14001c919  test    eax, eax
0x14001c91b  jnz     loc_14001CAE8
0x14001c921  mov     edi, 80004005h
0x14001c926  jmp     loc_14001CAF3
0x14001c92b  xor     ebx, ebx
0x14001c92d  mov     rax, [r13+8]
0x14001c931  test    rax, rax
0x14001c934  cmovz   rax, rbx
0x14001c938  mov     rcx, [rax+r15*8]
0x14001c93c  test    rcx, rcx
0x14001c93f  cmovz   rcx, rbx; lpFileName
0x14001c943  call    cs:__imp_GetFileAttributesW
0x14001c94a  nop     dword ptr [rax+rax+00h]
0x14001c94f  mov     ebx, eax
0x14001c951  cmp     eax, 0FFFFFFFFh
0x14001c954  jz      short loc_14001C960
0x14001c956  shr     ebx, 4
0x14001c959  not     ebx
0x14001c95b  and     ebx, 1
0x14001c95e  jmp     short loc_14001C964
0x14001c960  xor     edi, edi
0x14001c962  mov     ebx, edi
0x14001c964  xor     ecx, ecx
0x14001c966  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c96b  xor     ecx, ecx
0x14001c96d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001c972  test    ebx, ebx
0x14001c974  jz      short loc_14001C9DB
0x14001c976  mov     r9, [r13+8]
0x14001c97a  xor     ebx, ebx
0x14001c97c  test    r9, r9
0x14001c97f  cmovz   r9, rbx
0x14001c983  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001c98a  lea     rax, [r8-1]
0x14001c98e  mov     ecx, ebx
0x14001c990  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001c994  cmovbe  rcx, r8; hFile
0x14001c998  mov     r9, [r9+r15*8]
0x14001c99c  lea     r8, aDeletingFileS; "Deleting file [%s]..."
0x14001c9a3  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001c9aa  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001c9af  mov     rax, [r13+8]
0x14001c9b3  test    rax, rax
0x14001c9b6  cmovz   rax, rbx
0x14001c9ba  mov     rcx, [rax+r15*8]
0x14001c9be  test    rcx, rcx
0x14001c9c1  cmovz   rcx, rbx; lpFileName
0x14001c9c5  call    cs:__imp_DeleteFileW
0x14001c9cc  nop     dword ptr [rax+rax+00h]
0x14001c9d1  test    eax, eax
0x14001c9d3  jz      loc_14001C90B
0x14001c9d9  jmp     short loc_14001C9DD
0x14001c9db  xor     ebx, ebx
0x14001c9dd  mov     r9, [r12+8]
0x14001c9e2  test    r9, r9
0x14001c9e5  cmovz   r9, rbx
0x14001c9e9  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001c9f0  lea     rax, [r8-1]
0x14001c9f4  mov     rcx, rbx
0x14001c9f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001c9fb  cmovbe  rcx, r8; hFile
0x14001c9ff  mov     r9, [r9+r15*8]
0x14001ca03  lea     r8, aCreatingFileS; "Creating file [%s]..."
0x14001ca0a  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14001ca11  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14001ca16  mov     rax, [r12+8]
0x14001ca1b  test    rax, rax
0x14001ca1e  cmovz   rax, rbx
0x14001ca22  mov     rcx, [rax+r15*8]
0x14001ca26  test    rcx, rcx
0x14001ca29  cmovz   rcx, rbx; lpFileName
0x14001ca2d  lea     rdx, [rbp+hObject]
0x14001ca31  call    ?CreateFileWithAcl@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAGPEAPEAX@Z; CDlpHelpersT<CEmptyType>::CreateFileWithAcl(ushort *,void * *)
0x14001ca36  mov     edi, eax
0x14001ca38  test    eax, eax
0x14001ca3a  js      loc_14001C771
0x14001ca40  mov     rax, [r12+8]
0x14001ca45  test    rax, rax
0x14001ca48  cmovz   rax, rbx
0x14001ca4c  mov     rax, [rax+r15*8]
0x14001ca50  mov     r10, [r13+8]
0x14001ca54  test    r10, r10
0x14001ca57  cmovz   r10, rbx
0x14001ca5b  mov     r9, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14001ca62  lea     r8, [r9-1]
0x14001ca66  mov     rcx, rbx
0x14001ca69  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x14001ca6d  cmovbe  rcx, r9; hFile
0x14001ca71  mov     [rsp+40h+var_20], rax
  ... truncated ...
```
