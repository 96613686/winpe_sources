# CConnectJob::OnJobStepCompleted(int,void *)

- ea: `0x140013160`
- end: `0x1400143d0`
- name: `?OnJobStepCompleted@CConnectJob@@UEAAXHPEAX@Z`
- size: `4720`
- prototype: `void __fastcall(CConnectJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400100f8`
- `0x1400101c8`
- `0x140010730`
- `0x1400122e0`
- `0x1400124f4`
- `0x14001275c`
- `0x140013000`
- `0x140013160`
- `0x1400143d8`
- `0x1400147e8`
- `0x140014828`
- `0x140015dd8`
- `0x140017388`
- `0x14001f3cc`
- `0x140021280`
- `0x1400218e8`
- `0x1400230fc`
- `0x140028f1c`
- `0x1400297a0`
- `0x14002aa28`
- `0x140030d54`
- `0x140046f74`
- `0x140048ce0`
- `0x14004ab18`
- `0x14005373c`
- `0x140062e1c`
- `0x14007058c`
- `0x140087370`
- `0x1400b67d0`
- `0x1400c29e0`
- `0x1400c2a98`
- `0x1400c51cc`

## pseudocode

```c
void __fastcall CConnectJob::OnJobStepCompleted(CConnectJob *this, int started, void *a3)
{
  CAdapter *m_pAdapter; // r8
  unsigned __int16 m_PortId; // dx
  char v7; // r12
  unsigned int v8; // ecx
  CPort *v9; // r13
  struct CPortPropertyCache *PortPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // ebx
  unsigned __int64 v12; // rdx
  __int64 *p_roamOccured; // r8
  int v14; // eax
  char v15; // r14
  char v16; // r15
  bool *p_m_IsCancelled; // rbx
  CPort *PortFromPortId; // rax
  int v19; // r9d
  struct CPortPropertyCache *v20; // rax
  bool *p_m_IsCriticalRoamToLEAlreadyAttempted; // rbx
  _ROAM_TRACELOGGING_DATA *m_pRoamTraceLoggingData; // rax
  int v23; // r9d
  struct CPortPropertyCache *v24; // rax
  PDEVICE_OBJECT v25; // rcx
  int v26; // r9d
  int v27; // eax
  bool v28; // bl
  int v29; // eax
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  enum _WDI_ROAM_CONFIGURATION_FLAGS RoamConfig; // eax
  enum _WFC_ROAM_CONNECT_TRIGGER v33; // edx
  int v34; // ebx
  unsigned int m_LastBSSListChangedCounter; // ecx
  unsigned int v36; // eax
  IActivityId *v37; // rbx
  int v38; // eax
  int v39; // r9d
  int v40; // edx
  int v41; // r8d
  int v42; // eax
  int v43; // edx
  int v44; // r8d
  int v45; // eax
  unsigned __int8 *p_HostFIPSModeEnabled; // rbx
  char v47; // [rsp+28h] [rbp-41h]
  char v48; // [rsp+28h] [rbp-41h]
  unsigned int v49; // [rsp+30h] [rbp-39h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-39h]
  __int64 v51; // [rsp+38h] [rbp-31h]
  enum _WDI_ASSOC_STATUS v52[4]; // [rsp+50h] [rbp-19h] BYREF
  struct _DOT11_SSID v53; // [rsp+60h] [rbp-9h] BYREF
  bool v54; // [rsp+E8h] [rbp+7Fh] BYREF

  m_pAdapter = this->m_pAdapter;
  m_PortId = this->m_PortId;
  v7 = 0;
  v8 = 0;
  v52[0] = WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED;
  while ( v8 < 5 )
  {
    v9 = m_pAdapter->m_pPortList[v8];
    if ( v9 && v9->m_WfcPortId == m_PortId )
      goto LABEL_5;
    ++v8;
  }
  v9 = 0;
LABEL_5:
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(PortPropertyCache, 0x84u, 0);
  v12 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
  p_roamOccured = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (unsigned int)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        110,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
      v12 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
      p_roamOccured = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (unsigned int)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        111,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        this->m_ConnectState,
        started);
      v12 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
    }
  }
  switch ( this->m_ConnectState )
  {
    case WiFiConnectJobStateWaitingForFipsEncapsulationUpdate:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          112,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( v9->m_pRoamTraceLoggingData )
        v9->m_pRoamTraceLoggingData->timeToFinishFipsEncapsulationOffloadUpdateMS = (MEMORY[0xFFFFF78000000014]
                                                                                   - v9->m_pRoamTraceLoggingData->connectJobStartTime)
                                                                                  / 0x2710;
      p_HostFIPSModeEnabled = &this->m_ConnectionProfile.HostFIPSModeEnabled;
      if ( !started )
        CPropertyCache::SetPropertyBoolean(&v9->m_PortPropertyCache, 0x55u, *p_HostFIPSModeEnabled);
      started = CConnectJob::StartFipsOffloadUpdate(this, *p_HostFIPSModeEnabled != 0);
      if ( !started )
        goto LABEL_170;
LABEL_209:
      v28 = 0;
      v54 = 0;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          113,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( v9->m_pRoamTraceLoggingData )
      {
        p_roamOccured = (__int64 *)&v9->m_pRoamTraceLoggingData->roamOccured;
        v12 = (MEMORY[0xFFFFF78000000014] - p_roamOccured[10]) / 0x2710uLL;
        p_roamOccured[16] = v12;
      }
      if ( !started )
        CPropertyCache::SetPropertyBoolean(
          &v9->m_PortPropertyCache,
          0x55u,
          this->m_ConnectionProfile.HostFIPSModeEnabled);
      if ( (this->m_RoamConfigFlags & 1) != 0 && !this->m_IsP2PConnect )
      {
        v27 = CConnectJob::StartSetPrivacyExemptionIfNecessary(this, &v54);
        v28 = v54;
        started = v27;
      }
      if ( !started && v28 )
        goto LABEL_170;
      goto LABEL_131;
    case WiFiConnectJobStateWaitingForFipsChecksumUpdate:
      goto LABEL_209;
    case WiFiConnectJobStateWaitingForPrivacyExemptionListSet:
LABEL_131:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          114,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( v9->m_pRoamTraceLoggingData )
        v9->m_pRoamTraceLoggingData->timeToFinishPrivacyExemptionListSetMS = (MEMORY[0xFFFFF78000000014]
                                                                            - v9->m_pRoamTraceLoggingData->connectJobStartTime)
                                                                           / 0x2710;
      v29 = CConnectJob::StartBssListUpdate(this);
      started = v29;
      if ( !v29 )
        goto LABEL_57;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_61;
      LODWORD(v51) = v29;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        115,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v51);
LABEL_58:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          116,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
LABEL_61:
      if ( v9->m_pRoamTraceLoggingData )
      {
        p_roamOccured = (__int64 *)&v9->m_pRoamTraceLoggingData->roamOccured;
        v12 = (MEMORY[0xFFFFF78000000014] - p_roamOccured[10]) / 0x2710uLL;
        p_roamOccured[19] = v12;
      }
      if ( this->m_pAdapter->m_lResetRecovery )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 2;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            (_DWORD)p_roamOccured,
            117,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId);
        }
        v15 = 0;
        v16 = 0;
        if ( !started )
          started = -1073676280;
      }
      else
      {
        if ( this->m_IsP2PConnect && this->m_IsRoam )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              118,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          v15 = 0;
        }
        else
        {
          v15 = 1;
        }
        v16 = 0;
        v7 = 1;
      }
      goto LABEL_24;
    case WiFiConnectJobStateWaitingForBSSListUpdate:
      goto LABEL_58;
    case WiFiConnectJobStateWaitingForScanJobCompletion:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 4;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          119,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( v9->m_pRoamTraceLoggingData )
        v9->m_pRoamTraceLoggingData->timeToFinishScanJobCompletionMS = (MEMORY[0xFFFFF78000000014]
                                                                      - v9->m_pRoamTraceLoggingData->connectJobStartTime)
                                                                     / 0x2710;
      v14 = CConnectJob::CompleteScanJob(this, started);
      started = v14;
      if ( !v14 )
      {
        CPort::CancelOpportunisticRoam(v9);
        v15 = 1;
        if ( this->m_IsP2PConnect && this->m_IsRoam )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              120,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
        }
        else
        {
          v7 = 1;
        }
        goto LABEL_23;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_57:
        v15 = 0;
LABEL_23:
        v16 = 0;
        goto LABEL_24;
      }
      v23 = 121;
LABEL_101:
      LOBYTE(v12) = 2;
      LODWORD(v51) = v14;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        v23,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v51);
      goto LABEL_57;
    case WiFiConnectJobStateWaitingForActionFrameComplete:
      v34 = this->m_IsP2PConnect ? 3 : 0;
      CConnectJob::CompleteSendResponseActionFrameJob(this, started);
      m_LastBSSListChangedCounter = CAdapter::GetBSSListManager(this->m_pAdapter, (enum _WFC_PORT_TYPE)(v34 + 1))->m_LastBSSListChangedCounter;
      v36 = this->m_LastBSSListChangedCounter;
      if ( v36 == m_LastBSSListChangedCounter )
      {
        v37 = &this->IActivityId;
      }
      else
      {
        v37 = &this->IActivityId;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 4;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            (_DWORD)p_roamOccured,
            122,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            v37->m_ActivityId,
            v36,
            m_LastBSSListChangedCounter);
        }
        v38 = CConnectJob::PickCandidates(this, &this->m_ConnectionProfile);
        started = v38;
        if ( v38 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v51) = v38;
            v39 = 123;
            m_ActivityId = v37->m_ActivityId;
            v48 = (char)this;
LABEL_168:
            LOBYTE(v12) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              v39,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              v48,
              m_ActivityId,
              v51);
            goto LABEL_170;
          }
          goto LABEL_170;
        }
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v37 = &this->IActivityId;
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_qDL(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          124,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          this->m_TempBSSCandidateCount);
      }
      if ( CConnectJob::CheckAndRequestPMKIDUpdate(this, this->m_TempBSSCandidateCount, this->m_TempBSSCandidateList) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v40) = 4;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v40,
            v41,
            125,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            v37->m_ActivityId);
        }
        v42 = CConnectJob::StartWaitForPMKIDList(this);
        started = v42;
        if ( !v42 )
        {
          this->m_ConnectState = WiFiConnectJobStateWaitingForPMKIDUpdate;
          CJobBase::SetPending(this);
          goto LABEL_170;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v51) = v42;
          LOBYTE(v43) = 2;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v43,
            v44,
            126,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            v37->m_ActivityId,
            v51);
        }
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
             && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v40) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v40,
          v41,
          127,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          v37->m_ActivityId);
      }
      v45 = CConnectJob::StartConnectRoamTask(
              this,
              START_CONNECT_ROAM_CANDIDATE_LIST_AVAILABLE,
              START_CONNECT_ROAM_STOP_IF_NO_CANDIDATES_FOUND,
              v52);
      started = v45;
      if ( v45 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_170;
        LODWORD(v51) = v45;
        v39 = 129;
        m_ActivityId = this->m_ActivityId;
        v48 = (char)this;
        goto LABEL_168;
      }
      if ( v52[0] )
      {
        v15 = 0;
        v7 = 1;
        v16 = 0;
        goto LABEL_24;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          128,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
LABEL_170:
      v15 = 0;
      v16 = 0;
      goto LABEL_24;
    case WiFiConnectJobStateWaitingForPMKIDUpdate:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          130,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( v9->m_pRoamTraceLoggingData )
        v9->m_pRoamTraceLoggingData->timeToFinishPMKIDUpdateMS = (MEMORY[0xFFFFF78000000014]
                                                                - v9->m_pRoamTraceLoggingData->connectJobStartTime)
                                                               / 0x2710;
      v14 = CConnectJob::StartConnectRoamTask(
              this,
              START_CONNECT_ROAM_RECREATE_CANDIDATE_LIST,
              START_CONNECT_ROAM_STOP_IF_NO_CANDIDATES_FOUND,
              v52);
      started = v14;
      if ( v14 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v23 = 132;
        goto LABEL_101;
      }
      if ( v52[0] )
      {
        v7 = 1;
        goto LABEL_57;
      }
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v25 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_57;
      v26 = 131;
      v49 = this->m_ActivityId;
      v47 = (char)this;
LABEL_154:
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_qD(
        v25->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        v26,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        v47,
        v49);
      goto LABEL_57;
  }
  if ( this->m_ConnectState != WiFiConnectJobStateWaitingForConnectCompletion )
    goto LABEL_170;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    LODWORD(v51) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      (_DWORD)p_roamOccured,
      133,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v51);
  }
  started = CConnectJob::CompleteConnectTask(this, started);
  v24 = COidJobBase::GetPortPropertyCache(this);
  CPropertyCache::SetPropertyULong(v24, 0x84u, PropertyULongOrDefault + 1);
  if ( this->m_NotifiedSuccessfulAssociation )
  {
    v16 = 1;
  }
  else
  {
    if ( !this->m_IsReconnectNeededDueTo11r )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        LODWORD(v51) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          135,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          v51);
      }
      if ( started == -1073676280 )
        goto LABEL_57;
      v7 = 1;
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_57;
      v25 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_57;
      v26 = 136;
      v49 = this->m_ActivityId;
      v47 = (char)this;
      goto LABEL_154;
    }
    if ( started == -1073676280 )
      goto LABEL_57;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        134,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    if ( this->m_IsBlockSSIDFor11rNeeded )
    {
      v30 = *(_OWORD *)&this->m_SSID.uSSIDLength;
      v31 = *(_OWORD *)&this->m_SSID.ucSSID[12];
      *(_DWORD *)&v53.ucSSID[28] = *(_DWORD *)&this->m_SSID.ucSSID[28];
      *(_OWORD *)&v53.uSSIDLength = v30;
      *(_OWORD *)&v53.ucSSID[12] = v31;
      CPort::UpdateSSIDBlockInfoFor11r(v9, &v53, (enum _WFC_BLOCKED_REASON)p_roamOccured);
    }
    v16 = 1;
    RoamConfig = CConnectHelpers::GetRoamConfig(WfcRoamConnectTriggerAssociationLoss);
    CPort::TriggerReconnect(v9, (enum _WDI_ASSOC_STATUS)(v33 + 10), v33, RoamConfig);
  }
  v15 = 0;
LABEL_24:
  p_m_IsCancelled = &this->m_IsCancelled;
  if ( !this->m_IsCancelled )
  {
    if ( v15 )
    {
      started = CConnectJob::CheckAndStartConnectProcess(this, v52);
      if ( started )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 4;
          LODWORD(v51) = started;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            (_DWORD)p_roamOccured,
            139,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId,
            v51);
        }
        v7 = 0;
      }
      else
      {
        if ( v52[0] )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v12) = 5;
            WPP_RECORDER_SF_qDL(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              138,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId,
              v52[0]);
          }
        }
        else
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v12) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              137,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          v7 = 0;
        }
        p_m_IsCancelled = &this->m_IsCancelled;
      }
    }
    if ( !*p_m_IsCancelled && v7 )
    {
      started = CConnectJob::CheckAndStartScanProcess(this, v52);
      if ( started )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 4;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            (_DWORD)p_roamOccured,
            142,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId,
            started,
            v52[0]);
        }
        if ( started == -1073741252
          && v52[0] == WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED
          && (this->m_RoamConfigFlags & 0x40) != 0 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              (_DWORD)p_roamOccured,
              143,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId);
          }
          PortFromPortId = CAdapter::GetPortFromPortId(this->m_pAdapter, this->m_PortId);
          CPort::NotifyRoamingAttemptsExhausted(PortFromPortId, this->m_OidRequestId);
          CConnectJob::CheckForNloMatchAndSendIndicationIfNecessary(this);
        }
      }
      else if ( v52[0] )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v12) = 5;
          WPP_RECORDER_SF_qDL(
            WPP_GLOBAL_Control->DeviceExtension,
            v12,
            (_DWORD)p_roamOccured,
            141,
            (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
            (char)this,
            this->m_ActivityId,
            v52[0]);
        }
      }
      else if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
             && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          (_DWORD)p_roamOccured,
          140,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId);
      }
    }
  }
  if ( !v15 && !v7 )
  {
LABEL_49:
    if ( !started )
      goto LABEL_50;
    goto LABEL_46;
  }
  if ( (this->m_RoamConfigFlags & 4) == 0 )
    goto LABEL_44;
  if ( started && started != -1073741252 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v19 = 147;
      LOBYTE(v12) = 4;
LABEL_89:
      LODWORD(v51) = started;
LABEL_90:
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        v19,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v51);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  if ( v52[0] != WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED )
  {
    if ( v52[0] && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v19 = 146;
      SLODWORD(v51) = v52[0];
      LOBYTE(v12) = 4;
      goto LABEL_90;
    }
    goto LABEL_44;
  }
  v20 = COidJobBase::GetPortPropertyCache(this);
  if ( !CPropertyCache::GetPropertyBooleanOrDefault(v20, 0x51u, 0) && (this->m_RoamConfigFlags & 0x10) == 0 )
    goto LABEL_44;
  p_m_IsCriticalRoamToLEAlreadyAttempted = &this->m_IsCriticalRoamToLEAlreadyAttempted;
  if ( this->m_IsCriticalRoamToLEAlreadyAttempted || this->m_IsDeferred )
    goto LABEL_44;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_84;
      p_m_IsCriticalRoamToLEAlreadyAttempted = &this->m_IsCriticalRoamToLEAlreadyAttempted;
    }
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      (_DWORD)p_roamOccured,
      144,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
  }
LABEL_84:
  m_pRoamTraceLoggingData = v9->m_pRoamTraceLoggingData;
  if ( m_pRoamTraceLoggingData )
    m_pRoamTraceLoggingData->roamDebugCode = WdiRoamDebugCodeNoBetterAPIHVRequestedRoam;
  *p_m_IsCriticalRoamToLEAlreadyAttempted = 1;
  started = CConnectJob::StartConnectRoamTask(
              this,
              START_CONNECT_ROAM_RECREATE_CANDIDATE_LIST,
              START_CONNECT_ROAM_CONTINUE_IF_NO_CANDIDATE_FOUND,
              v52);
  if ( started && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v19 = 145;
    LOBYTE(v12) = 2;
    goto LABEL_89;
  }
LABEL_44:
  if ( !v15 && !v7 )
    goto LABEL_49;
  if ( !started )
  {
    if ( v52[0] == WDI_ASSOC_STATUS_SUCCESS )
    {
LABEL_50:
      if ( !v16 )
        goto LABEL_51;
      goto LABEL_46;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        (_DWORD)p_roamOccured,
        148,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    started = -1073741823;
  }
LABEL_46:
  CConnectJob::FinishJob(this, started);
LABEL_51:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    LODWORD(v51) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      (_DWORD)p_roamOccured,
      149,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v51);
  }
}

```

## disassembly

```asm
0x140013160  mov     [rsp-8+arg_10], rbx
0x140013165  push    rbp
0x140013166  push    rsi
0x140013167  push    rdi
0x140013168  push    r12
0x14001316a  push    r13
0x14001316c  push    r14
0x14001316e  push    r15
0x140013170  lea     rbp, [rsp-27h]
0x140013175  sub     rsp, 90h
0x14001317c  mov     r8, [rcx+200h]
0x140013183  xor     r14d, r14d
0x140013186  mov     esi, edx
0x140013188  mov     [rbp+57h+arg_0], r14b
0x14001318c  movzx   edx, word ptr [rcx+34h]
0x140013190  mov     rdi, rcx
0x140013193  mov     [rbp+57h+arg_8], r14b
0x140013197  mov     r12b, r14b
0x14001319a  mov     ecx, r14d
0x14001319d  mov     [rbp+57h+var_70], 6
0x1400131a4  cmp     ecx, 5
0x1400131a7  jnb     loc_140013922
0x1400131ad  mov     eax, ecx
0x1400131af  mov     r13, [r8+rax*8+1318h]
0x1400131b7  test    r13, r13
0x1400131ba  jz      loc_1400133FF
0x1400131c0  cmp     [r13+64h], dx
0x1400131c5  jnz     loc_1400133FF
0x1400131cb  mov     rcx, rdi; this
0x1400131ce  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400131d3  xor     r8d, r8d; unsigned int
0x1400131d6  mov     edx, 84h; unsigned int
0x1400131db  mov     rcx, rax; this
0x1400131de  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400131e3  mov     ebx, eax
0x1400131e5  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400131ec  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400131f3  lea     r8, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400131fa  jz      short loc_14001323D
0x1400131fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140013203  cmp     byte ptr [rcx+29h], 5
0x140013207  jnb     loc_140013A8D
0x14001320d  cmp     [rcx+48h], r14w
0x140013212  jnz     loc_140013A8D
0x140013218  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x14001321f  jz      short loc_14001323D
0x140013221  mov     rcx, cs:WPP_GLOBAL_Control
0x140013228  cmp     byte ptr [rcx+29h], 5
0x14001322c  jnb     loc_140013AC2
0x140013232  cmp     [rcx+48h], r14w
0x140013237  jnz     loc_140013AC2
0x14001323d  mov     ecx, [rdi+238h]
0x140013243  mov     r15, 0FFFFF78000000014h
0x14001324d  mov     r14, 346DC5D63886594Bh
0x140013257  sub     ecx, 1
0x14001325a  jz      loc_140013FDA
0x140013260  sub     ecx, 1
0x140013263  jz      loc_14001407E
0x140013269  sub     ecx, 1
0x14001326c  jz      loc_1400139A5
0x140013272  sub     ecx, 1
0x140013275  jz      loc_1400134B7
0x14001327b  sub     ecx, 1
0x14001327e  jnz     loc_140013721
0x140013284  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x14001328b  jnz     loc_14001347E
0x140013291  xor     ebx, ebx
0x140013293  cmp     [r13+48h], rbx
0x140013297  jz      short loc_1400132B5
0x140013299  mov     rcx, [r15]
0x14001329c  mov     rax, r14
0x14001329f  mov     r8, [r13+48h]
0x1400132a3  sub     rcx, [r8+50h]
0x1400132a7  mul     rcx
0x1400132aa  shr     rdx, 0Bh
0x1400132ae  mov     [r8+0A0h], rdx
0x1400132b5  mov     edx, esi; int
0x1400132b7  mov     rcx, rdi; this
0x1400132ba  call    ?CompleteScanJob@CConnectJob@@AEAAHH@Z; CConnectJob::CompleteScanJob(int)
0x1400132bf  mov     esi, eax
0x1400132c1  test    eax, eax
0x1400132c3  jnz     loc_140013462
0x1400132c9  mov     rcx, r13; this
0x1400132cc  call    ?CancelOpportunisticRoam@CPort@@QEAAXXZ; CPort::CancelOpportunisticRoam(void)
0x1400132d1  mov     r14b, 1
0x1400132d4  cmp     [rdi+13C8h], bl
0x1400132da  jnz     loc_140013F7A
0x1400132e0  mov     r12b, r14b
0x1400132e3  mov     r15b, bl
0x1400132e6  lea     rbx, [rdi+23Ch]
0x1400132ed  cmp     byte ptr [rbx], 0
0x1400132f0  jnz     loc_14001345B
0x1400132f6  test    r14b, r14b
0x1400132f9  jz      short loc_14001334E
0x1400132fb  lea     rdx, [rbp+57h+var_70]; enum _WDI_ASSOC_STATUS *
0x1400132ff  mov     rcx, rdi; this
0x140013302  call    ?CheckAndStartConnectProcess@CConnectJob@@AEAAHPEAW4_WDI_ASSOC_STATUS@@@Z; CConnectJob::CheckAndStartConnectProcess(_WDI_ASSOC_STATUS *)
0x140013307  mov     esi, eax
0x140013309  test    eax, eax
0x14001330b  jnz     loc_140014255
0x140013311  xor     ebx, ebx
0x140013313  cmp     [rbp+57h+var_70], ebx
0x140013316  jz      loc_1400137E5
0x14001331c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140013323  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001332a  jz      short loc_140013347
0x14001332c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013333  cmp     byte ptr [rcx+29h], 5
0x140013337  jnb     loc_140014220
0x14001333d  cmp     [rcx+48h], bx
0x140013341  jnz     loc_140014220
0x140013347  lea     rbx, [rdi+23Ch]
0x14001334e  cmp     byte ptr [rbx], 0
0x140013351  jnz     loc_14001345B
0x140013357  xor     ebx, ebx
0x140013359  test    r12b, r12b
0x14001335c  jz      short loc_1400133A8
0x14001335e  lea     rdx, [rbp+57h+var_70]; enum _WDI_ASSOC_STATUS *
0x140013362  mov     rcx, rdi; this
0x140013365  call    ?CheckAndStartScanProcess@CConnectJob@@AEAAHPEAW4_WDI_ASSOC_STATUS@@@Z; CConnectJob::CheckAndStartScanProcess(_WDI_ASSOC_STATUS *)
0x14001336a  mov     esi, eax
0x14001336c  test    eax, eax
0x14001336e  jnz     loc_140013534
0x140013374  cmp     [rbp+57h+var_70], ebx
0x140013377  jnz     loc_1400142CF
0x14001337d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140013384  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001338b  jz      short loc_1400133AF
0x14001338d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013394  cmp     byte ptr [rcx+29h], 5
0x140013398  jnb     loc_1400142A1
0x14001339e  cmp     [rcx+48h], bx
0x1400133a2  jnz     loc_1400142A1
0x1400133a8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400133af  test    r14b, r14b
0x1400133b2  jz      short loc_140013406
0x1400133b4  mov     eax, [rdi+260h]
0x1400133ba  test    al, 4
0x1400133bc  jz      short loc_1400133DB
0x1400133be  test    esi, esi
0x1400133c0  jnz     loc_14001360F
0x1400133c6  cmp     [rbp+57h+var_70], 6
0x1400133ca  jz      loc_14001363C
0x1400133d0  mov     eax, [rbp+57h+var_70]
0x1400133d3  test    eax, eax
0x1400133d5  jnz     loc_14001436B
0x1400133db  lea     r13, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400133e2  test    r14b, r14b
0x1400133e5  jz      loc_140014390
0x1400133eb  test    esi, esi
0x1400133ed  jz      loc_14001392A
0x1400133f3  mov     edx, esi; int
0x1400133f5  mov     rcx, rdi; this
0x1400133f8  call    ?FinishJob@CConnectJob@@AEAAXH@Z; CConnectJob::FinishJob(int)
0x1400133fd  jmp     short loc_140013414
0x1400133ff  inc     ecx
0x140013401  jmp     loc_1400131A4
0x140013406  test    r12b, r12b
0x140013409  jnz     short loc_1400133B4
0x14001340b  test    esi, esi
0x14001340d  jnz     short loc_1400133F3
0x14001340f  test    r15b, r15b
0x140013412  jnz     short loc_1400133F3
0x140013414  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001341b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013422  jz      short loc_14001343F
0x140013424  mov     rcx, cs:WPP_GLOBAL_Control
0x14001342b  cmp     byte ptr [rcx+29h], 5
0x14001342f  jnb     loc_14001439E
0x140013435  cmp     [rcx+48h], bx
0x140013439  jnz     loc_14001439E
0x14001343f  mov     rbx, [rsp+0C0h+arg_10]
0x140013447  add     rsp, 90h
0x14001344e  pop     r15
0x140013450  pop     r14
0x140013452  pop     r13
0x140013454  pop     r12
0x140013456  pop     rdi
0x140013457  pop     rsi
0x140013458  pop     rbp
0x140013459  retn
0x14001345b  xor     ebx, ebx
0x14001345d  jmp     loc_1400133A8
0x140013462  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140013469  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140013470  jnz     loc_140013FCF
0x140013476  mov     r14b, bl
0x140013479  jmp     loc_1400132E3
0x14001347e  mov     eax, [rdi+10h]
0x140013481  mov     r9d, 77h ; 'w'
0x140013487  mov     rcx, cs:WPP_GLOBAL_Control
0x14001348e  mov     dl, 4
0x140013490  mov     dword ptr [rsp+0C0h+var_88], esi
0x140013494  mov     [rsp+0C0h+var_90], eax
0x140013498  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14001349f  mov     [rsp+0C0h+var_98], rdi
0x1400134a4  mov     rcx, [rcx+40h]
0x1400134a8  mov     [rsp+0C0h+var_A0], rax
0x1400134ad  call    WPP_RECORDER_SF_qDD
0x1400134b2  jmp     loc_140013291
0x1400134b7  xor     ebx, ebx
0x1400134b9  lea     r9, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400134c0  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400134c7  jz      short loc_1400134E4
0x1400134c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400134d0  cmp     byte ptr [rcx+29h], 5
0x1400134d4  jnb     loc_14001411B
0x1400134da  cmp     [rcx+48h], bx
0x1400134de  jnz     loc_14001411B
0x1400134e4  cmp     [r13+48h], rbx
0x1400134e8  jz      short loc_140013506
0x1400134ea  mov     rcx, [r15]
0x1400134ed  mov     rax, r14
0x1400134f0  mov     r8, [r13+48h]
0x1400134f4  sub     rcx, [r8+50h]
0x1400134f8  mul     rcx
0x1400134fb  shr     rdx, 0Bh
0x1400134ff  mov     [r8+98h], rdx
0x140013506  mov     rax, [rdi+200h]
0x14001350d  cmp     [rax+15C8h], ebx
0x140013513  jnz     loc_140014154
0x140013519  cmp     [rdi+13C8h], bl
0x14001351f  jnz     loc_1400141A5
0x140013525  mov     r14b, 1
0x140013528  mov     r15b, [rbp+57h+arg_0]
0x14001352c  mov     r12b, 1
0x14001352f  jmp     loc_1400132E6
0x140013534  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001353b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140013542  jz      short loc_140013586
0x140013544  mov     eax, [rbp+57h+var_70]
0x140013547  mov     r9d, 8Eh
0x14001354d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013554  mov     dl, 4
0x140013556  mov     [rsp+0C0h+var_80], eax
0x14001355a  mov     eax, [rdi+10h]
0x14001355d  mov     dword ptr [rsp+0C0h+var_88], esi
0x140013561  mov     rcx, [rcx+40h]
0x140013565  mov     [rsp+0C0h+var_90], eax
0x140013569  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140013570  mov     [rsp+0C0h+var_98], rdi
0x140013575  mov     [rsp+0C0h+var_A0], rax
0x14001357a  call    WPP_RECORDER_SF_qDdd
0x14001357f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140013586  cmp     esi, 0C000023Ch
0x14001358c  jnz     loc_1400133AF
0x140013592  cmp     [rbp+57h+var_70], 6
0x140013596  jnz     loc_1400133AF
0x14001359c  mov     eax, [rdi+260h]
0x1400135a2  test    al, 40h
0x1400135a4  jz      loc_1400133AF
0x1400135aa  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x1400135b1  jz      short loc_1400135E3
0x1400135b3  mov     eax, [rdi+10h]
0x1400135b6  mov     r9d, 8Fh
0x1400135bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135c3  mov     dl, 4
0x1400135c5  mov     [rsp+0C0h+var_90], eax
0x1400135c9  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400135d0  mov     [rsp+0C0h+var_98], rdi
0x1400135d5  mov     [rsp+0C0h+var_A0], rax
0x1400135da  mov     rcx, [rcx+40h]
0x1400135de  call    WPP_RECORDER_SF_qD
0x1400135e3  movzx   edx, word ptr [rdi+34h]; unsigned __int16
0x1400135e7  mov     rcx, [rdi+200h]; this
0x1400135ee  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400135f3  mov     rdx, [rdi+1CA0h]; void *
0x1400135fa  mov     rcx, rax; this
0x1400135fd  call    ?NotifyRoamingAttemptsExhausted@CPort@@QEAAXPEAX@Z; CPort::NotifyRoamingAttemptsExhausted(void *)
0x140013602  mov     rcx, rdi; this
0x140013605  call    ?CheckForNloMatchAndSendIndicationIfNecessary@CConnectJob@@AEAAXXZ; CConnectJob::CheckForNloMatchAndSendIndicationIfNecessary(void)
0x14001360a  jmp     loc_1400133A8
0x14001360f  cmp     esi, 0C000023Ch
0x140013615  jz      loc_1400133C6
0x14001361b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx; __annotation("TMF:",
0x140013622  lea     r13, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140013629  jz      loc_1400133E2
0x14001362f  mov     r9d, 93h
0x140013635  mov     dl, 4
0x140013637  jmp     loc_1400136F7
0x14001363c  mov     rcx, rdi; this
0x14001363f  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140013644  xor     r8d, r8d; unsigned __int8
0x140013647  mov     rcx, rax; this
0x14001364a  lea     edx, [r8+51h]; unsigned int
0x14001364e  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x140013653  test    al, al
0x140013655  jz      loc_140013A7A
0x14001365b  lea     rbx, [rdi+1D81h]
0x140013662  xor     eax, eax
0x140013664  cmp     [rbx], al
0x140013666  jnz     loc_140014364
0x14001366c  cmp     [rdi+1DA8h], al
0x140013672  jnz     loc_140014364
0x140013678  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001367f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140013686  jz      short loc_1400136A3
0x140013688  mov     rcx, cs:WPP_GLOBAL_Control
0x14001368f  cmp     byte ptr [rcx+29h], 5
0x140013693  jnb     loc_140014336
  ... truncated ...
```
