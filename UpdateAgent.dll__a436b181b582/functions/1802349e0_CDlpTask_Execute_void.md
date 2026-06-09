# CDlpTask::Execute(void)

- ea: `0x1802349e0`
- end: `0x180235c6e`
- name: `?Execute@CDlpTask@@UEAAJXZ`
- size: `4750`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180039f90`
- `0x180077664`
- `0x18022c5f8`
- `0x18022c6f4`
- `0x180233cf0`
- `0x1802349e0`
- `0x180235db0`
- `0x180237368`
- `0x1802377ac`
- `0x18023f264`
- `0x180242ab0`
- `0x180246e40`
- `0x180251e44`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180234e9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802350c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235418`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802358e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18023594c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802359f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235c44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180234e9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802350c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235418`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235598`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802358e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18023594c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802359f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235a97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180235c44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180234a84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180234f01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023527e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802353ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802356c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802358b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023590f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235a24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180234a84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180234f01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023527e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802353ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802356c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802358b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18023590f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235962`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180235a24`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180235567`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180235567`

## string_xrefs

- `0x180234e78`: `DlpTask: Preparing Files...`
- `0x180234f97`: `DlpTask: Suspending task after prepare...`
- `0x180235045`: `DlpTask: Transferring Files...`
- `0x1802352c5`: `DlpTask: Suspending task during transfer...`
- `0x180234a6b`: `DlpTask: Entering Execute Method`
- `0x180234ae3`: `CDlpTask::Execute`
- `0x180235884`: `CDlpTask::Execute`
- `0x180235b49`: `CDlpTask::Execute`
- `0x180234cbd`: `DlpTask: Transport not set. Skipping download phase.`
- `0x1802353c3`: `DlpTask: Suspending task after transfer...`
- `0x180235552`: `DlpTask: Executing Actions...`
- `0x180235708`: `DlpTask: Suspending task during action...`
- `0x180235be8`: `DlpTask: Leaving Execute Method`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::Execute(CDlpTask *this)
{
  char *v2; // rbx
  __int64 v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int updated; // edi
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // r12d
  __int64 (__fastcall *v11)(char *); // rax
  int v12; // r13d
  unsigned int v13; // eax
  _QWORD *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  enum WINDLP_INTERRUPT_REASON *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned int v27; // r13d
  unsigned int v28; // esi
  __int64 v29; // rax
  enum WINDLP_INTERRUPT_REASON *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // esi
  int v35; // ecx
  unsigned int v36; // esi
  __int64 v37; // rdx
  int v38; // eax
  unsigned int v39; // esi
  __int64 v40; // rdx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // rax
  int v45; // [rsp+20h] [rbp-69h]
  int v46; // [rsp+20h] [rbp-69h]
  int v47; // [rsp+20h] [rbp-69h]
  int v48; // [rsp+28h] [rbp-61h]
  int v49; // [rsp+28h] [rbp-61h]
  int v50; // [rsp+28h] [rbp-61h]
  __int64 v51; // [rsp+40h] [rbp-49h] BYREF
  __int64 v52; // [rsp+48h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-39h] BYREF
  __int64 v54; // [rsp+58h] [rbp-31h]
  int v55; // [rsp+70h] [rbp-19h]
  int v56; // [rsp+88h] [rbp-1h]
  int v57; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v58; // [rsp+F8h] [rbp+6Fh] BYREF
  int v59; // [rsp+100h] [rbp+77h] BYREF
  int v60; // [rsp+108h] [rbp+7Fh] BYREF

  v54 = -2;
  v52 = 0;
  v51 = 0;
  v58 = 0;
  v57 = 0;
  v59 = 0;
  SystemTimeAsFileTime = 0;
  v60 = 0;
  v2 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v3 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v3, 2, L"DlpTask: Entering Execute Method");
  }
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 824);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
  v55 = 1;
  updated = CDlpTask::CheckInitialized(this, (enum WINDLP_STATE *)&v58);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_224;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v7 = 0;
    if ( !v6 )
      goto LABEL_9;
    v48 = updated;
    v45 = 1399;
    goto LABEL_7;
  }
  v10 = v58;
  if ( v58 == -1073741824 )
  {
    updated = -2147023661;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_223;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v17 = 0;
    if ( !v16 )
      goto LABEL_222;
    v49 = -2147023661;
    v46 = 1410;
LABEL_220:
    v41 = CDlpLogT<CEmptyType>::DlpLogFormat(v16, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v46, v49);
    v17 = (unsigned int)v41;
    if ( v41 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v41, v42);
    goto LABEL_222;
  }
  if ( (v58 & 0xFFFFFFFB) != 0 )
  {
    v11 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL);
    if ( v58 != 6 )
    {
      updated = -2147019873;
      if ( !v11(v2) )
        goto LABEL_224;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v7 = 0;
      if ( v6 )
      {
        v48 = -2147019873;
        v45 = 1418;
        goto LABEL_7;
      }
LABEL_9:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
      goto LABEL_224;
    }
    updated = -1048575740;
    if ( !v11(v2) )
      goto LABEL_224;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v7 = 0;
    if ( !v6 )
      goto LABEL_9;
    v48 = -1048575740;
    v45 = 1414;
LABEL_7:
    v8 = CDlpLogT<CEmptyType>::DlpLogFormat(v6, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v45, v48);
    v7 = (unsigned int)v8;
    if ( v8 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8, v9);
    goto LABEL_9;
  }
  v12 = *((_DWORD *)this + 91);
  v13 = *((_DWORD *)this + 95);
  v58 = v13;
  if ( !v12 && !v13 )
  {
    updated = -2147024637;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_224;
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v7 = 0;
    if ( !v6 )
      goto LABEL_9;
    v48 = -2147024637;
    v45 = 1432;
    goto LABEL_7;
  }
  v14 = (_QWORD *)((char *)this + 1488);
  v15 = WINDLP_TRANSPORT_NONE;
  if ( v12 )
  {
    if ( WINDLP_TRANSPORT_NONE != *v14 )
      goto LABEL_37;
    if ( !*((_QWORD *)this + 187) )
    {
      updated = -2147024883;
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_223;
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v17 = 0;
      if ( !v16 )
        goto LABEL_222;
      v49 = -2147024883;
      v46 = 1436;
      goto LABEL_220;
    }
  }
  if ( WINDLP_TRANSPORT_NONE == *v14 )
  {
    if ( !*((_QWORD *)this + 187) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"DlpTask: Transport not set. Skipping download phase.");
      }
      v15 = WINDLP_TRANSPORT_NONE;
    }
    if ( v15 == *v14 && !*((_QWORD *)this + 187) )
      goto LABEL_47;
  }
LABEL_37:
  updated = (*(__int64 (__fastcall **)(CDlpTask *, __int64 *))(*(_QWORD *)this + 216LL))(this, &v52);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_223;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v17 = 0;
    if ( !v16 )
      goto LABEL_222;
    v49 = updated;
    v46 = 1447;
    goto LABEL_220;
  }
  updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 24LL))(v52, &v57);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_223;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v17 = 0;
    if ( !v16 )
      goto LABEL_222;
    v49 = updated;
    v46 = 1448;
    goto LABEL_220;
  }
  if ( (v57 & 0xFFFFFFF9) != 0 || v57 == 2 )
  {
    updated = -2147024875;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_223;
    v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v17 = 0;
    if ( !v16 )
      goto LABEL_222;
    v49 = -2147024875;
    v46 = 1451;
    goto LABEL_220;
  }
LABEL_47:
  *((_QWORD *)this + 176) = 0;
  if ( WINDLP_TRANSPORT_NONE == *v14 && !*((_QWORD *)this + 187) )
    goto LABEL_118;
  if ( v10 == 4 )
  {
    if ( !*((_DWORD *)this + 354) )
      goto LABEL_118;
  }
  else
  {
    updated = CDlpTask::UpdateState(this, 1);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( !v19 )
        goto LABEL_177;
      v50 = updated;
      v47 = 1471;
      goto LABEL_175;
    }
    if ( v12 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v21 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v21, 2, L"DlpTask: Preparing Files...");
      }
      if ( v55 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
        v55 = 0;
      }
      updated = CDlpTask::ExecutePrepare(this);
      if ( updated < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
          goto LABEL_178;
        v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        v20 = 0;
        if ( !v19 )
          goto LABEL_177;
        v50 = updated;
        v47 = 1483;
        goto LABEL_175;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
      v55 = 1;
    }
    updated = CDlpTask::UpdateState(this, 2);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( !v19 )
        goto LABEL_177;
      v50 = updated;
      v47 = 1492;
      goto LABEL_175;
    }
    if ( *((_DWORD *)this + 353) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v22 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2, L"DlpTask: Suspending task after prepare...");
      }
LABEL_71:
      updated = 0;
      goto LABEL_178;
    }
  }
  updated = CDlpTask::UpdateState(this, 3);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( !v19 )
      goto LABEL_177;
    v50 = updated;
    v47 = 1510;
    goto LABEL_175;
  }
  if ( v12 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
    {
      v23 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"DlpTask: Transferring Files...");
    }
    updated = CDlpTask::ReportDiagTime(this, 4097, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( !v19 )
        goto LABEL_177;
      v50 = updated;
      v47 = 1518;
      goto LABEL_175;
    }
    if ( v55 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
      v55 = 0;
    }
    updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                (char *)this + 16,
                65538,
                this);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( !v19 )
        goto LABEL_177;
      v50 = updated;
      v47 = 1526;
      goto LABEL_175;
    }
    *((_DWORD *)this + 354) = 1;
    updated = CDlpTask::ExecuteTransfer((union _ULARGE_INTEGER *)this);
    CDlpTask::ReportDiagTime(this, 4098, (char *)this + 1488);
    CDlpTask::ReportDiagTime(this, 4096, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( !v19 )
        goto LABEL_177;
      v50 = updated;
      v47 = 1539;
      goto LABEL_175;
    }
    updated = CDlpTask::CheckUserInterrupt(this, v24);
    if ( updated == -2147023661 )
    {
      if ( *((_DWORD *)this + 353) )
      {
LABEL_96:
        updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                    (char *)this + 16,
                    65540,
                    this);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
            goto LABEL_178;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
          v20 = 0;
          if ( !v19 )
            goto LABEL_177;
          v50 = updated;
          v47 = 1550;
          goto LABEL_175;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
        v55 = 1;
        if ( *((_DWORD *)this + 353) )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
          {
            v25 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
            CDlpLogT<CEmptyType>::DlpLogFormat(v25, 2, L"DlpTask: Suspending task during transfer...");
          }
          updated = CDlpTask::UpdateState(this, 4);
          if ( updated >= 0 )
            goto LABEL_71;
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
            goto LABEL_178;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
          v20 = 0;
          if ( !v19 )
            goto LABEL_177;
          v50 = updated;
          v47 = 1561;
LABEL_175:
          v32 = CDlpLogT<CEmptyType>::DlpLogFormat(v19, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v47, v50);
          v20 = (unsigned int)v32;
          if ( v32 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32, v33);
          goto LABEL_177;
        }
        *((_DWORD *)this + 354) = 0;
        updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 24LL))(v52, &v57);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
            goto LABEL_178;
          v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
          v20 = 0;
          if ( !v19 )
            goto LABEL_177;
          v50 = updated;
          v47 = 1571;
          goto LABEL_175;
        }
        if ( v57 != 6 )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
          {
            v26 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
            CDlpLogT<CEmptyType>::DlpLogFormat(v26, 2, L"DlpTask: Suspending task after transfer...");
          }
          goto LABEL_71;
        }
        goto LABEL_118;
      }
    }
    else if ( updated >= 0 )
    {
      goto LABEL_96;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( !v19 )
      goto LABEL_177;
    v50 = updated;
    v47 = 1546;
    goto LABEL_175;
  }
LABEL_118:
  v27 = v58;
  if ( !v58 )
    goto LABEL_171;
  v28 = 0;
  v58 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v56 = 1;
  *((_DWORD *)this + 218) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v56 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
    v56 = 0;
  }
  updated = CDlpTask::UpdateState(this, 3);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( !v19 )
      goto LABEL_177;
    v50 = updated;
    v47 = 1590;
    goto LABEL_175;
  }
  if ( !v27 )
  {
LABEL_171:
    updated = CDlpTask::UpdateState(this, 6);
    if ( updated >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( !v19 )
      goto LABEL_177;
    v50 = updated;
    v47 = 1669;
    goto LABEL_175;
  }
  do
  {
    if ( v51 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      v51 = 0;
    }
    updated = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, __int64 *))(*(_QWORD *)this + 120LL))(this, v28, &v51);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( v19 )
      {
        v50 = updated;
        v47 = 1599;
        goto LABEL_175;
      }
      goto LABEL_177;
    }
    updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 24LL))(v51, &v59);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( v19 )
      {
        v50 = updated;
        v47 = 1603;
        goto LABEL_175;
      }
      goto LABEL_177;
    }
    if ( v59 != -21037378 && v59 )
    {
      if ( v59 == 6 )
        goto LABEL_135;
      if ( v59 != 4 )
      {
        updated = -2147019873;
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
          goto LABEL_178;
        v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        v20 = 0;
        if ( v19 )
        {
          v50 = -2147019873;
          v47 = 1607;
          goto LABEL_175;
        }
        goto LABEL_177;
      }
    }
    if ( v59 != 6 )
      break;
LABEL_135:
    updated = CDword::Increment((CDlpTask *)((char *)this + 872), &v58);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_178;
      v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v20 = 0;
      if ( v19 )
      {
        v50 = updated;
        v47 = 1615;
        goto LABEL_175;
      }
      goto LABEL_177;
    }
    v28 = v58;
  }
  while ( v58 < v27 );
  if ( v28 >= v27 )
    goto LABEL_171;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    v29 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v29, 2, L"DlpTask: Executing Actions...");
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)this + 185) = SystemTimeAsFileTime;
  if ( v55 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
    v55 = 0;
  }
  updated = CDlpTask::ExecuteActions(this);
  CDlpTask::ReportDiagTime(this, 0x2000, 0);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( v19 )
    {
      v50 = updated;
      v47 = 1643;
      goto LABEL_175;
    }
    goto LABEL_177;
  }
  updated = CDlpTask::CheckUserInterrupt(this, v30);
  if ( updated == -2147023661 )
  {
    if ( *((_DWORD *)this + 353) )
      goto LABEL_154;
LABEL_162:
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_178;
    v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v20 = 0;
    if ( v19 )
    {
      v50 = updated;
      v47 = 1650;
      goto LABEL_175;
    }
    goto LABEL_177;
  }
  if ( updated < 0 )
    goto LABEL_162;
LABEL_154:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
  v55 = 1;
  if ( !*((_DWORD *)this + 353) )
    goto LABEL_171;
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    v31 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2, L"DlpTask: Suspending task during action...");
  }
  updated = CDlpTask::UpdateState(this, 4);
  if ( updated >= 0 )
    goto LABEL_71;
  if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
    goto LABEL_178;
  v19 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
  v20 = 0;
  if ( v19 )
  {
    v50 = updated;
    v47 = 1661;
    goto LABEL_175;
  }
LABEL_177:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v20);
LABEL_178:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v56 = 1;
  v34 = *((_DWORD *)this + 74);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v56 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v56 = 0;
  }
  if ( v34 != -1073741824 )
  {
    if ( updated >= 0 )
      goto LABEL_223;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v56 = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v38 = *((_DWORD *)this + 74);
    if ( v38 == -1 || v38 == -21037378 )
    {
      v39 = 0;
    }
    else
    {
      if ( v38 == -858993460 )
      {
        v39 = -1048575735;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(3246391561LL, 3435973836LL);
        goto LABEL_209;
      }
      v39 = 0;
      if ( v38 != -1073741824 )
        *((_DWORD *)this + 75) = v38;
    }
    *((_DWORD *)this + 74) = -1;
LABEL_209:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
    if ( v56 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
      v56 = 0;
    }
    if ( (v39 & 0x80000000) != 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v39, v40);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
    CDlpTask::InternalSetError(this, updated);
    goto LABEL_223;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v56 = 1;
  if ( updated < 0 )
    *((_DWORD *)this + 26) = updated;
  else
    *((_DWORD *)this + 26) = -2147023661;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v56 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    v56 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v56 = 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v35 = *((_DWORD *)this + 74);
  if ( v35 == -858993460 || v35 == -21037378 )
  {
    v36 = 0;
    goto LABEL_188;
  }
  if ( v35 == -1 )
  {
    v36 = -1048575734;
LABEL_194:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v36, 3435973836LL);
  }
  else
  {
    v36 = 0;
    if ( ((v35 + 0x40000000) & 0xBFFFFFFF) != 0 )
    {
      v36 = -2147019873;
      goto LABEL_194;
    }
LABEL_188:
    *((_DWORD *)this + 74) = -858993460;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v36);
  if ( v56 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v56 = 0;
  }
  if ( (v36 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v36, v37);
  v17 = v36;
LABEL_222:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
LABEL_223:
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 824);
LABEL_224:
  v60 = updated;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    12288,
    0,
    &v60,
    0,
    0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 163) + 280LL))(*((_QWORD *)this + 163), 0);
  if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
  {
    v43 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v43, 2, L"DlpTask: Leaving Execute Method");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  if ( v55 )
  {
    LeaveCriticalSection(v4);
    v55 = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1802349e0  push    rbp
0x1802349e2  push    rbx
0x1802349e3  push    rsi
0x1802349e4  push    rdi
0x1802349e5  push    r12
0x1802349e7  push    r13
0x1802349e9  push    r14
0x1802349eb  push    r15
0x1802349ed  lea     rbp, [rsp-1Fh]
0x1802349f2  sub     rsp, 0A8h
0x1802349f9  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x180234a01  mov     r15, rcx
0x180234a04  mov     [rbp+57h+var_98], 0
0x180234a0c  mov     [rbp+57h+var_A0], 0
0x180234a14  mov     [rbp+57h+arg_8], 0
0x180234a1b  mov     [rbp+57h+arg_0], 0
0x180234a22  mov     [rbp+57h+arg_10], 0
0x180234a29  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180234a31  mov     [rbp+57h+arg_18], 0
0x180234a38  lea     rbx, [rcx+0B0h]
0x180234a3f  mov     rax, [rbx]
0x180234a42  mov     rcx, rbx
0x180234a45  mov     rax, [rax+10h]
0x180234a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234a4e  mov     r14d, 2
0x180234a54  test    rax, rax
0x180234a57  jz      short loc_180234A7A
0x180234a59  mov     rax, [rbx]
0x180234a5c  mov     rcx, rbx
0x180234a5f  mov     rax, [rax+10h]
0x180234a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234a68  mov     rcx, rax
0x180234a6b  lea     r8, aDlptaskEnterin; "DlpTask: Entering Execute Method"
0x180234a72  mov     edx, r14d
0x180234a75  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180234a7a  lea     rsi, [r15+338h]
0x180234a81  mov     rcx, rsi; lpCriticalSection
0x180234a84  call    cs:__imp_EnterCriticalSection
0x180234a8b  nop     dword ptr [rax+rax+00h]
0x180234a90  mov     [rbp+57h+var_70], 1
0x180234a97  lea     rdx, [rbp+57h+arg_8]; enum WINDLP_STATE *
0x180234a9b  mov     rcx, r15; this
0x180234a9e  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x180234aa3  mov     edi, eax
0x180234aa5  test    eax, eax
0x180234aa7  jns     short loc_180234B13
0x180234aa9  mov     rcx, [rbx]
0x180234aac  mov     rax, [rcx+10h]
0x180234ab0  mov     rcx, rbx
0x180234ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234ab8  test    rax, rax
0x180234abb  jz      loc_180235B7B
0x180234ac1  mov     rcx, [rbx]
0x180234ac4  mov     rax, [rcx+10h]
0x180234ac8  mov     rcx, rbx
0x180234acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234ad0  xor     ecx, ecx
0x180234ad2  test    rax, rax
0x180234ad5  jz      short loc_180234B09
0x180234ad7  mov     [rsp+0E0h+var_B8], edi
0x180234adb  mov     dword ptr [rsp+0E0h+var_C0], 577h
0x180234ae3  lea     r9, aCdlptaskExecut_3; "CDlpTask::Execute"
0x180234aea  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180234af1  mov     edx, 4
0x180234af6  mov     rcx, rax
0x180234af9  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180234afe  test    eax, eax
0x180234b00  mov     ecx, eax
0x180234b02  jns     short loc_180234B09
0x180234b04  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180234b09  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180234b0e  jmp     loc_180235B7B
0x180234b13  mov     r12d, [rbp+57h+arg_8]
0x180234b17  cmp     r12d, 0C0000000h
0x180234b1e  jz      loc_180235B0C
0x180234b24  test    r12d, 0FFFFFFFBh
0x180234b2b  jz      loc_180234BB9
0x180234b31  mov     rax, [rbx]
0x180234b34  mov     rcx, rbx
0x180234b37  mov     rax, [rax+10h]
0x180234b3b  cmp     r12d, 6
0x180234b3f  jz      short loc_180234B7B
0x180234b41  mov     edi, 8007139Fh
0x180234b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234b4b  test    rax, rax
0x180234b4e  jz      loc_180235B7B
0x180234b54  mov     rax, [rbx]
0x180234b57  mov     rcx, rbx
0x180234b5a  mov     rax, [rax+10h]
0x180234b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234b63  xor     ecx, ecx
0x180234b65  test    rax, rax
0x180234b68  jz      short loc_180234B09
0x180234b6a  mov     [rsp+0E0h+var_B8], edi
0x180234b6e  mov     dword ptr [rsp+0E0h+var_C0], 58Ah
0x180234b76  jmp     loc_180234AE3
0x180234b7b  mov     edi, 0C1800104h
0x180234b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234b85  test    rax, rax
0x180234b88  jz      loc_180235B7B
0x180234b8e  mov     rax, [rbx]
0x180234b91  mov     rcx, rbx
0x180234b94  mov     rax, [rax+10h]
0x180234b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234b9d  xor     ecx, ecx
0x180234b9f  test    rax, rax
0x180234ba2  jz      loc_180234B09
0x180234ba8  mov     [rsp+0E0h+var_B8], edi
0x180234bac  mov     dword ptr [rsp+0E0h+var_C0], 586h
0x180234bb4  jmp     loc_180234AE3
0x180234bb9  mov     r13d, [r15+16Ch]
0x180234bc0  mov     eax, [r15+17Ch]
0x180234bc7  mov     [rbp+57h+arg_8], eax
0x180234bca  test    r13d, r13d
0x180234bcd  jnz     short loc_180234C1B
0x180234bcf  test    eax, eax
0x180234bd1  jnz     short loc_180234C1B
0x180234bd3  mov     edi, 80070103h
0x180234bd8  mov     rax, [rbx]
0x180234bdb  mov     rcx, rbx
0x180234bde  mov     rax, [rax+10h]
0x180234be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234be7  test    rax, rax
0x180234bea  jz      loc_180235B7B
0x180234bf0  mov     rax, [rbx]
0x180234bf3  mov     rcx, rbx
0x180234bf6  mov     rax, [rax+10h]
0x180234bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234bff  xor     ecx, ecx
0x180234c01  test    rax, rax
0x180234c04  jz      loc_180234B09
0x180234c0a  mov     [rsp+0E0h+var_B8], edi
0x180234c0e  mov     dword ptr [rsp+0E0h+var_C0], 598h
0x180234c16  jmp     loc_180234AE3
0x180234c1b  lea     rsi, [r15+5D0h]
0x180234c22  mov     rcx, cs:qword_1802C2548
0x180234c29  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180234c30  test    r13d, r13d
0x180234c33  jz      short loc_180234C8C
0x180234c35  cmp     rax, [rsi]
0x180234c38  jnz     loc_180234CE9
0x180234c3e  cmp     rcx, [rsi+8]
0x180234c42  jnz     short loc_180234C8C
0x180234c44  mov     edi, 8007000Dh
0x180234c49  mov     rax, [rbx]
0x180234c4c  mov     rcx, rbx
0x180234c4f  mov     rax, [rax+10h]
0x180234c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234c58  test    rax, rax
0x180234c5b  jz      loc_180235B74
0x180234c61  mov     rax, [rbx]
0x180234c64  mov     rcx, rbx
0x180234c67  mov     rax, [rax+10h]
0x180234c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234c70  xor     ecx, ecx
0x180234c72  test    rax, rax
0x180234c75  jz      loc_180235B6F
0x180234c7b  mov     [rsp+0E0h+var_B8], edi
0x180234c7f  mov     dword ptr [rsp+0E0h+var_C0], 59Ch
0x180234c87  jmp     loc_180235B49
0x180234c8c  cmp     rax, [rsi]
0x180234c8f  jnz     short loc_180234CE9
0x180234c91  cmp     rcx, [rsi+8]
0x180234c95  jnz     short loc_180234CDA
0x180234c97  mov     rax, [rbx]
0x180234c9a  mov     rcx, rbx
0x180234c9d  mov     rax, [rax+10h]
0x180234ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234ca6  test    rax, rax
0x180234ca9  jz      short loc_180234CCC
0x180234cab  mov     rax, [rbx]
0x180234cae  mov     rcx, rbx
0x180234cb1  mov     rax, [rax+10h]
0x180234cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234cba  mov     rcx, rax
0x180234cbd  lea     r8, aDlptaskTranspo; "DlpTask: Transport not set. Skipping do"...
0x180234cc4  mov     edx, r14d
0x180234cc7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180234ccc  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180234cd3  mov     rcx, cs:qword_1802C2548
0x180234cda  cmp     rax, [rsi]
0x180234cdd  jnz     short loc_180234CE9
0x180234cdf  cmp     rcx, [rsi+8]
0x180234ce3  jz      loc_180234DBC
0x180234ce9  mov     rax, [r15]
0x180234cec  lea     rdx, [rbp+57h+var_98]
0x180234cf0  mov     rcx, r15
0x180234cf3  mov     rax, [rax+0D8h]
0x180234cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234cff  mov     edi, eax
0x180234d01  test    eax, eax
0x180234d03  jns     short loc_180234D48
0x180234d05  mov     rax, [rbx]
0x180234d08  mov     rcx, rbx
0x180234d0b  mov     rax, [rax+10h]
0x180234d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234d14  test    rax, rax
0x180234d17  jz      loc_180235B74
0x180234d1d  mov     rax, [rbx]
0x180234d20  mov     rcx, rbx
0x180234d23  mov     rax, [rax+10h]
0x180234d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234d2c  xor     ecx, ecx
0x180234d2e  test    rax, rax
0x180234d31  jz      loc_180235B6F
0x180234d37  mov     [rsp+0E0h+var_B8], edi
0x180234d3b  mov     dword ptr [rsp+0E0h+var_C0], 5A7h
0x180234d43  jmp     loc_180235B49
0x180234d48  mov     rcx, [rbp+57h+var_98]
0x180234d4c  mov     rax, [rcx]
0x180234d4f  lea     rdx, [rbp+57h+arg_0]
0x180234d53  mov     rax, [rax+18h]
0x180234d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234d5c  mov     edi, eax
0x180234d5e  test    eax, eax
0x180234d60  jns     short loc_180234DA5
0x180234d62  mov     rax, [rbx]
0x180234d65  mov     rcx, rbx
0x180234d68  mov     rax, [rax+10h]
0x180234d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234d71  test    rax, rax
0x180234d74  jz      loc_180235B74
0x180234d7a  mov     rax, [rbx]
0x180234d7d  mov     rcx, rbx
0x180234d80  mov     rax, [rax+10h]
0x180234d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234d89  xor     ecx, ecx
0x180234d8b  test    rax, rax
0x180234d8e  jz      loc_180235B6F
0x180234d94  mov     [rsp+0E0h+var_B8], edi
0x180234d98  mov     dword ptr [rsp+0E0h+var_C0], 5A8h
0x180234da0  jmp     loc_180235B49
0x180234da5  test    [rbp+57h+arg_0], 0FFFFFFF9h
0x180234dac  jnz     loc_180235ACB
0x180234db2  cmp     [rbp+57h+arg_0], r14d
0x180234db6  jz      loc_180235ACB
0x180234dbc  mov     qword ptr [r15+580h], 0
0x180234dc7  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x180234dce  mov     r14d, 4
0x180234dd4  cmp     rax, [rsi]
0x180234dd7  jnz     short loc_180234DEA
0x180234dd9  mov     rax, cs:qword_1802C2548
0x180234de0  cmp     rax, [rsi+8]
0x180234de4  jz      loc_1802353CF
0x180234dea  cmp     r12d, r14d
0x180234ded  jz      loc_180234FB2
0x180234df3  mov     edx, 1
0x180234df8  mov     rcx, r15
0x180234dfb  call    ?UpdateState@CDlpTask@@AEAAJW4WINDLP_STATE@@PEAW42@@Z; CDlpTask::UpdateState(WINDLP_STATE,WINDLP_STATE *)
0x180234e00  mov     edi, eax
0x180234e02  test    eax, eax
0x180234e04  jns     short loc_180234E49
0x180234e06  mov     rax, [rbx]
0x180234e09  mov     rcx, rbx
0x180234e0c  mov     rax, [rax+10h]
0x180234e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234e15  test    rax, rax
0x180234e18  jz      loc_1802358AD
0x180234e1e  mov     rax, [rbx]
0x180234e21  mov     rcx, rbx
0x180234e24  mov     rax, [rax+10h]
0x180234e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234e2d  xor     ecx, ecx
0x180234e2f  test    rax, rax
0x180234e32  jz      loc_1802358A8
0x180234e38  mov     [rsp+0E0h+var_B8], edi
0x180234e3c  mov     dword ptr [rsp+0E0h+var_C0], 5BFh
0x180234e44  jmp     loc_180235884
0x180234e49  test    r13d, r13d
0x180234e4c  jz      loc_180234F14
0x180234e52  mov     rax, [rbx]
0x180234e55  mov     rcx, rbx
0x180234e58  mov     rax, [rax+10h]
0x180234e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234e61  test    rax, rax
0x180234e64  jz      short loc_180234E89
0x180234e66  mov     rax, [rbx]
0x180234e69  mov     rcx, rbx
0x180234e6c  mov     rax, [rax+10h]
0x180234e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180234e75  mov     rcx, rax
0x180234e78  lea     r8, aDlptaskPrepari; "DlpTask: Preparing Files..."
0x180234e7f  mov     edx, 2
0x180234e84  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180234e89  mov     eax, [rbp+57h+var_70]
0x180234e8c  lea     r12, [r15+338h]
0x180234e93  test    eax, eax
0x180234e95  jz      short loc_180234EAD
0x180234e97  mov     rcx, r12; lpCriticalSection
0x180234e9a  call    cs:__imp_LeaveCriticalSection
0x180234ea1  nop     dword ptr [rax+rax+00h]
0x180234ea6  mov     [rbp+57h+var_70], 0
0x180234ead  mov     rcx, r15; this
0x180234eb0  call    ?ExecutePrepare@CDlpTask@@AEAAJXZ; CDlpTask::ExecutePrepare(void)
0x180234eb5  mov     edi, eax
0x180234eb7  test    eax, eax
0x180234eb9  jns     short loc_180234EFE
0x180234ebb  mov     rax, [rbx]
0x180234ebe  mov     rcx, rbx
0x180234ec1  mov     rax, [rax+10h]
  ... truncated ...
```
