# CDlpTask::Execute(void)

- ea: `0x1400356d0`
- end: `0x1400369c1`
- name: `?Execute@CDlpTask@@UEAAJXZ`
- size: `4849`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400110a4`
- `0x1400135b8`
- `0x14002db30`
- `0x14002dc58`
- `0x140034ab4`
- `0x1400356d0`
- `0x140036b00`
- `0x140038100`
- `0x140038564`
- `0x140038e64`
- `0x1400434a4`
- `0x1400470d4`
- `0x140052770`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400363f8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400363f8`
- `KERNEL32!LeaveCriticalSection` at `0x140035b6b`
- `KERNEL32!LeaveCriticalSection` at `0x140035d93`
- `KERNEL32!LeaveCriticalSection` at `0x14003610f`
- `KERNEL32!LeaveCriticalSection` at `0x140036424`
- `KERNEL32!LeaveCriticalSection` at `0x140036689`
- `KERNEL32!LeaveCriticalSection` at `0x140036734`
- `KERNEL32!LeaveCriticalSection` at `0x1400367d7`
- `KERNEL32!LeaveCriticalSection` at `0x140036997`
- `KERNEL32!LeaveCriticalSection` at `0x140035b6b`
- `KERNEL32!LeaveCriticalSection` at `0x140035d93`
- `KERNEL32!LeaveCriticalSection` at `0x14003610f`
- `KERNEL32!LeaveCriticalSection` at `0x140036424`
- `KERNEL32!LeaveCriticalSection` at `0x140036689`
- `KERNEL32!LeaveCriticalSection` at `0x140036734`
- `KERNEL32!LeaveCriticalSection` at `0x1400367d7`
- `KERNEL32!LeaveCriticalSection` at `0x140036997`
- `KERNEL32!EnterCriticalSection` at `0x140035771`
- `KERNEL32!EnterCriticalSection` at `0x140035bd3`
- `KERNEL32!EnterCriticalSection` at `0x140035f53`
- `KERNEL32!EnterCriticalSection` at `0x1400360e4`
- `KERNEL32!EnterCriticalSection` at `0x1400362e0`
- `KERNEL32!EnterCriticalSection` at `0x1400364ca`
- `KERNEL32!EnterCriticalSection` at `0x1400366a1`
- `KERNEL32!EnterCriticalSection` at `0x140036765`
- `KERNEL32!EnterCriticalSection` at `0x140035771`
- `KERNEL32!EnterCriticalSection` at `0x140035bd3`
- `KERNEL32!EnterCriticalSection` at `0x140035f53`
- `KERNEL32!EnterCriticalSection` at `0x1400360e4`
- `KERNEL32!EnterCriticalSection` at `0x1400362e0`
- `KERNEL32!EnterCriticalSection` at `0x1400364ca`
- `KERNEL32!EnterCriticalSection` at `0x1400366a1`
- `KERNEL32!EnterCriticalSection` at `0x140036765`

## string_xrefs

- `0x14003575b`: `DlpTask: Entering Execute Method`
- `0x14003627c`: `CDlpTask::Execute`
- `0x140036891`: `CDlpTask::Execute`
- `0x14003598b`: `DlpTask: Transport not set. Skipping download phase.`
- `0x140035b49`: `DlpTask: Preparing Files...`
- `0x140035c69`: `DlpTask: Suspending task after prepare...`
- `0x140035d17`: `DlpTask: Transferring Files...`
- `0x140035fa1`: `DlpTask: Suspending task during transfer...`
- `0x1400360b8`: `DlpTask: Suspending task after transfer...`
- `0x1400363e3`: `DlpTask: Executing Actions...`
- `0x140036518`: `DlpTask: Suspending task during action...`
- `0x140036937`: `DlpTask: Leaving Execute Method`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::Execute(CDlpTask *this)
{
  char *v2; // rbx
  __int64 v3; // rax
  int updated; // edi
  __int64 v5; // rax
  int v6; // r14d
  int v7; // r12d
  __int64 (__fastcall *v8)(char *); // rax
  int v9; // r13d
  unsigned int v10; // eax
  _QWORD *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // r14d
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  enum WINDLP_INTERRUPT_REASON *v19; // rdx
  enum WINDLP_INTERRUPT_REASON *v20; // r8
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned int v24; // r13d
  unsigned int v25; // r14d
  int v26; // eax
  int *v27; // r12
  __int64 v28; // rax
  enum WINDLP_INTERRUPT_REASON *v29; // rdx
  enum WINDLP_INTERRUPT_REASON *v30; // r8
  int v31; // eax
  __int64 v32; // rax
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // eax
  int v37; // r14d
  int v38; // eax
  __int64 v39; // rax
  int v41; // [rsp+20h] [rbp-69h]
  int v42; // [rsp+20h] [rbp-69h]
  int v43; // [rsp+28h] [rbp-61h]
  int v44; // [rsp+28h] [rbp-61h]
  __int64 v45; // [rsp+40h] [rbp-49h] BYREF
  int v46; // [rsp+48h] [rbp-41h] BYREF
  __int64 v47; // [rsp+50h] [rbp-39h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-31h] BYREF
  int v49; // [rsp+70h] [rbp-19h]
  int v50; // [rsp+88h] [rbp-1h]
  __int64 v51; // [rsp+98h] [rbp+Fh]
  int v52; // [rsp+F0h] [rbp+67h] BYREF
  int v53; // [rsp+F8h] [rbp+6Fh] BYREF
  int v54; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v55; // [rsp+108h] [rbp+7Fh] BYREF

  v51 = -2;
  v47 = 0;
  v45 = 0;
  v53 = 0;
  v52 = 0;
  v54 = 0;
  SystemTimeAsFileTime = 0;
  v46 = 0;
  v2 = (char *)this + 176;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v3 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v3, 2, L"DlpTask: Entering Execute Method");
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
  v49 = 1;
  updated = CDlpTask::CheckInitialized(this, (enum WINDLP_STATE *)&v53);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = updated;
    v41 = 1399;
    goto LABEL_214;
  }
  v7 = v53;
  if ( v53 == -1073741824 )
  {
    updated = -2147023661;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = -2147023661;
    v41 = 1410;
LABEL_214:
    v38 = CDlpLogT<CEmptyType>::DlpLogFormat(v5, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v41, v43);
    v6 = v38;
    if ( v38 < 0 )
    {
      v35 = v38;
LABEL_216:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v35);
    }
    goto LABEL_217;
  }
  if ( (v53 & 0xFFFFFFFB) != 0 )
  {
    v8 = *(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL);
    if ( v53 == 6 )
    {
      updated = -1048575740;
      if ( !v8(v2) )
        goto LABEL_218;
      v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v6 = 0;
      if ( !v5 )
        goto LABEL_217;
      v43 = -1048575740;
      v41 = 1414;
    }
    else
    {
      updated = -2147019873;
      if ( !v8(v2) )
        goto LABEL_218;
      v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v6 = 0;
      if ( !v5 )
        goto LABEL_217;
      v43 = -2147019873;
      v41 = 1418;
    }
    goto LABEL_214;
  }
  v9 = *((_DWORD *)this + 91);
  v10 = *((_DWORD *)this + 95);
  v55 = v10;
  if ( !v9 && !v10 )
  {
    updated = -2147024637;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = -2147024637;
    v41 = 1432;
    goto LABEL_214;
  }
  v11 = (_QWORD *)((char *)this + 1488);
  v12 = WINDLP_TRANSPORT_NONE;
  if ( v9 )
  {
    if ( WINDLP_TRANSPORT_NONE != *v11 )
      goto LABEL_34;
    if ( !*((_QWORD *)this + 187) )
    {
      updated = -2147024883;
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_218;
      v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v6 = 0;
      if ( !v5 )
        goto LABEL_217;
      v43 = -2147024883;
      v41 = 1436;
      goto LABEL_214;
    }
  }
  if ( WINDLP_TRANSPORT_NONE == *v11 )
  {
    if ( !*((_QWORD *)this + 187) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v13 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v13, 2, L"DlpTask: Transport not set. Skipping download phase.");
      }
      v12 = WINDLP_TRANSPORT_NONE;
    }
    if ( v12 == *v11 && !*((_QWORD *)this + 187) )
      goto LABEL_44;
  }
LABEL_34:
  updated = (*(__int64 (__fastcall **)(CDlpTask *, __int64 *))(*(_QWORD *)this + 216LL))(this, &v47);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = updated;
    v41 = 1447;
    goto LABEL_214;
  }
  updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 24LL))(v47, &v52);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = updated;
    v41 = 1448;
    goto LABEL_214;
  }
  if ( (v52 & 0xFFFFFFF9) != 0 || v52 == 2 )
  {
    updated = -2147024875;
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_218;
    v5 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v6 = 0;
    if ( !v5 )
      goto LABEL_217;
    v43 = -2147024875;
    v41 = 1451;
    goto LABEL_214;
  }
LABEL_44:
  *((_QWORD *)this + 176) = 0;
  if ( WINDLP_TRANSPORT_NONE == *v11 && !*((_QWORD *)this + 187) )
    goto LABEL_115;
  if ( v7 == 4 )
  {
    if ( !*((_DWORD *)this + 354) )
      goto LABEL_115;
  }
  else
  {
    updated = CDlpTask::UpdateState(this);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v15 = 0;
      if ( !v14 )
        goto LABEL_140;
      v44 = updated;
      v42 = 1471;
      goto LABEL_138;
    }
    if ( v9 )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2, L"DlpTask: Preparing Files...");
      }
      if ( v49 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
        v49 = 0;
      }
      updated = CDlpTask::ExecutePrepare(this);
      if ( updated < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
          goto LABEL_141;
        v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        v15 = 0;
        if ( !v14 )
          goto LABEL_140;
        v44 = updated;
        v42 = 1483;
        goto LABEL_138;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
      v49 = 1;
    }
    updated = CDlpTask::UpdateState(this);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v15 = 0;
      if ( !v14 )
        goto LABEL_140;
      v44 = updated;
      v42 = 1492;
      goto LABEL_138;
    }
    if ( *((_DWORD *)this + 353) )
    {
      if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      {
        v17 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
        CDlpLogT<CEmptyType>::DlpLogFormat(v17, 2, L"DlpTask: Suspending task after prepare...");
      }
LABEL_68:
      updated = 0;
      goto LABEL_141;
    }
  }
  updated = CDlpTask::UpdateState(this);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v15 = 0;
    if ( !v14 )
      goto LABEL_140;
    v44 = updated;
    v42 = 1510;
    goto LABEL_138;
  }
  if ( v9 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
    {
      v18 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"DlpTask: Transferring Files...");
    }
    updated = CDlpTask::ReportDiagTime(this, 4097, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v15 = 0;
      if ( !v14 )
        goto LABEL_140;
      v44 = updated;
      v42 = 1518;
      goto LABEL_138;
    }
    if ( v49 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
      v49 = 0;
    }
    updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                (char *)this + 16,
                65538,
                this);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v15 = 0;
      if ( !v14 )
        goto LABEL_140;
      v44 = updated;
      v42 = 1526;
      goto LABEL_138;
    }
    *((_DWORD *)this + 354) = 1;
    updated = CDlpTask::ExecuteTransfer((union _ULARGE_INTEGER *)this);
    CDlpTask::ReportDiagTime(this, 4098, (char *)this + 1488);
    CDlpTask::ReportDiagTime(this, 4096, (char *)this + 1488);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
      v15 = 0;
      if ( !v14 )
        goto LABEL_140;
      v44 = updated;
      v42 = 1539;
      goto LABEL_138;
    }
    v21 = CDlpTask::CheckUserInterrupt(this, v19, v20);
    updated = v21;
    if ( v21 == -2147023661 )
    {
      if ( *((_DWORD *)this + 353) )
      {
LABEL_93:
        updated = (*(__int64 (__fastcall **)(char *, __int64, CDlpTask *))(*((_QWORD *)this + 2) + 24LL))(
                    (char *)this + 16,
                    65540,
                    this);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
            goto LABEL_141;
          v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
          v15 = 0;
          if ( !v14 )
            goto LABEL_140;
          v44 = updated;
          v42 = 1550;
          goto LABEL_138;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
        v49 = 1;
        if ( *((_DWORD *)this + 353) )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
          {
            v22 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
            CDlpLogT<CEmptyType>::DlpLogFormat(v22, 2, L"DlpTask: Suspending task during transfer...");
          }
          updated = CDlpTask::UpdateState(this);
          if ( updated >= 0 )
            goto LABEL_68;
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
            goto LABEL_141;
          v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
          v15 = 0;
          if ( !v14 )
            goto LABEL_140;
          v44 = updated;
          v42 = 1561;
LABEL_138:
          v26 = CDlpLogT<CEmptyType>::DlpLogFormat(v14, 4, L"%s(%d): Result = 0x%X", L"CDlpTask::Execute", v42, v44);
          v15 = v26;
          if ( v26 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26);
          goto LABEL_140;
        }
        *((_DWORD *)this + 354) = 0;
        updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 24LL))(v47, &v52);
        if ( updated < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
            goto LABEL_141;
          v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
          v15 = 0;
          if ( !v14 )
            goto LABEL_140;
          v44 = updated;
          v42 = 1571;
          goto LABEL_138;
        }
        if ( v52 != 6 )
        {
          if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
          {
            v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
            CDlpLogT<CEmptyType>::DlpLogFormat(v23, 2, L"DlpTask: Suspending task after transfer...");
          }
          goto LABEL_68;
        }
        goto LABEL_115;
      }
    }
    else if ( v21 >= 0 )
    {
      goto LABEL_93;
    }
    if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))(v2);
    v15 = 0;
    if ( !v14 )
      goto LABEL_140;
    v44 = updated;
    v42 = 1546;
    goto LABEL_138;
  }
LABEL_115:
  v24 = v55;
  if ( !v55 )
    goto LABEL_134;
  v25 = 0;
  v55 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  v50 = 1;
  *((_DWORD *)this + 218) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v50 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
    v50 = 0;
  }
  updated = CDlpTask::UpdateState(this);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    v15 = 0;
    if ( !v14 )
      goto LABEL_140;
    v44 = updated;
    v42 = 1590;
    goto LABEL_138;
  }
  if ( !v24 )
  {
LABEL_134:
    updated = CDlpTask::UpdateState(this);
    if ( updated >= 0 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    v15 = 0;
    if ( !v14 )
      goto LABEL_140;
    v44 = updated;
    v42 = 1669;
    goto LABEL_138;
  }
  while ( 1 )
  {
    if ( v45 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v45 = 0;
    }
    updated = (*(__int64 (__fastcall **)(CDlpTask *, _QWORD, __int64 *))(*(_QWORD *)this + 120LL))(this, v25, &v45);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
      v15 = 0;
      if ( v14 )
      {
        v44 = updated;
        v42 = 1599;
        goto LABEL_138;
      }
      goto LABEL_140;
    }
    updated = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 24LL))(v45, &v54);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
      v15 = 0;
      if ( v14 )
      {
        v44 = updated;
        v42 = 1603;
        goto LABEL_138;
      }
      goto LABEL_140;
    }
    if ( v54 != -21037378 && v54 )
    {
      if ( v54 == 6 )
        goto LABEL_132;
      if ( v54 != 4 )
      {
        updated = -2147019873;
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
          goto LABEL_141;
        v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
        v15 = 0;
        if ( v14 )
        {
          v44 = -2147019873;
          v42 = 1607;
          goto LABEL_138;
        }
        goto LABEL_140;
      }
    }
    if ( v54 != 6 )
      break;
LABEL_132:
    updated = CDword::Increment((CDlpTask *)((char *)this + 872), &v55);
    if ( updated < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
        goto LABEL_141;
      v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
      v15 = 0;
      if ( v14 )
      {
        v44 = updated;
        v42 = 1615;
        goto LABEL_138;
      }
      goto LABEL_140;
    }
    v25 = v55;
    if ( v55 >= v24 )
      goto LABEL_134;
  }
  if ( v25 >= v24 )
    goto LABEL_134;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
  {
    v28 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v28, 2, L"DlpTask: Executing Actions...");
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)this + 185) = SystemTimeAsFileTime;
  if ( v49 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
    v49 = 0;
  }
  updated = CDlpTask::ExecuteActions(this);
  CDlpTask::ReportDiagTime(this, 0x2000, 0);
  if ( updated < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    v15 = 0;
    if ( v14 )
    {
      v44 = updated;
      v42 = 1643;
      goto LABEL_138;
    }
    goto LABEL_140;
  }
  v31 = CDlpTask::CheckUserInterrupt(this, v29, v30);
  updated = v31;
  if ( v31 == -2147023661 )
  {
    if ( *((_DWORD *)this + 353) )
      goto LABEL_162;
LABEL_170:
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
      goto LABEL_141;
    v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    v15 = 0;
    if ( v14 )
    {
      v44 = updated;
      v42 = 1650;
      goto LABEL_138;
    }
    goto LABEL_140;
  }
  if ( v31 < 0 )
    goto LABEL_170;
LABEL_162:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
  v49 = 1;
  if ( !*((_DWORD *)this + 353) )
    goto LABEL_134;
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
  {
    v32 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v32, 2, L"DlpTask: Suspending task during action...");
  }
  updated = CDlpTask::UpdateState(this);
  if ( updated >= 0 )
    goto LABEL_68;
  if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
    goto LABEL_141;
  v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
  v15 = 0;
  if ( v14 )
  {
    v44 = updated;
    v42 = 1661;
    goto LABEL_138;
  }
LABEL_140:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
LABEL_141:
  v27 = (int *)((char *)this + 296);
  if ( (int)CDlpState::Get((CDlpTask *)((char *)this + 296), (enum WINDLP_STATE *)&v53) < 0 )
    goto LABEL_218;
  if ( v53 != -1073741824 )
  {
    if ( updated >= 0 )
      goto LABEL_218;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v50 = 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v36 = *v27;
    if ( *v27 == -1 || v36 == -21037378 )
    {
      v37 = 0;
    }
    else
    {
      if ( v36 == -858993460 )
      {
        v37 = -1048575735;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-1048575735);
        goto LABEL_203;
      }
      v37 = 0;
      if ( v36 != -1073741824 )
        *((_DWORD *)this + 75) = v36;
    }
    *v27 = -1;
LABEL_203:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v37);
    if ( v50 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
      v50 = 0;
    }
    if ( v37 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v37);
    CDlpTask::InternalSetError(this, updated);
    goto LABEL_218;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v50 = 1;
  if ( updated < 0 )
    *((_DWORD *)this + 26) = updated;
  else
    *((_DWORD *)this + 26) = -2147023661;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( v50 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    v50 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  v50 = 1;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = 0;
  v33 = *v27;
  if ( *v27 == -858993460 || v33 == -21037378 )
    goto LABEL_187;
  if ( v33 == -1 )
  {
    v6 = -1048575734;
    v34 = -1048575734;
LABEL_189:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
  }
  else
  {
    if ( ((v33 + 0x40000000) & 0xBFFFFFFF) != 0 )
    {
      v34 = -2147019873;
      v6 = -2147019873;
      goto LABEL_189;
    }
LABEL_187:
    *v27 = -858993460;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v50 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
    v50 = 0;
  }
  if ( v6 < 0 )
  {
    v35 = v6;
    goto LABEL_216;
  }
LABEL_217:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
LABEL_218:
  v46 = updated;
  (**((void (__fastcall ***)(char *, __int64, _QWORD, int *, _QWORD, _DWORD))this + 2))(
    (char *)this + 16,
    12288,
    0,
    &v46,
    0,
    0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 163) + 280LL))(*((_QWORD *)this + 163), 0);
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2) )
  {
    v39 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))(v2);
    CDlpLogT<CEmptyType>::DlpLogFormat(v39, 2, L"DlpTask: Leaving Execute Method");
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)updated);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v49 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 824));
    v49 = 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1400356d0  push    rbp
0x1400356d2  push    rbx
0x1400356d3  push    rsi
0x1400356d4  push    rdi
0x1400356d5  push    r12
0x1400356d7  push    r13
0x1400356d9  push    r14
0x1400356db  push    r15
0x1400356dd  lea     rbp, [rsp-1Fh]
0x1400356e2  sub     rsp, 0A8h
0x1400356e9  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x1400356f1  mov     rsi, rcx
0x1400356f4  mov     [rbp+57h+var_90], 0
0x1400356fc  mov     [rbp+57h+var_A0], 0
0x140035704  mov     [rbp+57h+arg_8], 0
0x14003570b  mov     [rbp+57h+arg_0], 0
0x140035712  mov     [rbp+57h+arg_10], 0
0x140035719  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140035721  mov     [rbp+57h+var_98], 0
0x140035728  lea     rbx, [rcx+0B0h]
0x14003572f  mov     rax, [rbx]
0x140035732  mov     rcx, rbx
0x140035735  mov     rax, [rax+10h]
0x140035739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003573e  mov     r15d, 2
0x140035744  test    rax, rax
0x140035747  jz      short loc_14003576A
0x140035749  mov     rax, [rbx]
0x14003574c  mov     rcx, rbx
0x14003574f  mov     rax, [rax+10h]
0x140035753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035758  mov     rcx, rax
0x14003575b  lea     r8, aDlptaskEnterin; "DlpTask: Entering Execute Method"
0x140035762  mov     edx, r15d
0x140035765  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003576a  lea     rcx, [rsi+338h]; lpCriticalSection
0x140035771  call    cs:__imp_EnterCriticalSection
0x140035778  nop     dword ptr [rax+rax+00h]
0x14003577d  mov     [rbp+57h+var_70], 1
0x140035784  lea     rdx, [rbp+57h+arg_8]; enum WINDLP_STATE *
0x140035788  mov     rcx, rsi; this
0x14003578b  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x140035790  mov     edi, eax
0x140035792  test    eax, eax
0x140035794  jns     short loc_1400357DA
0x140035796  mov     rcx, [rbx]
0x140035799  mov     rax, [rcx+10h]
0x14003579d  mov     rcx, rbx
0x1400357a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400357a5  test    rax, rax
0x1400357a8  jz      loc_1400368C2
0x1400357ae  mov     rcx, [rbx]
0x1400357b1  mov     rax, [rcx+10h]
0x1400357b5  mov     rcx, rbx
0x1400357b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400357bd  xor     r14d, r14d
0x1400357c0  test    rax, rax
0x1400357c3  jz      loc_1400368BA
0x1400357c9  mov     [rsp+0E0h+var_B8], edi
0x1400357cd  mov     dword ptr [rsp+0E0h+var_C0], 577h
0x1400357d5  jmp     loc_140036891
0x1400357da  mov     r12d, [rbp+57h+arg_8]
0x1400357de  cmp     r12d, 0C0000000h
0x1400357e5  jz      loc_140036850
0x1400357eb  test    r12d, 0FFFFFFFBh
0x1400357f2  jz      loc_140035886
0x1400357f8  mov     rax, [rbx]
0x1400357fb  mov     rcx, rbx
0x1400357fe  mov     rax, [rax+10h]
0x140035802  cmp     r12d, 6
0x140035806  jz      short loc_140035847
0x140035808  mov     edi, 8007139Fh
0x14003580d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035812  test    rax, rax
0x140035815  jz      loc_1400368C2
0x14003581b  mov     rax, [rbx]
0x14003581e  mov     rcx, rbx
0x140035821  mov     rax, [rax+10h]
0x140035825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003582a  xor     r14d, r14d
0x14003582d  test    rax, rax
0x140035830  jz      loc_1400368BA
0x140035836  mov     [rsp+0E0h+var_B8], edi
0x14003583a  mov     dword ptr [rsp+0E0h+var_C0], 58Ah
0x140035842  jmp     loc_140036891
0x140035847  mov     edi, 0C1800104h
0x14003584c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035851  test    rax, rax
0x140035854  jz      loc_1400368C2
0x14003585a  mov     rax, [rbx]
0x14003585d  mov     rcx, rbx
0x140035860  mov     rax, [rax+10h]
0x140035864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035869  xor     r14d, r14d
0x14003586c  test    rax, rax
0x14003586f  jz      loc_1400368BA
0x140035875  mov     [rsp+0E0h+var_B8], edi
0x140035879  mov     dword ptr [rsp+0E0h+var_C0], 586h
0x140035881  jmp     loc_140036891
0x140035886  mov     r13d, [rsi+16Ch]
0x14003588d  mov     eax, [rsi+17Ch]
0x140035893  mov     [rbp+57h+arg_18], eax
0x140035896  test    r13d, r13d
0x140035899  jnz     short loc_1400358E8
0x14003589b  test    eax, eax
0x14003589d  jnz     short loc_1400358E8
0x14003589f  mov     edi, 80070103h
0x1400358a4  mov     rax, [rbx]
0x1400358a7  mov     rcx, rbx
0x1400358aa  mov     rax, [rax+10h]
0x1400358ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400358b3  test    rax, rax
0x1400358b6  jz      loc_1400368C2
0x1400358bc  mov     rax, [rbx]
0x1400358bf  mov     rcx, rbx
0x1400358c2  mov     rax, [rax+10h]
0x1400358c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400358cb  xor     r14d, r14d
0x1400358ce  test    rax, rax
0x1400358d1  jz      loc_1400368BA
0x1400358d7  mov     [rsp+0E0h+var_B8], edi
0x1400358db  mov     dword ptr [rsp+0E0h+var_C0], 598h
0x1400358e3  jmp     loc_140036891
0x1400358e8  lea     r14, [rsi+5D0h]
0x1400358ef  mov     rcx, cs:qword_140091428
0x1400358f6  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x1400358fd  test    r13d, r13d
0x140035900  jz      short loc_14003595A
0x140035902  cmp     rax, [r14]
0x140035905  jnz     loc_1400359B7
0x14003590b  cmp     rcx, [r14+8]
0x14003590f  jnz     short loc_14003595A
0x140035911  mov     edi, 8007000Dh
0x140035916  mov     rax, [rbx]
0x140035919  mov     rcx, rbx
0x14003591c  mov     rax, [rax+10h]
0x140035920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035925  test    rax, rax
0x140035928  jz      loc_1400368C2
0x14003592e  mov     rax, [rbx]
0x140035931  mov     rcx, rbx
0x140035934  mov     rax, [rax+10h]
0x140035938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003593d  xor     r14d, r14d
0x140035940  test    rax, rax
0x140035943  jz      loc_1400368BA
0x140035949  mov     [rsp+0E0h+var_B8], edi
0x14003594d  mov     dword ptr [rsp+0E0h+var_C0], 59Ch
0x140035955  jmp     loc_140036891
0x14003595a  cmp     rax, [r14]
0x14003595d  jnz     short loc_1400359B7
0x14003595f  cmp     rcx, [r14+8]
0x140035963  jnz     short loc_1400359A8
0x140035965  mov     rax, [rbx]
0x140035968  mov     rcx, rbx
0x14003596b  mov     rax, [rax+10h]
0x14003596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035974  test    rax, rax
0x140035977  jz      short loc_14003599A
0x140035979  mov     rax, [rbx]
0x14003597c  mov     rcx, rbx
0x14003597f  mov     rax, [rax+10h]
0x140035983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035988  mov     rcx, rax
0x14003598b  lea     r8, aDlptaskTranspo; "DlpTask: Transport not set. Skipping do"...
0x140035992  mov     edx, r15d
0x140035995  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14003599a  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x1400359a1  mov     rcx, cs:qword_140091428
0x1400359a8  cmp     rax, [r14]
0x1400359ab  jnz     short loc_1400359B7
0x1400359ad  cmp     rcx, [r14+8]
0x1400359b1  jz      loc_140035A8C
0x1400359b7  mov     rax, [rsi]
0x1400359ba  lea     rdx, [rbp+57h+var_90]
0x1400359be  mov     rcx, rsi
0x1400359c1  mov     rax, [rax+0D8h]
0x1400359c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359cd  mov     edi, eax
0x1400359cf  test    eax, eax
0x1400359d1  jns     short loc_140035A17
0x1400359d3  mov     rax, [rbx]
0x1400359d6  mov     rcx, rbx
0x1400359d9  mov     rax, [rax+10h]
0x1400359dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359e2  test    rax, rax
0x1400359e5  jz      loc_1400368C2
0x1400359eb  mov     rax, [rbx]
0x1400359ee  mov     rcx, rbx
0x1400359f1  mov     rax, [rax+10h]
0x1400359f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359fa  xor     r14d, r14d
0x1400359fd  test    rax, rax
0x140035a00  jz      loc_1400368BA
0x140035a06  mov     [rsp+0E0h+var_B8], edi
0x140035a0a  mov     dword ptr [rsp+0E0h+var_C0], 5A7h
0x140035a12  jmp     loc_140036891
0x140035a17  mov     rcx, [rbp+57h+var_90]
0x140035a1b  mov     rax, [rcx]
0x140035a1e  lea     rdx, [rbp+57h+arg_0]
0x140035a22  mov     rax, [rax+18h]
0x140035a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035a2b  mov     edi, eax
0x140035a2d  test    eax, eax
0x140035a2f  jns     short loc_140035A75
0x140035a31  mov     rax, [rbx]
0x140035a34  mov     rcx, rbx
0x140035a37  mov     rax, [rax+10h]
0x140035a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035a40  test    rax, rax
0x140035a43  jz      loc_1400368C2
0x140035a49  mov     rax, [rbx]
0x140035a4c  mov     rcx, rbx
0x140035a4f  mov     rax, [rax+10h]
0x140035a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035a58  xor     r14d, r14d
0x140035a5b  test    rax, rax
0x140035a5e  jz      loc_1400368BA
0x140035a64  mov     [rsp+0E0h+var_B8], edi
0x140035a68  mov     dword ptr [rsp+0E0h+var_C0], 5A8h
0x140035a70  jmp     loc_140036891
0x140035a75  test    [rbp+57h+arg_0], 0FFFFFFF9h
0x140035a7c  jnz     loc_14003680E
0x140035a82  cmp     [rbp+57h+arg_0], r15d
0x140035a86  jz      loc_14003680E
0x140035a8c  mov     qword ptr [rsi+580h], 0
0x140035a97  mov     rax, cs:WINDLP_TRANSPORT_NONE
0x140035a9e  mov     r15d, 4
0x140035aa4  cmp     rax, [r14]
0x140035aa7  jnz     short loc_140035ABA
0x140035aa9  mov     rax, cs:qword_140091428
0x140035ab0  cmp     rax, [r14+8]
0x140035ab4  jz      loc_1400360C4
0x140035aba  cmp     r12d, r15d
0x140035abd  jz      loc_140035C84
0x140035ac3  mov     edx, 1
0x140035ac8  mov     rcx, rsi
0x140035acb  call    ?UpdateState@CDlpTask@@AEAAJW4WINDLP_STATE@@PEAW42@@Z; CDlpTask::UpdateState(WINDLP_STATE,WINDLP_STATE *)
0x140035ad0  mov     edi, eax
0x140035ad2  test    eax, eax
0x140035ad4  jns     short loc_140035B1A
0x140035ad6  mov     rax, [rbx]
0x140035ad9  mov     rcx, rbx
0x140035adc  mov     rax, [rax+10h]
0x140035ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035ae5  test    rax, rax
0x140035ae8  jz      loc_1400362AB
0x140035aee  mov     rax, [rbx]
0x140035af1  mov     rcx, rbx
0x140035af4  mov     rax, [rax+10h]
0x140035af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035afd  xor     r14d, r14d
0x140035b00  test    rax, rax
0x140035b03  jz      loc_1400362A3
0x140035b09  mov     [rsp+0E0h+var_B8], edi
0x140035b0d  mov     dword ptr [rsp+0E0h+var_C0], 5BFh
0x140035b15  jmp     loc_14003627C
0x140035b1a  test    r13d, r13d
0x140035b1d  jz      loc_140035BE6
0x140035b23  mov     rax, [rbx]
0x140035b26  mov     rcx, rbx
0x140035b29  mov     rax, [rax+10h]
0x140035b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b32  test    rax, rax
0x140035b35  jz      short loc_140035B5A
0x140035b37  mov     rax, [rbx]
0x140035b3a  mov     rcx, rbx
0x140035b3d  mov     rax, [rax+10h]
0x140035b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b46  mov     rcx, rax
0x140035b49  lea     r8, aDlptaskPrepari; "DlpTask: Preparing Files..."
0x140035b50  mov     edx, 2
0x140035b55  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140035b5a  mov     eax, [rbp+57h+var_70]
0x140035b5d  lea     r12, [rsi+338h]
0x140035b64  test    eax, eax
0x140035b66  jz      short loc_140035B7E
0x140035b68  mov     rcx, r12; lpCriticalSection
0x140035b6b  call    cs:__imp_LeaveCriticalSection
0x140035b72  nop     dword ptr [rax+rax+00h]
0x140035b77  mov     [rbp+57h+var_70], 0
0x140035b7e  mov     rcx, rsi; this
0x140035b81  call    ?ExecutePrepare@CDlpTask@@AEAAJXZ; CDlpTask::ExecutePrepare(void)
0x140035b86  mov     edi, eax
0x140035b88  test    eax, eax
0x140035b8a  jns     short loc_140035BD0
0x140035b8c  mov     rax, [rbx]
0x140035b8f  mov     rcx, rbx
0x140035b92  mov     rax, [rax+10h]
0x140035b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b9b  test    rax, rax
0x140035b9e  jz      loc_1400362AB
0x140035ba4  mov     rax, [rbx]
0x140035ba7  mov     rcx, rbx
0x140035baa  mov     rax, [rax+10h]
0x140035bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035bb3  xor     r14d, r14d
0x140035bb6  test    rax, rax
0x140035bb9  jz      loc_1400362A3
0x140035bbf  mov     [rsp+0E0h+var_B8], edi
  ... truncated ...
```
