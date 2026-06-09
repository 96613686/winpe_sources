# CReflectedDumpServer::Start(wchar_t const *)

- ea: `0x140017f08`
- end: `0x140018828`
- name: `?Start@CReflectedDumpServer@@QEAAJPEB_W@Z`
- size: `2336`
- prototype: `__int64 __fastcall(HANDLE *pv, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140017c90`

## callees

- `0x1400032ef`
- `0x1400032fb`
- `0x140003343`
- `0x14001444c`
- `0x140014474`
- `0x140014678`
- `0x140017530`
- `0x140017f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018063`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018464`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018063`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018464`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140017fcd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140017fec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018037`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140017fcd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140017fec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018037`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001800b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001801e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018056`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400185a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018746`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001800b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001801e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018056`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400185a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018746`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400185b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140018733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140018754`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400185b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140018733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140018754`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400187d8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400182e8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001836e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400182e8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001836e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400181fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400187f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400181fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400187f9`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140017f49`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140017f49`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140017f7b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140017fa8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140017f7b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140017fa8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400187e6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018807`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400187e6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140018807`
- `ntdll!NtQueryInformationProcess` at `0x140018114`
- `ntdll!NtQueryInformationProcess` at `0x1400181be`
- `ntdll!NtQueryInformationProcess` at `0x140018114`
- `ntdll!NtQueryInformationProcess` at `0x1400181be`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140018537`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140018537`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReflectedDumpServer::Start(HANDLE *pv, LPCWSTR lpName)
{
  char *v3; // rdi
  struct _TP_WAIT *ThreadpoolWait; // rsi
  struct _TP_WAIT *v5; // rbp
  struct _TP_WAIT *v6; // r14
  HANDLE v7; // rax
  HANDLE *v8; // rax
  HANDLE *v9; // rbx
  signed int v10; // r15d
  struct _TP_WAIT *v11; // rax
  signed int v12; // eax
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // r15d
  NTSTATUS v16; // r15d
  HANDLE v17; // rax
  NTSTATUS v18; // r15d
  unsigned int v19; // r15d
  CUserModeHangReport *v20; // rcx
  int v21; // eax
  CUserModeHangReport *v22; // rcx
  char ProcessId; // al
  bool v24; // sf
  HANDLE v25; // rcx
  DWORD v26; // eax
  _WORD *v27; // r8
  _WORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  _WORD *v31; // rcx
  signed int v32; // eax
  signed int *v33; // rdx
  bool v34; // sf
  DWORD v35; // eax
  CUserModeHangReport *v36; // rcx
  __int64 v37; // rdx
  CUserModeHangReport *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r9
  signed int LastError_0; // eax
  HANDLE v42; // rcx
  HANDLE v43; // rcx
  HANDLE v44; // rcx
  HANDLE v45; // rcx
  HANDLE v46; // rcx
  unsigned int v48; // [rsp+30h] [rbp-68h]
  HANDLE hObject; // [rsp+38h] [rbp-60h]
  unsigned __int64 v50; // [rsp+40h] [rbp-58h]
  HANDLE v51; // [rsp+48h] [rbp-50h]
  __int128 Handles; // [rsp+50h] [rbp-48h] BYREF
  unsigned int ProcessInformation; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v55; // [rsp+B8h] [rbp+20h]

  ProcessInformation = 0;
  v3 = 0;
  ThreadpoolWait = 0;
  Handles = 0;
  v5 = 0;
  v6 = 0;
  v7 = OpenFileMappingW(4u, 0, lpName);
  v51 = v7;
  v50 = (unsigned __int64)v7 + 1;
  if ( (unsigned __int64)v7 + 1 <= 1 )
  {
    v9 = 0;
    LastError_0 = GetLastError_0();
    if ( LastError_0 > 0 )
      LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
    if ( LastError_0 >= 0 )
      LastError_0 = -2147467259;
    v10 = LastError_0;
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_136;
    }
    v39 = 54;
LABEL_134:
    v40 = (unsigned int)LastError_0;
    goto LABEL_135;
  }
  v8 = (HANDLE *)MapViewOfFile(v7, 4u, 0, 0, 0x248u);
  v9 = v8;
  if ( !v8 )
  {
    LastError_0 = GetLastError_0();
    if ( LastError_0 > 0 )
      LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
    if ( LastError_0 >= 0 )
      LastError_0 = -2147467259;
    v10 = LastError_0;
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_136;
    }
    v39 = 55;
    goto LABEL_134;
  }
  v3 = (char *)MapViewOfFile(v8[71], 2u, 0, 0, 0x218u);
  if ( !v3 )
  {
    LastError_0 = GetLastError_0();
    if ( LastError_0 > 0 )
      LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
    if ( LastError_0 >= 0 )
      LastError_0 = -2147467259;
    v10 = LastError_0;
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_136;
    }
    v39 = 56;
    goto LABEL_134;
  }
  v10 = -2147467259;
  ThreadpoolWait = CreateThreadpoolWait(CReflectedDumpServer::s_CancelCallback, pv, 0);
  if ( !ThreadpoolWait )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v39 = 57;
      goto LABEL_106;
    }
    goto LABEL_136;
  }
  v5 = CreateThreadpoolWait(CReflectedDumpServer::s_CancelCallback, pv, 0);
  if ( !v5 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v39 = 58;
      goto LABEL_106;
    }
LABEL_136:
    if ( !ThreadpoolWait )
      goto LABEL_138;
    goto LABEL_137;
  }
  SetThreadpoolWait(ThreadpoolWait, v9[68], 0);
  SetThreadpoolWait(ThreadpoolWait, v9[67], 0);
  *(_DWORD *)v3 = -2147483638;
  v11 = CreateThreadpoolWait(CReflectedDumpServer::s_ClaimDumpFileCallback, pv, 0);
  v6 = v11;
  if ( !v11 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v39 = 59;
LABEL_106:
      v40 = 2147500037LL;
LABEL_135:
      WPP_SF_d(*((_QWORD *)v38 + 2), v39, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v40);
      goto LABEL_136;
    }
    goto LABEL_136;
  }
  SetThreadpoolWait(v11, v9[70], 0);
  if ( !SetEvent(v9[72]) )
  {
    v12 = GetLastError_0();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_102;
    }
    v14 = 60;
    goto LABEL_15;
  }
  v15 = *((_DWORD *)v9 + 3);
  v55 = v15;
  if ( (v15 & 1) != 0 )
  {
LABEL_40:
    v21 = CReflectedDump::Reflect(
            (CReflectedDump *)pv,
            *(_DWORD *)v9,
            *((_DWORD *)v9 + 1),
            *((_DWORD *)v9 + 2),
            v15,
            (const wchar_t *)v9 + 8);
    v10 = v21;
    if ( v21 < 0 )
    {
      v33 = (signed int *)v3;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
          (unsigned int)v21);
        v33 = (signed int *)v3;
      }
      *((_DWORD *)v3 + 131) = 0;
      v32 = v10;
      *((_WORD *)v3 + 2) = 0;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( (unsigned __int64)pv[66] + 1 <= 1 )
        {
          ProcessId = 0;
        }
        else
        {
          ProcessId = GetProcessId(pv[66]);
          v22 = WPP_GLOBAL_Control;
        }
        WPP_SF_Sd(
          *((_QWORD *)v22 + 2),
          67,
          (unsigned int)WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
          (_DWORD)pv + 8,
          ProcessId);
      }
      v25 = pv[66];
      if ( (unsigned __int64)v25 + 1 <= 1 )
        v26 = 0;
      else
        v26 = GetProcessId(v25);
      *((_DWORD *)v3 + 131) = v26;
      v27 = v3 + 4;
      v28 = pv + 1;
      *((_QWORD *)v3 + 66) = pv[68];
      v29 = 260;
      v30 = 2147483646;
      do
      {
        if ( !v30 )
          break;
        if ( !*v28 )
          break;
        *v27++ = *v28++;
        --v30;
        --v29;
      }
      while ( v29 );
      v31 = v27 - 1;
      v10 = v29 == 0 ? 0x8007007A : 0;
      if ( v29 )
        v31 = v27;
      *v31 = 0;
      if ( v29 )
      {
        v32 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
            (unsigned int)v10);
        }
        v32 = v10;
      }
      v33 = (signed int *)v3;
    }
    *v33 = v32;
    if ( !SetEvent(v9[69]) )
    {
      v10 = GetLastError_0();
      v34 = v10 < 0;
      if ( v10 > 0 )
      {
        v10 = (unsigned __int16)v10 | 0x80070000;
        v34 = v10 < 0;
      }
      if ( !v34 )
        v10 = -2147467259;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_102;
      }
      v14 = 70;
      goto LABEL_15;
    }
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
      }
      goto LABEL_102;
    }
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
    }
    Handles = *(_OWORD *)(v9 + 67);
    v35 = WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, 0x36EE80u);
    if ( v35 )
    {
      if ( v35 == 1 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          goto LABEL_101;
        }
        v37 = 74;
      }
      else
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_101;
        }
        v37 = 75;
      }
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_101;
      }
      v37 = 73;
    }
    WPP_SF_(*((_QWORD *)v36 + 2), v37, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
LABEL_101:
    v10 = 0;
    goto LABEL_102;
  }
  v16 = NtQueryInformationProcess(v9[67], ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( v16 < 0 )
  {
    v10 = v16 | 0x10000000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_102;
    }
    v14 = 61;
    goto LABEL_15;
  }
  v48 = ProcessInformation;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
      ProcessInformation);
  }
  v17 = OpenProcess_0(0x1000u, 0, *(_DWORD *)v9);
  hObject = v17;
  if ( (unsigned __int64)v17 + 1 > 1 )
  {
    v18 = NtQueryInformationProcess(v17, ProcessSessionInformation, &ProcessInformation, 4u, 0);
    if ( v18 < 0 )
    {
      v10 = v18 | 0x10000000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
          (unsigned int)v10);
      }
      CloseHandle(hObject);
      goto LABEL_102;
    }
    v19 = ProcessInformation;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
        ProcessInformation);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v48 == v19 )
    {
      v15 = v55;
    }
    else
    {
      if ( v20 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v20 + 2), 66, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
      v15 = v55 | 1;
    }
    CloseHandle(hObject);
    goto LABEL_40;
  }
  v10 = GetLastError_0();
  v24 = v10 < 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v24 = v10 < 0;
  }
  if ( !v24 )
    v10 = -2147467259;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    goto LABEL_102;
  }
  v14 = 63;
LABEL_15:
  WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, (unsigned int)v10);
LABEL_102:
  SetThreadpoolWait(v6, 0, 0);
  WaitForThreadpoolWaitCallbacks(v6, 1);
LABEL_137:
  SetThreadpoolWait(ThreadpoolWait, 0, 0);
  WaitForThreadpoolWaitCallbacks(ThreadpoolWait, 1);
LABEL_138:
  if ( v5 )
  {
    SetThreadpoolWait(v5, 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
  }
  if ( v9 )
  {
    v42 = v9[67];
    if ( v42 )
      CloseHandle_0(v42);
    v43 = v9[68];
    if ( v43 )
      CloseHandle_0(v43);
    v44 = v9[69];
    if ( v44 )
      CloseHandle_0(v44);
    v45 = v9[71];
    if ( v45 )
      CloseHandle_0(v45);
    v46 = v9[72];
    if ( v46 )
      CloseHandle_0(v46);
  }
  if ( v6 )
    CloseThreadpoolWait(v6);
  if ( v5 )
    CloseThreadpoolWait(v5);
  if ( ThreadpoolWait )
    CloseThreadpoolWait(ThreadpoolWait);
  if ( v9 )
    UnmapViewOfFile(v9);
  if ( v50 > 1 )
    CloseHandle(v51);
  if ( v3 )
    UnmapViewOfFile(v3);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140017f08  mov     rax, rsp
0x140017f0b  mov     [rax+10h], rbx
0x140017f0f  mov     [rax+8], rcx
0x140017f13  push    rbp
0x140017f14  push    rsi
0x140017f15  push    rdi
0x140017f16  push    r12
0x140017f18  push    r13
0x140017f1a  push    r14
0x140017f1c  push    r15
0x140017f1e  sub     rsp, 60h
0x140017f22  xor     r12d, r12d
0x140017f25  mov     r8, rdx; lpName
0x140017f28  xor     edx, edx; bInheritHandle
0x140017f2a  mov     [rax+18h], r12d
0x140017f2e  mov     r13, rcx
0x140017f31  xorps   xmm0, xmm0
0x140017f34  mov     edi, r12d
0x140017f37  mov     esi, r12d
0x140017f3a  movups  xmmword ptr [rax-48h], xmm0
0x140017f3e  lea     ebx, [rdx+4]
0x140017f41  mov     ebp, r12d
0x140017f44  mov     ecx, ebx; dwDesiredAccess
0x140017f46  mov     r14d, r12d
0x140017f49  call    cs:__imp_OpenFileMappingW
0x140017f4f  mov     [rsp+98h+var_50], rax
0x140017f54  lea     rcx, [rax+1]
0x140017f58  mov     [rsp+98h+var_58], rcx
0x140017f5d  cmp     rcx, 1
0x140017f61  jbe     loc_1400186C4
0x140017f67  xor     r9d, r9d; dwFileOffsetLow
0x140017f6a  mov     [rsp+98h+dwNumberOfBytesToMap], 248h; dwNumberOfBytesToMap
0x140017f73  xor     r8d, r8d; dwFileOffsetHigh
0x140017f76  mov     edx, ebx; dwDesiredAccess
0x140017f78  mov     rcx, rax; hFileMappingObject
0x140017f7b  call    cs:__imp_MapViewOfFile
0x140017f81  mov     rbx, rax
0x140017f84  test    rax, rax
0x140017f87  jz      loc_140018684
0x140017f8d  mov     rcx, [rax+238h]; hFileMappingObject
0x140017f94  lea     edx, [r12+2]; dwDesiredAccess
0x140017f99  xor     r9d, r9d; dwFileOffsetLow
0x140017f9c  mov     [rsp+98h+dwNumberOfBytesToMap], 218h; dwNumberOfBytesToMap
0x140017fa5  xor     r8d, r8d; dwFileOffsetHigh
0x140017fa8  call    cs:__imp_MapViewOfFile
0x140017fae  mov     rdi, rax
0x140017fb1  test    rax, rax
0x140017fb4  jz      loc_140018639
0x140017fba  xor     r8d, r8d; pcbe
0x140017fbd  lea     rcx, ?s_CancelCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140017fc4  mov     rdx, r13; pv
0x140017fc7  mov     r15d, 80004005h
0x140017fcd  call    cs:__imp_CreateThreadpoolWait
0x140017fd3  mov     rsi, rax
0x140017fd6  test    rax, rax
0x140017fd9  jz      loc_140018611
0x140017fdf  xor     r8d, r8d; pcbe
0x140017fe2  lea     rcx, ?s_CancelCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140017fe9  mov     rdx, r13; pv
0x140017fec  call    cs:__imp_CreateThreadpoolWait
0x140017ff2  mov     rbp, rax
0x140017ff5  test    rax, rax
0x140017ff8  jz      loc_1400185E9
0x140017ffe  mov     rdx, [rbx+220h]; h
0x140018005  xor     r8d, r8d; pftTimeout
0x140018008  mov     rcx, rsi; pwa
0x14001800b  call    cs:__imp_SetThreadpoolWait
0x140018011  mov     rdx, [rbx+218h]; h
0x140018018  xor     r8d, r8d; pftTimeout
0x14001801b  mov     rcx, rsi; pwa
0x14001801e  call    cs:__imp_SetThreadpoolWait
0x140018024  xor     r8d, r8d; pcbe
0x140018027  mov     dword ptr [rdi], 8000000Ah
0x14001802d  mov     rdx, r13; pv
0x140018030  lea     rcx, ?s_ClaimDumpFileCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140018037  call    cs:__imp_CreateThreadpoolWait
0x14001803d  mov     r14, rax
0x140018040  test    rax, rax
0x140018043  jz      loc_1400185BB
0x140018049  mov     rdx, [rbx+230h]; h
0x140018050  xor     r8d, r8d; pftTimeout
0x140018053  mov     rcx, rax; pwa
0x140018056  call    cs:__imp_SetThreadpoolWait
0x14001805c  mov     rcx, [rbx+240h]; hEvent
0x140018063  call    cs:__imp_SetEvent
0x140018069  test    eax, eax
0x14001806b  jnz     short loc_1400180CE
0x14001806d  call    GetLastError_0
0x140018072  mov     r15d, eax
0x140018075  test    eax, eax
0x140018077  jle     short loc_140018084
0x140018079  movzx   r15d, ax
0x14001807d  or      r15d, 80070000h
0x140018084  test    r15d, r15d
0x140018087  mov     eax, 80004005h
0x14001808c  cmovns  r15d, eax
0x140018090  mov     rcx, cs:WPP_GLOBAL_Control
0x140018097  lea     r12, WPP_GLOBAL_Control
0x14001809e  cmp     rcx, r12
0x1400180a1  jz      loc_14001859A
0x1400180a7  test    byte ptr [rcx+1Ch], 1
0x1400180ab  jz      loc_14001859A
0x1400180b1  mov     edx, 3Ch ; '<'
0x1400180b6  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400180bd  mov     rcx, [rcx+10h]
0x1400180c1  mov     r9d, r15d
0x1400180c4  call    WPP_SF_d
0x1400180c9  jmp     loc_14001859A
0x1400180ce  mov     r15d, [rbx+0Ch]
0x1400180d2  lea     r12, WPP_GLOBAL_Control
0x1400180d9  mov     [rsp+98h+arg_18], r15d
0x1400180e1  lea     r13, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400180e8  test    r15b, 1
0x1400180ec  jnz     loc_14001827F
0x1400180f2  mov     rcx, [rbx+218h]; ProcessHandle
0x1400180f9  lea     r8, [rsp+98h+ProcessInformation]; ProcessInformation
0x140018101  mov     r9d, 4; ProcessInformationLength
0x140018107  mov     [rsp+98h+dwNumberOfBytesToMap], 0; ReturnLength
0x140018110  lea     edx, [r9+14h]; ProcessInformationClass
0x140018114  call    cs:__imp_NtQueryInformationProcess
0x14001811a  mov     r15d, eax
0x14001811d  test    eax, eax
0x14001811f  jns     short loc_14001814D
0x140018121  bts     r15d, 1Ch
0x140018126  mov     rcx, cs:WPP_GLOBAL_Control
0x14001812d  cmp     rcx, r12
0x140018130  jz      loc_14001859A
0x140018136  test    byte ptr [rcx+1Ch], 1
0x14001813a  jz      loc_14001859A
0x140018140  mov     edx, 3Dh ; '='
0x140018145  mov     r8, r13
0x140018148  jmp     loc_1400180BD
0x14001814d  mov     eax, [rsp+98h+ProcessInformation]
0x140018154  mov     [rsp+98h+var_68], eax
0x140018158  mov     rcx, cs:WPP_GLOBAL_Control
0x14001815f  cmp     rcx, r12
0x140018162  jz      short loc_14001817E
0x140018164  test    byte ptr [rcx+1Ch], 8
0x140018168  jz      short loc_14001817E
0x14001816a  mov     rcx, [rcx+10h]
0x14001816e  mov     edx, 3Eh ; '>'
0x140018173  mov     r9d, eax
0x140018176  mov     r8, r13
0x140018179  call    WPP_SF_d
0x14001817e  mov     r8d, [rbx]; dwProcessId
0x140018181  xor     edx, edx; bInheritHandle
0x140018183  mov     ecx, 1000h; dwDesiredAccess
0x140018188  call    OpenProcess_0
0x14001818d  mov     [rsp+98h+hObject], rax
0x140018192  lea     rcx, [rax+1]
0x140018196  cmp     rcx, 1
0x14001819a  jbe     loc_1400182F7
0x1400181a0  mov     r9d, 4; ProcessInformationLength
0x1400181a6  mov     [rsp+98h+dwNumberOfBytesToMap], 0; ReturnLength
0x1400181af  lea     r8, [rsp+98h+ProcessInformation]; ProcessInformation
0x1400181b7  mov     rcx, rax; ProcessHandle
0x1400181ba  lea     edx, [r9+14h]; ProcessInformationClass
0x1400181be  call    cs:__imp_NtQueryInformationProcess
0x1400181c4  mov     r15d, eax
0x1400181c7  test    eax, eax
0x1400181c9  jns     short loc_140018206
0x1400181cb  bts     r15d, 1Ch
0x1400181d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181d7  cmp     rcx, r12
0x1400181da  jz      short loc_1400181F6
0x1400181dc  test    byte ptr [rcx+1Ch], 1
0x1400181e0  jz      short loc_1400181F6
0x1400181e2  mov     rcx, [rcx+10h]
0x1400181e6  mov     edx, 40h ; '@'
0x1400181eb  mov     r9d, r15d
0x1400181ee  mov     r8, r13
0x1400181f1  call    WPP_SF_d
0x1400181f6  mov     rcx, [rsp+98h+hObject]; hObject
0x1400181fb  call    cs:__imp_CloseHandle
0x140018201  jmp     loc_14001859A
0x140018206  mov     r15d, [rsp+98h+ProcessInformation]
0x14001820e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018215  cmp     rcx, r12
0x140018218  jz      short loc_14001823B
0x14001821a  test    byte ptr [rcx+1Ch], 8
0x14001821e  jz      short loc_14001823B
0x140018220  mov     rcx, [rcx+10h]
0x140018224  mov     edx, 41h ; 'A'
0x140018229  mov     r9d, r15d
0x14001822c  mov     r8, r13
0x14001822f  call    WPP_SF_d
0x140018234  mov     rcx, cs:WPP_GLOBAL_Control
0x14001823b  cmp     [rsp+98h+var_68], r15d
0x140018240  jz      short loc_14001826C
0x140018242  cmp     rcx, r12
0x140018245  jz      short loc_14001825E
0x140018247  test    byte ptr [rcx+1Ch], 4
0x14001824b  jz      short loc_14001825E
0x14001824d  mov     rcx, [rcx+10h]
0x140018251  mov     edx, 42h ; 'B'
0x140018256  mov     r8, r13
0x140018259  call    WPP_SF_
0x14001825e  mov     r15d, [rsp+98h+arg_18]
0x140018266  or      r15d, 1
0x14001826a  jmp     short loc_140018274
0x14001826c  mov     r15d, [rsp+98h+arg_18]
0x140018274  mov     rcx, [rsp+98h+hObject]; hObject
0x140018279  call    cs:__imp_CloseHandle
0x14001827f  mov     r9d, [rbx+8]; unsigned int
0x140018283  lea     rax, [rbx+10h]
0x140018287  mov     r8d, [rbx+4]; dwThreadId
0x14001828b  mov     edx, [rbx]; dwProcessId
0x14001828d  mov     rcx, [rsp+98h+arg_0]; this
0x140018295  mov     [rsp+98h+var_70], rax; wchar_t *
0x14001829a  mov     dword ptr [rsp+98h+dwNumberOfBytesToMap], r15d; unsigned int
0x14001829f  call    ?Reflect@CReflectedDump@@UEAAJKKKKPEB_W@Z; CReflectedDump::Reflect(ulong,ulong,ulong,ulong,wchar_t const *)
0x1400182a4  xor     r10d, r10d
0x1400182a7  mov     r15d, eax
0x1400182aa  test    eax, eax
0x1400182ac  js      loc_14001841D
0x1400182b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182b9  mov     r15, [rsp+98h+arg_0]
0x1400182c1  cmp     rcx, r12
0x1400182c4  jz      loc_14001835D
0x1400182ca  test    byte ptr [rcx+1Ch], 4
0x1400182ce  jz      loc_14001835D
0x1400182d4  mov     rdx, [r15+210h]
0x1400182db  lea     rax, [rdx+1]
0x1400182df  cmp     rax, 1
0x1400182e3  jbe     short loc_14001833E
0x1400182e5  mov     rcx, rdx; Process
0x1400182e8  call    cs:__imp_GetProcessId
0x1400182ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182f5  jmp     short loc_140018341
0x1400182f7  call    GetLastError_0
0x1400182fc  mov     r15d, eax
0x1400182ff  test    eax, eax
0x140018301  jle     short loc_140018311
0x140018303  movzx   r15d, r15w
0x140018307  or      r15d, 80070000h
0x14001830e  test    r15d, r15d
0x140018311  mov     eax, 80004005h
0x140018316  cmovns  r15d, eax
0x14001831a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018321  cmp     rcx, r12
0x140018324  jz      loc_14001859A
0x14001832a  test    byte ptr [rcx+1Ch], 1
0x14001832e  jz      loc_14001859A
0x140018334  mov     edx, 3Fh ; '?'
0x140018339  jmp     loc_140018145
0x14001833e  mov     eax, r10d
0x140018341  mov     rcx, [rcx+10h]
0x140018345  lea     r9, [r15+8]
0x140018349  mov     edx, 43h ; 'C'
0x14001834e  mov     dword ptr [rsp+98h+dwNumberOfBytesToMap], eax
0x140018352  mov     r8, r13
0x140018355  call    WPP_SF_Sd
0x14001835a  xor     r10d, r10d
0x14001835d  mov     rcx, [r15+210h]; Process
0x140018364  lea     rax, [rcx+1]
0x140018368  cmp     rax, 1
0x14001836c  jbe     short loc_140018379
0x14001836e  call    cs:__imp_GetProcessId
0x140018374  xor     r10d, r10d
0x140018377  jmp     short loc_14001837C
0x140018379  mov     eax, r10d
0x14001837c  mov     [rdi+20Ch], eax
0x140018382  lea     r8, [rdi+4]
0x140018386  mov     rax, [r15+220h]
0x14001838d  lea     rcx, [r15+8]
0x140018391  mov     [rdi+210h], rax
0x140018398  mov     edx, 104h
0x14001839d  mov     eax, 7FFFFFFEh
0x1400183a2  test    rax, rax
0x1400183a5  jz      short loc_1400183C6
0x1400183a7  movzx   r9d, word ptr [rcx]
0x1400183ab  test    r9w, r9w
0x1400183af  jz      short loc_1400183C6
0x1400183b1  mov     [r8], r9w
0x1400183b5  add     rcx, 2
0x1400183b9  add     r8, 2
0x1400183bd  dec     rax
0x1400183c0  sub     rdx, 1
0x1400183c4  jnz     short loc_1400183A2
0x1400183c6  mov     rax, rdx
0x1400183c9  lea     rcx, [r8-2]
0x1400183cd  neg     rax
0x1400183d0  sbb     r15d, r15d
0x1400183d3  not     r15d
0x1400183d6  and     r15d, 8007007Ah
0x1400183dd  test    rdx, rdx
0x1400183e0  cmovnz  rcx, r8
0x1400183e4  mov     [rcx], r10w
0x1400183e8  jnz     short loc_140018415
0x1400183ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183f1  cmp     rcx, r12
0x1400183f4  jz      short loc_140018410
0x1400183f6  test    byte ptr [rcx+1Ch], 1
0x1400183fa  jz      short loc_140018410
0x1400183fc  mov     rcx, [rcx+10h]
0x140018400  mov     edx, 44h ; 'D'
0x140018405  mov     r9d, r15d
0x140018408  mov     r8, r13
0x14001840b  call    WPP_SF_d
0x140018410  mov     eax, r15d
  ... truncated ...
```
