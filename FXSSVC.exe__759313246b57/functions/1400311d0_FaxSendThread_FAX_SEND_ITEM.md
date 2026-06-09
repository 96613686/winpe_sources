# FaxSendThread(_FAX_SEND_ITEM *)

- ea: `0x1400311d0`
- end: `0x140031d6e`
- name: `?FaxSendThread@@YAKPEAU_FAX_SEND_ITEM@@@Z`
- size: `2974`
- prototype: `__int64 __fastcall(struct _FAX_SEND_ITEM *lpMem)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140002c73`
- `0x1400034d4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004fe4`
- `0x1400259bc`
- `0x1400306e0`
- `0x1400311d0`
- `0x140032e04`
- `0x14003354c`
- `0x140036164`
- `0x140036268`
- `0x140036a64`
- `0x140036b8c`
- `0x140036e68`
- `0x140052184`
- `0x1400529a4`
- `0x140058d78`
- `0x14006998c`
- `0x14006af2c`
- `0x140073444`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003139d`
- `KERNEL32!GetLastError` at `0x1400315c3`
- `KERNEL32!GetLastError` at `0x1400316d5`
- `KERNEL32!GetLastError` at `0x14003190f`
- `KERNEL32!GetLastError` at `0x1400319f8`
- `KERNEL32!GetLastError` at `0x140031ad4`
- `KERNEL32!GetLastError` at `0x140031b48`
- `KERNEL32!GetLastError` at `0x140031b9f`
- `KERNEL32!GetLastError` at `0x140031c39`
- `KERNEL32!GetLastError` at `0x140031d16`
- `KERNEL32!GetLastError` at `0x14003139d`
- `KERNEL32!GetLastError` at `0x1400315c3`
- `KERNEL32!GetLastError` at `0x1400316d5`
- `KERNEL32!GetLastError` at `0x14003190f`
- `KERNEL32!GetLastError` at `0x1400319f8`
- `KERNEL32!GetLastError` at `0x140031ad4`
- `KERNEL32!GetLastError` at `0x140031b48`
- `KERNEL32!GetLastError` at `0x140031b9f`
- `KERNEL32!GetLastError` at `0x140031c39`
- `KERNEL32!GetLastError` at `0x140031d16`
- `KERNEL32!EnterCriticalSection` at `0x14003145b`
- `KERNEL32!EnterCriticalSection` at `0x14003156a`
- `KERNEL32!EnterCriticalSection` at `0x140031870`
- `KERNEL32!EnterCriticalSection` at `0x140031be0`
- `KERNEL32!EnterCriticalSection` at `0x14003145b`
- `KERNEL32!EnterCriticalSection` at `0x14003156a`
- `KERNEL32!EnterCriticalSection` at `0x140031870`
- `KERNEL32!EnterCriticalSection` at `0x140031be0`
- `KERNEL32!LeaveCriticalSection` at `0x140031478`
- `KERNEL32!LeaveCriticalSection` at `0x140031604`
- `KERNEL32!LeaveCriticalSection` at `0x1400319c1`
- `KERNEL32!LeaveCriticalSection` at `0x140031c7a`
- `KERNEL32!LeaveCriticalSection` at `0x140031478`
- `KERNEL32!LeaveCriticalSection` at `0x140031604`
- `KERNEL32!LeaveCriticalSection` at `0x1400319c1`
- `KERNEL32!LeaveCriticalSection` at `0x140031c7a`
- `KERNEL32!GetLocalTime` at `0x1400314ef`
- `KERNEL32!GetLocalTime` at `0x1400314ef`
- `KERNEL32!SetThreadExecutionState` at `0x140031271`
- `KERNEL32!SetThreadExecutionState` at `0x140031271`

## pseudocode

```c
__int64 __fastcall FaxSendThread(struct _FAX_SEND_ITEM *lpMem)
{
  int v2; // ebx
  int v3; // r9d
  __int64 v4; // rcx
  __int64 v5; // r13
  CMapDeviceId *v6; // rax
  unsigned __int16 *v7; // rax
  LPVOID *v8; // rbx
  int v9; // ebx
  int v10; // ebx
  int v11; // edx
  LPVOID *v12; // rax
  struct _FSPI_JOB_STATUS *v13; // rbx
  unsigned int v14; // r8d
  int v15; // eax
  int v16; // edx
  __int64 v17; // rax
  void *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // ebx
  unsigned int v23; // r13d
  DWORD LastError; // eax
  __int64 v25; // r8
  int v26; // edx
  DWORD v27; // eax
  int v29; // [rsp+40h] [rbp-158h]
  int v30; // [rsp+44h] [rbp-154h]
  struct _FSPI_JOB_STATUS *v32; // [rsp+50h] [rbp-148h] BYREF
  unsigned __int16 **v33; // [rsp+58h] [rbp-140h]
  LPVOID lpMema; // [rsp+60h] [rbp-138h]
  LPVOID *v35; // [rsp+68h] [rbp-130h]
  LPVOID *v36; // [rsp+70h] [rbp-128h]
  LPVOID *v37; // [rsp+78h] [rbp-120h]
  LPVOID *v38; // [rsp+80h] [rbp-118h]
  int v39; // [rsp+90h] [rbp-108h] BYREF
  __int64 v40; // [rsp+98h] [rbp-100h]
  __int64 v41; // [rsp+A0h] [rbp-F8h]
  __int64 v42; // [rsp+A8h] [rbp-F0h]
  __int64 v43; // [rsp+B0h] [rbp-E8h]
  __int64 v44; // [rsp+B8h] [rbp-E0h]
  int v45; // [rsp+C0h] [rbp-D8h]
  char v46[8]; // [rsp+C4h] [rbp-D4h]
  __int64 v47; // [rsp+CCh] [rbp-CCh]
  __int128 v48; // [rsp+E0h] [rbp-B8h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime; // [rsp+100h] [rbp-98h] BYREF
  __int128 v51; // [rsp+110h] [rbp-88h] BYREF
  __int128 v52; // [rsp+120h] [rbp-78h]
  __int128 v53; // [rsp+130h] [rbp-68h]
  __int128 v54; // [rsp+140h] [rbp-58h]
  __int128 v55; // [rsp+150h] [rbp-48h]
  __int64 v56; // [rsp+160h] [rbp-38h]

  lpMema = lpMem;
  memset_0(&v39, 0, 0x48u);
  memset_0(&v51, 0, 0x58u);
  v32 = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  if ( !SetThreadExecutionState(0x80000001)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v4 = *(_QWORD *)lpMem;
  v5 = *(_QWORD *)(*(_QWORD *)lpMem + 1104LL);
  v39 = 72;
  v38 = (LPVOID *)((char *)lpMem + 40);
  v41 = *((_QWORD *)lpMem + 5);
  v35 = (LPVOID *)((char *)lpMem + 24);
  v42 = *((_QWORD *)lpMem + 3);
  v37 = (LPVOID *)((char *)lpMem + 32);
  v43 = *((_QWORD *)lpMem + 4);
  v36 = (LPVOID *)((char *)lpMem + 16);
  v44 = *((_QWORD *)lpMem + 2);
  *(_QWORD *)v46 = 0;
  v47 = 0;
  UpdateDeviceJobsCounter(*(struct _LINE_INFO **)(v4 + 16), 1, 1, v3);
  if ( *(_QWORD *)(v5 + 72) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(_DWORD *)(v5 + 32),
      *(_QWORD *)(v5 + 72));
LABEL_25:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v5 + 32));
  }
  if ( (unsigned int)CreateTiffFileForJob((struct _JOB_QUEUE *)v5) )
    goto LABEL_25;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v2 = 1;
LABEL_26:
  if ( v2 )
  {
    v8 = (LPVOID *)lpMem;
  }
  else
  {
    v7 = StringDup(*(unsigned __int16 **)(v5 + 72));
    v8 = (LPVOID *)lpMem;
    v33 = (unsigned __int16 **)((char *)lpMem + 8);
    *((_QWORD *)lpMem + 1) = v7;
    if ( v7 )
    {
      v40 = (__int64)v7;
      v45 = 0;
      EnterCriticalSection(&g_CsConfig);
      v9 = *((_DWORD *)g_pFaxConfig + 6);
      LeaveCriticalSection(&g_CsConfig);
      if ( v9 )
      {
        v48 = 0;
        v49 = 0;
        SystemTime = 0;
        LODWORD(v48) = 48;
        *(_QWORD *)&v49 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 464LL);
        *((_QWORD *)&v49 + 1) = *((_QWORD *)lpMem + 6);
        *((_QWORD *)&v48 + 1) = *v35;
        GetLocalTime(&SystemTime);
        v10 = FaxBrandDocument(*v33, (struct tag_FSPI_BRAND_INFO *)&v48);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
          }
          if ( v10 == -2147024713 || v10 == -2147024816 )
          {
            EnterCriticalSection(&g_CsJob);
            FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v11);
            *(_DWORD *)(*(_QWORD *)lpMem + 1128LL) = 11;
            *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
            if ( !(unsigned int)HandleFailedSendJob(*(struct _JOB_ENTRY **)lpMem)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              GetLastError();
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
            }
            LeaveCriticalSection(&g_CsJob);
            v12 = (LPVOID *)v33;
            v8 = (LPVOID *)lpMem;
            goto LABEL_125;
          }
        }
      }
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 72LL) = 536903680;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_lSSDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v40,
          *(_QWORD *)lpMem + 588LL,
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 32LL),
          v46[0]);
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64 (__fastcall *)(void *, unsigned int, unsigned int, unsigned int)))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 16LL) + 40LL) + 2184LL))(
              *(_QWORD *)(*(_QWORD *)lpMem + 32LL),
              &v39,
              FaxSendCallback);
      if ( !v30
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        GetLastError();
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
      }
      lpMema = 0;
      if ( GetDevStatus(*(void **)(*(_QWORD *)lpMem + 32LL), *(struct _LINE_INFO **)(*(_QWORD *)lpMem + 16LL), &v32) )
      {
        v29 = 1;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
        }
        v13 = v32;
      }
      else
      {
        v29 = 0;
        v13 = v32;
        v14 = *((_DWORD *)v32 + 2);
        if ( v14 == 10 || v14 <= 7 || v14 >= 0xE )
        {
          v29 = 1;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
          }
          lpMema = v13;
          v51 = *(_OWORD *)v13;
          v52 = *((_OWORD *)v13 + 1);
          v53 = *((_OWORD *)v13 + 2);
          v54 = *((_OWORD *)v13 + 3);
          v55 = *((_OWORD *)v13 + 4);
          v56 = *((_QWORD *)v13 + 10);
          if ( (*((_DWORD *)v13 + 1) & 0x10000000) != 0 )
          {
            HIDWORD(v51) = *((_DWORD *)v13 + 3);
            LODWORD(v52) = *((_DWORD *)v13 + 4);
          }
          v13 = 0;
        }
      }
      EnterCriticalSection(&g_CsJob);
      if ( v29 )
      {
        v13 = (struct _FSPI_JOB_STATUS *)&v51;
        LODWORD(v51) = 88;
        if ( v30 )
        {
          DWORD2(v51) = 9;
          if ( !HIDWORD(v51) )
            HIDWORD(v51) = 18;
        }
        else
        {
          DWORD2(v51) = 11;
          v15 = HIDWORD(v51);
          if ( !HIDWORD(v51) )
            v15 = 12;
          HIDWORD(v51) = v15;
        }
      }
      if ( !UpdateJobStatus(*(struct _JOB_ENTRY **)lpMem, v13) )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          GetLastError();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
        }
        FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v16);
        v17 = *(_QWORD *)lpMem;
        if ( v30 )
        {
          *(_DWORD *)(v17 + 1128) = 9;
          *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 18;
        }
        else
        {
          *(_DWORD *)(v17 + 1128) = 11;
          *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
        }
      }
      if ( v29 )
      {
        if ( !lpMema )
        {
LABEL_87:
          *(_DWORD *)(*(_QWORD *)lpMem + 1736LL) = 1;
          LeaveCriticalSection(&g_CsJob);
          v19 = *(_QWORD *)lpMem;
          if ( v30 )
          {
            v32 = 0;
            v20 = *(_QWORD *)(v19 + 1104);
            if ( *(_DWORD *)(v20 + 36) == 2 )
              v20 = *(_QWORD *)(v20 + 584);
            v21 = AllocateAndCopySid(*(PSID *)(v20 + 408));
            v22 = v21;
            if ( v21
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v21);
            }
            v23 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)lpMem + 1104LL) + 32LL);
            if ( !(unsigned int)HandleCompletedSendJob(*(struct _JOB_ENTRY **)lpMem)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              GetLastError();
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
            }
            if ( !v22 )
            {
              if ( !CreateFaxEvent(0, 0x17u, v23, v32)
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LastError = GetLastError();
                WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, v25, 23, v23, LastError);
              }
              pMemFree(v32);
            }
          }
          else if ( !(unsigned int)HandleFailedSendJob((struct _JOB_ENTRY *)v19)
                 && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            GetLastError();
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
          }
          v12 = (LPVOID *)v33;
          v8 = (LPVOID *)lpMem;
          goto LABEL_125;
        }
        v18 = lpMema;
      }
      else
      {
        v18 = v13;
      }
      pMemFree(v18);
      goto LABEL_87;
    }
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsJob);
  FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(*(_QWORD *)lpMem + 1120LL), v26);
  *(_DWORD *)(*(_QWORD *)lpMem + 1128LL) = 11;
  *(_DWORD *)(*(_QWORD *)lpMem + 1132LL) = 12;
  if ( !(unsigned int)HandleFailedSendJob(*(struct _JOB_ENTRY **)lpMem)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  LeaveCriticalSection(&g_CsJob);
  v12 = v8 + 1;
LABEL_125:
  pMemFree(*v12);
  pMemFree(*v36);
  pMemFree(*v35);
  pMemFree(*v37);
  pMemFree(*v38);
  pMemFree(v8[7]);
  pMemFree(v8[6]);
  pMemFree(v8[8]);
  pMemFree(v8[9]);
  pMemFree(v8);
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v27);
  }
  return 0;
}

```

## disassembly

```asm
0x1400311d0  mov     [rsp+arg_8], rbx
0x1400311d5  mov     [rsp+arg_10], rsi
0x1400311da  push    r12
0x1400311dc  push    r13
0x1400311de  push    r14
0x1400311e0  sub     rsp, 180h
0x1400311e7  mov     rax, cs:__security_cookie
0x1400311ee  xor     rax, rsp
0x1400311f1  mov     [rsp+198h+var_28], rax
0x1400311f9  mov     rsi, rcx
0x1400311fc  mov     [rsp+198h+lpMem], rcx
0x140031201  mov     [rsp+198h+var_150], rcx
0x140031206  xor     edx, edx; Val
0x140031208  lea     r8d, [rdx+48h]; Size
0x14003120c  lea     rcx, [rsp+198h+var_108]; void *
0x140031214  call    memset_0
0x140031219  xor     edx, edx; Val
0x14003121b  lea     r8d, [rdx+58h]; Size
0x14003121f  lea     rcx, [rsp+198h+var_88]; void *
0x140031227  call    memset_0
0x14003122c  mov     [rsp+198h+var_148], 0
0x140031235  xor     ebx, ebx
0x140031237  lea     r12, WPP_GLOBAL_Control
0x14003123e  mov     rcx, cs:WPP_GLOBAL_Control
0x140031245  mov     r14b, 4
0x140031248  cmp     rcx, r12
0x14003124b  jz      short loc_14003126C
0x14003124d  test    [rcx+1Ch], r14b
0x140031251  jz      short loc_14003126C
0x140031253  cmp     byte ptr [rcx+19h], 5
0x140031257  jb      short loc_14003126C
0x140031259  lea     edx, [rbx+44h]
0x14003125c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031263  mov     rcx, [rcx+10h]
0x140031267  call    WPP_SF_
0x14003126c  mov     ecx, 80000001h; esFlags
0x140031271  call    cs:__imp_SetThreadExecutionState
0x140031278  nop     dword ptr [rax+rax+00h]
0x14003127d  test    eax, eax
0x14003127f  jnz     short loc_1400312AC
0x140031281  mov     rcx, cs:WPP_GLOBAL_Control
0x140031288  cmp     rcx, r12
0x14003128b  jz      short loc_1400312AC
0x14003128d  test    [rcx+1Ch], r14b
0x140031291  jz      short loc_1400312AC
0x140031293  cmp     byte ptr [rcx+19h], 2
0x140031297  jb      short loc_1400312AC
0x140031299  lea     edx, [rax+45h]
0x14003129c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400312a3  mov     rcx, [rcx+10h]
0x1400312a7  call    WPP_SF_
0x1400312ac  mov     rcx, [rsi]
0x1400312af  mov     r13, [rcx+450h]
0x1400312b6  mov     [rsp+198h+var_108], 48h ; 'H'
0x1400312c1  lea     rax, [rsi+28h]
0x1400312c5  mov     [rsp+198h+var_118], rax
0x1400312cd  mov     rax, [rax]
0x1400312d0  mov     [rsp+198h+var_F8], rax
0x1400312d8  lea     rax, [rsi+18h]
0x1400312dc  mov     [rsp+198h+var_130], rax
0x1400312e1  mov     rax, [rax]
0x1400312e4  mov     [rsp+198h+var_F0], rax
0x1400312ec  lea     rax, [rsi+20h]
0x1400312f0  mov     [rsp+198h+var_120], rax
0x1400312f5  mov     rax, [rax]
0x1400312f8  mov     [rsp+198h+var_E8], rax
0x140031300  lea     rax, [rsi+10h]
0x140031304  mov     [rsp+198h+var_128], rax
0x140031309  mov     rax, [rax]
0x14003130c  mov     [rsp+198h+var_E0], rax
0x140031314  mov     qword ptr [rsp+198h+var_D4], rbx
0x14003131c  mov     [rsp+198h+var_CC], rbx
0x140031324  mov     eax, 1
0x140031329  mov     r8d, eax; int
0x14003132c  mov     edx, eax; int
0x14003132e  mov     rcx, [rcx+10h]; struct _LINE_INFO *
0x140031332  call    ?UpdateDeviceJobsCounter@@YAXPEAU_LINE_INFO@@HHH@Z; UpdateDeviceJobsCounter(_LINE_INFO *,int,int,int)
0x140031337  mov     rcx, [r13+48h]
0x14003133b  test    rcx, rcx
0x14003133e  jnz     loc_1400313DB
0x140031344  mov     rcx, cs:WPP_GLOBAL_Control
0x14003134b  cmp     rcx, r12
0x14003134e  jz      short loc_140031375
0x140031350  test    [rcx+1Ch], r14b
0x140031354  jz      short loc_140031375
0x140031356  cmp     byte ptr [rcx+19h], 5
0x14003135a  jb      short loc_140031375
0x14003135c  mov     edx, 46h ; 'F'
0x140031361  mov     r9d, [r13+20h]
0x140031365  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003136c  mov     rcx, [rcx+10h]
0x140031370  call    WPP_SF_d
0x140031375  mov     rcx, r13; struct _JOB_QUEUE *
0x140031378  call    ?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z; CreateTiffFileForJob(_JOB_QUEUE *)
0x14003137d  test    eax, eax
0x14003137f  jnz     loc_140031411
0x140031385  mov     rax, cs:WPP_GLOBAL_Control
0x14003138c  cmp     rax, r12
0x14003138f  jz      short loc_1400313D4
0x140031391  test    [rax+1Ch], r14b
0x140031395  jz      short loc_1400313D4
0x140031397  cmp     byte ptr [rax+19h], 2
0x14003139b  jb      short loc_1400313D4
0x14003139d  call    cs:__imp_GetLastError
0x1400313a4  nop     dword ptr [rax+rax+00h]
0x1400313a9  mov     edx, 47h ; 'G'
0x1400313ae  mov     dword ptr [rsp+198h+var_178], eax
0x1400313b2  mov     r9d, [r13+20h]
0x1400313b6  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400313bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400313c4  mov     rcx, [rcx+10h]
0x1400313c8  call    WPP_SF_dd
0x1400313cd  mov     rax, cs:WPP_GLOBAL_Control
0x1400313d4  mov     ebx, 1
0x1400313d9  jmp     short loc_140031418
0x1400313db  mov     rax, cs:WPP_GLOBAL_Control
0x1400313e2  cmp     rax, r12
0x1400313e5  jz      short loc_140031418
0x1400313e7  test    [rax+1Ch], r14b
0x1400313eb  jz      short loc_140031418
0x1400313ed  cmp     byte ptr [rax+19h], 2
0x1400313f1  jb      short loc_140031418
0x1400313f3  mov     edx, 48h ; 'H'
0x1400313f8  mov     [rsp+198h+var_178], rcx
0x1400313fd  mov     r9d, [r13+20h]
0x140031401  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031408  mov     rcx, [rax+10h]
0x14003140c  call    WPP_SF_DS
0x140031411  mov     rax, cs:WPP_GLOBAL_Control
0x140031418  test    ebx, ebx
0x14003141a  jnz     loc_140031B8B
0x140031420  mov     rcx, [r13+48h]; unsigned __int16 *
0x140031424  call    StringDup
0x140031429  mov     rbx, rsi
0x14003142c  lea     rcx, [rsi+8]
0x140031430  mov     [rsp+198h+var_140], rcx
0x140031435  mov     [rcx], rax
0x140031438  test    rax, rax
0x14003143b  jz      loc_140031B82
0x140031441  mov     [rsp+198h+var_100], rax
0x140031449  mov     [rsp+198h+var_D8], 0
0x140031454  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003145b  call    cs:__imp_EnterCriticalSection
0x140031462  nop     dword ptr [rax+rax+00h]
0x140031467  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14003146e  mov     ebx, [rax+18h]
0x140031471  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031478  call    cs:__imp_LeaveCriticalSection
0x14003147f  nop     dword ptr [rax+rax+00h]
0x140031484  test    ebx, ebx
0x140031486  jz      loc_14003161D
0x14003148c  xorps   xmm0, xmm0
0x14003148f  movups  [rsp+198h+var_B8], xmm0
0x140031497  movups  [rsp+198h+var_A8], xmm0
0x14003149f  movups  xmmword ptr [rsp+198h+SystemTime.wYear], xmm0
0x1400314a7  mov     dword ptr [rsp+198h+var_B8], 30h ; '0'
0x1400314b2  mov     rax, [rsi]
0x1400314b5  mov     rcx, [rax+450h]
0x1400314bc  mov     rax, [rcx+1D0h]
0x1400314c3  mov     qword ptr [rsp+198h+var_A8], rax
0x1400314cb  mov     rax, [rsi+30h]
0x1400314cf  mov     qword ptr [rsp+198h+var_A8+8], rax
0x1400314d7  mov     rax, [rsp+198h+var_130]
0x1400314dc  mov     rax, [rax]
0x1400314df  mov     qword ptr [rsp+198h+var_B8+8], rax
0x1400314e7  lea     rcx, [rsp+198h+SystemTime]; lpSystemTime
0x1400314ef  call    cs:__imp_GetLocalTime
0x1400314f6  nop     dword ptr [rax+rax+00h]
0x1400314fb  lea     rdx, [rsp+198h+var_B8]; struct tag_FSPI_BRAND_INFO *
0x140031503  mov     rcx, [rsp+198h+var_140]
0x140031508  mov     rcx, [rcx]; unsigned __int16 *
0x14003150b  call    FaxBrandDocument
0x140031510  mov     ebx, eax
0x140031512  test    eax, eax
0x140031514  jns     loc_14003161D
0x14003151a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031521  cmp     rcx, r12
0x140031524  jz      short loc_14003154F
0x140031526  test    [rcx+1Ch], r14b
0x14003152a  jz      short loc_14003154F
0x14003152c  cmp     byte ptr [rcx+19h], 2
0x140031530  jb      short loc_14003154F
0x140031532  mov     edx, 4Bh ; 'K'
0x140031537  mov     dword ptr [rsp+198h+var_178], eax
0x14003153b  mov     r9d, [r13+20h]
0x14003153f  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031546  mov     rcx, [rcx+10h]
0x14003154a  call    WPP_SF_dd
0x14003154f  cmp     ebx, 800700B7h
0x140031555  jz      short loc_140031563
0x140031557  cmp     ebx, 80070050h
0x14003155d  jnz     loc_14003161D
0x140031563  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003156a  call    cs:__imp_EnterCriticalSection
0x140031571  nop     dword ptr [rax+rax+00h]
0x140031576  mov     rcx, [rsi]
0x140031579  add     rcx, 460h; struct _FSPI_JOB_STATUS *
0x140031580  call    ?FreeFSPIJobStatus@@YAHPEAU_FSPI_JOB_STATUS@@H@Z; FreeFSPIJobStatus(_FSPI_JOB_STATUS *,int)
0x140031585  mov     rax, [rsi]
0x140031588  mov     dword ptr [rax+468h], 0Bh
0x140031592  mov     rax, [rsi]
0x140031595  mov     dword ptr [rax+46Ch], 0Ch
0x14003159f  mov     rcx, [rsi]; lpMem
0x1400315a2  call    ?HandleFailedSendJob@@YAHPEAU_JOB_ENTRY@@@Z; HandleFailedSendJob(_JOB_ENTRY *)
0x1400315a7  test    eax, eax
0x1400315a9  jnz     short loc_1400315FD
0x1400315ab  mov     rax, cs:WPP_GLOBAL_Control
0x1400315b2  cmp     rax, r12
0x1400315b5  jz      short loc_1400315FD
0x1400315b7  test    [rax+1Ch], r14b
0x1400315bb  jz      short loc_1400315FD
0x1400315bd  cmp     byte ptr [rax+19h], 2
0x1400315c1  jb      short loc_1400315FD
0x1400315c3  call    cs:__imp_GetLastError
0x1400315ca  nop     dword ptr [rax+rax+00h]
0x1400315cf  mov     rdx, [rsi]
0x1400315d2  mov     r9, [rdx+450h]
0x1400315d9  mov     edx, 4Ch ; 'L'
0x1400315de  mov     dword ptr [rsp+198h+var_178], eax
0x1400315e2  mov     r9d, [r9+20h]
0x1400315e6  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400315ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400315f4  mov     rcx, [rcx+10h]
0x1400315f8  call    WPP_SF_dd
0x1400315fd  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031604  call    cs:__imp_LeaveCriticalSection
0x14003160b  nop     dword ptr [rax+rax+00h]
0x140031610  mov     rax, [rsp+198h+var_140]
0x140031615  mov     rbx, rsi
0x140031618  jmp     loc_140031C8A
0x14003161d  mov     [rsp+198h+var_154], 0
0x140031625  mov     rax, [rsi]
0x140031628  mov     rcx, [rax+10h]
0x14003162c  mov     dword ptr [rcx+48h], 20008000h
0x140031633  mov     rcx, cs:WPP_GLOBAL_Control
0x14003163a  cmp     rcx, r12
0x14003163d  jz      short loc_14003168B
0x14003163f  test    [rcx+1Ch], r14b
0x140031643  jz      short loc_14003168B
0x140031645  cmp     byte ptr [rcx+19h], 5
0x140031649  jb      short loc_14003168B
0x14003164b  mov     rax, [rsi]
0x14003164e  mov     rdx, [rax+10h]
0x140031652  lea     r8, [rax+24Ch]
0x140031659  mov     eax, dword ptr [rsp+198h+var_D4]
0x140031660  mov     dword ptr [rsp+198h+var_160], eax; char
0x140031664  mov     eax, [rdx+20h]
0x140031667  mov     dword ptr [rsp+198h+var_168], eax; char
0x14003166b  mov     [rsp+198h+var_170], r8; __int64
0x140031670  mov     rax, [rsp+198h+var_100]
0x140031678  mov     [rsp+198h+var_178], rax; __int64
0x14003167d  mov     r9d, [r13+20h]
0x140031681  mov     rcx, [rcx+10h]; LoggerHandle
0x140031685  call    WPP_SF_lSSDD
0x14003168a  nop
0x14003168b  mov     rcx, [rsi]
0x14003168e  mov     rax, [rcx+10h]
0x140031692  mov     rdx, [rax+28h]
0x140031696  mov     rax, [rdx+888h]
0x14003169d  lea     r8, ?FaxSendCallback@@YAHPEAXKKK@Z; FaxSendCallback(void *,ulong,ulong,ulong)
0x1400316a4  lea     rdx, [rsp+198h+var_108]
0x1400316ac  mov     rcx, [rcx+20h]
0x1400316b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400316b5  mov     [rsp+198h+var_154], eax
0x1400316b9  test    eax, eax
0x1400316bb  jnz     short loc_140031705
0x1400316bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316c4  cmp     rcx, r12
0x1400316c7  jz      short loc_140031705
0x1400316c9  test    [rcx+1Ch], r14b
0x1400316cd  jz      short loc_140031705
0x1400316cf  cmp     byte ptr [rcx+19h], 2
0x1400316d3  jb      short loc_140031705
0x1400316d5  call    cs:__imp_GetLastError
0x1400316dc  nop     dword ptr [rax+rax+00h]
0x1400316e1  mov     edx, 4Eh ; 'N'
0x1400316e6  mov     dword ptr [rsp+198h+var_178], eax
0x1400316ea  mov     r9d, [r13+20h]
0x1400316ee  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400316f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316fc  mov     rcx, [rcx+10h]
0x140031700  call    WPP_SF_dd
0x140031705  jmp     short loc_140031716
0x140031707  lea     r12, WPP_GLOBAL_Control
0x14003170e  mov     r14b, 4
0x140031711  mov     rsi, [rsp+198h+lpMem]
0x140031716  mov     [rsp+198h+lpMem], 0
0x14003171f  mov     rcx, [rsi]
0x140031722  lea     r8, [rsp+198h+var_148]; struct _FSPI_JOB_STATUS **
0x140031727  mov     rdx, [rcx+10h]; struct _LINE_INFO *
0x14003172b  mov     rcx, [rcx+20h]; void *
0x14003172f  call    ?GetDevStatus@@YAKPEAXPEAU_LINE_INFO@@PEAPEAU_FSPI_JOB_STATUS@@@Z; GetDevStatus(void *,_LINE_INFO *,_FSPI_JOB_STATUS * *)
0x140031734  mov     r8d, eax
0x140031737  test    eax, eax
0x140031739  jz      short loc_14003178D
0x14003173b  mov     [rsp+198h+var_158], 1
0x140031743  mov     rcx, cs:WPP_GLOBAL_Control
0x14003174a  cmp     rcx, r12
0x14003174d  jz      short loc_140031783
0x14003174f  test    [rcx+1Ch], r14b
  ... truncated ...
```
