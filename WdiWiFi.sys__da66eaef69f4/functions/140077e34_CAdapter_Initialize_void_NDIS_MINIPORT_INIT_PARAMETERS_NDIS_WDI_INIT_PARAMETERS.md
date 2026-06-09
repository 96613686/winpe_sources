# CAdapter::Initialize(void *,_NDIS_MINIPORT_INIT_PARAMETERS *,_NDIS_WDI_INIT_PARAMETERS *)

- ea: `0x140077e34`
- end: `0x140078cb6`
- name: `?Initialize@CAdapter@@QEAAHPEAXPEAU_NDIS_MINIPORT_INIT_PARAMETERS@@PEAU_NDIS_WDI_INIT_PARAMETERS@@@Z`
- size: `3714`
- prototype: `__int64 __fastcall(CAdapter *__hidden this, void *, struct _NDIS_MINIPORT_INIT_PARAMETERS *, struct _NDIS_WDI_INIT_PARAMETERS *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140077cb4`

## callees

- `0x14000c134`
- `0x1400100f8`
- `0x1400174e8`
- `0x1400176b0`
- `0x140023ae0`
- `0x140026490`
- `0x140028c44`
- `0x140034e04`
- `0x140034ec4`
- `0x14005dc94`
- `0x1400687e0`
- `0x140072e6c`
- `0x1400744dc`
- `0x140077e34`
- `0x14007a4c8`
- `0x14007d2e4`
- `0x14007e26c`
- `0x14008218c`
- `0x14009e910`
- `0x14009ea00`
- `0x1400a1694`
- `0x1400a1bc0`
- `0x1400a29d0`
- `0x1400a32dc`
- `0x1400a36d8`
- `0x1400a488c`
- `0x1400a4a90`
- `0x1400a7e3c`
- `0x1400a8e0c`
- `0x1400b9b14`
- `0x1400b9b74`
- `0x1400d88c0`
- `0x1400da4f0`
- `0x1400da680`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140078a19`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140078a19`
- `ntoskrnl!ZwPowerInformation` at `0x1400789e4`
- `ntoskrnl!ZwPowerInformation` at `0x1400789e4`
- `ntoskrnl!ExAllocatePool2` at `0x14007807c`
- `ntoskrnl!ExAllocatePool2` at `0x14007843f`
- `ntoskrnl!ExAllocatePool2` at `0x14007853b`
- `ntoskrnl!ExAllocatePool2` at `0x1400785c3`
- `ntoskrnl!ExAllocatePool2` at `0x14007864f`
- `ntoskrnl!ExAllocatePool2` at `0x1400786ef`
- `ntoskrnl!ExAllocatePool2` at `0x14007807c`
- `ntoskrnl!ExAllocatePool2` at `0x14007843f`
- `ntoskrnl!ExAllocatePool2` at `0x14007853b`
- `ntoskrnl!ExAllocatePool2` at `0x1400785c3`
- `ntoskrnl!ExAllocatePool2` at `0x14007864f`
- `ntoskrnl!ExAllocatePool2` at `0x1400786ef`
- `NDIS!NdisCloseConfiguration` at `0x140078c30`
- `NDIS!NdisCloseConfiguration` at `0x140078c30`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140077ef2`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140077ef2`

## string_xrefs

- `0x140078199`: `System\CurrentControlSet\Services\WlanSvc`
- `0x1400782c6`: `ComponentId`

## pseudocode

```c
__int64 __fastcall CAdapter::Initialize(
        CAdapter *this,
        void *a2,
        struct _NDIS_MINIPORT_INIT_PARAMETERS *a3,
        struct _NDIS_WDI_INIT_PARAMETERS *a4)
{
  struct IOperationCompletionCallback *v4; // rbx
  __int64 *v8; // rdx
  CGlobalCtlDevice *p_m_CtlDevice; // rax
  NET_LUID *p_NetLuid; // rsi
  NTSTATUS v11; // eax
  enum _NDIS_HALT_ACTION v12; // edx
  int v13; // r8d
  int v14; // r9d
  unsigned int Instance; // edi
  _QWORD *Pool2; // rax
  struct _WFC_REG_ENTRY *v18; // r8
  unsigned int v19; // r9d
  _QWORD *v20; // rsi
  unsigned int PropertiesFromRegistry; // eax
  int v22; // edx
  CMiniportRestartJob *v23; // r12
  int v24; // r9d
  unsigned int *p_m_OemPLDRSupported; // rdi
  int v26; // edx
  unsigned int v27; // eax
  CAdapter *v28; // rcx
  int v29; // edx
  int v30; // edx
  unsigned int v31; // r14d
  __int64 i; // rcx
  struct _WDF_OBJECT_ATTRIBUTES *v33; // r8
  int v34; // eax
  int v35; // edx
  unsigned int v36; // edx
  int v37; // edx
  CMiniportPauseJob *v38; // r14
  CMiniportSurpriseRemovalJob *v39; // r13
  unsigned int NextActivityId; // eax
  int v41; // edx
  int v42; // r9d
  int v43; // r9d
  int v44; // edx
  unsigned int v45; // eax
  int v46; // edx
  unsigned int v47; // eax
  int v48; // edx
  unsigned int v49; // eax
  CMiniportInitializeJob *v50; // r9
  CMiniportInitializeJob *v51; // rax
  int v52; // edx
  int v53; // r9d
  int v54; // edx
  unsigned int v55; // eax
  int v56; // edx
  int v57; // r9d
  struct CJobBase *v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rcx
  NTSTATUS v61; // eax
  void *v62; // rcx
  int OutputBufferLength; // [rsp+20h] [rbp-E0h]
  __int64 v64; // [rsp+28h] [rbp-D8h]
  char OutputBuffer; // [rsp+40h] [rbp-C0h] BYREF
  char v66; // [rsp+41h] [rbp-BFh]
  struct _UNICODE_STRING v67; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v68; // [rsp+58h] [rbp-A8h] BYREF
  struct IEventContext *v69; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v70; // [rsp+68h] [rbp-98h] BYREF
  struct _NDIS_WDI_INIT_PARAMETERS *v71; // [rsp+78h] [rbp-88h]
  struct _NDIS_MINIPORT_INIT_PARAMETERS *v72; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v73[2]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SourceString[264]; // [rsp+A0h] [rbp-60h] BYREF

  v71 = a4;
  v66 = 0;
  v4 = 0;
  v69 = 0;
  v68 = 0;
  v72 = a3;
  v8 = WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      1,
      20,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  p_m_CtlDevice = &g_pWdiDriver->m_CtlDevice;
  this->m_MiniportAdapterHandle = a2;
  p_NetLuid = &a3->NetLuid;
  this->m_pCtlDevice = p_m_CtlDevice;
  v11 = ConvertInterfaceLuidToGuid(&a3->NetLuid, &this->m_NetGuid);
  Instance = v11;
  if ( v11 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_iD(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14, OutputBufferLength, p_NetLuid->Value, v11);
    goto LABEL_8;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF__guid_id(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      v14,
      OutputBufferLength,
      (__int64)&this->m_NetGuid,
      p_NetLuid->Value,
      a3->IfIndex);
  Instance = CAdapterPropertyCache::Initialize(&this->m_AdapterPropertyCache);
  if ( Instance )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        23,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    }
    goto LABEL_8;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(64, 16, 1198089303);
  v20 = Pool2;
  if ( Pool2 )
  {
    Pool2[1] = 0;
    *Pool2 = a2;
    PropertiesFromRegistry = CRegistryHelper::LoadPropertiesFromRegistry(
                               (CRegistryHelper *)Pool2,
                               &this->m_AdapterPropertyCache,
                               v18,
                               v19);
    v23 = 0;
    Instance = PropertiesFromRegistry;
    if ( PropertiesFromRegistry )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_147:
        v62 = (void *)v20[1];
        if ( v62 )
        {
          NdisCloseConfiguration(v62);
          v20[1] = 0;
        }
        operator delete(v20);
        goto LABEL_8;
      }
      v24 = 25;
LABEL_29:
      LODWORD(v64) = PropertiesFromRegistry;
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        1,
        v24,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        v64);
      goto LABEL_147;
    }
    *(_QWORD *)&v67.Length = 1966108;
    p_m_OemPLDRSupported = &this->m_OemPLDRSupported;
    v67.Buffer = L"PldrCapability";
    if ( CRegistryHelper::ReadAdapterRegistryDword((CRegistryHelper *)v20, &v67, &this->m_OemPLDRSupported) )
    {
      *p_m_OemPLDRSupported = 0;
      LOBYTE(v27) = 0;
    }
    else
    {
      v27 = *p_m_OemPLDRSupported;
    }
    this->m_OemFLDRSupported = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v26,
        1,
        26,
        (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
        v27,
        0);
    }
    if ( *p_m_OemPLDRSupported )
    {
      *(_DWORD *)&v67.Length = 0;
      memset(SourceString, 0, 0x208u);
      KmWlanStateSeparation_GetMutableRegistryKey(SourceString);
      if ( !CAdapter::ReadRegDword(
              v28,
              SourceString,
              L"WLANPlatformLevelDeviceResetSupported",
              (unsigned int *)&v67.Length)
        && !*(_DWORD *)&v67.Length )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v29,
            1,
            27,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        }
        *p_m_OemPLDRSupported = 0;
      }
    }
    *(_DWORD *)&v67.Length = 0;
    if ( !(unsigned int)CPropertyCache::GetPropertyULong(
                          &this->m_AdapterPropertyCache,
                          0x41u,
                          (unsigned int *)&v67.Length) )
    {
      v31 = *(_DWORD *)&v67.Length;
      if ( *(_DWORD *)&v67.Length != -1 && (*(_DWORD *)&v67.Length != 0) != (this->m_OemPLDRSupported != 0) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v64) = *(_DWORD *)&v67.Length;
          LOBYTE(v30) = 2;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v30,
            1,
            28,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
            v64);
        }
        *p_m_OemPLDRSupported = v31;
      }
    }
    CPropertyCache::GetPropertyULong(
      &this->m_AdapterPropertyCache,
      0x2Fu,
      (unsigned int *)&WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    for ( i = 0; i != 5; ++i )
    {
      this->m_PortLockList[i].m_pAdapter = this;
      _InterlockedIncrement((volatile signed __int32 *)&this->m_PortLockList[i]);
    }
    CPropertyCache::SetPropertyULong(&this->m_AdapterPropertyCache, 0x2Bu, 0xFFFFFFFF);
    *(_QWORD *)&v70.Length = 1572886;
    v70.Buffer = L"ComponentId";
    *(_QWORD *)&v67.Length = 0;
    v34 = CRegistryHelper::ReadAdapterRegistryString((CRegistryHelper *)v20, &v70, v33, (struct WDFSTRING__ **)&v67);
    if ( v34 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v64) = v34;
        LOBYTE(v35) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v35,
          1,
          29,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
          v64);
      }
      this->m_ExpandStackSizeFlags.AsULong64 = 0;
    }
    else
    {
      *(_OWORD *)v73 = 0;
      ((void (__fastcall *)(_QWORD, _QWORD, unsigned __int16 **))WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[38].SystemArgument1)(
        *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement,
        *(_QWORD *)&v67.Length,
        v73);
      WdiQueryDeviceFlags(v73[1], &this->m_ExpandStackSizeFlags.AsULong64);
    }
    if ( *(_QWORD *)&v67.Length )
      (*(void (__fastcall **)(_QWORD))&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[26].TargetInfoAsUlong)(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement);
    PropertiesFromRegistry = CAdapter::InitializeControlPath(this);
    Instance = PropertiesFromRegistry;
    if ( PropertiesFromRegistry )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_147;
      v24 = 30;
      goto LABEL_29;
    }
    v66 = 1;
    CPropertyCache::GetPropertyULong(
      &this->m_AdapterPropertyCache,
      0x40u,
      &this->m_EventQueue.m_HungResetRecoveryIterations);
    if ( this->m_EventQueue.m_HungResetRecoveryIterations )
    {
      CAdapter::SimulateFirmwareHang(this, v36);
    }
    else
    {
      Instance = CAdapter::ControlResetRecovery(this);
      if ( Instance )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_147;
        v43 = 31;
        goto LABEL_69;
      }
    }
    CBSSListManager::Initialize(&this->m_ExtStaBSSList, this, &this->m_AdapterPropertyCache, WfcPortTypeExtSTA);
    CBSSListManager::Initialize(&this->m_DevicePortBSSList, this, &this->m_AdapterPropertyCache, WfcPortTypeWFDDevice);
    CServicesManager::Initialize(&this->m_ServicesManager, this, &this->m_AdapterPropertyCache);
    CAdapter::SetDataPathApis(this);
    v38 = (CMiniportPauseJob *)ExAllocatePool2(64, 544, 1198089303);
    if ( v38 )
    {
      v39 = 0;
      NextActivityId = IActivityId::get_NextActivityId();
      CMiniportJobBase::CMiniportJobBase(v38, NextActivityId);
      v38->CMiniportJobBase::CJobBase::IOperationCompletionCallback::__vftable = (CMiniportPauseJob_vtbl *)&CMiniportPauseJob::`vftable'{for `IOperationCompletionCallback'};
      v38->CMiniportJobBase::CJobBase::IEventQueueCallback::__vftable = (IEventQueueCallback_vtbl *)&CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
      Instance = CMiniportJobBase::Initialize(v38, this, WiFiJobMiniportPause);
      if ( Instance )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        {
LABEL_142:
          ((void (__fastcall *)(CMiniportPauseJob *, __int64))v38->~CMiniportPauseJob)(v38, 1);
LABEL_143:
          if ( v39 )
            ((void (__fastcall *)(CMiniportSurpriseRemovalJob *, __int64))v39->~CMiniportSurpriseRemovalJob)(v39, 1);
          if ( v23 )
            ((void (__fastcall *)(CMiniportRestartJob *, __int64))v23->~CMiniportRestartJob)(v23, 1);
          goto LABEL_147;
        }
        v42 = 33;
LABEL_65:
        LOBYTE(v41) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v41,
          1,
          v42,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        goto LABEL_142;
      }
      v23 = (CMiniportRestartJob *)ExAllocatePool2(64, 544, 1198089303);
      if ( !v23 )
      {
        Instance = -1073741670;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v44) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v44,
            1,
            34,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        }
        v23 = 0;
        goto LABEL_142;
      }
      v45 = IActivityId::get_NextActivityId();
      CMiniportJobBase::CMiniportJobBase(v23, v45);
      v23->CMiniportJobBase::CJobBase::IOperationCompletionCallback::__vftable = (CMiniportRestartJob_vtbl *)&CMiniportRestartJob::`vftable'{for `IOperationCompletionCallback'};
      v23->CMiniportJobBase::CJobBase::IEventQueueCallback::__vftable = (IEventQueueCallback_vtbl *)&CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
      Instance = CMiniportJobBase::Initialize(v23, this, WiFiJobMiniportRestart);
      if ( Instance )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_142;
        v42 = 35;
        goto LABEL_65;
      }
      v39 = (CMiniportSurpriseRemovalJob *)ExAllocatePool2(64, 536, 1198089303);
      if ( !v39 )
      {
        Instance = -1073741670;
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v46) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v46,
            1,
            36,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        }
        v39 = 0;
        goto LABEL_142;
      }
      v47 = IActivityId::get_NextActivityId();
      CMiniportJobBase::CMiniportJobBase(v39, v47);
      v39->m_RequiresPassiveIrql = 1;
      v39->CMiniportJobBase::CJobBase::IOperationCompletionCallback::__vftable = (CMiniportSurpriseRemovalJob_vtbl *)&CMiniportSurpriseRemovalJob::`vftable'{for `IOperationCompletionCallback'};
      v39->CMiniportJobBase::CJobBase::IEventQueueCallback::__vftable = (IEventQueueCallback_vtbl *)&CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
      Instance = CMiniportJobBase::Initialize(v39, this, WiFiJobMiniportSurpriseRemoval);
      if ( Instance )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_142;
        v42 = 37;
        goto LABEL_65;
      }
      if ( !ExAllocatePool2(64, 6552, 1198089303)
        || (v49 = IActivityId::get_NextActivityId(),
            v51 = CMiniportInitializeJob::CMiniportInitializeJob(v50, v49),
            (*(_QWORD *)&v67.Length = v51) == 0) )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v48) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v48,
            1,
            38,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        }
        Instance = -1073741670;
        goto LABEL_142;
      }
      Instance = CMiniportInitializeJob::Initialize(v51, this, v72, v71);
      if ( Instance )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_129;
        v53 = 39;
        goto LABEL_83;
      }
      v4 = (struct IOperationCompletionCallback *)ExAllocatePool2(64, 24, 1198089303);
      if ( v4 )
      {
        v4[1].__vftable = 0;
        v4->__vftable = (IOperationCompletionCallback_vtbl *)&CJobCompleteNotifier::`vftable';
        v4[2].__vftable = 0;
        v55 = IEventContext::CreateInstance(&v69);
        Instance = v55;
        if ( v55 )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            goto LABEL_129;
          v57 = 41;
          LODWORD(v64) = v55;
          goto LABEL_88;
        }
        v4[1].__vftable = (IOperationCompletionCallback_vtbl *)v69;
        v4[2].__vftable = (IOperationCompletionCallback_vtbl *)&v68;
        v58 = *(struct CJobBase **)&v67.Length;
        this->m_PendingInitHaltJob = *(IOperationCompletionCallback **)&v67.Length;
        Instance = SerializedJobList::QueueSerializedJob(&this->m_SerializedJobList, v58, v4);
        if ( Instance )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v53 = 43;
LABEL_83:
            LOBYTE(v52) = 2;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v52,
              1,
              v53,
              (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
          }
        }
        else
        {
          v4 = 0;
          (*(void (__fastcall **)(struct IEventContext *, _QWORD))(*(_QWORD *)v69 + 24LL))(v69, 0);
          v56 = 0;
          if ( this->m_lResetRecovery )
          {
            Instance = 0;
            v68 = 0;
          }
          else
          {
            Instance = v68;
          }
          if ( Instance )
          {
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v57 = 44;
              LODWORD(v64) = Instance;
LABEL_88:
              LOBYTE(v56) = 2;
LABEL_89:
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                v56,
                1,
                v57,
                (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
                v64);
            }
          }
          else
          {
            v59 = *(_QWORD *)&v67.Length;
            v60 = 0;
            this->m_MiniportPauseJob = v38;
            v38 = 0;
            this->m_MiniportRestartJob = v23;
            v23 = 0;
            this->m_MiniportSurpriseRemovalJob = v39;
            v39 = 0;
            *(_QWORD *)&v67.Length = v59;
            do
            {
              this->m_NdisPortNumToActivate[v60] = 0;
              this->m_NdisPortNumToDeactivate[v60++] = 0;
            }
            while ( v60 != 5 );
            *(_WORD *)&this->m_bDeactivateWorkerActive = 0;
            Instance = CNdisSpinLock::CreateInstance(&this->m_ISpinLockDelayDeactivation);
            if ( Instance )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v53 = 45;
                goto LABEL_83;
              }
            }
            else
            {
              Instance = CNdisSpinLock::CreateInstance(&this->m_ISpinLockDelayActivation);
              if ( Instance )
              {
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v53 = 46;
                  goto LABEL_83;
                }
              }
              else
              {
                Instance = IWorkItemContext::CreateInstance(&this->m_pWorkItemDeactivatePort);
                if ( Instance )
                {
                  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    v53 = 47;
                    goto LABEL_83;
                  }
                }
                else
                {
                  Instance = this->m_pWorkItemDeactivatePort->Initialize(
                               this->m_pWorkItemDeactivatePort,
                               this->m_pCtlDevice,
                               (IWorkItemCallback *)((unsigned __int64)&this->IWorkItemCallback & -(__int64)(this != 0)),
                               this->m_pWorkItemDeactivatePort);
                  if ( Instance )
                  {
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      v53 = 48;
                      goto LABEL_83;
                    }
                  }
                  else
                  {
                    Instance = IWorkItemContext::CreateInstance(&this->m_pWorkItemActivatePort);
                    if ( Instance )
                    {
                      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                      {
                        v53 = 49;
                        goto LABEL_83;
                      }
                    }
                    else
                    {
                      Instance = this->m_pWorkItemActivatePort->Initialize(
                                   this->m_pWorkItemActivatePort,
                                   this->m_pCtlDevice,
                                   &this->IWorkItemCallback,
                                   this->m_pWorkItemActivatePort);
                      if ( Instance )
                      {
                        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                        {
                          v53 = 50;
                          goto LABEL_83;
                        }
                      }
                      else
                      {
                        OutputBuffer = 0;
                        if ( ZwPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, &OutputBuffer, 1u) >= 0 )
                        {
                          if ( OutputBuffer )
                          {
                            v61 = PoRegisterPowerSettingCallback(
                                    0,
                                    &GUID_LOW_POWER_EPOCH,
                                    OnPowerSettingLowEpochNotificationWDI,
                                    this,
                                    &this->m_hLowPowerEpochHandler);
                            if ( v61 )
                            {
                              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                                goto LABEL_129;
                              LODWORD(v64) = v61;
                              LOBYTE(v56) = 2;
                              WPP_RECORDER_SF_D(
                                WPP_GLOBAL_Control->DeviceExtension,
                                v56,
                                1,
                                51,
                                (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
                                v64);
                            }
                          }
                        }
                        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                        {
                          v57 = 52;
                          LODWORD(v64) = 0;
                          LOBYTE(v56) = 4;
                          goto LABEL_89;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v54) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v54,
            1,
            40,
            (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
        }
        Instance = -1073741670;
        v4 = 0;
      }
LABEL_129:
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v67.Length + 40LL))(*(_QWORD *)&v67.Length, 1);
      if ( v69 )
        (**(void (__fastcall ***)(struct IEventContext *, __int64))v69)(v69, 1);
      if ( !v38 )
        goto LABEL_143;
      goto LABEL_142;
    }
    Instance = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_147;
    v43 = 32;
LABEL_69:
    LOBYTE(v37) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v37,
      1,
      v43,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
    goto LABEL_147;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      24,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  Instance = -1073741670;
LABEL_8:
  this->m_PendingInitHaltJob = 0;
  if ( Instance && v66 )
    CAdapter::Halt(this, v12);
  this->m_IsRecoverable = 1;
  if ( this->m_lResetRecovery )
    CAdapter::ReenumerateFailedAdapter(this);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v64) = Instance;
    LOBYTE(v12) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      53,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v64);
  }
  if ( v4 )
    operator delete((void *)v4);
  return Instance;
}

```

## disassembly

```asm
0x140077e34  mov     [rsp-8+arg_8], rbx
0x140077e39  push    rbp
0x140077e3a  push    rsi
0x140077e3b  push    rdi
0x140077e3c  push    r12
0x140077e3e  push    r13
0x140077e40  push    r14
0x140077e42  push    r15
0x140077e44  lea     rbp, [rsp-1C0h]
0x140077e4c  sub     rsp, 2C0h
0x140077e53  mov     rax, cs:__security_cookie
0x140077e5a  xor     rax, rsp
0x140077e5d  mov     [rbp+1F0h+var_40], rax
0x140077e64  xor     eax, eax
0x140077e66  mov     [rsp+2F0h+var_278], r9
0x140077e6b  mov     [rsp+2F0h+var_2AF], al
0x140077e6f  mov     ebx, eax
0x140077e71  mov     [rsp+2F0h+var_290], rax
0x140077e76  mov     r13, r8
0x140077e79  mov     [rsp+2F0h+var_298], eax
0x140077e7d  mov     r12, rdx
0x140077e80  mov     [rbp+1F0h+var_270], r8
0x140077e84  mov     r15, rcx
0x140077e87  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077e8e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140077e95  lea     rdx, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140077e9c  jz      short loc_140077ECB
0x140077e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140077ea5  cmp     byte ptr [rcx+29h], 5
0x140077ea9  jnb     short loc_140077EB1
0x140077eab  cmp     [rcx+48h], ax
0x140077eaf  jz      short loc_140077ECB
0x140077eb1  mov     rcx, [rcx+40h]
0x140077eb5  mov     r9d, 14h
0x140077ebb  mov     qword ptr [rsp+2F0h+OutputBufferLength], rdx
0x140077ec0  mov     dl, 5
0x140077ec2  lea     r8d, [r9-13h]
0x140077ec6  call    WPP_RECORDER_SF_
0x140077ecb  mov     rax, cs:?g_pWdiDriver@@3PEAVCWdiDriver@@EA; CWdiDriver * g_pWdiDriver
0x140077ed2  lea     r14, [r15+1308h]
0x140077ed9  add     rax, 28h ; '('
0x140077edd  mov     [r15+58h], r12
0x140077ee1  lea     rsi, [r13+28h]
0x140077ee5  mov     [r15+320h], rax
0x140077eec  mov     rdx, r14; InterfaceGuid
0x140077eef  mov     rcx, rsi; InterfaceLuid
0x140077ef2  call    cs:__imp_ConvertInterfaceLuidToGuid
0x140077ef9  nop     dword ptr [rax+rax+00h]
0x140077efe  mov     edi, eax
0x140077f00  test    eax, eax
0x140077f02  jz      loc_140077FE6
0x140077f08  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077f0f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140077f16  jz      short loc_140077F34
0x140077f18  mov     rcx, [rsi]
0x140077f1b  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x140077f1f  mov     [rsp+2F0h+var_2C8], rcx
0x140077f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f2b  mov     rcx, [rcx+40h]
0x140077f2f  call    WPP_RECORDER_SF_iD
0x140077f34  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140077f3b  xor     r12d, r12d
0x140077f3e  mov     [r15+12F8h], r12
0x140077f45  test    edi, edi
0x140077f47  jz      short loc_140077F58
0x140077f49  cmp     [rsp+2F0h+var_2AF], r12b
0x140077f4e  jz      short loc_140077F58
0x140077f50  mov     rcx, r15; this
0x140077f53  call    ?Halt@CAdapter@@QEAAXW4_NDIS_HALT_ACTION@@@Z; CAdapter::Halt(_NDIS_HALT_ACTION)
0x140077f58  mov     byte ptr [r15+12F5h], 1
0x140077f60  cmp     [r15+15C8h], r12d
0x140077f67  jz      short loc_140077F71
0x140077f69  mov     rcx, r15; this
0x140077f6c  call    ?ReenumerateFailedAdapter@CAdapter@@QEAAXXZ; CAdapter::ReenumerateFailedAdapter(void)
0x140077f71  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x140077f78  jz      short loc_140077FAC
0x140077f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f81  cmp     byte ptr [rcx+29h], 5
0x140077f85  jnb     short loc_140077F8E
0x140077f87  cmp     [rcx+48h], r12w
0x140077f8c  jz      short loc_140077FAC
0x140077f8e  mov     rcx, [rcx+40h]
0x140077f92  mov     r9d, 35h ; '5'
0x140077f98  mov     dword ptr [rsp+2F0h+var_2C8], edi
0x140077f9c  mov     dl, 5
0x140077f9e  mov     qword ptr [rsp+2F0h+OutputBufferLength], rsi
0x140077fa3  lea     r8d, [r9-34h]
0x140077fa7  call    WPP_RECORDER_SF_D
0x140077fac  test    rbx, rbx
0x140077faf  jz      short loc_140077FB9
0x140077fb1  mov     rcx, rbx; void *
0x140077fb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140077fb9  mov     eax, edi
0x140077fbb  mov     rcx, [rbp+1F0h+var_40]
0x140077fc2  xor     rcx, rsp; StackCookie
0x140077fc5  call    __security_check_cookie
0x140077fca  mov     rbx, [rsp+2F0h+arg_8]
0x140077fd2  add     rsp, 2C0h
0x140077fd9  pop     r15
0x140077fdb  pop     r14
0x140077fdd  pop     r13
0x140077fdf  pop     r12
0x140077fe1  pop     rdi
0x140077fe2  pop     rsi
0x140077fe3  pop     rbp
0x140077fe4  retn
0x140077fe6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140077fed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140077ff4  jz      short loc_14007801B
0x140077ff6  mov     eax, [r13+20h]
0x140077ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x140078001  mov     [rsp+2F0h+var_2B8], eax
0x140078005  mov     rax, [rsi]
0x140078008  mov     [rsp+2F0h+var_2C0], rax
0x14007800d  mov     rcx, [rcx+40h]
0x140078011  mov     [rsp+2F0h+var_2C8], r14
0x140078016  call    WPP_RECORDER_SF__guid_id
0x14007801b  lea     r13, [r15+78h]
0x14007801f  mov     rcx, r13; this
0x140078022  call    ?Initialize@CAdapterPropertyCache@@QEAAHXZ; CAdapterPropertyCache::Initialize(void)
0x140078027  mov     edi, eax
0x140078029  test    eax, eax
0x14007802b  jz      short loc_14007806E
0x14007802d  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140078034  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007803b  lea     rsi, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140078042  jz      loc_140077F3B
0x140078048  mov     rcx, cs:WPP_GLOBAL_Control
0x14007804f  mov     r9d, 17h
0x140078055  mov     dl, 2
0x140078057  mov     qword ptr [rsp+2F0h+OutputBufferLength], rsi
0x14007805c  mov     rcx, [rcx+40h]
0x140078060  lea     r8d, [r9-16h]
0x140078064  call    WPP_RECORDER_SF_
0x140078069  jmp     loc_140077F3B
0x14007806e  mov     edx, 10h
0x140078073  mov     r8d, 47696457h
0x140078079  lea     ecx, [rdx+30h]
0x14007807c  call    cs:__imp_ExAllocatePool2
0x140078083  nop     dword ptr [rax+rax+00h]
0x140078088  mov     rsi, rax
0x14007808b  test    rax, rax
0x14007808e  jz      loc_140078C74
0x140078094  mov     rdx, r13; CPropertyCache *
0x140078097  mov     [rax+8], rbx
0x14007809b  mov     rcx, rax; this
0x14007809e  mov     [rax], r12
0x1400780a1  call    ?LoadPropertiesFromRegistry@CRegistryHelper@@QEAAHPEAVCPropertyCache@@PEAU_WFC_REG_ENTRY@@K@Z; CRegistryHelper::LoadPropertiesFromRegistry(CPropertyCache *,_WFC_REG_ENTRY *,ulong)
0x1400780a6  xor     r12d, r12d
0x1400780a9  mov     edi, eax
0x1400780ab  test    eax, eax
0x1400780ad  jz      short loc_1400780F5
0x1400780af  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400780b6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400780bd  jz      loc_140078C27
0x1400780c3  lea     r9d, [r12+19h]
0x1400780c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400780cf  mov     r8d, 1
0x1400780d5  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x1400780d9  mov     dl, 2
0x1400780db  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400780e2  mov     qword ptr [rsp+2F0h+OutputBufferLength], rax
0x1400780e7  mov     rcx, [rcx+40h]
0x1400780eb  call    WPP_RECORDER_SF_D
0x1400780f0  jmp     loc_140078C27
0x1400780f5  lea     rax, aPldrcapability; "PldrCapability"
0x1400780fc  mov     qword ptr [rsp+2F0h+var_2A8.Length], 1E001Ch
0x140078105  lea     rdi, [r15+15D4h]
0x14007810c  mov     [rsp+2F0h+var_2A8.Buffer], rax
0x140078111  mov     r8, rdi; unsigned int *
0x140078114  lea     rdx, [rsp+2F0h+var_2A8]; struct _UNICODE_STRING *
0x140078119  mov     rcx, rsi; this
0x14007811c  call    ?ReadAdapterRegistryDword@CRegistryHelper@@QEAAHPEAU_UNICODE_STRING@@PEAK@Z; CRegistryHelper::ReadAdapterRegistryDword(_UNICODE_STRING *,ulong *)
0x140078121  test    eax, eax
0x140078123  jz      short loc_14007812D
0x140078125  mov     [rdi], r12d
0x140078128  mov     eax, r12d
0x14007812b  jmp     short loc_14007812F
0x14007812d  mov     eax, [rdi]
0x14007812f  mov     [r15+15D8h], r12d
0x140078136  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007813d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140078144  jz      short loc_140078177
0x140078146  mov     rcx, cs:WPP_GLOBAL_Control
0x14007814d  mov     r9d, 1Ah
0x140078153  mov     dword ptr [rsp+2F0h+var_2C0], r12d
0x140078158  mov     dl, 4
0x14007815a  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x14007815e  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140078165  mov     qword ptr [rsp+2F0h+OutputBufferLength], rax
0x14007816a  mov     rcx, [rcx+40h]
0x14007816e  lea     r8d, [r9-19h]
0x140078172  call    WPP_RECORDER_SF_DD
0x140078177  cmp     [rdi], r12d
0x14007817a  jz      short loc_1400781FB
0x14007817c  xor     edx, edx; Val
0x14007817e  mov     dword ptr [rsp+2F0h+var_2A8.Length], r12d
0x140078183  mov     r8d, 208h; Size
0x140078189  lea     rcx, [rbp+1F0h+SourceString]; void *
0x14007818d  call    memset
0x140078192  lea     r9, aParametersOemS; "Parameters\\OEM\\SystemCapabilities"
0x140078199  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wl"...
0x1400781a0  lea     rcx, [rbp+1F0h+SourceString]; SourceString
0x1400781a4  call    KmWlanStateSeparation_GetMutableRegistryKey
0x1400781a9  lea     r9, [rsp+2F0h+var_2A8]; unsigned int *
0x1400781ae  lea     r8, aWlanplatformle; "WLANPlatformLevelDeviceResetSupported"
0x1400781b5  lea     rdx, [rbp+1F0h+SourceString]; unsigned __int16 *
0x1400781b9  call    ?ReadRegDword@CAdapter@@QEAAHPEAG0PEAK@Z; CAdapter::ReadRegDword(ushort *,ushort *,ulong *)
0x1400781be  test    eax, eax
0x1400781c0  jnz     short loc_1400781FB
0x1400781c2  cmp     dword ptr [rsp+2F0h+var_2A8.Length], r12d
0x1400781c7  jnz     short loc_1400781FB
0x1400781c9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400781d0  jz      short loc_1400781F8
0x1400781d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400781d9  lea     r9d, [rax+1Bh]
0x1400781dd  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400781e4  mov     dl, 2
0x1400781e6  lea     r8d, [r9-1Ah]
0x1400781ea  mov     qword ptr [rsp+2F0h+OutputBufferLength], rax
0x1400781ef  mov     rcx, [rcx+40h]
0x1400781f3  call    WPP_RECORDER_SF_
0x1400781f8  mov     [rdi], r12d
0x1400781fb  lea     r8, [rsp+2F0h+var_2A8]; unsigned int *
0x140078200  mov     dword ptr [rsp+2F0h+var_2A8.Length], r12d
0x140078205  mov     edx, 41h ; 'A'; unsigned int
0x14007820a  mov     rcx, r13; this
0x14007820d  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140078212  test    eax, eax
0x140078214  jnz     short loc_14007827E
0x140078216  mov     r14d, dword ptr [rsp+2F0h+var_2A8.Length]
0x14007821b  cmp     r14d, 0FFFFFFFFh
0x14007821f  jz      short loc_140078277
0x140078221  test    r14d, r14d
0x140078224  mov     ecx, r12d
0x140078227  mov     eax, r12d
0x14007822a  setnz   cl
0x14007822d  cmp     [rdi], r12d
0x140078230  setnz   al
0x140078233  cmp     ecx, eax
0x140078235  jz      short loc_140078277
0x140078237  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007823e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140078245  jz      short loc_140078274
0x140078247  mov     rcx, cs:WPP_GLOBAL_Control
0x14007824e  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140078255  mov     r9d, 1Ch
0x14007825b  mov     dword ptr [rsp+2F0h+var_2C8], r14d
0x140078260  mov     dl, 2
0x140078262  mov     qword ptr [rsp+2F0h+OutputBufferLength], rax
0x140078267  mov     rcx, [rcx+40h]
0x14007826b  lea     r8d, [r9-1Bh]
0x14007826f  call    WPP_RECORDER_SF_D
0x140078274  mov     [rdi], r14d
0x140078277  lea     r14, WPP_RECORDER_INITIALIZED
0x14007827e  lea     r8, WPP_MAIN_CB.Queue+18h; unsigned int *
0x140078285  mov     edx, 2Fh ; '/'; unsigned int
0x14007828a  mov     rcx, r13; this
0x14007828d  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140078292  mov     rcx, r12
0x140078295  lea     rax, [rcx+rcx*2]
0x140078299  shl     rax, 5
0x14007829d  mov     [r15+rax+1398h], r15
0x1400782a5  lock inc dword ptr [rax+r15+1340h]
0x1400782ae  inc     rcx
0x1400782b1  cmp     rcx, 5
0x1400782b5  jnz     short loc_140078295
0x1400782b7  lea     edx, [rcx+26h]; unsigned int
0x1400782ba  or      r8d, 0FFFFFFFFh; unsigned int
0x1400782be  mov     rcx, r13; this
0x1400782c1  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400782c6  lea     rax, aComponentid; "ComponentId"
0x1400782cd  mov     qword ptr [rsp+2F0h+var_288.Length], 180016h
0x1400782d6  lea     r9, [rsp+2F0h+var_2A8]; struct WDFSTRING__ **
0x1400782db  mov     [rsp+2F0h+var_288.Buffer], rax
0x1400782e0  lea     rdx, [rsp+2F0h+var_288]; struct _UNICODE_STRING *
0x1400782e5  mov     qword ptr [rsp+2F0h+var_2A8.Length], r12
0x1400782ea  mov     rcx, rsi; this
0x1400782ed  call    ?ReadAdapterRegistryString@CRegistryHelper@@QEAAHPEAU_UNICODE_STRING@@PEAU_WDF_OBJECT_ATTRIBUTES@@PEAPEAUWDFSTRING__@@@Z; CRegistryHelper::ReadAdapterRegistryString(_UNICODE_STRING *,_WDF_OBJECT_ATTRIBUTES *,WDFSTRING__ * *)
0x1400782f2  test    eax, eax
0x1400782f4  jz      short loc_140078334
0x1400782f6  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400782fd  jz      short loc_14007832B
0x1400782ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140078306  mov     r9d, 1Dh
0x14007830c  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x140078310  mov     dl, 2
0x140078312  lea     rax, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x140078319  mov     qword ptr [rsp+2F0h+OutputBufferLength], rax
0x14007831e  mov     rcx, [rcx+40h]
0x140078322  lea     r8d, [r9-1Ch]
0x140078326  call    WPP_RECORDER_SF_D
0x14007832b  mov     [r15+3FA0h], r12
0x140078332  jmp     short loc_14007836E
0x140078334  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14007833b  lea     r8, [rbp+1F0h+var_268]
0x14007833f  mov     rdx, qword ptr [rsp+2F0h+var_2A8.Length]
0x140078344  xorps   xmm0, xmm0
0x140078347  mov     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x14007834e  movups  xmmword ptr [rbp+1F0h+var_268], xmm0
  ... truncated ...
```
