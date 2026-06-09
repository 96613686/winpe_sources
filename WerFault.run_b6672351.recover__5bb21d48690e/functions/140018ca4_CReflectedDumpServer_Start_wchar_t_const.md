# CReflectedDumpServer::Start(wchar_t const *)

- ea: `0x140018ca4`
- end: `0x140019679`
- name: `?Start@CReflectedDumpServer@@QEAAJPEB_W@Z`
- size: `2517`
- prototype: `__int64 __fastcall(PVOID pv, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140018a1c`

## callees

- `0x14000333f`
- `0x14000334b`
- `0x140003393`
- `0x140014ee4`
- `0x140014f14`
- `0x140015138`
- `0x140018280`
- `0x140018ca4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018e35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140019260`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140018e35`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140019260`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018d7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018da0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018dfd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018d7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018da0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140018dfd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018dc5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018dde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018e22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400193aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140019539`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140019566`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018dc5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018dde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140018e22`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400193aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140019539`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140019566`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400193be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001954d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001957a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400193be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001954d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14001957a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400195e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400195fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140019610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400195e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400195fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140019610`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400190d8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140019164`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400190d8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140019164`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001963d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018fdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019063`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001963d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140018ce5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140018ce5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018d1d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018d50`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018d1d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140018d50`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019624`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019651`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019624`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019651`
- `ntdll!NtQueryInformationProcess` at `0x140018eec`
- `ntdll!NtQueryInformationProcess` at `0x140018f9c`
- `ntdll!NtQueryInformationProcess` at `0x140018eec`
- `ntdll!NtQueryInformationProcess` at `0x140018f9c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140019339`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140019339`

## pseudocode

```c
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
0x140018ca4  mov     rax, rsp
0x140018ca7  mov     [rax+10h], rbx
0x140018cab  mov     [rax+8], rcx
0x140018caf  push    rbp
0x140018cb0  push    rsi
0x140018cb1  push    rdi
0x140018cb2  push    r12
0x140018cb4  push    r13
0x140018cb6  push    r14
0x140018cb8  push    r15
0x140018cba  sub     rsp, 60h
0x140018cbe  xor     r12d, r12d
0x140018cc1  mov     r8, rdx; lpName
0x140018cc4  xor     edx, edx; bInheritHandle
0x140018cc6  mov     [rax+18h], r12d
0x140018cca  mov     r13, rcx
0x140018ccd  xorps   xmm0, xmm0
0x140018cd0  mov     edi, r12d
0x140018cd3  mov     esi, r12d
0x140018cd6  movups  xmmword ptr [rax-48h], xmm0
0x140018cda  lea     ebx, [rdx+4]
0x140018cdd  mov     ebp, r12d
0x140018ce0  mov     ecx, ebx; dwDesiredAccess
0x140018ce2  mov     r14d, r12d
0x140018ce5  call    cs:__imp_OpenFileMappingW
0x140018cec  nop     dword ptr [rax+rax+00h]
0x140018cf1  mov     [rsp+98h+var_50], rax
0x140018cf6  lea     rcx, [rax+1]
0x140018cfa  mov     [rsp+98h+var_58], rcx
0x140018cff  cmp     rcx, 1
0x140018d03  jbe     loc_1400194D8
0x140018d09  xor     r9d, r9d; dwFileOffsetLow
0x140018d0c  mov     [rsp+98h+dwNumberOfBytesToMap], 248h; dwNumberOfBytesToMap
0x140018d15  xor     r8d, r8d; dwFileOffsetHigh
0x140018d18  mov     edx, ebx; dwDesiredAccess
0x140018d1a  mov     rcx, rax; hFileMappingObject
0x140018d1d  call    cs:__imp_MapViewOfFile
0x140018d24  nop     dword ptr [rax+rax+00h]
0x140018d29  mov     rbx, rax
0x140018d2c  test    rax, rax
0x140018d2f  jz      loc_140019498
0x140018d35  mov     rcx, [rax+238h]; hFileMappingObject
0x140018d3c  lea     edx, [r12+2]; dwDesiredAccess
0x140018d41  xor     r9d, r9d; dwFileOffsetLow
0x140018d44  mov     [rsp+98h+dwNumberOfBytesToMap], 218h; dwNumberOfBytesToMap
0x140018d4d  xor     r8d, r8d; dwFileOffsetHigh
0x140018d50  call    cs:__imp_MapViewOfFile
0x140018d57  nop     dword ptr [rax+rax+00h]
0x140018d5c  mov     rdi, rax
0x140018d5f  test    rax, rax
0x140018d62  jz      loc_14001944D
0x140018d68  xor     r8d, r8d; pcbe
0x140018d6b  lea     rcx, ?s_CancelCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140018d72  mov     rdx, r13; pv
0x140018d75  mov     r15d, 80004005h
0x140018d7b  call    cs:__imp_CreateThreadpoolWait
0x140018d82  nop     dword ptr [rax+rax+00h]
0x140018d87  mov     rsi, rax
0x140018d8a  test    rax, rax
0x140018d8d  jz      loc_140019425
0x140018d93  xor     r8d, r8d; pcbe
0x140018d96  lea     rcx, ?s_CancelCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140018d9d  mov     rdx, r13; pv
0x140018da0  call    cs:__imp_CreateThreadpoolWait
0x140018da7  nop     dword ptr [rax+rax+00h]
0x140018dac  mov     rbp, rax
0x140018daf  test    rax, rax
0x140018db2  jz      loc_1400193FD
0x140018db8  mov     rdx, [rbx+220h]; h
0x140018dbf  xor     r8d, r8d; pftTimeout
0x140018dc2  mov     rcx, rsi; pwa
0x140018dc5  call    cs:__imp_SetThreadpoolWait
0x140018dcc  nop     dword ptr [rax+rax+00h]
0x140018dd1  mov     rdx, [rbx+218h]; h
0x140018dd8  xor     r8d, r8d; pftTimeout
0x140018ddb  mov     rcx, rsi; pwa
0x140018dde  call    cs:__imp_SetThreadpoolWait
0x140018de5  nop     dword ptr [rax+rax+00h]
0x140018dea  xor     r8d, r8d; pcbe
0x140018ded  mov     dword ptr [rdi], 8000000Ah
0x140018df3  mov     rdx, r13; pv
0x140018df6  lea     rcx, ?s_ClaimDumpFileCallback@CReflectedDumpServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140018dfd  call    cs:__imp_CreateThreadpoolWait
0x140018e04  nop     dword ptr [rax+rax+00h]
0x140018e09  mov     r14, rax
0x140018e0c  test    rax, rax
0x140018e0f  jz      loc_1400193CF
0x140018e15  mov     rdx, [rbx+230h]; h
0x140018e1c  xor     r8d, r8d; pftTimeout
0x140018e1f  mov     rcx, rax; pwa
0x140018e22  call    cs:__imp_SetThreadpoolWait
0x140018e29  nop     dword ptr [rax+rax+00h]
0x140018e2e  mov     rcx, [rbx+240h]; hEvent
0x140018e35  call    cs:__imp_SetEvent
0x140018e3c  nop     dword ptr [rax+rax+00h]
0x140018e41  test    eax, eax
0x140018e43  jnz     short loc_140018EA6
0x140018e45  call    GetLastError_0
0x140018e4a  mov     r15d, eax
0x140018e4d  test    eax, eax
0x140018e4f  jle     short loc_140018E5C
0x140018e51  movzx   r15d, ax
0x140018e55  or      r15d, 80070000h
0x140018e5c  test    r15d, r15d
0x140018e5f  mov     eax, 80004005h
0x140018e64  cmovns  r15d, eax
0x140018e68  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e6f  lea     r12, WPP_GLOBAL_Control
0x140018e76  cmp     rcx, r12
0x140018e79  jz      loc_1400193A2
0x140018e7f  test    byte ptr [rcx+1Ch], 1
0x140018e83  jz      loc_1400193A2
0x140018e89  mov     edx, 3Ch ; '<'
0x140018e8e  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018e95  mov     rcx, [rcx+10h]
0x140018e99  mov     r9d, r15d
0x140018e9c  call    WPP_SF_d
0x140018ea1  jmp     loc_1400193A2
0x140018ea6  mov     r15d, [rbx+0Ch]
0x140018eaa  lea     r12, WPP_GLOBAL_Control
0x140018eb1  mov     [rsp+98h+arg_18], r15d
0x140018eb9  lea     r13, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018ec0  test    r15b, 1
0x140018ec4  jnz     loc_14001906F
0x140018eca  mov     rcx, [rbx+218h]; ProcessHandle
0x140018ed1  lea     r8, [rsp+98h+ProcessInformation]; ProcessInformation
0x140018ed9  mov     r9d, 4; ProcessInformationLength
0x140018edf  mov     [rsp+98h+dwNumberOfBytesToMap], 0; ReturnLength
0x140018ee8  lea     edx, [r9+14h]; ProcessInformationClass
0x140018eec  call    cs:__imp_NtQueryInformationProcess
0x140018ef3  nop     dword ptr [rax+rax+00h]
0x140018ef8  mov     r15d, eax
0x140018efb  test    eax, eax
0x140018efd  jns     short loc_140018F2B
0x140018eff  bts     r15d, 1Ch
0x140018f04  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f0b  cmp     rcx, r12
0x140018f0e  jz      loc_1400193A2
0x140018f14  test    byte ptr [rcx+1Ch], 1
0x140018f18  jz      loc_1400193A2
0x140018f1e  mov     edx, 3Dh ; '='
0x140018f23  mov     r8, r13
0x140018f26  jmp     loc_140018E95
0x140018f2b  mov     eax, [rsp+98h+ProcessInformation]
0x140018f32  mov     [rsp+98h+var_68], eax
0x140018f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f3d  cmp     rcx, r12
0x140018f40  jz      short loc_140018F5C
0x140018f42  test    byte ptr [rcx+1Ch], 8
0x140018f46  jz      short loc_140018F5C
0x140018f48  mov     rcx, [rcx+10h]
0x140018f4c  mov     edx, 3Eh ; '>'
0x140018f51  mov     r9d, eax
0x140018f54  mov     r8, r13
0x140018f57  call    WPP_SF_d
0x140018f5c  mov     r8d, [rbx]; dwProcessId
0x140018f5f  xor     edx, edx; bInheritHandle
0x140018f61  mov     ecx, 1000h; dwDesiredAccess
0x140018f66  call    OpenProcess_0
0x140018f6b  mov     [rsp+98h+hObject], rax
0x140018f70  lea     rcx, [rax+1]
0x140018f74  cmp     rcx, 1
0x140018f78  jbe     loc_1400190ED
0x140018f7e  mov     r9d, 4; ProcessInformationLength
0x140018f84  mov     [rsp+98h+dwNumberOfBytesToMap], 0; ReturnLength
0x140018f8d  lea     r8, [rsp+98h+ProcessInformation]; ProcessInformation
0x140018f95  mov     rcx, rax; ProcessHandle
0x140018f98  lea     edx, [r9+14h]; ProcessInformationClass
0x140018f9c  call    cs:__imp_NtQueryInformationProcess
0x140018fa3  nop     dword ptr [rax+rax+00h]
0x140018fa8  mov     r15d, eax
0x140018fab  test    eax, eax
0x140018fad  jns     short loc_140018FF0
0x140018faf  bts     r15d, 1Ch
0x140018fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fbb  cmp     rcx, r12
0x140018fbe  jz      short loc_140018FDA
0x140018fc0  test    byte ptr [rcx+1Ch], 1
0x140018fc4  jz      short loc_140018FDA
0x140018fc6  mov     rcx, [rcx+10h]
0x140018fca  mov     edx, 40h ; '@'
0x140018fcf  mov     r9d, r15d
0x140018fd2  mov     r8, r13
0x140018fd5  call    WPP_SF_d
0x140018fda  mov     rcx, [rsp+98h+hObject]; hObject
0x140018fdf  call    cs:__imp_CloseHandle
0x140018fe6  nop     dword ptr [rax+rax+00h]
0x140018feb  jmp     loc_1400193A2
0x140018ff0  mov     r15d, [rsp+98h+ProcessInformation]
0x140018ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fff  cmp     rcx, r12
0x140019002  jz      short loc_140019025
0x140019004  test    byte ptr [rcx+1Ch], 8
0x140019008  jz      short loc_140019025
0x14001900a  mov     rcx, [rcx+10h]
0x14001900e  mov     edx, 41h ; 'A'
0x140019013  mov     r9d, r15d
0x140019016  mov     r8, r13
0x140019019  call    WPP_SF_d
0x14001901e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019025  cmp     [rsp+98h+var_68], r15d
0x14001902a  jz      short loc_140019056
0x14001902c  cmp     rcx, r12
0x14001902f  jz      short loc_140019048
0x140019031  test    byte ptr [rcx+1Ch], 4
0x140019035  jz      short loc_140019048
0x140019037  mov     rcx, [rcx+10h]
0x14001903b  mov     edx, 42h ; 'B'
0x140019040  mov     r8, r13
0x140019043  call    WPP_SF_
0x140019048  mov     r15d, [rsp+98h+arg_18]
0x140019050  or      r15d, 1
0x140019054  jmp     short loc_14001905E
0x140019056  mov     r15d, [rsp+98h+arg_18]
0x14001905e  mov     rcx, [rsp+98h+hObject]; hObject
0x140019063  call    cs:__imp_CloseHandle
0x14001906a  nop     dword ptr [rax+rax+00h]
0x14001906f  mov     r9d, [rbx+8]; unsigned int
0x140019073  lea     rax, [rbx+10h]
0x140019077  mov     r8d, [rbx+4]; dwThreadId
0x14001907b  mov     edx, [rbx]; dwProcessId
0x14001907d  mov     rcx, [rsp+98h+arg_0]; this
0x140019085  mov     [rsp+98h+var_70], rax; wchar_t *
0x14001908a  mov     dword ptr [rsp+98h+dwNumberOfBytesToMap], r15d; unsigned int
0x14001908f  call    ?Reflect@CReflectedDump@@UEAAJKKKKPEB_W@Z; CReflectedDump::Reflect(ulong,ulong,ulong,ulong,wchar_t const *)
0x140019094  xor     r10d, r10d
0x140019097  mov     r15d, eax
0x14001909a  test    eax, eax
0x14001909c  js      loc_140019219
0x1400190a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190a9  mov     r15, [rsp+98h+arg_0]
0x1400190b1  cmp     rcx, r12
0x1400190b4  jz      loc_140019153
0x1400190ba  test    byte ptr [rcx+1Ch], 4
0x1400190be  jz      loc_140019153
0x1400190c4  mov     rdx, [r15+210h]
0x1400190cb  lea     rax, [rdx+1]
0x1400190cf  cmp     rax, 1
0x1400190d3  jbe     short loc_140019134
0x1400190d5  mov     rcx, rdx; Process
0x1400190d8  call    cs:__imp_GetProcessId
0x1400190df  nop     dword ptr [rax+rax+00h]
0x1400190e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190eb  jmp     short loc_140019137
0x1400190ed  call    GetLastError_0
0x1400190f2  mov     r15d, eax
0x1400190f5  test    eax, eax
0x1400190f7  jle     short loc_140019107
0x1400190f9  movzx   r15d, r15w
0x1400190fd  or      r15d, 80070000h
0x140019104  test    r15d, r15d
0x140019107  mov     eax, 80004005h
0x14001910c  cmovns  r15d, eax
0x140019110  mov     rcx, cs:WPP_GLOBAL_Control
0x140019117  cmp     rcx, r12
0x14001911a  jz      loc_1400193A2
0x140019120  test    byte ptr [rcx+1Ch], 1
0x140019124  jz      loc_1400193A2
0x14001912a  mov     edx, 3Fh ; '?'
0x14001912f  jmp     loc_140018F23
0x140019134  mov     eax, r10d
0x140019137  mov     rcx, [rcx+10h]
0x14001913b  lea     r9, [r15+8]
0x14001913f  mov     edx, 43h ; 'C'
0x140019144  mov     dword ptr [rsp+98h+dwNumberOfBytesToMap], eax
0x140019148  mov     r8, r13
0x14001914b  call    WPP_SF_Sd
0x140019150  xor     r10d, r10d
0x140019153  mov     rcx, [r15+210h]; Process
0x14001915a  lea     rax, [rcx+1]
0x14001915e  cmp     rax, 1
0x140019162  jbe     short loc_140019175
0x140019164  call    cs:__imp_GetProcessId
0x14001916b  nop     dword ptr [rax+rax+00h]
0x140019170  xor     r10d, r10d
0x140019173  jmp     short loc_140019178
0x140019175  mov     eax, r10d
0x140019178  mov     [rdi+20Ch], eax
0x14001917e  lea     r8, [rdi+4]
0x140019182  mov     rax, [r15+220h]
0x140019189  lea     rcx, [r15+8]
0x14001918d  mov     [rdi+210h], rax
0x140019194  mov     edx, 104h
0x140019199  mov     eax, 7FFFFFFEh
0x14001919e  test    rax, rax
0x1400191a1  jz      short loc_1400191C2
0x1400191a3  movzx   r9d, word ptr [rcx]
0x1400191a7  test    r9w, r9w
0x1400191ab  jz      short loc_1400191C2
0x1400191ad  mov     [r8], r9w
0x1400191b1  add     rcx, 2
0x1400191b5  add     r8, 2
0x1400191b9  dec     rax
0x1400191bc  sub     rdx, 1
0x1400191c0  jnz     short loc_14001919E
0x1400191c2  mov     rax, rdx
0x1400191c5  lea     rcx, [r8-2]
0x1400191c9  neg     rax
0x1400191cc  sbb     r15d, r15d
0x1400191cf  not     r15d
  ... truncated ...
```
