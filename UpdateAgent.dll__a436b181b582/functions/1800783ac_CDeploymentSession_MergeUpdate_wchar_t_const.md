# CDeploymentSession::MergeUpdate(wchar_t const *)

- ea: `0x1800783ac`
- end: `0x1800789eb`
- name: `?MergeUpdate@CDeploymentSession@@QEAAJPEB_W@Z`
- size: `1599`
- prototype: `int(CDeploymentSession *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002efc0`

## callees

- `0x180039f90`
- `0x18003c418`
- `0x180077664`
- `0x1800783ac`
- `0x180078b9c`
- `0x18008c4c4`
- `0x1800acd88`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180078451`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180078451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078923`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078967`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078923`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078967`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800786de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007890a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007897c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800789b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800786de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007890a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007897c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800789b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180078837`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180078837`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800785c1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800785c1`

## string_xrefs

- `0x180078421`: `CDeploymentSession::MergeUpdate`
- `0x1800784a9`: `CDeploymentSession::MergeUpdate`
- `0x180078569`: `CDeploymentSession::MergeUpdate`
- `0x18007876b`: `CDeploymentSession::MergeUpdate`
- `0x1800787d7`: `CDeploymentSession::MergeUpdate`
- `0x180078891`: `CDeploymentSession::MergeUpdate`
- `0x1800784c1`: `MergeUpdate: MergedSandBoxPath [%s]`
- `0x1800784fe`: `ActionList_%s.xml`
- `0x1800785a3`: `MergeUpdate: Copying ActionList to [%s]`
- `0x18007862f`: `MergeUpdate: Calling Arbiter to load the ActionList`
- `0x18007881b`: `MergeUpdate: Moving File: [%s]`
- `0x1800788d2`: `MergeUpdate: Update successfully merged`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDeploymentSession::MergeUpdate(CDeploymentSession *this, const wchar_t *a2)
{
  const WCHAR *v4; // r13
  const WCHAR *v5; // r14
  LPCWSTR v6; // r15
  __int64 v7; // rcx
  signed int v8; // edi
  __int64 updated; // rcx
  __int64 v10; // rdx
  DWORD FileAttributesW; // ebx
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  signed int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // r12d
  __int64 v23; // rcx
  unsigned int i; // r13d
  HANDLE v25; // rax
  HANDLE v26; // rax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rdx
  signed int LastError; // eax
  __int64 v37; // rax
  __int64 v38; // rcx
  const char *v39; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v41; // rax
  HANDLE v42; // rax
  wchar_t *v43; // rbx
  HANDLE v44; // rax
  __int64 result; // rax
  int v46; // [rsp+20h] [rbp-88h]
  int v47; // [rsp+28h] [rbp-80h]
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-78h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+38h] [rbp-70h] BYREF
  LPCWSTR v50; // [rsp+40h] [rbp-68h] BYREF
  __int64 v51; // [rsp+48h] [rbp-60h] BYREF
  wchar_t *v52; // [rsp+50h] [rbp-58h] BYREF
  __int64 v53; // [rsp+58h] [rbp-50h]
  __int64 v54; // [rsp+60h] [rbp-48h]
  const wchar_t *v55; // [rsp+68h] [rbp-40h]
  __int64 v56; // [rsp+70h] [rbp-38h]
  __int64 v57; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v57 = -2;
  try
  {
    v55 = a2;
    v52 = 0;
    v4 = 0;
    lpNewFileName = 0;
    v51 = 0;
    v5 = 0;
    lpExistingFileName = 0;
    v6 = 0;
    v50 = 0;
    if ( !a2 )
    {
      v7 = *((_QWORD *)this + 75);
      v8 = -2147024809;
      if ( !v7 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_78:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
        if ( v6 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v5 )
        {
          v41 = GetProcessHeap();
          HeapFree(v41, 0, (LPVOID)(v5 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v51 )
          (**(void (__fastcall ***)(__int64))v51)(v51);
        if ( v4 )
        {
          v42 = GetProcessHeap();
          HeapFree(v42, 0, (LPVOID)(v4 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v52 )
        {
          v43 = v52 - 2;
          v44 = GetProcessHeap();
          HeapFree(v44, 0, v43);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        return (unsigned int)v8;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v7,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::MergeUpdate",
                                5366,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v10);
      goto LABEL_8;
    }
    FileAttributesW = GetFileAttributesW(a2);
    if ( FileAttributesW == -1 )
      v12 = 0;
    else
      v12 = (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v13 = *((_QWORD *)this + 75);
    if ( !v12 )
    {
      v8 = -2147024893;
      if ( !v13 )
        goto LABEL_4;
      v47 = -2147024893;
      v46 = 5368;
      goto LABEL_15;
    }
    if ( v13 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v13, 2, L"MergeUpdate: MergedSandBoxPath [%s]", a2);
    if ( !*((_QWORD *)this + 9) )
    {
      v13 = *((_QWORD *)this + 75);
      v8 = -2147418113;
      if ( !v13 )
        goto LABEL_4;
      v47 = -2147418113;
      v46 = 5376;
      goto LABEL_15;
    }
    v14 = STRAPI_Format(&v52, L"ActionList_%s.xml");
    v8 = v14;
    if ( v14 < 0 )
    {
      v13 = *((_QWORD *)this + 75);
      if ( !v13 )
        goto LABEL_4;
      v47 = v14;
      v46 = 5377;
      goto LABEL_15;
    }
    v15 = CMiscHelpersT<CEmptyType>::CombinePath(a2, v52, 0, &lpNewFileName);
    v8 = v15;
    v16 = *((_QWORD *)this + 75);
    if ( v15 < 0 )
    {
      if ( v16 )
      {
        v16 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v16,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::MergeUpdate",
                              5378,
                              v15);
LABEL_27:
        if ( (int)v16 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16, v17);
      }
      goto LABEL_29;
    }
    v4 = lpNewFileName;
    if ( v16 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v16, 2, L"MergeUpdate: Copying ActionList to [%s]", lpNewFileName);
    if ( CopyFileW(*((LPCWSTR *)this + 63), v4, 0) )
    {
      v20 = *((_QWORD *)this + 75);
      if ( v20 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v20, 2, L"MergeUpdate: Calling Arbiter to load the ActionList");
      v21 = LoadActionList(0, *((_QWORD *)this + 63), v18, &v51);
      v8 = v21;
      if ( v21 >= 0 )
      {
        v22 = 0;
LABEL_46:
        if ( v22 >= *(_DWORD *)(v51 + 72) )
        {
          v38 = *((_QWORD *)this + 75);
          if ( v38 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v38, 2, L"MergeUpdate: Update successfully merged");
          goto LABEL_77;
        }
        v23 = *(_QWORD *)(v51 + 64) + 168LL * v22;
        v56 = v23;
        for ( i = 0; ; ++i )
        {
          if ( i >= *(_DWORD *)(v23 + 120) )
          {
            ++v22;
            goto LABEL_46;
          }
          v54 = 184LL * i;
          v53 = *(_QWORD *)(v23 + 112);
          if ( v5 )
          {
            v25 = GetProcessHeap();
            HeapFree(v25, 0, (LPVOID)(v5 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpExistingFileName = 0;
          }
          if ( v6 )
          {
            v26 = GetProcessHeap();
            HeapFree(v26, 0, (LPVOID)(v6 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            v6 = 0;
            v50 = 0;
          }
          v27 = v53;
          v28 = CMiscHelpersT<CEmptyType>::CombinePath(
                  *((_QWORD *)this + 61),
                  *(_QWORD *)(184LL * i + v53 + 24),
                  0,
                  &lpExistingFileName);
          v8 = v28;
          if ( v28 < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            if ( v29 )
            {
              v30 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v29,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::MergeUpdate",
                      5398,
                      v28);
              v29 = (unsigned int)v30;
              if ( v30 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v30, v31);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v29);
            v5 = lpExistingFileName;
            goto LABEL_77;
          }
          v32 = CMiscHelpersT<CEmptyType>::CombinePath(v55, *(_QWORD *)(v54 + v27 + 24), 0, &v50);
          v8 = v32;
          v33 = *((_QWORD *)this + 75);
          if ( v32 < 0 )
          {
            if ( v33 )
            {
              v34 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v33,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDeploymentSession::MergeUpdate",
                      5399,
                      v32);
              v33 = (unsigned int)v34;
              if ( v34 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34, v35);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v33);
            v5 = lpExistingFileName;
            v6 = v50;
            goto LABEL_77;
          }
          v5 = lpExistingFileName;
          if ( v33 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v33, 2, L"MergeUpdate: Moving File: [%s]", lpExistingFileName);
          v6 = v50;
          if ( !MoveFileW(v5, v50) )
            break;
          v23 = v56;
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
        v37 = *((_QWORD *)this + 75);
        v16 = 0;
        if ( v8 < 0 && v37 )
        {
          v16 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v37,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::MergeUpdate",
                                5402,
                                v8);
          goto LABEL_27;
        }
LABEL_29:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v16);
LABEL_77:
        v4 = lpNewFileName;
        goto LABEL_78;
      }
      v13 = *((_QWORD *)this + 75);
      if ( !v13 )
        goto LABEL_4;
      v47 = v21;
      v46 = 5387;
    }
    else
    {
      v19 = GetLastError();
      v8 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      updated = 0;
      if ( v8 >= 0 || !*((_QWORD *)this + 75) )
        goto LABEL_8;
      v47 = v8;
      v46 = 5380;
      v13 = *((_QWORD *)this + 75);
    }
LABEL_15:
    updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v13,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::MergeUpdate",
                              v46,
                              v47);
    goto LABEL_6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1522,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v39);
  }
  return result;
}

```

## disassembly

```asm
0x1800783ac  mov     rax, rsp
0x1800783af  push    rdi
0x1800783b0  push    r12
0x1800783b2  push    r13
0x1800783b4  push    r14
0x1800783b6  push    r15
0x1800783b8  sub     rsp, 80h
0x1800783bf  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x1800783c7  mov     [rax+18h], rbx
0x1800783cb  mov     [rax+20h], rsi
0x1800783cf  mov     r12, rdx
0x1800783d2  mov     [rsp+0A8h+var_40], rdx
0x1800783d7  mov     rsi, rcx
0x1800783da  xor     edx, edx
0x1800783dc  mov     [rax-58h], rdx
0x1800783e0  xor     r13d, r13d
0x1800783e3  mov     [rax-78h], r13
0x1800783e7  xor     ebx, ebx
0x1800783e9  mov     [rax-60h], rbx
0x1800783ed  xor     r14d, r14d
0x1800783f0  mov     [rax-70h], r14
0x1800783f4  xor     r15d, r15d
0x1800783f7  mov     [rax-68h], r15
0x1800783fb  test    r12, r12
0x1800783fe  jnz     short loc_18007844E
0x180078400  mov     rcx, [rcx+258h]
0x180078407  mov     edi, 80070057h
0x18007840c  test    rcx, rcx
0x18007840f  jnz     short loc_180078415
0x180078411  xor     ecx, ecx
0x180078413  jmp     short loc_180078444
0x180078415  mov     [rsp+0A8h+var_80], edi
0x180078419  mov     [rsp+0A8h+var_88], 14F6h
0x180078421  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078428  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007842f  mov     edx, 4
0x180078434  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078439  mov     ecx, eax
0x18007843b  test    ecx, ecx
0x18007843d  jns     short loc_180078444
0x18007843f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078444  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078449  jmp     loc_1800788E8
0x18007844e  mov     rcx, r12; lpFileName
0x180078451  call    cs:__imp_GetFileAttributesW
0x180078458  nop     dword ptr [rax+rax+00h]
0x18007845d  mov     ebx, eax
0x18007845f  cmp     eax, 0FFFFFFFFh
0x180078462  jz      short loc_18007846C
0x180078464  shr     ebx, 4
0x180078467  and     ebx, 1
0x18007846a  jmp     short loc_18007846E
0x18007846c  xor     ebx, ebx
0x18007846e  xor     ecx, ecx
0x180078470  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078475  xor     ecx, ecx
0x180078477  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007847c  mov     rcx, [rsi+258h]
0x180078483  test    ebx, ebx
0x180078485  jnz     short loc_1800784B9
0x180078487  mov     edi, 80070003h
0x18007848c  test    rcx, rcx
0x18007848f  jz      short loc_180078411
0x180078491  mov     [rsp+0A8h+var_80], edi
0x180078495  mov     [rsp+0A8h+var_88], 14F8h
0x18007849d  mov     edx, 4
0x1800784a2  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800784a9  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x1800784b0  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800784b5  mov     ecx, eax
0x1800784b7  jmp     short loc_18007843B
0x1800784b9  test    rcx, rcx
0x1800784bc  jz      short loc_1800784D2
0x1800784be  mov     r9, r12
0x1800784c1  lea     r8, aMergeupdateMer; "MergeUpdate: MergedSandBoxPath [%s]"
0x1800784c8  mov     edx, 2
0x1800784cd  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800784d2  mov     r8, [rsi+48h]
0x1800784d6  test    r8, r8
0x1800784d9  jnz     short loc_1800784FE
0x1800784db  mov     rcx, [rsi+258h]
0x1800784e2  mov     edi, 8000FFFFh
0x1800784e7  test    rcx, rcx
0x1800784ea  jz      loc_180078411
0x1800784f0  mov     [rsp+0A8h+var_80], edi
0x1800784f4  mov     [rsp+0A8h+var_88], 1500h
0x1800784fc  jmp     short loc_18007849D
0x1800784fe  lea     rdx, aActionlistSXml; "ActionList_%s.xml"
0x180078505  lea     rcx, [rsp+0A8h+var_58]; wchar_t **
0x18007850a  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18007850f  mov     edi, eax
0x180078511  test    eax, eax
0x180078513  jns     short loc_180078536
0x180078515  mov     rcx, [rsi+258h]
0x18007851c  test    rcx, rcx
0x18007851f  jz      loc_180078411
0x180078525  mov     [rsp+0A8h+var_80], eax
0x180078529  mov     [rsp+0A8h+var_88], 1501h
0x180078531  jmp     loc_18007849D
0x180078536  lea     r9, [rsp+0A8h+lpNewFileName]
0x18007853b  xor     r8d, r8d
0x18007853e  mov     rdx, [rsp+0A8h+var_58]
0x180078543  mov     rcx, r12
0x180078546  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18007854b  mov     edi, eax
0x18007854d  mov     rcx, [rsi+258h]
0x180078554  test    eax, eax
0x180078556  jns     short loc_180078596
0x180078558  test    rcx, rcx
0x18007855b  jz      short loc_18007858C
0x18007855d  mov     [rsp+0A8h+var_80], eax
0x180078561  mov     [rsp+0A8h+var_88], 1502h
0x180078569  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078570  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180078577  mov     edx, 4
0x18007857c  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078581  mov     ecx, eax
0x180078583  test    ecx, ecx
0x180078585  jns     short loc_18007858C
0x180078587  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007858c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078591  jmp     loc_1800788E3
0x180078596  mov     r13, [rsp+0A8h+lpNewFileName]
0x18007859b  test    rcx, rcx
0x18007859e  jz      short loc_1800785B4
0x1800785a0  mov     r9, r13
0x1800785a3  lea     r8, aMergeupdateCop; "MergeUpdate: Copying ActionList to [%s]"
0x1800785aa  mov     edx, 2
0x1800785af  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800785b4  xor     r8d, r8d; bFailIfExists
0x1800785b7  mov     rdx, r13; lpNewFileName
0x1800785ba  mov     rcx, [rsi+1F8h]; lpExistingFileName
0x1800785c1  call    cs:__imp_CopyFileW
0x1800785c8  nop     dword ptr [rax+rax+00h]
0x1800785cd  test    eax, eax
0x1800785cf  jnz     short loc_180078623
0x1800785d1  call    cs:__imp_GetLastError
0x1800785d8  nop     dword ptr [rax+rax+00h]
0x1800785dd  mov     edi, eax
0x1800785df  test    eax, eax
0x1800785e1  jnz     short loc_1800785EA
0x1800785e3  mov     edi, 80004005h
0x1800785e8  jmp     short loc_1800785F5
0x1800785ea  jle     short loc_1800785F5
0x1800785ec  movzx   edi, ax
0x1800785ef  or      edi, 80070000h
0x1800785f5  mov     rax, [rsi+258h]
0x1800785fc  xor     ecx, ecx
0x1800785fe  test    edi, edi
0x180078600  jns     loc_180078444
0x180078606  test    rax, rax
0x180078609  jz      loc_180078444
0x18007860f  mov     [rsp+0A8h+var_80], edi
0x180078613  mov     [rsp+0A8h+var_88], 1504h
0x18007861b  mov     rcx, rax
0x18007861e  jmp     loc_18007849D
0x180078623  mov     rcx, [rsi+258h]
0x18007862a  test    rcx, rcx
0x18007862d  jz      short loc_180078640
0x18007862f  lea     r8, aMergeupdateCal; "MergeUpdate: Calling Arbiter to load th"...
0x180078636  mov     edx, 2
0x18007863b  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078640  lea     r9, [rsp+0A8h+var_60]
0x180078645  mov     rdx, [rsi+1F8h]
0x18007864c  xor     ecx, ecx
0x18007864e  call    LoadActionList
0x180078653  mov     edi, eax
0x180078655  test    eax, eax
0x180078657  jns     short loc_18007867A
0x180078659  mov     rcx, [rsi+258h]
0x180078660  test    rcx, rcx
0x180078663  jz      loc_180078411
0x180078669  mov     [rsp+0A8h+var_80], eax
0x18007866d  mov     [rsp+0A8h+var_88], 150Bh
0x180078675  jmp     loc_18007849D
0x18007867a  xor     r12d, r12d
0x18007867d  mov     rbx, [rsp+0A8h+var_60]
0x180078682  cmp     r12d, [rbx+48h]
0x180078686  jnb     loc_1800788C6
0x18007868c  mov     eax, r12d
0x18007868f  imul    rcx, rax, 0A8h
0x180078696  add     rcx, [rbx+40h]
0x18007869a  mov     [rsp+0A8h+var_38], rcx
0x18007869f  xor     r13d, r13d
0x1800786a2  cmp     r13d, [rcx+78h]
0x1800786a6  jnb     loc_1800788BE
0x1800786ac  mov     eax, r13d
0x1800786af  imul    rdi, rax, 0B8h
0x1800786b6  mov     [rsp+0A8h+var_48], rdi
0x1800786bb  mov     rax, [rcx+70h]
0x1800786bf  mov     [rsp+0A8h+var_50], rax
0x1800786c4  test    r14, r14
0x1800786c7  jz      short loc_1800786FA
0x1800786c9  call    cs:__imp_GetProcessHeap
0x1800786d0  nop     dword ptr [rax+rax+00h]
0x1800786d5  mov     rcx, rax; hHeap
0x1800786d8  lea     r8, [r14-4]; lpMem
0x1800786dc  xor     edx, edx; dwFlags
0x1800786de  call    cs:__imp_HeapFree
0x1800786e5  nop     dword ptr [rax+rax+00h]
0x1800786ea  xor     ecx, ecx
0x1800786ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800786f1  mov     [rsp+0A8h+lpExistingFileName], 0
0x1800786fa  test    r15, r15
0x1800786fd  jz      short loc_18007872F
0x1800786ff  call    cs:__imp_GetProcessHeap
0x180078706  nop     dword ptr [rax+rax+00h]
0x18007870b  mov     rcx, rax; hHeap
0x18007870e  lea     r8, [r15-4]; lpMem
0x180078712  xor     edx, edx; dwFlags
0x180078714  call    cs:__imp_HeapFree
0x18007871b  nop     dword ptr [rax+rax+00h]
0x180078720  xor     ecx, ecx
0x180078722  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078727  xor     r15d, r15d
0x18007872a  mov     [rsp+0A8h+var_68], r15
0x18007872f  lea     r9, [rsp+0A8h+lpExistingFileName]
0x180078734  xor     r8d, r8d
0x180078737  mov     rbx, [rsp+0A8h+var_50]
0x18007873c  mov     rdx, [rdi+rbx+18h]
0x180078741  mov     rcx, [rsi+1E8h]
0x180078748  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18007874d  mov     edi, eax
0x18007874f  test    eax, eax
0x180078751  jns     short loc_18007879D
0x180078753  mov     rcx, [rsi+258h]
0x18007875a  test    rcx, rcx
0x18007875d  jz      short loc_18007878E
0x18007875f  mov     [rsp+0A8h+var_80], eax
0x180078763  mov     [rsp+0A8h+var_88], 1516h
0x18007876b  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078772  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180078779  mov     edx, 4
0x18007877e  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078783  mov     ecx, eax
0x180078785  test    eax, eax
0x180078787  jns     short loc_18007878E
0x180078789  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007878e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078793  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078798  jmp     loc_1800788E3
0x18007879d  lea     r9, [rsp+0A8h+var_68]
0x1800787a2  xor     r8d, r8d
0x1800787a5  mov     rdx, [rsp+0A8h+var_48]
0x1800787aa  mov     rdx, [rdx+rbx+18h]
0x1800787af  mov     rcx, [rsp+0A8h+var_40]
0x1800787b4  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1800787b9  mov     edi, eax
0x1800787bb  mov     rcx, [rsi+258h]
0x1800787c2  test    eax, eax
0x1800787c4  jns     short loc_18007880E
0x1800787c6  test    rcx, rcx
0x1800787c9  jz      short loc_1800787FA
0x1800787cb  mov     [rsp+0A8h+var_80], eax
0x1800787cf  mov     [rsp+0A8h+var_88], 1517h
0x1800787d7  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x1800787de  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800787e5  mov     edx, 4
0x1800787ea  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800787ef  mov     ecx, eax
0x1800787f1  test    eax, eax
0x1800787f3  jns     short loc_1800787FA
0x1800787f5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800787fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800787ff  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078804  mov     r15, [rsp+0A8h+var_68]
0x180078809  jmp     loc_1800788E3
0x18007880e  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078813  test    rcx, rcx
0x180078816  jz      short loc_18007882C
0x180078818  mov     r9, r14
0x18007881b  lea     r8, aMergeupdateMov; "MergeUpdate: Moving File: [%s]"
0x180078822  mov     edx, 2
0x180078827  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007882c  mov     r15, [rsp+0A8h+var_68]
0x180078831  mov     rdx, r15; lpNewFileName
0x180078834  mov     rcx, r14; lpExistingFileName
0x180078837  call    cs:__imp_MoveFileW
0x18007883e  nop     dword ptr [rax+rax+00h]
0x180078843  test    eax, eax
0x180078845  jnz     short loc_1800788B1
0x180078847  call    cs:__imp_GetLastError
0x18007884e  nop     dword ptr [rax+rax+00h]
0x180078853  mov     edi, eax
0x180078855  test    eax, eax
0x180078857  jnz     short loc_180078860
0x180078859  mov     edi, 80004005h
0x18007885e  jmp     short loc_18007886B
0x180078860  jle     short loc_18007886B
0x180078862  movzx   edi, ax
0x180078865  or      edi, 80070000h
0x18007886b  mov     rax, [rsi+258h]
0x180078872  xor     ecx, ecx
0x180078874  test    edi, edi
0x180078876  jns     loc_18007858C
0x18007887c  test    rax, rax
0x18007887f  jz      loc_18007858C
0x180078885  mov     [rsp+0A8h+var_80], edi
0x180078889  mov     [rsp+0A8h+var_88], 151Ah
0x180078891  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
  ... truncated ...
```
