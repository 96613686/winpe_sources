# CDeploymentSession::CopyMetadataPayload(ActionList *,int *,int *)

- ea: `0x18003dc94`
- end: `0x18003e2fd`
- name: `?CopyMetadataPayload@CDeploymentSession@@QEAAJPEAUActionList@@PEAH1@Z`
- size: `1641`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, struct ActionList *, int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180068e98`

## callees

- `0x1800127a4`
- `0x180039f90`
- `0x18003c418`
- `0x18003dc94`
- `0x18004c794`
- `0x180077664`
- `0x180078b9c`
- `0x18009f0b0`
- `0x180223ec8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003df29`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003e1e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003df29`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003e1e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dfef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e170`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e2b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dfef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e0a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e170`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e2b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e29b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e004`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e29b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e10b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18003e0f7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x18003e0f7`

## string_xrefs

- `0x18003dd02`: `CDeploymentSession::CopyMetadataPayload`
- `0x18003dd5d`: `CDeploymentSession::CopyMetadataPayload`
- `0x18003deef`: `CDeploymentSession::CopyMetadataPayload`
- `0x18003dfb8`: `CDeploymentSession::CopyMetadataPayload`
- `0x18003e079`: `CDeploymentSession::CopyMetadataPayload`
- `0x18003e0db`: `Copying [%s] to Metadata folder`
- `0x18003e22d`: `PSF file [%s] already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeploymentSession::CopyMetadataPayload(
        CDeploymentSession *this,
        struct ActionList *a2,
        int *a3,
        int *a4)
{
  struct ActionList *v6; // r8
  const WCHAR *v8; // r14
  __int64 v9; // rcx
  unsigned int v10; // edi
  __int64 updated; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r15d
  unsigned int i; // edx
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // r13
  wchar_t *v19; // rdi
  LPCWSTR v20; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  wchar_t *v23; // r12
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  DWORD FileAttributesW; // eax
  BOOL v30; // ebx
  wchar_t *v31; // rbx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  wchar_t *v37; // rbx
  HANDLE v38; // rax
  CDeploymentSession *v39; // rcx
  int FileFromWim; // eax
  __int64 v41; // rcx
  wchar_t *v42; // rbx
  HANDLE v43; // rax
  __int64 v44; // rcx
  signed int LastError; // eax
  LPCWSTR v46; // rbx
  HANDLE v47; // rax
  wchar_t *v48; // r12
  int v49; // eax
  DWORD v50; // eax
  BOOL v51; // ebx
  __int64 v52; // rcx
  const char *v53; // r9
  HANDLE v54; // rax
  LPCWSTR v55; // rbx
  HANDLE v56; // rax
  __int64 result; // rax
  int v58; // [rsp+20h] [rbp-A8h]
  int v59; // [rsp+28h] [rbp-A0h]
  wchar_t *v60; // [rsp+30h] [rbp-98h] BYREF
  BOOL v61; // [rsp+38h] [rbp-90h]
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-88h] BYREF
  int v63; // [rsp+48h] [rbp-80h]
  unsigned int v64; // [rsp+4Ch] [rbp-7Ch]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-78h] BYREF
  wchar_t *v66; // [rsp+58h] [rbp-70h] BYREF
  __int64 v67; // [rsp+60h] [rbp-68h]
  struct ActionList *v68; // [rsp+68h] [rbp-60h]
  int *v69; // [rsp+70h] [rbp-58h]
  int *v70; // [rsp+78h] [rbp-50h]
  __int64 v71; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v71 = -2;
  try
  {
    v70 = a4;
    v69 = a3;
    v6 = a2;
    v68 = a2;
    lpExistingFileName = 0;
    v8 = 0;
    lpFileName = 0;
    if ( !a2 )
    {
      v9 = *((_QWORD *)this + 75);
      v10 = -2147024809;
      if ( v9 )
      {
        updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v9,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::CopyMetadataPayload",
                                  5099,
                                  -2147024809);
        goto LABEL_6;
      }
      goto LABEL_4;
    }
    if ( !a3 )
    {
      v13 = *((_QWORD *)this + 75);
      v10 = -2147024809;
      if ( v13 )
      {
        v59 = -2147024809;
        v58 = 5100;
        goto LABEL_12;
      }
LABEL_4:
      updated = 0;
      goto LABEL_8;
    }
    if ( !a4 )
    {
      v13 = *((_QWORD *)this + 75);
      v10 = -2147024809;
      if ( v13 )
      {
        v59 = -2147024809;
        v58 = 5101;
        goto LABEL_12;
      }
      goto LABEL_4;
    }
    v10 = 0;
    v14 = 0;
    v61 = 0;
    for ( i = 0; ; ++i )
    {
      v64 = i;
      if ( i >= *((_DWORD *)v6 + 18) )
      {
        *v69 = v14;
        *v70 = v61;
        goto LABEL_81;
      }
      v16 = *((_QWORD *)v6 + 8) + 168LL * i;
      v67 = v16;
      if ( *(_DWORD *)(v16 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
        break;
LABEL_79:
      ;
    }
    v61 = *(_DWORD *)(v16 + 104) == 2;
    v17 = 0;
    while ( 1 )
    {
      v63 = v17;
      if ( (unsigned int)v17 >= *(_DWORD *)(v16 + 120) )
      {
        i = v64;
        v6 = v68;
        goto LABEL_79;
      }
      v18 = 92 * v17;
      v19 = *(wchar_t **)(v16 + 112);
      v60 = v19;
      v20 = lpExistingFileName;
      if ( lpExistingFileName )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v20 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        lpExistingFileName = 0;
      }
      if ( v8 )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 0, (LPVOID)(v8 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v8 = 0;
        lpFileName = 0;
      }
      v23 = &v19[v18];
      v24 = CMiscHelpersT<CEmptyType>::CombinePath(
              *((_QWORD *)this + 61),
              *(_QWORD *)&v19[v18 + 12],
              0,
              &lpExistingFileName);
      v10 = v24;
      if ( v24 < 0 )
      {
        v13 = *((_QWORD *)this + 75);
        if ( !v13 )
          goto LABEL_4;
        v59 = v24;
        v58 = 5121;
        goto LABEL_12;
      }
      v25 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), *((_QWORD *)v23 + 3), 0, &lpFileName);
      v10 = v25;
      if ( v25 < 0 )
      {
        v26 = *((_QWORD *)this + 75);
        if ( v26 )
        {
          v27 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v26,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::CopyMetadataPayload",
                  5122,
                  v25);
          v26 = (unsigned int)v27;
          if ( v27 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v27, v28);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
        v8 = lpFileName;
        goto LABEL_81;
      }
      v8 = lpFileName;
      FileAttributesW = GetFileAttributesW(lpFileName);
      v30 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v30 )
      {
        v10 = 0;
        v31 = v60;
        if ( *(_QWORD *)&v60[v18 + 24] )
        {
          v60 = 0;
          v32 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v60);
          v33 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)&v31[v18 + 24], 0, v32);
          v10 = v33;
          if ( v33 < 0 )
          {
            v34 = *((_QWORD *)this + 75);
            if ( !v34 )
            {
LABEL_41:
              v35 = 0;
LABEL_45:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v35);
              v37 = v60;
              if ( !v60 )
                goto LABEL_81;
              v38 = GetProcessHeap();
              HeapFree(v38, 0, v37 - 2);
              goto LABEL_4;
            }
            v35 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v34,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::CopyMetadataPayload",
                                  5133,
                                  v33);
LABEL_43:
            if ( (int)v35 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v35, v36);
            goto LABEL_45;
          }
          if ( (unsigned int)FileExists(v60) )
          {
            v66 = v60;
            LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Extracting [{}] from [{}]", v23 + 12, &v66);
            FileFromWim = CDeploymentSession::ExtractFileFromWim(
                            v39,
                            v60,
                            *((const wchar_t **)v23 + 3),
                            lpExistingFileName);
            v10 = FileFromWim;
            if ( FileFromWim < 0 )
            {
              v41 = *((_QWORD *)this + 75);
              if ( !v41 )
                goto LABEL_41;
              v35 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                    v41,
                                    4,
                                    L"%s(%d): Result = 0x%X",
                                    L"CDeploymentSession::CopyMetadataPayload",
                                    5138,
                                    FileFromWim);
              goto LABEL_43;
            }
          }
          v42 = v60;
          if ( v60 )
          {
            v43 = GetProcessHeap();
            HeapFree(v43, 0, v42 - 2);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
        }
        v44 = *((_QWORD *)this + 75);
        if ( v44 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v44, 2, L"Copying [%s] to Metadata folder", *((_QWORD *)v23 + 3));
        if ( !CopyFileW(lpExistingFileName, v8, 0) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v10 = -2147467259;
          }
          updated = 0;
          if ( (v10 & 0x80000000) != 0 && *((_QWORD *)this + 75) )
          {
            v59 = v10;
            v58 = 5143;
            v13 = *((_QWORD *)this + 75);
            goto LABEL_12;
          }
          goto LABEL_8;
        }
        goto LABEL_75;
      }
      if ( v14 )
      {
        v10 = 0;
      }
      else
      {
        v46 = lpExistingFileName;
        if ( lpExistingFileName )
        {
          v47 = GetProcessHeap();
          HeapFree(v47, 0, (LPVOID)(v46 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          lpExistingFileName = 0;
        }
        v48 = v60;
        v49 = CMiscHelpersT<CEmptyType>::CombinePath(
                *((_QWORD *)this + 61),
                *(_QWORD *)&v60[v18 + 36],
                0,
                &lpExistingFileName);
        v10 = v49;
        if ( v49 < 0 )
        {
          v13 = *((_QWORD *)this + 75);
          if ( !v13 )
            goto LABEL_4;
          v59 = v49;
          v58 = 5150;
LABEL_12:
          updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                    v13,
                                    4,
                                    L"%s(%d): Result = 0x%X",
                                    L"CDeploymentSession::CopyMetadataPayload",
                                    v58,
                                    v59);
LABEL_6:
          if ( (int)updated < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v12);
LABEL_8:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_81:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
          if ( v8 )
          {
            v54 = GetProcessHeap();
            HeapFree(v54, 0, (LPVOID)(v8 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          v55 = lpExistingFileName;
          if ( lpExistingFileName )
          {
            v56 = GetProcessHeap();
            HeapFree(v56, 0, (LPVOID)(v55 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          return v10;
        }
        v50 = GetFileAttributesW(v8);
        v51 = v50 != -1 && (v50 & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v10 = 0;
        if ( !v51 )
        {
          v52 = *((_QWORD *)this + 75);
          if ( v52 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v52,
              2,
              L"PSF file [%s] already exists",
              *(_QWORD *)&v48[v18 + 36]);
LABEL_75:
          v14 = 1;
        }
      }
      v17 = (unsigned int)(v63 + 1);
      v16 = v67;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1431,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v53);
  }
  return result;
}

```

## disassembly

```asm
0x18003dc94  mov     rax, rsp
0x18003dc97  push    rbx
0x18003dc98  push    rsi
0x18003dc99  push    rdi
0x18003dc9a  push    r12
0x18003dc9c  push    r13
0x18003dc9e  push    r14
0x18003dca0  push    r15
0x18003dca2  sub     rsp, 90h
0x18003dca9  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18003dcb1  mov     r10, r9
0x18003dcb4  mov     [rsp+0C8h+var_50], r9
0x18003dcb9  mov     r9, r8
0x18003dcbc  mov     [rsp+0C8h+var_58], r8
0x18003dcc1  mov     r8, rdx
0x18003dcc4  mov     [rsp+0C8h+var_60], rdx
0x18003dcc9  mov     rsi, rcx
0x18003dccc  mov     [rsp+0C8h+lpExistingFileName], 0
0x18003dcd5  xor     r14d, r14d
0x18003dcd8  mov     [rax-78h], r14
0x18003dcdc  test    rdx, rdx
0x18003dcdf  jnz     short loc_18003DD2F
0x18003dce1  mov     rcx, [rcx+258h]
0x18003dce8  mov     edi, 80070057h
0x18003dced  test    rcx, rcx
0x18003dcf0  jnz     short loc_18003DCF6
0x18003dcf2  xor     ecx, ecx
0x18003dcf4  jmp     short loc_18003DD25
0x18003dcf6  mov     [rsp+0C8h+var_A0], edi
0x18003dcfa  mov     [rsp+0C8h+var_A8], 13EBh
0x18003dd02  lea     r9, aCdeploymentses_80; "CDeploymentSession::CopyMetadataPayload"
0x18003dd09  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003dd10  mov     edx, 4
0x18003dd15  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003dd1a  mov     ecx, eax
0x18003dd1c  test    ecx, ecx
0x18003dd1e  jns     short loc_18003DD25
0x18003dd20  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003dd25  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003dd2a  jmp     loc_18003E279
0x18003dd2f  test    r9, r9
0x18003dd32  jnz     short loc_18003DD6D
0x18003dd34  mov     rcx, [rcx+258h]
0x18003dd3b  mov     edi, 80070057h
0x18003dd40  test    rcx, rcx
0x18003dd43  jz      short loc_18003DCF2
0x18003dd45  mov     [rsp+0C8h+var_A0], edi
0x18003dd49  mov     [rsp+0C8h+var_A8], 13ECh
0x18003dd51  mov     edx, 4
0x18003dd56  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003dd5d  lea     r9, aCdeploymentses_80; "CDeploymentSession::CopyMetadataPayload"
0x18003dd64  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003dd69  mov     ecx, eax
0x18003dd6b  jmp     short loc_18003DD1C
0x18003dd6d  test    r10, r10
0x18003dd70  jnz     short loc_18003DD95
0x18003dd72  mov     rcx, [rcx+258h]
0x18003dd79  mov     edi, 80070057h
0x18003dd7e  test    rcx, rcx
0x18003dd81  jz      loc_18003DCF2
0x18003dd87  mov     [rsp+0C8h+var_A0], edi
0x18003dd8b  mov     [rsp+0C8h+var_A8], 13EDh
0x18003dd93  jmp     short loc_18003DD51
0x18003dd95  xor     edi, edi
0x18003dd97  xor     r15d, r15d
0x18003dd9a  xor     eax, eax
0x18003dd9c  mov     [rsp+0C8h+var_90], eax
0x18003dda0  xor     edx, edx
0x18003dda2  mov     [rsp+0C8h+var_7C], edx
0x18003dda6  cmp     edx, [r8+48h]
0x18003ddaa  jnb     loc_18003E266
0x18003ddb0  mov     eax, edx
0x18003ddb2  imul    rcx, rax, 0A8h
0x18003ddb9  add     rcx, [r8+40h]
0x18003ddbd  mov     [rsp+0C8h+var_68], rcx
0x18003ddc2  cmp     dword ptr [rcx+68h], 2
0x18003ddc6  jz      short loc_18003DDD5
0x18003ddc8  cmp     dword ptr [rsi+1C8h], 8
0x18003ddcf  jnz     loc_18003E25F
0x18003ddd5  xor     r9d, r9d
0x18003ddd8  cmp     dword ptr [rcx+68h], 2
0x18003dddc  setz    r9b
0x18003dde0  mov     [rsp+0C8h+var_90], r9d
0x18003dde5  xor     eax, eax
0x18003dde7  mov     [rsp+0C8h+var_80], eax
0x18003ddeb  cmp     eax, [rcx+78h]
0x18003ddee  jnb     loc_18003E256
0x18003ddf4  imul    r13, rax, 0B8h
0x18003ddfb  mov     rdi, [rcx+70h]
0x18003ddff  mov     [rsp+0C8h+var_98], rdi
0x18003de04  mov     rbx, [rsp+0C8h+lpExistingFileName]
0x18003de09  test    rbx, rbx
0x18003de0c  jz      short loc_18003DE3F
0x18003de0e  call    cs:__imp_GetProcessHeap
0x18003de15  nop     dword ptr [rax+rax+00h]
0x18003de1a  mov     rcx, rax; hHeap
0x18003de1d  lea     r8, [rbx-4]; lpMem
0x18003de21  xor     edx, edx; dwFlags
0x18003de23  call    cs:__imp_HeapFree
0x18003de2a  nop     dword ptr [rax+rax+00h]
0x18003de2f  xor     ecx, ecx
0x18003de31  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003de36  mov     [rsp+0C8h+lpExistingFileName], 0
0x18003de3f  test    r14, r14
0x18003de42  jz      short loc_18003DE74
0x18003de44  call    cs:__imp_GetProcessHeap
0x18003de4b  nop     dword ptr [rax+rax+00h]
0x18003de50  mov     rcx, rax; hHeap
0x18003de53  lea     r8, [r14-4]; lpMem
0x18003de57  xor     edx, edx; dwFlags
0x18003de59  call    cs:__imp_HeapFree
0x18003de60  nop     dword ptr [rax+rax+00h]
0x18003de65  xor     ecx, ecx
0x18003de67  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003de6c  xor     r14d, r14d
0x18003de6f  mov     [rsp+0C8h+lpFileName], r14
0x18003de74  lea     r12, [rdi+r13]
0x18003de78  lea     r9, [rsp+0C8h+lpExistingFileName]
0x18003de7d  xor     r8d, r8d
0x18003de80  mov     rdx, [r12+18h]
0x18003de85  mov     rcx, [rsi+1E8h]
0x18003de8c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003de91  mov     edi, eax
0x18003de93  test    eax, eax
0x18003de95  jns     short loc_18003DEB8
0x18003de97  mov     rcx, [rsi+258h]
0x18003de9e  test    rcx, rcx
0x18003dea1  jz      loc_18003DCF2
0x18003dea7  mov     [rsp+0C8h+var_A0], eax
0x18003deab  mov     [rsp+0C8h+var_A8], 1401h
0x18003deb3  jmp     loc_18003DD51
0x18003deb8  lea     r9, [rsp+0C8h+lpFileName]
0x18003debd  xor     r8d, r8d
0x18003dec0  mov     rdx, [r12+18h]
0x18003dec5  mov     rcx, [rsi+1F0h]
0x18003decc  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003ded1  mov     edi, eax
0x18003ded3  test    eax, eax
0x18003ded5  jns     short loc_18003DF21
0x18003ded7  mov     rcx, [rsi+258h]
0x18003dede  test    rcx, rcx
0x18003dee1  jz      short loc_18003DF12
0x18003dee3  mov     [rsp+0C8h+var_A0], eax
0x18003dee7  mov     [rsp+0C8h+var_A8], 1402h
0x18003deef  lea     r9, aCdeploymentses_80; "CDeploymentSession::CopyMetadataPayload"
0x18003def6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003defd  mov     edx, 4
0x18003df02  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003df07  mov     ecx, eax
0x18003df09  test    eax, eax
0x18003df0b  jns     short loc_18003DF12
0x18003df0d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003df12  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003df17  mov     r14, [rsp+0C8h+lpFileName]
0x18003df1c  jmp     loc_18003E279
0x18003df21  mov     r14, [rsp+0C8h+lpFileName]
0x18003df26  mov     rcx, r14; lpFileName
0x18003df29  call    cs:__imp_GetFileAttributesW
0x18003df30  nop     dword ptr [rax+rax+00h]
0x18003df35  mov     ebx, eax
0x18003df37  cmp     eax, 0FFFFFFFFh
0x18003df3a  jz      short loc_18003DF46
0x18003df3c  shr     ebx, 4
0x18003df3f  not     ebx
0x18003df41  and     ebx, 1
0x18003df44  jmp     short loc_18003DF48
0x18003df46  xor     ebx, ebx
0x18003df48  xor     ecx, ecx
0x18003df4a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003df4f  xor     ecx, ecx
0x18003df51  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003df56  test    ebx, ebx
0x18003df58  jnz     loc_18003E15D
0x18003df5e  xor     edi, edi
0x18003df60  mov     rbx, [rsp+0C8h+var_98]
0x18003df65  cmp     [rbx+r13+30h], rdi
0x18003df6a  jz      loc_18003E0CA
0x18003df70  mov     [rsp+0C8h+var_98], rdi
0x18003df75  lea     rcx, [rsp+0C8h+var_98]
0x18003df7a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18003df7f  mov     r9, rax
0x18003df82  xor     r8d, r8d
0x18003df85  mov     rdx, [rbx+r13+30h]
0x18003df8a  mov     rcx, [rsi+1E8h]
0x18003df91  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003df96  mov     edi, eax
0x18003df98  test    eax, eax
0x18003df9a  jns     short loc_18003E015
0x18003df9c  mov     rcx, [rsi+258h]
0x18003dfa3  test    rcx, rcx
0x18003dfa6  jnz     short loc_18003DFAC
0x18003dfa8  xor     ecx, ecx
0x18003dfaa  jmp     short loc_18003DFDB
0x18003dfac  mov     [rsp+0C8h+var_A0], eax
0x18003dfb0  mov     [rsp+0C8h+var_A8], 140Dh
0x18003dfb8  lea     r9, aCdeploymentses_80; "CDeploymentSession::CopyMetadataPayload"
0x18003dfbf  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003dfc6  mov     edx, 4
0x18003dfcb  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003dfd0  mov     ecx, eax
0x18003dfd2  test    ecx, ecx
0x18003dfd4  jns     short loc_18003DFDB
0x18003dfd6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003dfdb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003dfe0  nop
0x18003dfe1  mov     rbx, [rsp+0C8h+var_98]
0x18003dfe6  test    rbx, rbx
0x18003dfe9  jz      loc_18003E279
0x18003dfef  call    cs:__imp_GetProcessHeap
0x18003dff6  nop     dword ptr [rax+rax+00h]
0x18003dffb  mov     rcx, rax; hHeap
0x18003dffe  lea     r8, [rbx-4]; lpMem
0x18003e002  xor     edx, edx; dwFlags
0x18003e004  call    cs:__imp_HeapFree
0x18003e00b  nop     dword ptr [rax+rax+00h]
0x18003e010  jmp     loc_18003DCF2
0x18003e015  mov     rcx, [rsp+0C8h+var_98]
0x18003e01a  call    FileExists
0x18003e01f  test    eax, eax
0x18003e021  jz      short loc_18003E098
0x18003e023  mov     rax, [rsp+0C8h+var_98]
0x18003e028  mov     [rsp+0C8h+var_70], rax
0x18003e02d  lea     r8, [rsp+0C8h+var_70]
0x18003e032  lea     rdx, [r12+18h]
0x18003e037  lea     rcx, aExtractingFrom; "Extracting [{}] from [{}]"
0x18003e03e  call    ??$TraceInfo@PEB_WPEA_W@LogAdapter@@YAXQEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(char const * const,wchar_t const * const &,wchar_t * const &)
0x18003e043  mov     r9, [rsp+0C8h+lpExistingFileName]; wchar_t *
0x18003e048  mov     r8, [r12+18h]; wchar_t *
0x18003e04d  mov     rdx, [rsp+0C8h+var_98]; wchar_t *
0x18003e052  call    ?ExtractFileFromWim@CDeploymentSession@@AEAAJQEB_W00@Z; CDeploymentSession::ExtractFileFromWim(wchar_t const * const,wchar_t const * const,wchar_t const * const)
0x18003e057  mov     edi, eax
0x18003e059  test    eax, eax
0x18003e05b  jns     short loc_18003E098
0x18003e05d  mov     rcx, [rsi+258h]
0x18003e064  test    rcx, rcx
0x18003e067  jz      loc_18003DFA8
0x18003e06d  mov     [rsp+0C8h+var_A0], eax
0x18003e071  mov     [rsp+0C8h+var_A8], 1412h
0x18003e079  lea     r9, aCdeploymentses_80; "CDeploymentSession::CopyMetadataPayload"
0x18003e080  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003e087  mov     edx, 4
0x18003e08c  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003e091  mov     ecx, eax
0x18003e093  jmp     loc_18003DFD2
0x18003e098  mov     rbx, [rsp+0C8h+var_98]
0x18003e09d  test    rbx, rbx
0x18003e0a0  jz      short loc_18003E0CA
0x18003e0a2  call    cs:__imp_GetProcessHeap
0x18003e0a9  nop     dword ptr [rax+rax+00h]
0x18003e0ae  mov     rcx, rax; hHeap
0x18003e0b1  lea     r8, [rbx-4]; lpMem
0x18003e0b5  xor     edx, edx; dwFlags
0x18003e0b7  call    cs:__imp_HeapFree
0x18003e0be  nop     dword ptr [rax+rax+00h]
0x18003e0c3  xor     ecx, ecx
0x18003e0c5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003e0ca  mov     rcx, [rsi+258h]
0x18003e0d1  test    rcx, rcx
0x18003e0d4  jz      short loc_18003E0EC
0x18003e0d6  mov     r9, [r12+18h]
0x18003e0db  lea     r8, aCopyingSToMeta; "Copying [%s] to Metadata folder"
0x18003e0e2  mov     edx, 2
0x18003e0e7  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003e0ec  xor     r8d, r8d; bFailIfExists
0x18003e0ef  mov     rdx, r14; lpNewFileName
0x18003e0f2  mov     rcx, [rsp+0C8h+lpExistingFileName]; lpExistingFileName
0x18003e0f7  call    cs:__imp_CopyFileW
0x18003e0fe  nop     dword ptr [rax+rax+00h]
0x18003e103  test    eax, eax
0x18003e105  jnz     loc_18003E23C
0x18003e10b  call    cs:__imp_GetLastError
0x18003e112  nop     dword ptr [rax+rax+00h]
0x18003e117  mov     edi, eax
0x18003e119  test    eax, eax
0x18003e11b  jnz     short loc_18003E124
0x18003e11d  mov     edi, 80004005h
0x18003e122  jmp     short loc_18003E12F
0x18003e124  jle     short loc_18003E12F
0x18003e126  movzx   edi, ax
0x18003e129  or      edi, 80070000h
0x18003e12f  mov     rax, [rsi+258h]
0x18003e136  xor     ecx, ecx
0x18003e138  test    edi, edi
0x18003e13a  jns     loc_18003DD25
0x18003e140  test    rax, rax
0x18003e143  jz      loc_18003DD25
0x18003e149  mov     [rsp+0C8h+var_A0], edi
0x18003e14d  mov     [rsp+0C8h+var_A8], 1417h
0x18003e155  mov     rcx, rax
0x18003e158  jmp     loc_18003DD51
0x18003e15d  test    r15d, r15d
0x18003e160  jnz     loc_18003E244
0x18003e166  mov     rbx, [rsp+0C8h+lpExistingFileName]
0x18003e16b  test    rbx, rbx
0x18003e16e  jz      short loc_18003E1A1
0x18003e170  call    cs:__imp_GetProcessHeap
0x18003e177  nop     dword ptr [rax+rax+00h]
0x18003e17c  mov     rcx, rax; hHeap
0x18003e17f  lea     r8, [rbx-4]; lpMem
0x18003e183  xor     edx, edx; dwFlags
  ... truncated ...
```
