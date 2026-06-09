# CConnectJob::OnJobStepCompleted(int,void *)

- ea: `0x1400adae0`
- end: `0x1400aeba9`
- name: `?OnJobStepCompleted@CConnectJob@@UEAAXHPEAX@Z`
- size: `4297`
- prototype: `void __fastcall(CConnectJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x14000688c`
- `0x140018270`
- `0x14001c0d0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002aaec`
- `0x14002ac4c`
- `0x14002bd34`
- `0x14002ed50`
- `0x14002ef48`
- `0x14005f8bc`
- `0x140063d7c`
- `0x140071720`
- `0x140084958`
- `0x14008bd8c`
- `0x14008c820`
- `0x1400a22d4`
- `0x1400a2644`
- `0x1400a2b64`
- `0x1400a3c2c`
- `0x1400a42c8`
- `0x1400a4434`
- `0x1400a4740`
- `0x1400a77e8`
- `0x1400a9d4c`
- `0x1400adae0`
- `0x1400b0128`
- `0x1400b204c`
- `0x1400b4c3c`
- `0x1400b511c`
- `0x1400b6268`
- `0x1400b8560`

## pseudocode

```c
void __fastcall CConnectJob::OnJobStepCompleted(CConnectJob *this, int started, void *a3)
{
  _QWORD *v4; // r14
  char v6; // r12
  struct CPort *PortFromPortId; // r13
  CPropertyCache *PortPropertyCache; // rax
  unsigned int PropertyULongOrDefault; // ebx
  unsigned __int64 v10; // rdx
  const struct _DOT11_SSID *v11; // r8
  CPropertyCache *v12; // rax
  char v13; // r15
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  unsigned int RoamConfig; // eax
  unsigned int v17; // edx
  char v18; // r14
  _BYTE *v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rbx
  int v22; // eax
  int v23; // r9d
  int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // r9
  int v27; // ecx
  int v28; // eax
  int *v29; // rbx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // edx
  int v34; // r8d
  int v35; // edx
  int v36; // r8d
  int v37; // eax
  int v38; // r9d
  const char *v39; // rdx
  const char *v40; // rdx
  __int64 v41; // rbx
  __int64 v42; // rbx
  __int64 v43; // rbx
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rbx
  CPort *v47; // rax
  int v48; // r9d
  CPropertyCache *v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int v52; // eax
  int v53; // [rsp+20h] [rbp-60h]
  __int64 v54; // [rsp+38h] [rbp-48h]
  __int64 v55; // [rsp+38h] [rbp-48h]
  _OWORD v56[2]; // [rsp+50h] [rbp-30h] BYREF
  int v57; // [rsp+70h] [rbp-10h]
  int v58; // [rsp+D8h] [rbp+58h] BYREF

  v58 = 6;
  v4 = (_QWORD *)((char *)this + 536);
  v6 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(PortPropertyCache, 0x86u, 0);
  v10 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
  v11 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_10;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    goto LABEL_5;
  if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v4 = (_QWORD *)((char *)this + 536);
LABEL_5:
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      (unsigned int)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      163,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v10 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
    v11 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      (unsigned int)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      164,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      *((_DWORD *)this + 148),
      started);
    v10 = (unsigned __int64)&WPP_RECORDER_INITIALIZED;
  }
LABEL_10:
  switch ( *((_DWORD *)this + 148) )
  {
    case 3:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v10) = 5;
        LODWORD(v54) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          165,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54);
      }
      v43 = *((_QWORD *)PortFromPortId + 9);
      if ( v43 )
      {
        v44 = *(_QWORD *)(v43 + 80);
        *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 144LL) = (CSystem::get_CurrentTime() - v44) / 0x2710;
      }
      started = CConnectJob::StartBssListUpdate(this);
      if ( !started )
        goto LABEL_72;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_133;
      LODWORD(v54) = started;
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        (_DWORD)v11,
        166,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v54);
      break;
    case 4:
      break;
    case 5:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        LODWORD(v54) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          170,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54);
      }
      v41 = *((_QWORD *)PortFromPortId + 9);
      if ( v41 )
      {
        v42 = *(_QWORD *)(v41 + 80);
        *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 160LL) = (CSystem::get_CurrentTime() - v42) / 0x2710;
      }
      started = CConnectJob::CompleteScanJob(this, started);
      if ( !started )
      {
        CPort::CancelOpportunisticRoam(PortFromPortId);
        v18 = 1;
        if ( *((_BYTE *)this + 2784) && *((_BYTE *)this + 5518) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v10) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              171,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
        }
        else
        {
          v6 = 1;
        }
        goto LABEL_40;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        LODWORD(v54) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          172,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54);
      }
LABEL_39:
      v18 = 0;
LABEL_40:
      v13 = 0;
      goto LABEL_41;
    case 6:
      v24 = *((_BYTE *)this + 2784) != 0 ? 3 : 0;
      CConnectJob::CompleteSendResponseActionFrameJob(this, started);
      v27 = *(_DWORD *)(CAdapter::GetBSSListManager(*v4, (unsigned int)(v24 + 1), v25, v26) + 96);
      v28 = *((_DWORD *)this + 162);
      if ( v28 == v27 )
      {
        v29 = (int *)((char *)this + 16);
      }
      else
      {
        v29 = (int *)((char *)this + 16);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 4;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            173,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *v29,
            v28,
            v27);
        }
        v30 = CConnectJob::PickCandidates(this, (CConnectJob *)((char *)this + 976));
        started = v30;
        if ( v30 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v54) = v30;
            v23 = 174;
            v22 = *v29;
            goto LABEL_71;
          }
LABEL_72:
          v18 = 0;
          v13 = 0;
          goto LABEL_41;
        }
      }
      if ( *((_BYTE *)this + 5568) )
      {
        *((_BYTE *)this + 5568) = 0;
        v31 = 0;
        *((_BYTE *)this + 5521) = 1;
        v32 = 1;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          v29 = (int *)((char *)this + 16);
          LODWORD(v54) = *((_DWORD *)this + 161);
          LOBYTE(v10) = 5;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            175,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v54);
        }
        if ( CConnectJob::CheckAndRequestPMKIDUpdate(this, *((_DWORD *)this + 161), (struct CBSSEntry **)this + 82) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v33) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v33,
              v34,
              176,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *v29);
          }
          started = CConnectJob::StartWaitForPMKIDList(this);
          if ( !started )
          {
            *((_DWORD *)this + 148) = 7;
            CJobBase::SetPending(this);
            goto LABEL_72;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v35) = 2;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v35,
              v36,
              177,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *v29);
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v33) = 5;
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            v33,
            v34,
            178,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *v29);
        }
        v31 = 1;
        v29 = (int *)((char *)this + 16);
        v32 = 0;
      }
      v37 = CConnectJob::StartConnectRoamTask(this, v31, v32, &v58);
      started = v37;
      if ( v37 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v40 = "Critical-Roam";
          if ( !*((_BYTE *)this + 5521) )
            v40 = "Connect";
          WPP_RECORDER_SF_qDsD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v40,
            (unsigned int)"Connect",
            v38,
            v53,
            (char)this,
            *v29,
            (__int64)v40,
            v37);
        }
      }
      else if ( v58 )
      {
        if ( !*((_BYTE *)this + 5521) )
          v6 = 1;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
             && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        v39 = "Critical-Roam";
        if ( !*((_BYTE *)this + 5521) )
          v39 = "Connect";
        v55 = (__int64)v39;
        LOBYTE(v39) = 5;
        WPP_RECORDER_SF_qDs(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v39,
          (unsigned int)"Connect",
          179,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v55);
      }
      v18 = 0;
LABEL_107:
      v13 = 0;
      goto LABEL_41;
    case 7:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v10) = 5;
        LODWORD(v54) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          181,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54);
      }
      v20 = *((_QWORD *)PortFromPortId + 9);
      v18 = 0;
      if ( v20 )
      {
        v21 = *(_QWORD *)(v20 + 80);
        *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 168LL) = (CSystem::get_CurrentTime() - v21) / 0x2710;
      }
      started = CConnectJob::StartConnectRoamTask(this, 0, 0, &v58);
      if ( !started )
      {
        if ( !v58 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              182,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          goto LABEL_72;
        }
        v6 = 1;
        goto LABEL_107;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = *((_DWORD *)this + 4);
        v23 = 183;
        LODWORD(v54) = started;
LABEL_71:
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          v23,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          v22,
          v54);
        goto LABEL_72;
      }
      goto LABEL_72;
    case 8:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        LODWORD(v54) = started;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          184,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54);
      }
      started = CConnectJob::CompleteConnectTask(this, started);
      v12 = COidJobBase::GetPortPropertyCache(this);
      CPropertyCache::SetPropertyULong(v12, 0x86u, PropertyULongOrDefault + 1);
      if ( *((_BYTE *)this + 613) )
      {
        v13 = 1;
LABEL_29:
        v18 = 0;
        goto LABEL_41;
      }
      if ( *((_BYTE *)this + 5519) )
      {
        if ( started != -1073676280 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              185,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          if ( *((_BYTE *)this + 5520) )
          {
            v14 = *(_OWORD *)((char *)this + 5524);
            v15 = *(_OWORD *)((char *)this + 5540);
            v57 = *((_DWORD *)this + 1389);
            v56[0] = v14;
            v56[1] = v15;
            CPort::UpdateSSIDBlockInfoFor11r(PortFromPortId, v56);
          }
          v13 = 1;
          RoamConfig = CConnectHelpers::GetRoamConfig(1);
          CPort::TriggerReconnect(PortFromPortId, v17 + 10, v17, RoamConfig);
          goto LABEL_29;
        }
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v10) = 5;
          LODWORD(v54) = started;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            186,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v54);
        }
        if ( started != -1073676280 )
        {
          v6 = 1;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              187,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
        }
      }
      goto LABEL_39;
    default:
      goto LABEL_72;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    LODWORD(v54) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      (_DWORD)v11,
      167,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v54);
  }
LABEL_133:
  v45 = *((_QWORD *)PortFromPortId + 9);
  if ( v45 )
  {
    v46 = *(_QWORD *)(v45 + 80);
    v10 = (CSystem::get_CurrentTime() - v46) / 0x2710;
    *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 152LL) = v10;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 67) + 5364LL) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        (_DWORD)v11,
        168,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    v18 = 0;
    v13 = 0;
    if ( !started )
      started = -1073676280;
  }
  else
  {
    if ( *((_BYTE *)this + 2784) && *((_BYTE *)this + 5518) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          169,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      v18 = 0;
    }
    else
    {
      v18 = 1;
    }
    v13 = 0;
    v6 = 1;
  }
LABEL_41:
  v19 = (char *)this + 596;
  if ( !*((_BYTE *)this + 596) )
  {
    if ( v18 )
    {
      started = CConnectJob::CheckAndStartConnectProcess(this, (enum _WDI_ASSOC_STATUS *)&v58);
      if ( started )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 4;
          LODWORD(v54) = started;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            190,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v54);
        }
        v6 = 0;
      }
      else
      {
        if ( v58 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            LODWORD(v54) = v58;
            WPP_RECORDER_SF_qDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              189,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              v54);
          }
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              188,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          v6 = 0;
        }
        v19 = (char *)this + 596;
      }
    }
    if ( !*v19 && v6 )
    {
      started = CConnectJob::CheckAndStartScanProcess(this, (enum _WDI_ASSOC_STATUS *)&v58);
      if ( started )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 4;
          WPP_RECORDER_SF_qDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            193,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            started,
            v58);
        }
        if ( started == -1073741252 && v58 == 6 && (*((_DWORD *)this + 158) & 0x40) != 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v10) = 4;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              194,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          v47 = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
          CPort::NotifyRoamingAttemptsExhausted(v47, *((void **)this + 662));
          CConnectJob::CheckForNloMatchAndSendIndicationIfNecessary(this);
        }
      }
      else if ( v58 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v10) = 5;
          LODWORD(v54) = v58;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            (_DWORD)v11,
            192,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v54);
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
             && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          191,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
    }
  }
  if ( !v18 && !v6 )
    goto LABEL_210;
  if ( (*((_DWORD *)this + 158) & 4) != 0 )
  {
    if ( !started || started == -1073741252 )
    {
      if ( v58 == 6 )
      {
        v49 = COidJobBase::GetPortPropertyCache(this);
        if ( (CPropertyCache::GetPropertyBooleanOrDefault(v49, 0x52u, 0) || (*((_DWORD *)this + 158) & 0x10) != 0)
          && !*((_BYTE *)this + 5521)
          && !*((_BYTE *)this + 5560) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
          {
            LOBYTE(v10) = 5;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v10,
              (_DWORD)v11,
              195,
              (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
              (char)this,
              *((_DWORD *)this + 4));
          }
          v50 = *((_QWORD *)PortFromPortId + 9);
          if ( v50 )
            *(_DWORD *)(v50 + 36) = 4;
          v51 = *((_DWORD *)this + 158);
          *((_BYTE *)this + 5568) = 0;
          if ( (v51 & 8) != 0 )
          {
            if ( *((_BYTE *)PortFromPortId + 434) )
            {
              started = CConnectJob::SendBSSTransitionAcceptResponse(this);
              if ( !started )
              {
                v58 = 0;
                *((_BYTE *)this + 5568) = 1;
              }
            }
          }
          if ( !*((_BYTE *)this + 5568) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = 4;
              LODWORD(v54) = started;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v10,
                (_DWORD)v11,
                196,
                (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                (char)this,
                *((_DWORD *)this + 4),
                v54);
            }
            *((_BYTE *)this + 5521) = 1;
            v52 = CConnectJob::StartConnectRoamTask(this, 0, 1, &v58);
            started = v52;
            if ( v52 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                v48 = 197;
                LODWORD(v54) = v52;
                LOBYTE(v10) = 2;
                goto LABEL_183;
              }
            }
          }
        }
      }
      else if ( v58 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v48 = 198;
        LODWORD(v54) = v58;
        goto LABEL_182;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v48 = 199;
      LODWORD(v54) = started;
LABEL_182:
      LOBYTE(v10) = 4;
LABEL_183:
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        (_DWORD)v11,
        v48,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v54);
    }
  }
  if ( v18 || v6 )
  {
    if ( started )
      goto LABEL_212;
    if ( v58 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 4;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          (_DWORD)v11,
          200,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
      }
      started = -1073741823;
      goto LABEL_212;
    }
    goto LABEL_211;
  }
LABEL_210:
  if ( started )
  {
LABEL_212:
    CConnectJob::FinishJob(this, started);
    goto LABEL_213;
  }
LABEL_211:
  if ( v13 )
    goto LABEL_212;
LABEL_213:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    LODWORD(v54) = started;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      (_DWORD)v11,
      201,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v54);
  }
}

```

## disassembly

```asm
0x1400adae0  mov     [rsp-38h+arg_10], rbx
0x1400adae5  push    rbp
0x1400adae6  push    rsi
0x1400adae7  push    rdi
0x1400adae8  push    r12
0x1400adaea  push    r13
0x1400adaec  push    r14
0x1400adaee  push    r15
0x1400adaf0  mov     rbp, rsp
0x1400adaf3  sub     rsp, 80h
0x1400adafa  xor     r15d, r15d
0x1400adafd  mov     [rbp+arg_18], 6
0x1400adb04  mov     esi, edx
0x1400adb06  mov     [rbp+arg_0], r15b
0x1400adb0a  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400adb0e  lea     r14, [rcx+218h]
0x1400adb15  mov     rdi, rcx
0x1400adb18  mov     [rbp+arg_8], r15b
0x1400adb1c  mov     rcx, [r14]; this
0x1400adb1f  mov     r12b, r15b
0x1400adb22  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400adb27  mov     rcx, rdi; this
0x1400adb2a  mov     r13, rax
0x1400adb2d  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400adb32  xor     r8d, r8d; unsigned int
0x1400adb35  mov     edx, 86h; unsigned int
0x1400adb3a  mov     rcx, rax; this
0x1400adb3d  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400adb42  mov     ebx, eax
0x1400adb44  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400adb4b  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400adb52  lea     r8, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400adb59  jz      loc_1400ADBFE
0x1400adb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adb66  cmp     byte ptr [rcx+29h], 5
0x1400adb6a  jnb     short loc_1400ADB7A
0x1400adb6c  cmp     [rcx+48h], r15w
0x1400adb71  jz      short loc_1400ADBAA
0x1400adb73  lea     r14, [rdi+218h]
0x1400adb7a  mov     eax, [rdi+10h]
0x1400adb7d  mov     r9d, 0A3h
0x1400adb83  mov     rcx, [rcx+40h]
0x1400adb87  mov     dl, 5
0x1400adb89  mov     [rsp+80h+var_50], eax
0x1400adb8d  mov     [rsp+80h+var_58], rdi
0x1400adb92  mov     [rsp+80h+var_60], r8
0x1400adb97  call    WPP_RECORDER_SF_qD
0x1400adb9c  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400adba3  lea     r8, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400adbaa  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400adbb1  jz      short loc_1400ADBFE
0x1400adbb3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adbba  cmp     byte ptr [rcx+29h], 5
0x1400adbbe  jnb     short loc_1400ADBC7
0x1400adbc0  cmp     [rcx+48h], r15w
0x1400adbc5  jz      short loc_1400ADBFE
0x1400adbc7  mov     eax, [rdi+250h]
0x1400adbcd  mov     r9d, 0A4h
0x1400adbd3  mov     rcx, [rcx+40h]
0x1400adbd7  mov     dl, 5
0x1400adbd9  mov     [rsp+80h+var_40], esi
0x1400adbdd  mov     dword ptr [rsp+80h+var_48], eax
0x1400adbe1  mov     eax, [rdi+10h]
0x1400adbe4  mov     [rsp+80h+var_50], eax
0x1400adbe8  mov     [rsp+80h+var_58], rdi
0x1400adbed  mov     [rsp+80h+var_60], r8
0x1400adbf2  call    WPP_RECORDER_SF_qDdd
0x1400adbf7  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400adbfe  mov     ecx, [rdi+250h]
0x1400adc04  mov     r15, 346DC5D63886594Bh
0x1400adc0e  sub     ecx, 3
0x1400adc11  jz      loc_1400AE440
0x1400adc17  sub     ecx, 1
0x1400adc1a  jz      loc_1400AE517
0x1400adc20  sub     ecx, 1
0x1400adc23  jz      loc_1400AE312
0x1400adc29  sub     ecx, 1
0x1400adc2c  jz      loc_1400ADFC1
0x1400adc32  sub     ecx, 1
0x1400adc35  jz      loc_1400ADEA1
0x1400adc3b  cmp     ecx, 1
0x1400adc3e  jnz     loc_1400AE093
0x1400adc44  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400adc4b  lea     r14, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400adc52  jz      short loc_1400ADC81
0x1400adc54  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adc5b  mov     r9d, 0B8h
0x1400adc61  mov     eax, [rdi+10h]
0x1400adc64  mov     dl, 4
0x1400adc66  mov     dword ptr [rsp+80h+var_48], esi
0x1400adc6a  mov     [rsp+80h+var_50], eax
0x1400adc6e  mov     rcx, [rcx+40h]
0x1400adc72  mov     [rsp+80h+var_58], rdi
0x1400adc77  mov     [rsp+80h+var_60], r14
0x1400adc7c  call    WPP_RECORDER_SF_qDD
0x1400adc81  mov     edx, esi; int
0x1400adc83  mov     rcx, rdi; this
0x1400adc86  call    ?CompleteConnectTask@CConnectJob@@AEAAHH@Z; CConnectJob::CompleteConnectTask(int)
0x1400adc8b  mov     rcx, rdi; this
0x1400adc8e  mov     esi, eax
0x1400adc90  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400adc95  lea     r8d, [rbx+1]; unsigned int
0x1400adc99  mov     edx, 86h; unsigned int
0x1400adc9e  mov     rcx, rax; this
0x1400adca1  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400adca6  xor     ebx, ebx
0x1400adca8  cmp     [rdi+265h], bl
0x1400adcae  jz      short loc_1400ADCB8
0x1400adcb0  mov     r15b, 1
0x1400adcb3  jmp     loc_1400ADD69
0x1400adcb8  cmp     [rdi+158Fh], bl
0x1400adcbe  jz      loc_1400ADD71
0x1400adcc4  cmp     esi, 0C0010008h
0x1400adcca  jz      loc_1400ADE0A
0x1400adcd0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400adcd7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400adcde  jz      short loc_1400ADD15
0x1400adce0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adce7  cmp     byte ptr [rcx+29h], 5
0x1400adceb  jnb     short loc_1400ADCF3
0x1400adced  cmp     [rcx+48h], bx
0x1400adcf1  jz      short loc_1400ADD15
0x1400adcf3  mov     eax, [rdi+10h]
0x1400adcf6  mov     r9d, 0B9h
0x1400adcfc  mov     rcx, [rcx+40h]
0x1400add00  mov     dl, 5
0x1400add02  mov     [rsp+80h+var_50], eax
0x1400add06  mov     [rsp+80h+var_58], rdi
0x1400add0b  mov     [rsp+80h+var_60], r14
0x1400add10  call    WPP_RECORDER_SF_qD
0x1400add15  cmp     [rdi+1590h], bl
0x1400add1b  jz      short loc_1400ADD48
0x1400add1d  movups  xmm0, xmmword ptr [rdi+1594h]
0x1400add24  mov     eax, [rdi+15B4h]
0x1400add2a  lea     rdx, [rbp+var_30]
0x1400add2e  movups  xmm1, xmmword ptr [rdi+15A4h]
0x1400add35  mov     rcx, r13
0x1400add38  mov     [rbp+var_10], eax
0x1400add3b  movaps  [rbp+var_30], xmm0
0x1400add3f  movaps  [rbp+var_20], xmm1
0x1400add43  call    ?UpdateSSIDBlockInfoFor11r@CPort@@QEAAXU_DOT11_SSID@@W4_WFC_BLOCKED_REASON@@@Z; CPort::UpdateSSIDBlockInfoFor11r(_DOT11_SSID,_WFC_BLOCKED_REASON)
0x1400add48  mov     edx, 1
0x1400add4d  mov     ecx, edx
0x1400add4f  mov     r15b, dl
0x1400add52  call    ?GetRoamConfig@CConnectHelpers@@YA?AW4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WFC_ROAM_CONNECT_TRIGGER@@@Z; CConnectHelpers::GetRoamConfig(_WFC_ROAM_CONNECT_TRIGGER)
0x1400add57  mov     r8d, edx
0x1400add5a  mov     r9d, eax
0x1400add5d  mov     rcx, r13
0x1400add60  lea     edx, [r8+0Ah]
0x1400add64  call    ?TriggerReconnect@CPort@@QEAAHW4_WDI_ASSOC_STATUS@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CPort::TriggerReconnect(_WDI_ASSOC_STATUS,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ROAM_CONFIGURATION_FLAGS)
0x1400add69  mov     r14b, bl
0x1400add6c  jmp     loc_1400ADE10
0x1400add71  lea     rax, WPP_RECORDER_INITIALIZED
0x1400add78  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400add7f  jz      short loc_1400ADDC1
0x1400add81  mov     rcx, cs:WPP_GLOBAL_Control
0x1400add88  cmp     byte ptr [rcx+29h], 5
0x1400add8c  jnb     short loc_1400ADD94
0x1400add8e  cmp     [rcx+48h], bx
0x1400add92  jz      short loc_1400ADDC1
0x1400add94  mov     eax, [rdi+10h]
0x1400add97  mov     r9d, 0BAh
0x1400add9d  mov     rcx, [rcx+40h]
0x1400adda1  mov     dl, 5
0x1400adda3  mov     dword ptr [rsp+80h+var_48], esi
0x1400adda7  mov     [rsp+80h+var_50], eax
0x1400addab  mov     [rsp+80h+var_58], rdi
0x1400addb0  mov     [rsp+80h+var_60], r14
0x1400addb5  call    WPP_RECORDER_SF_qDD
0x1400addba  lea     rax, WPP_RECORDER_INITIALIZED
0x1400addc1  cmp     esi, 0C0010008h
0x1400addc7  jz      short loc_1400ADE0A
0x1400addc9  mov     r12b, 1
0x1400addcc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400addd3  jz      short loc_1400ADE0A
0x1400addd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adddc  cmp     byte ptr [rcx+29h], 5
0x1400adde0  jnb     short loc_1400ADDE8
0x1400adde2  cmp     [rcx+48h], bx
0x1400adde6  jz      short loc_1400ADE0A
0x1400adde8  mov     eax, [rdi+10h]
0x1400addeb  mov     r9d, 0BBh
0x1400addf1  mov     rcx, [rcx+40h]
0x1400addf5  mov     dl, 5
0x1400addf7  mov     [rsp+80h+var_50], eax
0x1400addfb  mov     [rsp+80h+var_58], rdi
0x1400ade00  mov     [rsp+80h+var_60], r14
0x1400ade05  call    WPP_RECORDER_SF_qD
0x1400ade0a  mov     r14b, bl
0x1400ade0d  mov     r15b, bl
0x1400ade10  lea     rbx, [rdi+254h]
0x1400ade17  xor     eax, eax
0x1400ade19  cmp     [rbx], al
0x1400ade1b  jnz     loc_1400AE8C0
0x1400ade21  test    r14b, r14b
0x1400ade24  jz      loc_1400AE70D
0x1400ade2a  lea     rdx, [rbp+arg_18]; enum _WDI_ASSOC_STATUS *
0x1400ade2e  mov     rcx, rdi; this
0x1400ade31  call    ?CheckAndStartConnectProcess@CConnectJob@@AEAAHPEAW4_WDI_ASSOC_STATUS@@@Z; CConnectJob::CheckAndStartConnectProcess(_WDI_ASSOC_STATUS *)
0x1400ade36  mov     esi, eax
0x1400ade38  xor     eax, eax
0x1400ade3a  test    esi, esi
0x1400ade3c  jnz     loc_1400AE6C4
0x1400ade42  xor     ebx, ebx
0x1400ade44  cmp     [rbp+arg_18], ebx
0x1400ade47  jnz     loc_1400AE666
0x1400ade4d  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ade54  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ade5b  jz      short loc_1400ADE99
0x1400ade5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ade64  cmp     byte ptr [rcx+29h], 5
0x1400ade68  jnb     short loc_1400ADE70
0x1400ade6a  cmp     [rcx+48h], bx
0x1400ade6e  jz      short loc_1400ADE99
0x1400ade70  mov     eax, [rdi+10h]
0x1400ade73  mov     r9d, 0BCh
0x1400ade79  mov     rcx, [rcx+40h]
0x1400ade7d  mov     dl, 5
0x1400ade7f  mov     [rsp+80h+var_50], eax
0x1400ade83  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400ade8a  mov     [rsp+80h+var_58], rdi
0x1400ade8f  mov     [rsp+80h+var_60], rax
0x1400ade94  call    WPP_RECORDER_SF_qD
0x1400ade99  mov     r12b, bl
0x1400ade9c  jmp     loc_1400AE6B9
0x1400adea1  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400adea8  jz      short loc_1400ADEEC
0x1400adeaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adeb1  cmp     byte ptr [rcx+29h], 5
0x1400adeb5  jnb     short loc_1400ADEBF
0x1400adeb7  xor     eax, eax
0x1400adeb9  cmp     [rcx+48h], ax
0x1400adebd  jz      short loc_1400ADEEC
0x1400adebf  mov     eax, [rdi+10h]
0x1400adec2  mov     r9d, 0B5h
0x1400adec8  mov     rcx, [rcx+40h]
0x1400adecc  mov     dl, 5
0x1400adece  mov     dword ptr [rsp+80h+var_48], esi
0x1400aded2  mov     [rsp+80h+var_50], eax
0x1400aded6  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400adedd  mov     [rsp+80h+var_58], rdi
0x1400adee2  mov     [rsp+80h+var_60], rax
0x1400adee7  call    WPP_RECORDER_SF_qDD
0x1400adeec  mov     rbx, [r13+48h]
0x1400adef0  xor     r14d, r14d
0x1400adef3  test    rbx, rbx
0x1400adef6  jz      short loc_1400ADF1C
0x1400adef8  mov     rbx, [rbx+50h]
0x1400adefc  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400adf01  mov     rcx, rax
0x1400adf04  mov     rax, r15
0x1400adf07  sub     rcx, rbx
0x1400adf0a  mul     rcx
0x1400adf0d  mov     rax, [r13+48h]
0x1400adf11  shr     rdx, 0Bh
0x1400adf15  mov     [rax+0A8h], rdx
0x1400adf1c  lea     r9, [rbp+arg_18]
0x1400adf20  xor     r8d, r8d
0x1400adf23  xor     edx, edx
0x1400adf25  mov     rcx, rdi
0x1400adf28  call    ?StartConnectRoamTask@CConnectJob@@AEAAHW4_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS@1@W4_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS@1@PEAW4_WDI_ASSOC_STATUS@@@Z; CConnectJob::StartConnectRoamTask(CConnectJob::_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS,CConnectJob::_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS,_WDI_ASSOC_STATUS *)
0x1400adf2d  mov     esi, eax
0x1400adf2f  test    eax, eax
0x1400adf31  jnz     short loc_1400ADF9B
0x1400adf33  cmp     [rbp+arg_18], r14d
0x1400adf37  jnz     short loc_1400ADF93
0x1400adf39  lea     rax, WPP_RECORDER_INITIALIZED
0x1400adf40  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400adf47  jz      loc_1400AE093
0x1400adf4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adf54  cmp     byte ptr [rcx+29h], 5
0x1400adf58  jnb     short loc_1400ADF65
0x1400adf5a  cmp     [rcx+48h], r14w
0x1400adf5f  jz      loc_1400AE093
0x1400adf65  mov     eax, [rdi+10h]
0x1400adf68  mov     r9d, 0B6h
0x1400adf6e  mov     rcx, [rcx+40h]
0x1400adf72  mov     dl, 5
0x1400adf74  mov     [rsp+80h+var_50], eax
0x1400adf78  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400adf7f  mov     [rsp+80h+var_58], rdi
0x1400adf84  mov     [rsp+80h+var_60], rax
0x1400adf89  call    WPP_RECORDER_SF_qD
0x1400adf8e  jmp     loc_1400AE093
0x1400adf93  mov     r12b, 1
0x1400adf96  jmp     loc_1400AE30A
0x1400adf9b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400adfa2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400adfa9  jz      loc_1400AE093
0x1400adfaf  mov     eax, [rdi+10h]
0x1400adfb2  mov     r9d, 0B7h
0x1400adfb8  mov     dword ptr [rsp+80h+var_48], esi
0x1400adfbc  jmp     loc_1400AE06C
0x1400adfc1  mov     al, [rdi+0AE0h]
0x1400adfc7  mov     edx, esi; int
0x1400adfc9  neg     al
0x1400adfcb  mov     rcx, rdi; this
0x1400adfce  sbb     ebx, ebx
0x1400adfd0  and     ebx, 3
0x1400adfd3  call    ?CompleteSendResponseActionFrameJob@CConnectJob@@AEAAXH@Z; CConnectJob::CompleteSendResponseActionFrameJob(int)
  ... truncated ...
```
