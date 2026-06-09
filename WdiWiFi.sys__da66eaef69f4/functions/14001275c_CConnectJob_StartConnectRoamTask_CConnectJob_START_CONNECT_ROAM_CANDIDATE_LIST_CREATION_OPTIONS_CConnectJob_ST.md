# CConnectJob::StartConnectRoamTask(CConnectJob::_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS,CConnectJob::_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS,_WDI_ASSOC_STATUS *)

- ea: `0x14001275c`
- end: `0x140012ff9`
- name: `?StartConnectRoamTask@CConnectJob@@AEAAHW4_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS@1@W4_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS@1@PEAW4_WDI_ASSOC_STATUS@@@Z`
- size: `2205`
- prototype: `__int64 __fastcall(CConnectJob *__hidden this, enum CConnectJob::_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS, enum CConnectJob::_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS, enum _WDI_ASSOC_STATUS *)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140013160`
- `0x140014828`

## callees

- `0x1400100f8`
- `0x1400101c8`
- `0x1400122e0`
- `0x1400125b8`
- `0x14001275c`
- `0x140013000`
- `0x1400147e8`
- `0x140015dd8`
- `0x140017388`
- `0x14001d764`
- `0x14001d9a4`
- `0x140021280`
- `0x140023ae0`
- `0x1400243b4`
- `0x1400253f4`
- `0x140026f48`
- `0x1400297a0`
- `0x14002aa28`
- `0x1400622d0`
- `0x1400da680`

## pseudocode

```c
__int64 __fastcall CConnectJob::StartConnectRoamTask(
        CConnectJob *this,
        enum CConnectJob::_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS a2,
        enum CConnectJob::_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS a3,
        enum _WDI_ASSOC_STATUS *a4)
{
  CAdapter *m_pAdapter; // r10
  unsigned __int16 m_PortId; // r9
  unsigned int i; // ecx
  CPort *v11; // rsi
  struct CPortPropertyCache *PortPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // r13d
  unsigned __int8 *v14; // rdx
  __int64 *v15; // r8
  CPropertyCache *v16; // rax
  int v17; // edx
  int v18; // r8d
  CAdapterPropertyCache *v19; // rax
  unsigned int v20; // edi
  unsigned int v21; // eax
  unsigned __int8 *m_pConnectParametersTlvBuffer; // rcx
  unsigned int v23; // eax
  char v24; // r14
  struct CPort *PortFromPortId; // rax
  int v26; // edx
  int v27; // r8d
  unsigned int *p_m_ConnectParametersTlvLength; // rax
  unsigned int RoamTaskTlv; // eax
  int v30; // r9d
  unsigned int m_TempBSSCandidateCount; // ecx
  char v33; // al
  unsigned int j; // edi
  _ROAM_TRACELOGGING_DATA *m_pRoamTraceLoggingData; // rax
  struct CPortPropertyCache *v36; // rax
  int v37; // eax
  int v38; // edx
  int v39; // r8d
  struct CPortPropertyCache *v40; // rax
  int v41; // eax
  int v42; // edx
  int v43; // r8d
  struct CPortPropertyCache *v44; // rax
  unsigned int started; // eax
  CBSSEntry *v46; // r10
  unsigned __int64 m_ProbeResponseTime; // r9
  int v48; // [rsp+20h] [rbp-98h]
  unsigned int m_ActivityId; // [rsp+30h] [rbp-88h]
  __int64 v50; // [rsp+38h] [rbp-80h]

  m_pAdapter = this->m_pAdapter;
  m_PortId = this->m_PortId;
  for ( i = 0; i < 5; ++i )
  {
    v11 = m_pAdapter->m_pPortList[i];
    if ( v11 && v11->m_WfcPortId == m_PortId )
      goto LABEL_5;
  }
  v11 = 0;
LABEL_5:
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(PortPropertyCache, 0x84u, 0);
  v14 = &WPP_RECORDER_INITIALIZED;
  v15 = WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      (unsigned int)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      286,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId);
    v14 = &WPP_RECORDER_INITIALIZED;
  }
  if ( v11->m_pRoamTraceLoggingData )
    v11->m_pRoamTraceLoggingData->connectRoamTaskStartTime = MEMORY[0xFFFFF78000000014];
  *a4 = WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED;
  if ( this->m_IsCancelled )
  {
    v20 = -1073741823;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v20;
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      (_DWORD)v15,
      287,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      -1073741823);
    goto LABEL_27;
  }
  v16 = (CPropertyCache *)((__int64 (__fastcall *)(IPropertyCacheDirectory *, unsigned __int8 *, __int64 *))this->m_pAdapter->GetAdapterPropertyCache)(
                            &this->m_pAdapter->IPropertyCacheDirectory,
                            &WPP_RECORDER_INITIALIZED,
                            v15);
  if ( CPropertyCache::GetPropertyBooleanOrDefault(v16, 0x2Du, 0)
    || (v19 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory),
        CPropertyCache::GetPropertyBooleanOrDefault(v19, 0x2Eu, 0)) )
  {
    v20 = -1071439870;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v20;
    v30 = 288;
    LODWORD(v50) = -1071439870;
    goto LABEL_25;
  }
  v18 = (_DWORD)this + 596;
  v20 = 0;
  if ( !this->m_AssocNotificationRegistrationToken )
  {
    v21 = NotificationManager::RegisterForNotifications(
            &this->m_pAdapter->m_NotificationManager,
            WiFiIndicationAssociationResult,
            0,
            this->m_PortId,
            (struct INotifyDeviceIndicationCallback *)((unsigned __int64)&this->INotifyDeviceIndicationCallback
                                                     & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
            &this->m_AssocNotificationRegistrationToken);
    v20 = v21;
    if ( v21 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v20;
      v30 = 289;
      LODWORD(v50) = v21;
      m_ActivityId = this->m_ActivityId;
      goto LABEL_26;
    }
  }
  m_pConnectParametersTlvBuffer = this->m_pConnectParametersTlvBuffer;
  if ( m_pConnectParametersTlvBuffer )
  {
    operator delete(m_pConnectParametersTlvBuffer);
    this->m_pConnectParametersTlvBuffer = 0;
    this->m_ConnectParametersTlvLength = 0;
  }
  if ( a2 == START_CONNECT_ROAM_RECREATE_CANDIDATE_LIST )
  {
    v23 = CConnectJob::PickCandidates(this, &this->m_ConnectionProfile);
    v20 = v23;
    if ( v23 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return v20;
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        v18,
        290,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId,
        v23);
      goto LABEL_27;
    }
  }
  if ( !this->m_TempBSSCandidateCount && a3 != START_CONNECT_ROAM_CONTINUE_IF_NO_CANDIDATE_FOUND )
  {
    *a4 = WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED;
    goto LABEL_27;
  }
  v24 = 0;
  *a4 = WDI_ASSOC_STATUS_SUCCESS;
  if ( (this->m_RoamConfigFlags & 4) != 0
    && (v24 = 1,
        PortFromPortId = CAdapter::GetPortFromPortId(this->m_pAdapter, this->m_PortId),
        !PortFromPortId->m_pPeerList->FindPeerByAssociationState(
           PortFromPortId->m_pPeerList,
           dot11_assoc_state_auth_assoc)) )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v26,
        v27,
        291,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        (char)this,
        this->m_ActivityId);
    }
    v24 = 0;
    p_m_ConnectParametersTlvLength = &this->m_ConnectParametersTlvLength;
  }
  else
  {
    p_m_ConnectParametersTlvLength = &this->m_ConnectParametersTlvLength;
    if ( v24 )
    {
      RoamTaskTlv = CConnectJob::GenerateRoamTaskTlv(
                      this,
                      &this->m_ConnectParametersTlvLength,
                      &this->m_pConnectParametersTlvBuffer);
      v20 = RoamTaskTlv;
      if ( RoamTaskTlv )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v20;
        v30 = 292;
        goto LABEL_24;
      }
LABEL_45:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        m_TempBSSCandidateCount = this->m_TempBSSCandidateCount;
        v33 = 3;
        LOBYTE(v17) = 4;
        if ( m_TempBSSCandidateCount < 3 )
          v33 = this->m_TempBSSCandidateCount;
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          v18,
          294,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
          (char)this,
          this->m_ActivityId,
          m_TempBSSCandidateCount,
          v33);
      }
      for ( j = 0; j < this->m_TempBSSCandidateCount; ++j )
      {
        if ( j >= 3 )
          break;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v46 = this->m_TempBSSCandidateList[j];
          m_ProbeResponseTime = v46->m_ProbeResponseTime;
          if ( m_ProbeResponseTime <= v46->m_BeaconTime )
            m_ProbeResponseTime = v46->m_BeaconTime;
          WPP_RECORDER_SF_qDdd_MAC_dddd(
            WPP_GLOBAL_Control->DeviceExtension,
            (MEMORY[0xFFFFF78000000014] - m_ProbeResponseTime) / 0x2710,
            MEMORY[0xFFFFF78000000014] - m_ProbeResponseTime,
            m_ProbeResponseTime,
            v48,
            (char)this,
            this->m_ActivityId,
            j,
            v46->m_CachedRank,
            (__int64)v46->m_BssID,
            v46->m_SignalInfo.LinkQuality,
            v46->m_BssChannelInfo.BandId,
            v46->m_BssChannelInfo.Channel,
            (MEMORY[0xFFFFF78000000014] - m_ProbeResponseTime) / 0x2710);
        }
      }
      RoamTaskTlv = Task::Initialize(
                      &this->m_ConnectTask,
                      &this->m_pAdapter->m_NotificationManager,
                      &this->m_pAdapter->m_CommandScheduler,
                      &this->m_pAdapter->m_EventQueue);
      v20 = RoamTaskTlv;
      if ( RoamTaskTlv )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v20;
        v30 = 296;
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v17) = 5;
          LODWORD(v50) = 0;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v17,
            v18,
            62,
            (__int64)WPP_13843484fb6a395abd563b849973c7a7_Traceguids,
            (_BYTE)this + 32,
            this->m_ConnectTask.m_ActivityId,
            v50);
        }
        RoamTaskTlv = DeviceCommand::Initialize(
                        &this->m_ConnectTask.m_TaskDeviceCommand,
                        this->m_PortId,
                        v24 != 0 ? 100 : 6,
                        this->m_ConnectParametersTlvLength,
                        this->m_pConnectParametersTlvBuffer);
        v20 = RoamTaskTlv;
        if ( !RoamTaskTlv )
        {
          m_pRoamTraceLoggingData = v11->m_pRoamTraceLoggingData;
          if ( m_pRoamTraceLoggingData )
          {
            m_pRoamTraceLoggingData->taskOccured = 1;
            v11->m_pRoamTraceLoggingData->associationStatusCode = WDI_ASSOC_STATUS_CANDIDATE_LIST_EXHAUSTED;
          }
          v36 = COidJobBase::GetPortPropertyCache(this);
          v37 = CPropertyCache::SetPropertyBoolean(v36, 0x51u, 0);
          if ( v37 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v50) = v37;
            LOBYTE(v38) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v38,
              v39,
              299,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId,
              v50);
          }
          v40 = COidJobBase::GetPortPropertyCache(this);
          v41 = CPropertyCache::SetPropertyULong(v40, 0x53u, 0xFFFFu);
          if ( v41 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v50) = v41;
            LOBYTE(v42) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v42,
              v43,
              300,
              (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
              (char)this,
              this->m_ActivityId,
              v50);
          }
          v44 = COidJobBase::GetPortPropertyCache(this);
          CPropertyCache::SetPropertyULong(v44, 0x84u, PropertyULongOrDefault + 1);
          started = CJobBase::StartTask(this, &this->m_ConnectTask);
          v20 = started;
          if ( !started )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 4;
              WPP_RECORDER_SF_qD(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                v18,
                302,
                (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
                (char)this,
                this->m_ActivityId);
            }
            this->m_ConnectState = WiFiConnectJobStateWaitingForConnectCompletion;
            goto LABEL_27;
          }
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return v20;
          LODWORD(v50) = started;
          v30 = 301;
          m_ActivityId = this->m_ActivityId;
          goto LABEL_26;
        }
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return v20;
        v30 = 298;
      }
      goto LABEL_24;
    }
  }
  RoamTaskTlv = CConnectJob::GenerateConnectTaskTlv(
                  this,
                  (this->m_RoamConfigFlags & 1) == 0,
                  p_m_ConnectParametersTlvLength,
                  &this->m_pConnectParametersTlvBuffer);
  v20 = RoamTaskTlv;
  if ( !RoamTaskTlv )
    goto LABEL_45;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return v20;
  v30 = 293;
LABEL_24:
  LODWORD(v50) = RoamTaskTlv;
LABEL_25:
  m_ActivityId = this->m_ActivityId;
LABEL_26:
  LOBYTE(v17) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v17,
    v18,
    v30,
    (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
    (char)this,
    m_ActivityId,
    v50);
LABEL_27:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v17) = 5;
    LODWORD(v50) = v20;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      v18,
      303,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      (char)this,
      this->m_ActivityId,
      v50);
  }
  return v20;
}

```

## disassembly

```asm
0x14001275c  push    rbx
0x14001275e  push    rbp
0x14001275f  push    rsi
0x140012760  push    rdi
0x140012761  push    r12
0x140012763  push    r13
0x140012765  push    r14
0x140012767  push    r15
0x140012769  sub     rsp, 78h
0x14001276d  mov     r10, [rcx+200h]
0x140012774  mov     rbp, r9
0x140012777  movzx   r9d, word ptr [rcx+34h]
0x14001277c  xor     r15d, r15d
0x14001277f  mov     rbx, rcx
0x140012782  mov     r12d, r8d
0x140012785  mov     ecx, r15d
0x140012788  mov     r14d, edx
0x14001278b  cmp     ecx, 5
0x14001278e  jnb     loc_140012E7B
0x140012794  mov     eax, ecx
0x140012796  mov     rsi, [r10+rax*8+1318h]
0x14001279e  test    rsi, rsi
0x1400127a1  jz      loc_140012A06
0x1400127a7  cmp     [rsi+64h], r9w
0x1400127ac  jnz     loc_140012A06
0x1400127b2  mov     rcx, rbx; this
0x1400127b5  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400127ba  xor     r8d, r8d; unsigned int
0x1400127bd  mov     edx, 84h; unsigned int
0x1400127c2  mov     rcx, rax; this
0x1400127c5  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400127ca  mov     r13d, eax
0x1400127cd  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400127d4  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400127db  lea     r8, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400127e2  jnz     loc_140012A35
0x1400127e8  mov     rax, 0FFFFF78000000014h
0x1400127f2  cmp     [rsi+48h], r15
0x1400127f6  jz      short loc_140012803
0x1400127f8  mov     rcx, [rax]
0x1400127fb  mov     rax, [rsi+48h]
0x1400127ff  mov     [rax+60h], rcx
0x140012803  mov     dword ptr [rbp+0], 6
0x14001280a  cmp     [rbx+23Ch], r15b
0x140012811  jnz     loc_140012E83
0x140012817  mov     rcx, [rbx+200h]
0x14001281e  add     rcx, 8
0x140012822  mov     rax, [rcx]
0x140012825  mov     rax, [rax+8]
0x140012829  call    _guard_dispatch_icall
0x14001282e  xor     r8d, r8d; unsigned __int8
0x140012831  mov     rcx, rax; this
0x140012834  lea     edx, [r8+2Dh]; unsigned int
0x140012838  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14001283d  test    al, al
0x14001283f  jnz     loc_140012E37
0x140012845  mov     rcx, [rbx+200h]
0x14001284c  add     rcx, 8
0x140012850  mov     rax, [rcx]
0x140012853  mov     rax, [rax+8]
0x140012857  call    _guard_dispatch_icall
0x14001285c  xor     r8d, r8d; unsigned __int8
0x14001285f  mov     rcx, rax; this
0x140012862  lea     edx, [r8+2Eh]; unsigned int
0x140012866  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14001286b  test    al, al
0x14001286d  jnz     loc_140012E37
0x140012873  lea     r8, [rbx+254h]
0x14001287a  mov     edi, r15d
0x14001287d  cmp     [r8], r15d
0x140012880  jnz     short loc_1400128C8
0x140012882  movzx   r9d, word ptr [rbx+34h]; unsigned __int16
0x140012887  lea     rcx, [rbx+228h]
0x14001288e  mov     [rsp+0B8h+var_90], r8; unsigned int *
0x140012893  mov     rax, rbx
0x140012896  neg     rax
0x140012899  sbb     rdx, rdx
0x14001289c  xor     r8d, r8d; unsigned int
0x14001289f  and     rdx, rcx
0x1400128a2  mov     rcx, [rbx+200h]
0x1400128a9  mov     [rsp+0B8h+var_98], rdx; struct INotifyDeviceIndicationCallback *
0x1400128ae  add     rcx, 460h; this
0x1400128b5  lea     edx, [r8+4Ch]; enum _WDI_INDICATION_TYPE
0x1400128b9  call    ?RegisterForNotifications@NotificationManager@@QEAAHW4_WDI_INDICATION_TYPE@@KGPEAVINotifyDeviceIndicationCallback@@PEAK@Z; NotificationManager::RegisterForNotifications(_WDI_INDICATION_TYPE,ulong,ushort,INotifyDeviceIndicationCallback *,ulong *)
0x1400128be  mov     edi, eax
0x1400128c0  test    eax, eax
0x1400128c2  jnz     loc_140012A0D
0x1400128c8  lea     r15, [rbx+468h]
0x1400128cf  mov     rcx, [r15]; void *
0x1400128d2  test    rcx, rcx
0x1400128d5  jnz     loc_140012EEF
0x1400128db  test    r14d, r14d
0x1400128de  jnz     short loc_1400128F9
0x1400128e0  lea     rdx, [rbx+3B8h]; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400128e7  mov     rcx, rbx; this
0x1400128ea  call    ?PickCandidates@CConnectJob@@AEAAHPEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectJob::PickCandidates(_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400128ef  mov     edi, eax
0x1400128f1  test    eax, eax
0x1400128f3  jnz     loc_140012D01
0x1400128f9  cmp     dword ptr [rbx+26Ch], 0
0x140012900  jbe     loc_140012AC3
0x140012906  xor     r14b, r14b
0x140012909  mov     dword ptr [rbp+0], 0
0x140012910  mov     eax, [rbx+260h]
0x140012916  test    al, 4
0x140012918  jz      short loc_14001294E
0x14001291a  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x14001291e  mov     r14b, 1
0x140012921  mov     rcx, [rbx+200h]; this
0x140012928  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x14001292d  mov     edx, 3
0x140012932  mov     rcx, [rax+398h]
0x140012939  mov     rax, [rcx]
0x14001293c  mov     rax, [rax+18h]
0x140012940  call    _guard_dispatch_icall
0x140012945  test    rax, rax
0x140012948  jz      loc_140012AEA
0x14001294e  lea     rax, [rbx+470h]
0x140012955  test    r14b, r14b
0x140012958  jz      loc_140012A7B
0x14001295e  mov     r8, r15; unsigned __int8 **
0x140012961  mov     rdx, rax; unsigned int *
0x140012964  mov     rcx, rbx; this
0x140012967  call    ?GenerateRoamTaskTlv@CConnectJob@@AEAAHPEAKPEAPEAE@Z; CConnectJob::GenerateRoamTaskTlv(ulong *,uchar * *)
0x14001296c  xor     r15d, r15d
0x14001296f  mov     edi, eax
0x140012971  test    eax, eax
0x140012973  jz      loc_140012B14
0x140012979  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140012980  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012987  jz      loc_140012A21
0x14001298d  mov     r9d, 124h
0x140012993  mov     dword ptr [rsp+0B8h+var_80], eax
0x140012997  mov     eax, [rbx+10h]
0x14001299a  mov     [rsp+0B8h+var_88], eax
0x14001299e  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x1400129a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129ac  mov     dl, 2
0x1400129ae  mov     [rsp+0B8h+var_90], rbx
0x1400129b3  mov     [rsp+0B8h+var_98], rsi
0x1400129b8  mov     rcx, [rcx+40h]
0x1400129bc  call    WPP_RECORDER_SF_qDD
0x1400129c1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400129c8  jz      short loc_140012A21
0x1400129ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129d1  cmp     byte ptr [rcx+29h], 5
0x1400129d5  jnb     short loc_1400129DE
0x1400129d7  cmp     [rcx+48h], r15w
0x1400129dc  jz      short loc_140012A21
0x1400129de  mov     eax, [rbx+10h]
0x1400129e1  mov     r9d, 12Fh
0x1400129e7  mov     rcx, [rcx+40h]
0x1400129eb  mov     dl, 5
0x1400129ed  mov     dword ptr [rsp+0B8h+var_80], edi
0x1400129f1  mov     [rsp+0B8h+var_88], eax
0x1400129f5  mov     [rsp+0B8h+var_90], rbx
0x1400129fa  mov     [rsp+0B8h+var_98], rsi
0x1400129ff  call    WPP_RECORDER_SF_qDD
0x140012a04  jmp     short loc_140012A21
0x140012a06  inc     ecx
0x140012a08  jmp     loc_14001278B
0x140012a0d  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140012a14  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012a1b  jnz     loc_140012ED9
0x140012a21  mov     eax, edi
0x140012a23  add     rsp, 78h
0x140012a27  pop     r15
0x140012a29  pop     r14
0x140012a2b  pop     r13
0x140012a2d  pop     r12
0x140012a2f  pop     rdi
0x140012a30  pop     rsi
0x140012a31  pop     rbp
0x140012a32  pop     rbx
0x140012a33  retn
0x140012a35  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a3c  cmp     byte ptr [rcx+29h], 5
0x140012a40  jnb     short loc_140012A4D
0x140012a42  cmp     [rcx+48h], r15w
0x140012a47  jz      loc_1400127E8
0x140012a4d  mov     eax, [rbx+10h]
0x140012a50  mov     r9d, 11Eh
0x140012a56  mov     rcx, [rcx+40h]
0x140012a5a  mov     dl, 5
0x140012a5c  mov     [rsp+0B8h+var_88], eax
0x140012a60  mov     [rsp+0B8h+var_90], rbx
0x140012a65  mov     [rsp+0B8h+var_98], r8
0x140012a6a  call    WPP_RECORDER_SF_qD
0x140012a6f  lea     rdx, WPP_RECORDER_INITIALIZED
0x140012a76  jmp     loc_1400127E8
0x140012a7b  lea     r12, WPP_RECORDER_INITIALIZED
0x140012a82  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140012a89  mov     dl, [rbx+260h]
0x140012a8f  mov     r9, r15; unsigned __int8 **
0x140012a92  not     dl
0x140012a94  mov     r8, rax; unsigned int *
0x140012a97  and     dl, 1; bool
0x140012a9a  mov     rcx, rbx; this
0x140012a9d  call    ?GenerateConnectTaskTlv@CConnectJob@@AEAAH_NPEAKPEAPEAE@Z; CConnectJob::GenerateConnectTaskTlv(bool,ulong *,uchar * *)
0x140012aa2  xor     r15d, r15d
0x140012aa5  mov     edi, eax
0x140012aa7  test    eax, eax
0x140012aa9  jz      short loc_140012B22
0x140012aab  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140012ab2  jz      loc_140012A21
0x140012ab8  mov     r9d, 125h
0x140012abe  jmp     loc_140012993
0x140012ac3  cmp     r12d, 1
0x140012ac7  jz      loc_140012906
0x140012acd  mov     dword ptr [rbp+0], 6
0x140012ad4  lea     r12, WPP_RECORDER_INITIALIZED
0x140012adb  xor     r15d, r15d
0x140012ade  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140012ae5  jmp     loc_1400129C1
0x140012aea  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140012af1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012af8  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140012aff  jnz     loc_140012CD3
0x140012b05  xor     r14b, r14b
0x140012b08  lea     rax, [rbx+470h]
0x140012b0f  jmp     loc_140012A89
0x140012b14  lea     r12, WPP_RECORDER_INITIALIZED
0x140012b1b  lea     rbp, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140012b22  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140012b29  jz      short loc_140012B6C
0x140012b2b  mov     ecx, [rbx+26Ch]
0x140012b31  mov     eax, 3
0x140012b36  cmp     ecx, eax
0x140012b38  mov     r9d, 126h
0x140012b3e  mov     dl, 4
0x140012b40  cmovb   eax, ecx
0x140012b43  mov     [rsp+0B8h+var_78], eax
0x140012b47  mov     eax, [rbx+10h]
0x140012b4a  mov     dword ptr [rsp+0B8h+var_80], ecx
0x140012b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b55  mov     [rsp+0B8h+var_88], eax
0x140012b59  mov     [rsp+0B8h+var_90], rbx
0x140012b5e  mov     [rsp+0B8h+var_98], rbp
0x140012b63  mov     rcx, [rcx+40h]
0x140012b67  call    WPP_RECORDER_SF_qDdd
0x140012b6c  mov     edi, r15d
0x140012b6f  cmp     [rbx+26Ch], r15d
0x140012b76  ja      loc_140012D51
0x140012b7c  mov     rdx, [rbx+200h]
0x140012b83  lea     rbp, [rbx+520h]
0x140012b8a  mov     rcx, rbp; this
0x140012b8d  lea     r9, [rdx+328h]; struct EventQueue *
0x140012b94  lea     r8, [rdx+490h]; struct DeviceCommandScheduler *
0x140012b9b  add     rdx, 460h; struct NotificationManager *
0x140012ba2  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x140012ba7  mov     edi, eax
0x140012ba9  test    eax, eax
0x140012bab  jnz     loc_140012E1F
0x140012bb1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140012bb8  jz      short loc_140012BD6
0x140012bba  mov     rcx, cs:WPP_GLOBAL_Control
0x140012bc1  cmp     byte ptr [rcx+29h], 5
0x140012bc5  jnb     loc_140012F0A
0x140012bcb  cmp     [rcx+48h], r15w
0x140012bd0  jnz     loc_140012F0A
0x140012bd6  mov     rax, [rbx+468h]
0x140012bdd  lea     rcx, [rbp+38h]; this
0x140012be1  mov     r9d, [rbx+470h]; unsigned int
0x140012be8  neg     r14b
0x140012beb  movzx   edx, word ptr [rbx+34h]; unsigned __int16
0x140012bef  sbb     r8d, r8d
0x140012bf2  mov     [rsp+0B8h+var_98], rax; unsigned __int8 *
0x140012bf7  and     r8d, 5Eh
0x140012bfb  add     r8d, 6; unsigned int
0x140012bff  call    ?Initialize@DeviceCommand@@QEAAHGKKPEAE@Z; DeviceCommand::Initialize(ushort,ulong,ulong,uchar *)
0x140012c04  mov     edi, eax
0x140012c06  test    eax, eax
0x140012c08  jnz     loc_140012E63
0x140012c0e  mov     rax, [rsi+48h]
0x140012c12  test    rax, rax
0x140012c15  jnz     loc_140012F3D
0x140012c1b  mov     rcx, rbx; this
0x140012c1e  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140012c23  xor     r8d, r8d; unsigned __int8
0x140012c26  mov     rcx, rax; this
0x140012c29  lea     edx, [r8+51h]; unsigned int
0x140012c2d  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x140012c32  test    eax, eax
0x140012c34  jnz     loc_140012F51
0x140012c3a  lea     rsi, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140012c41  mov     rcx, rbx; this
0x140012c44  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140012c49  mov     edx, 53h ; 'S'; unsigned int
0x140012c4e  mov     r8d, 0FFFFh; unsigned int
0x140012c54  mov     rcx, rax; this
0x140012c57  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140012c5c  test    eax, eax
0x140012c5e  jnz     loc_140012F97
0x140012c64  mov     rcx, rbx; this
0x140012c67  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140012c6c  lea     r8d, [r13+1]; unsigned int
0x140012c70  mov     edx, 84h; unsigned int
0x140012c75  mov     rcx, rax; this
0x140012c78  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140012c7d  mov     rdx, rbp; Task *
  ... truncated ...
```
