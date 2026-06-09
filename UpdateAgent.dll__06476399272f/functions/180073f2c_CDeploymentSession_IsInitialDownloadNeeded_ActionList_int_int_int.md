# CDeploymentSession::IsInitialDownloadNeeded(ActionList *,int,int *,int *)

- ea: `0x180073f2c`
- end: `0x18007473c`
- name: `?IsInitialDownloadNeeded@CDeploymentSession@@QEAAJPEAUActionList@@HPEAH1@Z`
- size: `2064`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, struct ActionList *, int, int *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180052d40`

## callees

- `0x1800059d0`
- `0x180036d28`
- `0x18003734c`
- `0x180039f90`
- `0x18003c418`
- `0x180073f2c`
- `0x180075044`
- `0x180077664`
- `0x180078b9c`
- `0x18007c740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800745b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800745b6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180074189`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180074398`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180074189`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180074398`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007455b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007455b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007415b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800741e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074474`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800744e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007469f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007415b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800741e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074474`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800744e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074660`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007469f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800741f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800744fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800746b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074170`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800741f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800744fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074675`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800746b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800745c6`

## string_xrefs

- `0x180074535`: `Expected hash not available; assuming hashless CompDB and skipping validation.`
- `0x180074649`: `File hash doesn't match but file was not deleted in Test Mode.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeploymentSession::IsInitialDownloadNeeded(
        CDeploymentSession *this,
        struct ActionList *a2,
        int a3,
        int *a4,
        int *a5)
{
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 updated; // rcx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // r14
  __int64 v14; // rax
  int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // r13
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  LPCWSTR v22; // rbx
  HANDLE v23; // rax
  WCHAR *v24; // r8
  LPCWSTR v25; // r12
  DWORD FileAttributesW; // eax
  BOOL v27; // ebx
  int v28; // eax
  HANDLE ProcessHeap; // rax
  int v30; // eax
  __int64 v31; // rcx
  int v32; // ecx
  __int64 v33; // r13
  __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // r12
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  const WCHAR *v41; // r14
  DWORD v42; // r15d
  BOOL v43; // r15d
  __int64 v44; // rdx
  const WCHAR *v45; // rbx
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  int v54; // eax
  HANDLE v55; // rax
  const WCHAR *v56; // rax
  __int64 v57; // rcx
  bool v58; // zf
  __int64 v59; // rcx
  signed int LastError; // eax
  __int64 v61; // rax
  __int64 v62; // rcx
  int v63; // eax
  HANDLE v64; // rax
  HANDLE v65; // rax
  const char *v66; // r9
  __int64 result; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-B8h]
  __int64 cchCount2; // [rsp+28h] [rbp-B0h]
  int cchCount2a; // [rsp+28h] [rbp-B0h]
  int v71; // [rsp+30h] [rbp-A8h]
  int v72; // [rsp+30h] [rbp-A8h]
  int v73; // [rsp+34h] [rbp-A4h]
  int v74; // [rsp+34h] [rbp-A4h]
  const WCHAR *v75; // [rsp+38h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-98h] BYREF
  int v77; // [rsp+48h] [rbp-90h] BYREF
  __int64 i; // [rsp+50h] [rbp-88h]
  __int64 j; // [rsp+58h] [rbp-80h]
  int *v80; // [rsp+60h] [rbp-78h]
  int *v81; // [rsp+68h] [rbp-70h]
  __int64 v82; // [rsp+70h] [rbp-68h]
  _OWORD v83[2]; // [rsp+78h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v82 = -2;
  try
  {
    v80 = a4;
    LODWORD(v75) = a3;
    v81 = a5;
    v77 = 0;
    if ( !a2 )
    {
      v7 = *((_QWORD *)this + 75);
      v8 = -2147024809;
      if ( !v7 )
        goto LABEL_4;
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v7,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::IsInitialDownloadNeeded",
                                4679,
                                -2147024809);
      goto LABEL_6;
    }
    if ( !a4 )
    {
      v10 = *((_QWORD *)this + 75);
      v8 = -2147024809;
      if ( !v10 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      LODWORD(lpString2) = 4680;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v10,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::IsInitialDownloadNeeded",
                                lpString2,
                                cchCount2a);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
      goto LABEL_8;
    }
    if ( !a5 )
    {
      v10 = *((_QWORD *)this + 75);
      v8 = -2147024809;
      if ( !v10 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      LODWORD(lpString2) = 4681;
      goto LABEL_12;
    }
    v11 = CMoUpdateHelpersT<CEmptyType>::IsSkipDeleteCorruptFile(&v77);
    v8 = v11;
    if ( v11 < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( !v10 )
        goto LABEL_4;
      cchCount2a = v11;
      LODWORD(lpString2) = 4683;
      goto LABEL_12;
    }
    v12 = 0;
    v73 = 0;
    v71 = 0;
    v13 = *((_QWORD *)a2 + 8);
    v14 = v13 + 168LL * *((unsigned int *)a2 + 18);
    j = v14;
    v15 = 36992;
    while ( v13 != v14 )
    {
      v16 = *(_DWORD *)(v13 + 88);
      if ( v16 <= 0xF && _bittest(&v15, v16) || *(_DWORD *)(v13 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
      {
        *((_DWORD *)this + 71) = 1;
        v17 = *(_QWORD *)(v13 + 112);
        v18 = v17 + 184LL * *(unsigned int *)(v13 + 120);
        for ( i = v18; ; v18 = i )
        {
          if ( v17 == v18 )
          {
            v15 = 36992;
            goto LABEL_46;
          }
          lpFileName = 0;
          v19 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v17 + 24), 0, &lpFileName);
          v8 = v19;
          if ( v19 < 0 )
            break;
          v25 = lpFileName;
          FileAttributesW = GetFileAttributesW(lpFileName);
          v27 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v8 = 0;
          if ( !v27 )
          {
            v28 = v71;
            if ( *(_QWORD *)(v17 + 48) )
              v28 = 1;
            v71 = v28;
          }
          v12 = !v27 | v73;
          v73 = v12;
          if ( v25 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, (LPVOID)(v25 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            v12 = v73;
          }
          v17 += 184;
        }
        v20 = *((_QWORD *)this + 75);
        if ( v20 )
        {
          v21 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v20,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::IsInitialDownloadNeeded",
                  4702,
                  v19);
          v20 = (unsigned int)v21;
          if ( v21 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
LABEL_32:
        v22 = lpFileName;
        if ( lpFileName )
        {
          v23 = GetProcessHeap();
          v24 = (WCHAR *)(v22 - 2);
          goto LABEL_34;
        }
        goto LABEL_121;
      }
LABEL_46:
      v13 += 168;
      v14 = j;
    }
    if ( v12 && v71 )
    {
      v30 = CDeploymentSession::ProcessSandboxContainerPayload(this, (__int64)a2, v12, (DWORD)v75, 0);
      v8 = v30;
      if ( v30 < 0 )
      {
        v31 = *((_QWORD *)this + 75);
        if ( v31 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v31,
            4,
            L"ProcessSandboxContainerPayload for IsInitialDownloadNeeded failed: [0x%X]",
            (unsigned int)v30);
        v10 = *((_QWORD *)this + 75);
        if ( !v10 )
          goto LABEL_4;
        cchCount2a = v8;
        LODWORD(lpString2) = 4724;
        goto LABEL_12;
      }
      v15 = 36992;
    }
    v74 = 0;
    v32 = 0;
    v72 = 0;
    v33 = *((_QWORD *)a2 + 8);
    v34 = v33 + 168LL * *((unsigned int *)a2 + 18);
    for ( i = v34; ; v34 = i )
    {
      if ( v33 == v34 )
      {
        *v80 = v32;
        *v81 = v74;
        goto LABEL_121;
      }
      v35 = *(_DWORD *)(v33 + 88);
      if ( v35 <= 0xF )
      {
        if ( _bittest(&v15, v35) )
          break;
      }
      if ( *(_DWORD *)(v33 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
        break;
LABEL_119:
      v33 += 168;
    }
    *((_DWORD *)this + 71) = 1;
    v36 = *(_QWORD *)(v33 + 112);
    v37 = v36 + 184LL * *(unsigned int *)(v33 + 120);
    for ( j = v37; ; v37 = j )
    {
      if ( v36 == v37 )
      {
        v15 = 36992;
        goto LABEL_119;
      }
      lpFileName = 0;
      v38 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v36 + 24), 0, &lpFileName);
      v8 = v38;
      if ( v38 < 0 )
      {
        v39 = *((_QWORD *)this + 75);
        if ( v39 )
        {
          LODWORD(cchCount2) = v38;
          LODWORD(lpString2) = 4745;
          v40 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v39,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::IsInitialDownloadNeeded",
                  lpString2,
                  cchCount2);
          v39 = (unsigned int)v40;
          if ( v40 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
        goto LABEL_32;
      }
      v41 = lpFileName;
      v42 = GetFileAttributesW(lpFileName);
      v43 = v42 != -1 && ((v42 >> 4) & 1) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v8 = 0;
      if ( v43 )
        break;
LABEL_115:
      v32 = !v43 | v72;
      v72 = v32;
      if ( v41 )
      {
        v65 = GetProcessHeap();
        HeapFree(v65, 0, (LPVOID)(v41 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v32 = v72;
      }
      v36 += 184;
    }
    v45 = 0;
    v75 = 0;
    memset(v83, 0, sizeof(v83));
    v46 = *((_QWORD *)this + 75);
    if ( v46 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v46, 2, L"Validating initial file [%ws]", *(_QWORD *)(v36 + 24));
    if ( *(_QWORD *)(v36 + 40) )
    {
      v47 = CDlpHelpersT<CEmptyType>::CalculateHash(v41, v44, (UCHAR *)v83);
      v8 = v47;
      if ( v47 < 0 )
      {
        v50 = *((_QWORD *)this + 75);
        if ( v50 )
        {
          LODWORD(cchCount2) = v47;
          LODWORD(lpString2) = 4757;
          v51 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v50,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::IsInitialDownloadNeeded",
                  lpString2,
                  cchCount2);
          v50 = (unsigned int)v51;
          if ( v51 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v51);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v50);
        goto LABEL_80;
      }
      v52 = CStringConvertT<unsigned long>::Base64Encode(v83, v48, v49, &v75);
      v8 = v52;
      if ( v52 < 0 )
      {
        v53 = *((_QWORD *)this + 75);
        if ( v53 )
        {
          LODWORD(cchCount2) = v52;
          LODWORD(lpString2) = 4758;
          v54 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v53,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::IsInitialDownloadNeeded",
                  lpString2,
                  cchCount2);
          v53 = (unsigned int)v54;
          if ( v54 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v54);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v53);
        v45 = v75;
        goto LABEL_87;
      }
      v45 = v75;
    }
    v56 = *(const WCHAR **)(v36 + 40);
    if ( !v56 )
    {
      v57 = *((_QWORD *)this + 75);
      if ( v57 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v57,
          3,
          L"Expected hash not available; assuming hashless CompDB and skipping validation.");
      goto LABEL_113;
    }
    v58 = CompareStringW(0x409u, 1u, v45, -1, v56, -1) == 2;
    v59 = *((_QWORD *)this + 75);
    if ( v58 )
    {
      if ( v59 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v59, 2, L"Initial file is valid");
      goto LABEL_113;
    }
    if ( v77 )
    {
      if ( v59 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v59,
          3,
          L"File hash doesn't match but file was not deleted in Test Mode.");
      goto LABEL_113;
    }
    if ( v59 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v59, 2, L"Deleting corrupt initial file");
    if ( DeleteFileW(v41) )
    {
      v74 = 1;
      v43 = 0;
LABEL_113:
      if ( v45 )
      {
        v64 = GetProcessHeap();
        HeapFree(v64, 0, (LPVOID)(v45 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      goto LABEL_115;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    v61 = *((_QWORD *)this + 75);
    v62 = 0;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( v61 )
      {
        LODWORD(cchCount2) = v8;
        LODWORD(lpString2) = 4774;
        v63 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v61,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::IsInitialDownloadNeeded",
                lpString2,
                cchCount2);
        v62 = (unsigned int)v63;
        if ( v63 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v63);
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v62);
LABEL_87:
    if ( v45 )
    {
      v55 = GetProcessHeap();
      HeapFree(v55, 0, (LPVOID)(v45 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
LABEL_80:
    if ( !v41 )
      goto LABEL_121;
    v23 = GetProcessHeap();
    v24 = (WCHAR *)(v41 - 2);
LABEL_34:
    HeapFree(v23, 0, v24);
LABEL_4:
    updated = 0;
LABEL_8:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_121:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
    result = v8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12BC,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v66);
  }
  return result;
}

```

## disassembly

```asm
0x180073f2c  push    rbx
0x180073f2e  push    rsi
0x180073f2f  push    rdi
0x180073f30  push    r12
0x180073f32  push    r13
0x180073f34  push    r14
0x180073f36  push    r15
0x180073f38  sub     rsp, 0A0h
0x180073f3f  mov     [rsp+0D8h+var_68], 0FFFFFFFFFFFFFFFEh
0x180073f48  mov     rax, cs:__security_cookie
0x180073f4f  xor     rax, rsp
0x180073f52  mov     [rsp+0D8h+var_40], rax
0x180073f5a  mov     rbx, r9
0x180073f5d  mov     [rsp+0D8h+var_78], rbx
0x180073f62  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x180073f67  mov     r15, rdx
0x180073f6a  mov     rsi, rcx
0x180073f6d  mov     r12, [rsp+0D8h+arg_20]
0x180073f75  mov     [rsp+0D8h+var_70], r12
0x180073f7a  mov     [rsp+0D8h+var_90], 0
0x180073f82  test    rdx, rdx
0x180073f85  jnz     short loc_180073FD5
0x180073f87  mov     rcx, [rcx+258h]
0x180073f8e  mov     edi, 80070057h
0x180073f93  test    rcx, rcx
0x180073f96  jnz     short loc_180073F9C
0x180073f98  xor     ecx, ecx
0x180073f9a  jmp     short loc_180073FCB
0x180073f9c  mov     dword ptr [rsp+0D8h+cchCount2], edi
0x180073fa0  mov     dword ptr [rsp+0D8h+lpString2], 1247h
0x180073fa8  lea     r9, aCdeploymentses_127; "CDeploymentSession::IsInitialDownloadNe"...
0x180073faf  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180073fb6  mov     edx, 4
0x180073fbb  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180073fc0  mov     ecx, eax
0x180073fc2  test    ecx, ecx
0x180073fc4  jns     short loc_180073FCB
0x180073fc6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180073fcb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180073fd0  jmp     loc_180074709
0x180073fd5  test    rbx, rbx
0x180073fd8  jnz     short loc_180074013
0x180073fda  mov     rcx, [rcx+258h]
0x180073fe1  mov     edi, 80070057h
0x180073fe6  test    rcx, rcx
0x180073fe9  jz      short loc_180073F98
0x180073feb  mov     dword ptr [rsp+0D8h+cchCount2], edi
0x180073fef  mov     dword ptr [rsp+0D8h+lpString2], 1248h
0x180073ff7  lea     r9, aCdeploymentses_127; "CDeploymentSession::IsInitialDownloadNe"...
0x180073ffe  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180074005  mov     edx, 4
0x18007400a  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007400f  mov     ecx, eax
0x180074011  jmp     short loc_180073FC2
0x180074013  test    r12, r12
0x180074016  jnz     short loc_18007403B
0x180074018  mov     rcx, [rcx+258h]
0x18007401f  mov     edi, 80070057h
0x180074024  test    rcx, rcx
0x180074027  jz      loc_180073F98
0x18007402d  mov     dword ptr [rsp+0D8h+cchCount2], edi
0x180074031  mov     dword ptr [rsp+0D8h+lpString2], 1249h
0x180074039  jmp     short loc_180073FF7
0x18007403b  lea     rcx, [rsp+0D8h+var_90]
0x180074040  call    ?IsSkipDeleteCorruptFile@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAH@Z; CMoUpdateHelpersT<CEmptyType>::IsSkipDeleteCorruptFile(int *)
0x180074045  mov     edi, eax
0x180074047  test    eax, eax
0x180074049  jns     short loc_180074069
0x18007404b  mov     rcx, [rsi+258h]
0x180074052  test    rcx, rcx
0x180074055  jz      loc_180073F98
0x18007405b  mov     dword ptr [rsp+0D8h+cchCount2], eax
0x18007405f  mov     dword ptr [rsp+0D8h+lpString2], 124Bh
0x180074067  jmp     short loc_180073FF7
0x180074069  xor     ecx, ecx
0x18007406b  mov     [rsp+0D8h+var_A4], ecx
0x18007406f  xor     eax, eax
0x180074071  mov     [rsp+0D8h+var_A8], eax
0x180074075  mov     r14, [r15+40h]
0x180074079  mov     eax, [r15+48h]
0x18007407d  imul    rax, 0A8h
0x180074084  add     rax, r14
0x180074087  mov     [rsp+0D8h+var_80], rax
0x18007408c  mov     edx, 9080h
0x180074091  lea     ebx, [rcx+1]
0x180074094  cmp     r14, rax
0x180074097  jz      loc_180074239
0x18007409d  mov     eax, [r14+58h]
0x1800740a1  cmp     eax, 0Fh
0x1800740a4  ja      short loc_1800740AB
0x1800740a6  bt      edx, eax
0x1800740a9  jb      short loc_1800740BF
0x1800740ab  cmp     dword ptr [r14+68h], 2
0x1800740b0  jz      short loc_1800740BF
0x1800740b2  cmp     dword ptr [rsi+1C8h], 8
0x1800740b9  jnz     loc_180074228
0x1800740bf  mov     [rsi+11Ch], ebx
0x1800740c5  mov     r13, [r14+70h]
0x1800740c9  mov     eax, [r14+78h]
0x1800740cd  imul    rax, 0B8h
0x1800740d4  add     rax, r13
0x1800740d7  mov     [rsp+0D8h+var_88], rax
0x1800740dc  cmp     r13, rax
0x1800740df  jz      loc_18007421E
0x1800740e5  mov     [rsp+0D8h+lpFileName], 0
0x1800740ee  lea     r9, [rsp+0D8h+lpFileName]
0x1800740f3  xor     r8d, r8d
0x1800740f6  mov     rdx, [r13+18h]
0x1800740fa  mov     rcx, [rsi+1E8h]
0x180074101  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180074106  mov     edi, eax
0x180074108  test    eax, eax
0x18007410a  jns     short loc_180074181
0x18007410c  mov     rcx, [rsi+258h]
0x180074113  test    rcx, rcx
0x180074116  jz      short loc_180074147
0x180074118  mov     dword ptr [rsp+0D8h+cchCount2], eax
0x18007411c  mov     dword ptr [rsp+0D8h+lpString2], 125Eh
0x180074124  lea     r9, aCdeploymentses_127; "CDeploymentSession::IsInitialDownloadNe"...
0x18007412b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180074132  mov     edx, 4
0x180074137  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007413c  mov     ecx, eax
0x18007413e  test    eax, eax
0x180074140  jns     short loc_180074147
0x180074142  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180074147  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007414c  nop
0x18007414d  mov     rbx, [rsp+0D8h+lpFileName]
0x180074152  test    rbx, rbx
0x180074155  jz      loc_180074709
0x18007415b  call    cs:__imp_GetProcessHeap
0x180074162  nop     dword ptr [rax+rax+00h]
0x180074167  lea     r8, [rbx-4]; lpMem
0x18007416b  mov     rcx, rax; hHeap
0x18007416e  xor     edx, edx; dwFlags
0x180074170  call    cs:__imp_HeapFree
0x180074177  nop     dword ptr [rax+rax+00h]
0x18007417c  jmp     loc_180073F98
0x180074181  mov     r12, [rsp+0D8h+lpFileName]
0x180074186  mov     rcx, r12; lpFileName
0x180074189  call    cs:__imp_GetFileAttributesW
0x180074190  nop     dword ptr [rax+rax+00h]
0x180074195  mov     ebx, eax
0x180074197  cmp     eax, 0FFFFFFFFh
0x18007419a  jz      short loc_1800741A6
0x18007419c  shr     ebx, 4
0x18007419f  not     ebx
0x1800741a1  and     ebx, 1
0x1800741a4  jmp     short loc_1800741A8
0x1800741a6  xor     ebx, ebx
0x1800741a8  xor     ecx, ecx
0x1800741aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800741af  xor     ecx, ecx
0x1800741b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800741b6  xor     edi, edi
0x1800741b8  test    ebx, ebx
0x1800741ba  jnz     short loc_1800741CE
0x1800741bc  mov     eax, [rsp+0D8h+var_A8]
0x1800741c0  cmp     [r13+30h], rdi
0x1800741c4  lea     ecx, [rdi+1]
0x1800741c7  cmovnz  eax, ecx
0x1800741ca  mov     [rsp+0D8h+var_A8], eax
0x1800741ce  xor     ebx, 1
0x1800741d1  mov     ecx, [rsp+0D8h+var_A4]
0x1800741d5  or      ecx, ebx
0x1800741d7  mov     [rsp+0D8h+var_A4], ecx
0x1800741db  test    r12, r12
0x1800741de  jz      short loc_18007420D
0x1800741e0  call    cs:__imp_GetProcessHeap
0x1800741e7  nop     dword ptr [rax+rax+00h]
0x1800741ec  mov     rcx, rax; hHeap
0x1800741ef  lea     r8, [r12-4]; lpMem
0x1800741f4  xor     edx, edx; dwFlags
0x1800741f6  call    cs:__imp_HeapFree
0x1800741fd  nop     dword ptr [rax+rax+00h]
0x180074202  xor     ecx, ecx
0x180074204  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180074209  mov     ecx, [rsp+0D8h+var_A4]
0x18007420d  add     r13, 0B8h
0x180074214  mov     rax, [rsp+0D8h+var_88]
0x180074219  jmp     loc_1800740DC
0x18007421e  mov     ebx, 1
0x180074223  mov     edx, 9080h
0x180074228  add     r14, 0A8h
0x18007422f  mov     rax, [rsp+0D8h+var_80]
0x180074234  jmp     loc_180074094
0x180074239  test    ecx, ecx
0x18007423b  jz      short loc_1800742AC
0x18007423d  cmp     [rsp+0D8h+var_A8], 0
0x180074242  jz      short loc_1800742AC
0x180074244  mov     [rsp+0D8h+lpString2], 0; __int64
0x18007424d  mov     r9d, dword ptr [rsp+0D8h+var_A0]
0x180074252  mov     r8d, ecx
0x180074255  mov     rdx, r15
0x180074258  mov     rcx, rsi; this
0x18007425b  call    ?ProcessSandboxContainerPayload@CDeploymentSession@@QEAAJPEAUActionList@@HHPEAV?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@@Z; CDeploymentSession::ProcessSandboxContainerPayload(ActionList *,int,int,std::vector<UaLiteManagerDownloadRequest> *)
0x180074260  mov     edi, eax
0x180074262  test    eax, eax
0x180074264  jns     short loc_1800742A7
0x180074266  mov     rcx, [rsi+258h]
0x18007426d  test    rcx, rcx
0x180074270  jz      short loc_180074286
0x180074272  mov     r9d, eax
0x180074275  lea     r8, aProcesssandbox_1; "ProcessSandboxContainerPayload for IsIn"...
0x18007427c  mov     edx, 4
0x180074281  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180074286  mov     rcx, [rsi+258h]
0x18007428d  test    rcx, rcx
0x180074290  jz      loc_180073F98
0x180074296  mov     dword ptr [rsp+0D8h+cchCount2], edi
0x18007429a  mov     dword ptr [rsp+0D8h+lpString2], 1274h
0x1800742a2  jmp     loc_180073FF7
0x1800742a7  mov     edx, 9080h
0x1800742ac  mov     [rsp+0D8h+var_A4], 0
0x1800742b4  xor     ecx, ecx
0x1800742b6  mov     [rsp+0D8h+var_A8], ecx
0x1800742ba  mov     r13, [r15+40h]
0x1800742be  mov     eax, [r15+48h]
0x1800742c2  imul    rax, 0A8h
0x1800742c9  add     rax, r13
0x1800742cc  mov     [rsp+0D8h+var_88], rax
0x1800742d1  cmp     r13, rax
0x1800742d4  jz      loc_1800746F7
0x1800742da  mov     eax, [r13+58h]
0x1800742de  cmp     eax, 0Fh
0x1800742e1  ja      short loc_1800742E8
0x1800742e3  bt      edx, eax
0x1800742e6  jb      short loc_1800742FC
0x1800742e8  cmp     dword ptr [r13+68h], 2
0x1800742ed  jz      short loc_1800742FC
0x1800742ef  cmp     dword ptr [rsi+1C8h], 8
0x1800742f6  jnz     loc_1800746E6
0x1800742fc  mov     [rsi+11Ch], ebx
0x180074302  mov     r12, [r13+70h]
0x180074306  mov     eax, [r13+78h]
0x18007430a  imul    rax, 0B8h
0x180074311  add     rax, r12
0x180074314  mov     [rsp+0D8h+var_80], rax
0x180074319  cmp     r12, rax
0x18007431c  jz      loc_1800746E1
0x180074322  mov     [rsp+0D8h+lpFileName], 0
0x18007432b  lea     r9, [rsp+0D8h+lpFileName]
0x180074330  xor     r8d, r8d
0x180074333  mov     rdx, [r12+18h]
0x180074338  mov     rcx, [rsi+1E8h]
0x18007433f  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180074344  mov     edi, eax
0x180074346  test    eax, eax
0x180074348  jns     short loc_180074390
0x18007434a  mov     rcx, [rsi+258h]
0x180074351  test    rcx, rcx
0x180074354  jz      short loc_180074385
0x180074356  mov     dword ptr [rsp+0D8h+cchCount2], eax
0x18007435a  mov     dword ptr [rsp+0D8h+lpString2], 1289h
0x180074362  lea     r9, aCdeploymentses_127; "CDeploymentSession::IsInitialDownloadNe"...
0x180074369  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180074370  mov     edx, 4
0x180074375  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007437a  mov     ecx, eax
0x18007437c  test    eax, eax
0x18007437e  jns     short loc_180074385
0x180074380  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180074385  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007438a  nop
0x18007438b  jmp     loc_18007414D
0x180074390  mov     r14, [rsp+0D8h+lpFileName]
0x180074395  mov     rcx, r14; lpFileName
0x180074398  call    cs:__imp_GetFileAttributesW
0x18007439f  nop     dword ptr [rax+rax+00h]
0x1800743a4  mov     r15d, eax
0x1800743a7  cmp     eax, 0FFFFFFFFh
0x1800743aa  jz      short loc_1800743B8
0x1800743ac  shr     r15d, 4
0x1800743b0  not     r15d
0x1800743b3  and     r15d, ebx
0x1800743b6  jmp     short loc_1800743BB
0x1800743b8  xor     r15d, r15d
0x1800743bb  xor     ecx, ecx
0x1800743bd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800743c2  xor     ecx, ecx
0x1800743c4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800743c9  xor     edi, edi
0x1800743cb  test    r15d, r15d
0x1800743ce  jz      loc_180074688
0x1800743d4  xor     ebx, ebx
0x1800743d6  mov     [rsp+0D8h+var_A0], rbx
0x1800743db  xorps   xmm0, xmm0
0x1800743de  movups  [rsp+0D8h+var_60], xmm0
0x1800743e3  movups  [rsp+0D8h+var_50], xmm0
0x1800743eb  mov     rcx, [rsi+258h]
0x1800743f2  test    rcx, rcx
0x1800743f5  jz      short loc_18007440B
0x1800743f7  mov     r9, [r12+18h]
0x1800743fc  lea     r8, aValidatingInit; "Validating initial file [%ws]"
0x180074403  lea     edx, [rdi+2]
0x180074406  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007440b  cmp     qword ptr [r12+28h], 0
0x180074411  jz      loc_18007451B
0x180074417  lea     r8, [rsp+0D8h+var_60]
  ... truncated ...
```
