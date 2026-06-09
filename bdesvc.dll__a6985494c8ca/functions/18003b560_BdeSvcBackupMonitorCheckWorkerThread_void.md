# BdeSvcBackupMonitorCheckWorkerThread(void *)

- ea: `0x18003b560`
- end: `0x18003c274`
- name: `?BdeSvcBackupMonitorCheckWorkerThread@@YAIPEAX@Z`
- size: `3348`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180001b6c`
- `0x180001d50`
- `0x180001fe8`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x18001a508`
- `0x18001c6c8`
- `0x180020430`
- `0x180021d18`
- `0x180022008`
- `0x180022a1c`
- `0x180026190`
- `0x18002ff00`
- `0x180030984`
- `0x180033618`
- `0x180033a24`
- `0x180034070`
- `0x180034d28`
- `0x18003b560`
- `0x180043e5c`
- `0x180044408`
- `0x18006a26c`
- `0x18006a594`
- `0x18006fc78`
- `0x180070378`
- `0x180070958`
- `0x180070f40`
- `0x180071170`
- `0x1800714cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b818`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b818`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003b701`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003b701`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c1f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c1f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003b6a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003b6a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003b68e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003b68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b84d`
- `FVEAPI!FveSelectBestRecoveryPasswordByBackupInformation` at `0x18003bc23`
- `FVEAPI!FveSelectBestRecoveryPasswordByBackupInformation` at `0x18003bc23`
- `FVEAPI!FveOpenVolumeW` at `0x18003ba63`
- `FVEAPI!FveOpenVolumeW` at `0x18003ba63`
- `FVEAPI!FveGetStatus` at `0x18003ba95`
- `FVEAPI!FveGetStatus` at `0x18003ba95`
- `FVEAPI!FveCloseVolume` at `0x18003c1d7`
- `FVEAPI!FveCloseVolume` at `0x18003c1d7`
- `WTSAPI32!WTSQueryUserToken` at `0x18003b838`
- `WTSAPI32!WTSQueryUserToken` at `0x18003b838`

## pseudocode

```c
__int64 __fastcall BdeSvcBackupMonitorCheckWorkerThread(void *a1)
{
  unsigned int v2; // edi
  bool v3; // r13
  bool v4; // si
  bool v5; // r12
  bool v6; // r15
  bool v7; // r14
  PVOID *v8; // rcx
  signed int IsMSAOrLocalAdminByToken; // ebx
  HANDLE v10; // rbx
  DWORD v11; // eax
  unsigned int v12; // r13d
  signed int LastError; // eax
  int v14; // r13d
  signed int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  char IsEnabled; // al
  void **p_phToken; // rcx
  int v20; // eax
  char v21; // al
  unsigned int v22; // r8d
  char v23; // al
  void **v24; // rcx
  char v25; // al
  void **v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r8
  BdeSvcWorkTracking *v30; // rcx
  bool v32; // [rsp+C0h] [rbp-80h] BYREF
  bool v33; // [rsp+C1h] [rbp-7Fh] BYREF
  bool v34; // [rsp+C2h] [rbp-7Eh] BYREF
  bool v35; // [rsp+C3h] [rbp-7Dh] BYREF
  unsigned __int8 v36; // [rsp+C4h] [rbp-7Ch] BYREF
  bool v37; // [rsp+C5h] [rbp-7Bh] BYREF
  bool v38; // [rsp+C6h] [rbp-7Ah] BYREF
  bool v39; // [rsp+C7h] [rbp-79h] BYREF
  char v40; // [rsp+C8h] [rbp-78h]
  unsigned int v41; // [rsp+CCh] [rbp-74h] BYREF
  unsigned int v42; // [rsp+D0h] [rbp-70h] BYREF
  unsigned int v43; // [rsp+D4h] [rbp-6Ch] BYREF
  int v44; // [rsp+D8h] [rbp-68h] BYREF
  unsigned int v45; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v46; // [rsp+E0h] [rbp-60h] BYREF
  ULONG SessionId[2]; // [rsp+E8h] [rbp-58h] BYREF
  int v48; // [rsp+F0h] [rbp-50h] BYREF
  BOOL v49; // [rsp+F4h] [rbp-4Ch] BYREF
  BOOL v50; // [rsp+F8h] [rbp-48h] BYREF
  BOOL v51; // [rsp+FCh] [rbp-44h] BYREF
  int v52; // [rsp+100h] [rbp-40h] BYREF
  BOOL v53; // [rsp+104h] [rbp-3Ch] BYREF
  BOOL v54; // [rsp+108h] [rbp-38h] BYREF
  unsigned int v55; // [rsp+10Ch] [rbp-34h] BYREF
  unsigned int v56; // [rsp+110h] [rbp-30h] BYREF
  unsigned int v57; // [rsp+114h] [rbp-2Ch] BYREF
  BOOL v58; // [rsp+118h] [rbp-28h] BYREF
  BOOL v59; // [rsp+11Ch] [rbp-24h] BYREF
  __int64 v60; // [rsp+120h] [rbp-20h] BYREF
  __int64 v61; // [rsp+128h] [rbp-18h] BYREF
  __int64 v62; // [rsp+130h] [rbp-10h] BYREF
  void *v63[3]; // [rsp+138h] [rbp-8h] BYREF
  void *v64; // [rsp+150h] [rbp+10h] BYREF
  _QWORD v65[2]; // [rsp+158h] [rbp+18h] BYREF
  _QWORD v66[2]; // [rsp+168h] [rbp+28h] BYREF
  void *phToken; // [rsp+178h] [rbp+38h] BYREF
  struct _GUID v68; // [rsp+180h] [rbp+40h] BYREF
  _DWORD v69[3]; // [rsp+190h] [rbp+50h] BYREF
  int v70; // [rsp+19Ch] [rbp+5Ch]
  __int64 v71; // [rsp+1C8h] [rbp+88h]
  _BYTE v72[528]; // [rsp+220h] [rbp+E0h] BYREF

  *(_QWORD *)SessionId = a1;
  v2 = 0;
  v44 = 0;
  v45 = 0;
  v3 = 0;
  v32 = 0;
  v38 = 0;
  v37 = 0;
  memset_0(v72, 0, 0x208u);
  v64 = (void *)-1LL;
  memset_0(v69, 0, 0x90u);
  v68 = 0;
  v35 = 0;
  v4 = 0;
  v36 = 0;
  v5 = 0;
  v34 = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v39 = 0;
  v40 = 0;
  v43 = 0;
  v42 = 0;
  phToken = 0;
  v46 = 0;
  v41 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    SessionId[0] = 0;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_(v8[2], 236, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v2 = 6302;
    IsMSAOrLocalAdminByToken = -2147024809;
    goto LABEL_151;
  }
  AcquireSRWLockShared(&g_srwlStopEvent);
  v10 = g_hStopEvent;
  ReleaseSRWLockShared(&g_srwlStopEvent);
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v2 = 6317;
    IsMSAOrLocalAdminByToken = -2147418113;
    goto LABEL_151;
  }
  v11 = WaitForSingleObjectEx(v10, 0x15F90u, 0);
  if ( v11 )
  {
    v12 = 4;
    if ( v11 != 258 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
      v2 = 6331;
      LastError = GetLastError();
      IsMSAOrLocalAdminByToken = LastError;
      if ( LastError > 0 )
        IsMSAOrLocalAdminByToken = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          240,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          (unsigned int)IsMSAOrLocalAdminByToken);
      goto LABEL_27;
    }
    EnterCriticalSection(&g_backupMonitoringLock);
    v40 = 1;
    SH<void *,SH_HANDLE>::Reset(&phToken);
    if ( !WTSQueryUserToken(SessionId[0], &phToken) )
    {
      v2 = 6339;
      v15 = GetLastError();
      IsMSAOrLocalAdminByToken = v15;
      if ( v15 > 0 )
        IsMSAOrLocalAdminByToken = (unsigned __int16)v15 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          241,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          SessionId[0],
          IsMSAOrLocalAdminByToken);
      goto LABEL_27;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      IsMSAOrLocalAdminByToken = FveBackupMonitor::IsMSAOrLocalAdminByToken(
                                   (const struct CNgscbToken *)&phToken,
                                   &v34,
                                   &v33);
      if ( IsMSAOrLocalAdminByToken < 0 )
      {
        v2 = 6348;
LABEL_41:
        v5 = v34;
        v6 = v33;
        goto LABEL_150;
      }
    }
    else
    {
      IsMSAOrLocalAdminByToken = CNgscbToken::GetFullToken((CNgscbToken *)&phToken, (struct CNgscbToken *)&v46);
      if ( IsMSAOrLocalAdminByToken < 0 )
      {
        v2 = 6351;
        goto LABEL_150;
      }
      IsMSAOrLocalAdminByToken = FveBackupMonitor::IsMSAOrLocalAdminByToken(
                                   (const struct CNgscbToken *)&v46,
                                   &v34,
                                   &v33);
      if ( IsMSAOrLocalAdminByToken < 0 )
      {
        v2 = 6352;
        goto LABEL_41;
      }
    }
    v5 = v34;
    v6 = v33;
    if ( v34 )
    {
      if ( !v33 )
      {
        v12 = 1;
LABEL_54:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::IsShowPromptEnabledForCurrentUser(
                                       (const struct CNgscbToken *)&phToken,
                                       &v35);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6363;
            goto LABEL_150;
          }
        }
        else
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::IsShowPromptEnabledForCurrentUser(
                                       (const struct CNgscbToken *)&v46,
                                       &v35);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6365;
            goto LABEL_150;
          }
        }
        IsMSAOrLocalAdminByToken = FveBackupMonitor::IsBackupMonitoringHasRanBefore(v12, &v36);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6367;
          goto LABEL_150;
        }
        IsMSAOrLocalAdminByToken = FveBackupMonitor::IsBitLockerPolicyToHideRPEnabled(&v39);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6368;
          goto LABEL_150;
        }
        if ( v39 )
        {
          v4 = 0;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_28;
          v17 = 243;
          goto LABEL_67;
        }
        IsMSAOrLocalAdminByToken = NgscbGetOSVolume(v72);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6380;
          goto LABEL_150;
        }
        IsMSAOrLocalAdminByToken = FveOpenVolumeW(v72, 0, &v64);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6381;
          goto LABEL_150;
        }
        v69[0] = 144;
        v69[1] = 10;
        IsMSAOrLocalAdminByToken = FveGetStatus(v64, v69);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6384;
          goto LABEL_150;
        }
        if ( (v70 & 1) == 0 )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
          p_phToken = &phToken;
          if ( !IsEnabled )
            p_phToken = (void **)&v46;
          FveBackupMonitor::DeleteOsvRecoveryPasswordBackupTypeRecords((const struct CNgscbToken *)p_phToken);
LABEL_104:
          v4 = 0;
          goto LABEL_28;
        }
        if ( (v71 & 8) != 0 )
        {
          v4 = 0;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_28;
          v17 = 244;
          goto LABEL_67;
        }
        v33 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          IsMSAOrLocalAdminByToken = CScopedImpersonation::ImpersonateUser(
                                       (CScopedImpersonation *)&v33,
                                       (const struct CNgscbToken *)&phToken);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6421;
LABEL_85:
            CScopedImpersonation::Revert((CScopedImpersonation *)&v33);
            goto LABEL_150;
          }
        }
        else
        {
          IsMSAOrLocalAdminByToken = CScopedImpersonation::ImpersonateUser(
                                       (CScopedImpersonation *)&v33,
                                       (const struct CNgscbToken *)&v46);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6423;
            goto LABEL_85;
          }
        }
        IsMSAOrLocalAdminByToken = FveDomain::CheckIsDeviceAzureJoined(&v32, &v37);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6425;
          goto LABEL_85;
        }
        CScopedImpersonation::Revert((CScopedImpersonation *)&v33);
        if ( v32 )
        {
          v4 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 245, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v32);
          goto LABEL_28;
        }
        IsMSAOrLocalAdminByToken = FveDomain::GetDomainInfo(&v38, 0);
        if ( IsMSAOrLocalAdminByToken < 0 )
        {
          v2 = 6435;
          goto LABEL_150;
        }
        if ( v38 )
        {
          v4 = 0;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_28;
          v17 = 246;
LABEL_67:
          WPP_SF_(v16[2], v17, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          goto LABEL_28;
        }
        v20 = FveSelectBestRecoveryPasswordByBackupInformation(v64, &v68);
        IsMSAOrLocalAdminByToken = v20;
        if ( v20 == 1168 )
        {
          IsMSAOrLocalAdminByToken = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          goto LABEL_104;
        }
        if ( v20 < 0 )
        {
          v2 = 6456;
          goto LABEL_150;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::GetOsvRecoveryPasswordBackupTypeMaskForUser(
                                       (const struct CNgscbToken *)&phToken,
                                       &v68,
                                       &v45);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6459;
            goto LABEL_150;
          }
        }
        else
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::GetOsvRecoveryPasswordBackupTypeMaskForUser(
                                       (const struct CNgscbToken *)&v46,
                                       &v68,
                                       &v45);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6462;
            goto LABEL_150;
          }
        }
        v7 = (v45 & 0x1E) != 0;
        v4 = (v45 & 0x1E) == 0;
        if ( v36 )
        {
          if ( (v45 & 0x1E) != 0 )
            goto LABEL_27;
          goto LABEL_131;
        }
        if ( (v45 & 0x1E) != 0 )
          goto LABEL_27;
        v4 = 0;
        if ( !v37 )
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::GetCountOfAdminsByAcctType(&v43, &v42);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6492;
            goto LABEL_150;
          }
          v4 = v5 && v43 > 1;
          if ( v6 )
          {
            if ( v42 > 1 )
            {
              v4 = 1;
LABEL_131:
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
              {
                IsMSAOrLocalAdminByToken = RevokeDismiss((const struct CNgscbToken *)&phToken, v64, &v41);
                if ( IsMSAOrLocalAdminByToken < 0 )
                {
                  v2 = 6517;
                  goto LABEL_150;
                }
              }
              else
              {
                IsMSAOrLocalAdminByToken = RevokeDismiss((const struct CNgscbToken *)&v46, v64, &v41);
                if ( IsMSAOrLocalAdminByToken < 0 )
                {
                  v2 = 6521;
                  goto LABEL_150;
                }
              }
              v2 = v41;
LABEL_28:
              if ( !v36 && (v6 || v5) )
              {
                v14 = FveBackupMonitor::RegisterStartOfBackupMonitoring(v12);
                v44 = v14;
              }
              else
              {
                v14 = v44;
              }
              if ( v35 )
              {
                if ( !v4 )
                {
                  v23 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
                  v24 = &phToken;
                  if ( !v23 )
                    v24 = (void **)&v46;
                  IsMSAOrLocalAdminByToken = FveBackupMonitor::ShowPromptForCurrentUser(
                                               (const struct CNgscbToken *)v24,
                                               0);
                }
              }
              else if ( v4 )
              {
                v25 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
                v26 = &phToken;
                if ( !v25 )
                  v26 = (void **)&v46;
                IsMSAOrLocalAdminByToken = FveBackupMonitor::ShowPromptForCurrentUser(
                                             (const struct CNgscbToken *)v26,
                                             1u);
                v65[0] = 0;
                memset(v63, 0, sizeof(v63));
                v66[1] = v66;
                v66[0] = v66;
                v65[1] = FVE_OP_BACKUP_SHOW_PROMPT_SET;
                FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v63, (struct _FVEAPI_EVENT_DATA_COLLECTION *)v65);
                FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v63);
              }
              if ( v14 < 0 && IsMSAOrLocalAdminByToken >= 0 )
                IsMSAOrLocalAdminByToken = v14;
              goto LABEL_150;
            }
            v4 = 0;
          }
          else if ( v4 )
          {
            goto LABEL_131;
          }
        }
        v21 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl);
        v22 = v5 ? 2 : 16;
        if ( v21 )
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::SetOsvRecoveryPasswordBackupType(
                                       (const struct CNgscbToken *)&phToken,
                                       &v68,
                                       v22);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6503;
            goto LABEL_150;
          }
        }
        else
        {
          IsMSAOrLocalAdminByToken = FveBackupMonitor::SetOsvRecoveryPasswordBackupType(
                                       (const struct CNgscbToken *)&v46,
                                       &v68,
                                       v22);
          if ( IsMSAOrLocalAdminByToken < 0 )
          {
            v2 = 6507;
            goto LABEL_150;
          }
        }
        goto LABEL_27;
      }
    }
    else if ( !v33 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_27:
      if ( IsMSAOrLocalAdminByToken >= 0 )
        goto LABEL_28;
LABEL_150:
      v3 = v32;
      goto LABEL_151;
    }
    v12 = 2;
    goto LABEL_54;
  }
  IsMSAOrLocalAdminByToken = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_151:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_18009A2D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A2D8, 0x400000000000LL) )
    {
      v60 = 0x1000000;
      v45 = 1;
      v41 = SessionId[0];
      v58 = v2;
      v59 = IsMSAOrLocalAdminByToken;
      v61 = v71;
      v48 = v70;
      v49 = v7;
      v50 = v4;
      v51 = v35;
      v52 = v36;
      v53 = v37;
      v54 = v38;
      v55 = v3;
      v56 = v6;
      v57 = v5;
      SessionId[0] = v39;
      v62 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        1,
        (int)&dword_18008C85C,
        v27,
        (__int64)&v62,
        (__int64)SessionId,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v61,
        (__int64)&v44,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v45,
        (__int64)&v60);
    }
  }
  else if ( (unsigned int)dword_18009A2D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A2D8, 0x400000000000LL) )
  {
    v62 = 0x1000000;
    v57 = v42;
    v56 = v43;
    v55 = v2;
    v54 = IsMSAOrLocalAdminByToken;
    v53 = v44;
    v61 = v71;
    v52 = v70;
    v51 = v7;
    v50 = v4;
    v49 = v35;
    v48 = v36;
    v59 = v37;
    v58 = v38;
    v45 = v3;
    v43 = v6;
    v42 = v5;
    v41 = v39;
    v60 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v28,
      (int)&dword_18008C6FC,
      v29,
      (__int64)&v60,
      (__int64)&v41,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v45,
      (__int64)&v58,
      (__int64)&v59,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v50,
      (__int64)&v51,
      (__int64)&v52,
      (__int64)&v61,
      (__int64)&v53,
      (__int64)&v54,
      (__int64)&v55,
      (__int64)&v56,
      (__int64)&v57,
      (__int64)SessionId,
      (__int64)&v62);
  }
  v30 = (BdeSvcWorkTracking *)v64;
  if ( v64 != (void *)-1LL )
  {
    FveCloseVolume(v64);
    v64 = (void *)-1LL;
  }
  if ( v40 )
    LeaveCriticalSection(&g_backupMonitoringLock);
  BdeSvcWorkTracking::FinishWorkImpl(v30);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      248,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      (unsigned int)IsMSAOrLocalAdminByToken);
  SH<void *,SH_HANDLE>::Reset(&v46);
  SH<void *,SH_HANDLE>::Reset(&phToken);
  return (unsigned int)IsMSAOrLocalAdminByToken;
}

```

## disassembly

```asm
0x18003b560  push    rbp
0x18003b562  push    rbx
0x18003b563  push    rsi
0x18003b564  push    rdi
0x18003b565  push    r12
0x18003b567  push    r13
0x18003b569  push    r14
0x18003b56b  push    r15
0x18003b56d  lea     rbp, [rsp-308h]
0x18003b575  sub     rsp, 448h
0x18003b57c  mov     rax, cs:__security_cookie
0x18003b583  xor     rax, rsp
0x18003b586  mov     [rbp+340h+var_50], rax
0x18003b58d  mov     rbx, rcx
0x18003b590  mov     qword ptr [rbp+340h+SessionId], rcx
0x18003b594  xor     edi, edi
0x18003b596  mov     [rbp+340h+var_3A8], edi
0x18003b599  mov     [rbp+340h+var_3A4], edi
0x18003b59c  mov     r13b, dil
0x18003b59f  mov     [rbp+340h+var_3C0], dil
0x18003b5a3  mov     [rbp+340h+var_3BA], dil
0x18003b5a7  mov     [rbp+340h+var_3BB], dil
0x18003b5ab  xor     edx, edx; Val
0x18003b5ad  mov     r8d, 208h; Size
0x18003b5b3  lea     rcx, [rbp+340h+var_260]; void *
0x18003b5ba  call    memset_0
0x18003b5bf  mov     [rbp+340h+var_330], 0FFFFFFFFFFFFFFFFh
0x18003b5c7  xor     edx, edx; Val
0x18003b5c9  mov     r8d, 90h; Size
0x18003b5cf  lea     rcx, [rbp+340h+var_2F0]; void *
0x18003b5d3  call    memset_0
0x18003b5d8  xorps   xmm0, xmm0
0x18003b5db  movups  xmmword ptr [rbp+340h+var_300.Data1], xmm0
0x18003b5df  mov     [rbp+340h+var_3BD], dil
0x18003b5e3  mov     sil, dil
0x18003b5e6  mov     [rbp+340h+var_3BC], dil
0x18003b5ea  mov     r12b, dil
0x18003b5ed  mov     [rbp+340h+var_3BE], dil
0x18003b5f1  mov     r15b, dil
0x18003b5f4  mov     [rbp+340h+var_3BF], dil
0x18003b5f8  mov     r14b, dil
0x18003b5fb  mov     [rbp+340h+var_3B9], dil
0x18003b5ff  mov     [rbp+340h+var_3B8], dil
0x18003b603  mov     [rbp+340h+var_3AC], edi
0x18003b606  mov     [rbp+340h+var_3B0], edi
0x18003b609  mov     [rbp+340h+phToken], rdi
0x18003b60d  mov     [rbp+340h+var_3A0], rdi
0x18003b611  mov     [rbp+340h+var_3B4], edi
0x18003b614  lea     rax, WPP_GLOBAL_Control
0x18003b61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b622  cmp     rcx, rax
0x18003b625  jz      short loc_18003B650
0x18003b627  test    byte ptr [rcx+1Ch], 20h
0x18003b62b  jz      short loc_18003B650
0x18003b62d  mov     edx, 0EBh
0x18003b632  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b639  mov     rcx, [rcx+10h]
0x18003b63d  call    WPP_SF_
0x18003b642  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b649  lea     rax, WPP_GLOBAL_Control
0x18003b650  test    rbx, rbx
0x18003b653  jnz     short loc_18003B687
0x18003b655  mov     [rbp+340h+SessionId], ebx
0x18003b658  cmp     rcx, rax
0x18003b65b  jz      short loc_18003B678
0x18003b65d  test    byte ptr [rcx+1Ch], 8
0x18003b661  jz      short loc_18003B678
0x18003b663  mov     edx, 0ECh
0x18003b668  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b66f  mov     rcx, [rcx+10h]
0x18003b673  call    WPP_SF_
0x18003b678  mov     edi, 189Eh
0x18003b67d  mov     ebx, 80070057h
0x18003b682  jmp     loc_18003BEA4
0x18003b687  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003b68e  call    cs:__imp_AcquireSRWLockShared
0x18003b695  nop     dword ptr [rax+rax+00h]
0x18003b69a  mov     rbx, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x18003b6a1  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003b6a8  call    cs:__imp_ReleaseSRWLockShared
0x18003b6af  nop     dword ptr [rax+rax+00h]
0x18003b6b4  test    rbx, rbx
0x18003b6b7  jnz     short loc_18003B6F6
0x18003b6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6c0  lea     rdx, WPP_GLOBAL_Control
0x18003b6c7  cmp     rcx, rdx
0x18003b6ca  jz      short loc_18003B6E7
0x18003b6cc  test    byte ptr [rcx+1Ch], 8
0x18003b6d0  jz      short loc_18003B6E7
0x18003b6d2  mov     edx, 0EDh
0x18003b6d7  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b6de  mov     rcx, [rcx+10h]
0x18003b6e2  call    WPP_SF_
0x18003b6e7  mov     edi, 18ADh
0x18003b6ec  mov     ebx, 8000FFFFh
0x18003b6f1  jmp     loc_18003BEA4
0x18003b6f6  xor     r8d, r8d; bAlertable
0x18003b6f9  mov     edx, 15F90h; dwMilliseconds
0x18003b6fe  mov     rcx, rbx; hHandle
0x18003b701  call    cs:__imp_WaitForSingleObjectEx
0x18003b708  nop     dword ptr [rax+rax+00h]
0x18003b70d  test    eax, eax
0x18003b70f  jnz     short loc_18003B74E
0x18003b711  xor     ebx, ebx
0x18003b713  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b71a  lea     rdx, WPP_GLOBAL_Control
0x18003b721  cmp     rcx, rdx
0x18003b724  jz      loc_18003BEA4
0x18003b72a  test    byte ptr [rcx+1Ch], 8
0x18003b72e  jz      loc_18003BEA4
0x18003b734  mov     edx, 0EEh
0x18003b739  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b740  mov     rcx, [rcx+10h]
0x18003b744  call    WPP_SF_
0x18003b749  jmp     loc_18003BEA4
0x18003b74e  mov     r13d, 4
0x18003b754  cmp     eax, 102h
0x18003b759  jz      loc_18003B811
0x18003b75f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b766  lea     rdx, WPP_GLOBAL_Control
0x18003b76d  cmp     rcx, rdx
0x18003b770  jz      short loc_18003B78D
0x18003b772  test    byte ptr [rcx+1Ch], 2
0x18003b776  jz      short loc_18003B78D
0x18003b778  mov     edx, 0EFh
0x18003b77d  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b784  mov     rcx, [rcx+10h]
0x18003b788  call    WPP_SF_
0x18003b78d  mov     edi, 18BBh
0x18003b792  call    cs:__imp_GetLastError
0x18003b799  nop     dword ptr [rax+rax+00h]
0x18003b79e  mov     ebx, eax
0x18003b7a0  test    eax, eax
0x18003b7a2  jle     short loc_18003B7AD
0x18003b7a4  movzx   ebx, ax
0x18003b7a7  or      ebx, 80070000h
0x18003b7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7b4  lea     rax, WPP_GLOBAL_Control
0x18003b7bb  cmp     rcx, rax
0x18003b7be  jz      short loc_18003B7DE
0x18003b7c0  test    byte ptr [rcx+1Ch], 40h
0x18003b7c4  jz      short loc_18003B7DE
0x18003b7c6  mov     edx, 0F0h
0x18003b7cb  mov     r9d, ebx
0x18003b7ce  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b7d5  mov     rcx, [rcx+10h]
0x18003b7d9  call    WPP_SF_d
0x18003b7de  test    ebx, ebx
0x18003b7e0  js      loc_18003BEA0
0x18003b7e6  cmp     [rbp+340h+var_3BC], 0
0x18003b7ea  jnz     loc_18003BDF1
0x18003b7f0  test    r15b, r15b
0x18003b7f3  jnz     short loc_18003B7FE
0x18003b7f5  test    r12b, r12b
0x18003b7f8  jz      loc_18003BDF1
0x18003b7fe  mov     ecx, r13d
0x18003b801  call    ?RegisterStartOfBackupMonitoring@FveBackupMonitor@@SAJW4_BACKUP_MONITOR_TYPE@@@Z; FveBackupMonitor::RegisterStartOfBackupMonitoring(_BACKUP_MONITOR_TYPE)
0x18003b806  mov     r13d, eax
0x18003b809  mov     [rbp+340h+var_3A8], eax
0x18003b80c  jmp     loc_18003BDF5
0x18003b811  lea     rcx, ?g_backupMonitoringLock@@3VCAutoCS@@A; lpCriticalSection
0x18003b818  call    cs:__imp_EnterCriticalSection
0x18003b81f  nop     dword ptr [rax+rax+00h]
0x18003b824  mov     [rbp+340h+var_3B8], 1
0x18003b828  lea     rcx, [rbp+340h+phToken]
0x18003b82c  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18003b831  lea     rdx, [rbp+340h+phToken]; phToken
0x18003b835  mov     ecx, [rbp+340h+SessionId]; SessionId
0x18003b838  call    cs:__imp_WTSQueryUserToken
0x18003b83f  nop     dword ptr [rax+rax+00h]
0x18003b844  test    eax, eax
0x18003b846  jnz     short loc_18003B8AB
0x18003b848  mov     edi, 18C3h
0x18003b84d  call    cs:__imp_GetLastError
0x18003b854  nop     dword ptr [rax+rax+00h]
0x18003b859  mov     ebx, eax
0x18003b85b  test    eax, eax
0x18003b85d  jle     short loc_18003B868
0x18003b85f  movzx   ebx, ax
0x18003b862  or      ebx, 80070000h
0x18003b868  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b86f  lea     rax, WPP_GLOBAL_Control
0x18003b876  cmp     rcx, rax
0x18003b879  jz      loc_18003B7DE
0x18003b87f  test    byte ptr [rcx+1Ch], 2
0x18003b883  jz      loc_18003B7DE
0x18003b889  mov     edx, 0F1h
0x18003b88e  mov     dword ptr [rsp+480h+var_460], ebx
0x18003b892  mov     r9d, [rbp+340h+SessionId]
0x18003b896  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b89d  mov     rcx, [rcx+10h]
0x18003b8a1  call    WPP_SF_DD
0x18003b8a6  jmp     loc_18003B7DE
0x18003b8ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003b8b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003b8b7  lea     rcx, [rbp+340h+phToken]; this
0x18003b8bb  test    al, al
0x18003b8bd  jz      short loc_18003B8E4
0x18003b8bf  lea     r8, [rbp+340h+var_3BF]; bool *
0x18003b8c3  lea     rdx, [rbp+340h+var_3BE]; bool *
0x18003b8c7  call    ?IsMSAOrLocalAdminByToken@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N1@Z; FveBackupMonitor::IsMSAOrLocalAdminByToken(CNgscbToken const *,bool *,bool *)
0x18003b8cc  mov     ebx, eax
0x18003b8ce  test    eax, eax
0x18003b8d0  jns     short loc_18003B91B
0x18003b8d2  mov     edi, 18CCh
0x18003b8d7  mov     r12b, [rbp+340h+var_3BE]
0x18003b8db  mov     r15b, [rbp+340h+var_3BF]
0x18003b8df  jmp     loc_18003BEA0
0x18003b8e4  lea     rdx, [rbp+340h+var_3A0]; struct CNgscbToken *
0x18003b8e8  call    ?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z; CNgscbToken::GetFullToken(CNgscbToken &)
0x18003b8ed  mov     ebx, eax
0x18003b8ef  test    eax, eax
0x18003b8f1  jns     short loc_18003B8FD
0x18003b8f3  mov     edi, 18CFh
0x18003b8f8  jmp     loc_18003BEA0
0x18003b8fd  lea     r8, [rbp+340h+var_3BF]; bool *
0x18003b901  lea     rdx, [rbp+340h+var_3BE]; bool *
0x18003b905  lea     rcx, [rbp+340h+var_3A0]; this
0x18003b909  call    ?IsMSAOrLocalAdminByToken@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N1@Z; FveBackupMonitor::IsMSAOrLocalAdminByToken(CNgscbToken const *,bool *,bool *)
0x18003b90e  mov     ebx, eax
0x18003b910  test    eax, eax
0x18003b912  jns     short loc_18003B91B
0x18003b914  mov     edi, 18D0h
0x18003b919  jmp     short loc_18003B8D7
0x18003b91b  mov     r12b, [rbp+340h+var_3BE]
0x18003b91f  mov     r15b, [rbp+340h+var_3BF]
0x18003b923  test    r12b, r12b
0x18003b926  jnz     short loc_18003B968
0x18003b928  test    r15b, r15b
0x18003b92b  jnz     short loc_18003B96D
0x18003b92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b934  lea     rax, WPP_GLOBAL_Control
0x18003b93b  cmp     rcx, rax
0x18003b93e  jz      loc_18003B7DE
0x18003b944  test    byte ptr [rcx+1Ch], 8
0x18003b948  jz      loc_18003B7DE
0x18003b94e  mov     edx, 0F2h
0x18003b953  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003b95a  mov     rcx, [rcx+10h]
0x18003b95e  call    WPP_SF_
0x18003b963  jmp     loc_18003B7DE
0x18003b968  test    r15b, r15b
0x18003b96b  jz      short loc_18003B975
0x18003b96d  mov     r13d, 2
0x18003b973  jmp     short loc_18003B97B
0x18003b975  mov     r13d, 1
0x18003b97b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003b982  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003b987  lea     rdx, [rbp+340h+var_3BD]; bool *
0x18003b98b  test    al, al
0x18003b98d  jz      short loc_18003B9A8
0x18003b98f  lea     rcx, [rbp+340h+phToken]; struct CNgscbToken *
0x18003b993  call    ?IsShowPromptEnabledForCurrentUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N@Z; FveBackupMonitor::IsShowPromptEnabledForCurrentUser(CNgscbToken const *,bool *)
0x18003b998  mov     ebx, eax
0x18003b99a  test    eax, eax
0x18003b99c  jns     short loc_18003B9C1
0x18003b99e  mov     edi, 18DBh
0x18003b9a3  jmp     loc_18003BEA0
0x18003b9a8  lea     rcx, [rbp+340h+var_3A0]; struct CNgscbToken *
0x18003b9ac  call    ?IsShowPromptEnabledForCurrentUser@FveBackupMonitor@@SAJPEBVCNgscbToken@@PEA_N@Z; FveBackupMonitor::IsShowPromptEnabledForCurrentUser(CNgscbToken const *,bool *)
0x18003b9b1  mov     ebx, eax
0x18003b9b3  test    eax, eax
0x18003b9b5  jns     short loc_18003B9C1
0x18003b9b7  mov     edi, 18DDh
0x18003b9bc  jmp     loc_18003BEA0
0x18003b9c1  lea     rdx, [rbp+340h+var_3BC]
0x18003b9c5  mov     ecx, r13d
0x18003b9c8  call    ?IsBackupMonitoringHasRanBefore@FveBackupMonitor@@SAJW4_BACKUP_MONITOR_TYPE@@PEA_N@Z; FveBackupMonitor::IsBackupMonitoringHasRanBefore(_BACKUP_MONITOR_TYPE,bool *)
0x18003b9cd  mov     ebx, eax
0x18003b9cf  test    eax, eax
0x18003b9d1  jns     short loc_18003B9DD
0x18003b9d3  mov     edi, 18DFh
0x18003b9d8  jmp     loc_18003BEA0
0x18003b9dd  lea     rcx, [rbp+340h+var_3B9]; bool *
0x18003b9e1  call    ?IsBitLockerPolicyToHideRPEnabled@FveBackupMonitor@@SAJPEA_N@Z; FveBackupMonitor::IsBitLockerPolicyToHideRPEnabled(bool *)
0x18003b9e6  mov     ebx, eax
0x18003b9e8  test    eax, eax
0x18003b9ea  jns     short loc_18003B9F6
0x18003b9ec  mov     edi, 18E0h
0x18003b9f1  jmp     loc_18003BEA0
0x18003b9f6  cmp     [rbp+340h+var_3B9], 0
0x18003b9fa  jz      short loc_18003BA3A
0x18003b9fc  xor     sil, sil
0x18003b9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ba06  lea     rax, WPP_GLOBAL_Control
0x18003ba0d  cmp     rcx, rax
0x18003ba10  jz      loc_18003B7E6
0x18003ba16  test    byte ptr [rcx+1Ch], 8
0x18003ba1a  jz      loc_18003B7E6
0x18003ba20  mov     edx, 0F3h
0x18003ba25  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003ba2c  mov     rcx, [rcx+10h]
0x18003ba30  call    WPP_SF_
0x18003ba35  jmp     loc_18003B7E6
0x18003ba3a  lea     rcx, [rbp+340h+var_260]
0x18003ba41  call    NgscbGetOSVolume
0x18003ba46  mov     ebx, eax
0x18003ba48  test    eax, eax
0x18003ba4a  jns     short loc_18003BA56
0x18003ba4c  mov     edi, 18ECh
  ... truncated ...
```
