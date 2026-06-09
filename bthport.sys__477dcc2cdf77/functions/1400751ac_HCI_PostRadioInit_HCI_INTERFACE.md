# HCI_PostRadioInit(HCI_INTERFACE *)

- ea: `0x1400751ac`
- end: `0x140075dd4`
- name: `?HCI_PostRadioInit@@YAXPEAUHCI_INTERFACE@@@Z`
- size: `3112`
- prototype: `void __fastcall(struct HCI_INTERFACE *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140072690`

## callees

- `0x14000113c`
- `0x140001e54`
- `0x140002104`
- `0x1400023d8`
- `0x140004388`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005b4c`
- `0x14000c74c`
- `0x140011b74`
- `0x1400137c8`
- `0x140029bf0`
- `0x1400344dc`
- `0x140035860`
- `0x1400631f0`
- `0x140074ef4`
- `0x1400751ac`
- `0x140077a20`
- `0x14007f1f8`
- `0x14012f1f0`
- `0x14013e32c`
- `0x14013e364`
- `0x1401b2060`
- `0x1401c3da4`
- `0x1401ca070`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140075220`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140075220`
- `ntoskrnl!KeSetEvent` at `0x140075d58`
- `ntoskrnl!KeSetEvent` at `0x140075d58`

## pseudocode

```c
void __fastcall HCI_PostRadioInit(struct HCI_INTERFACE *a1)
{
  DEVICE_EXTENSION *DevExt; // r15
  char v3; // r12
  unsigned int LEBufferSize; // eax
  unsigned int MaxBytesPerAclDataPacket; // ecx
  DEVICE_EXTENSION *v6; // rcx
  unsigned __int64 HostSupportedFeatures; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  struct _SCO_INTERFACE *v10; // rcx
  __int64 v11; // rdx
  DEVICE_EXTENSION *v12; // rax
  int v13; // edx
  int v14; // r8d
  AvdtpOffload *v15; // rbx
  int v16; // r8d
  DEVICE_EXTENSION *v17; // rdx
  bool v18; // al
  struct _BIP *NextCommand; // rbx
  BOOL IsIdlePowerDownCapable; // r14d
  DEVICE_EXTENSION *v21; // rdx
  __int64 v22; // rdx
  unsigned int classOfDevice; // ecx
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  DEVICE_EXTENSION *v27; // r8
  unsigned __int64 address; // rdx
  unsigned __int64 v29; // rax
  unsigned int v30; // eax
  unsigned int v31; // ecx
  __int64 v32; // r8
  unsigned __int64 v33; // rdx
  int v34; // r9d
  unsigned __int64 v35; // rax
  DEVICE_EXTENSION *v36; // r8
  unsigned int v37; // ecx
  __int64 v38; // r8
  unsigned __int64 v39; // rdx
  unsigned __int8 v40; // al
  int v41; // r9d
  __int64 v42; // rdx
  int v43; // r8d
  int v44; // edx
  int v45; // r8d
  __int16 mfg; // [rsp+100h] [rbp-80h] BYREF
  __int16 v47; // [rsp+102h] [rbp-7Eh] BYREF
  __int16 v48; // [rsp+104h] [rbp-7Ch] BYREF
  unsigned __int16 hciRevision; // [rsp+106h] [rbp-7Ah] BYREF
  _WORD v50[2]; // [rsp+108h] [rbp-78h] BYREF
  int SupportedResetTypes; // [rsp+10Ch] [rbp-74h] BYREF
  BOOL tlvTelemetryEnabled; // [rsp+110h] [rbp-70h] BYREF
  BOOL v53; // [rsp+114h] [rbp-6Ch] BYREF
  int v54; // [rsp+118h] [rbp-68h] BYREF
  BOOL BroadcastIsoEnabled; // [rsp+11Ch] [rbp-64h] BYREF
  BOOL ConnectedIsoEnabled; // [rsp+120h] [rbp-60h] BYREF
  int v57; // [rsp+124h] [rbp-5Ch] BYREF
  unsigned __int64 SupportedFeatures; // [rsp+128h] [rbp-58h] BYREF
  unsigned __int64 v59; // [rsp+130h] [rbp-50h] BYREF
  unsigned __int64 v60; // [rsp+138h] [rbp-48h] BYREF
  unsigned __int64 LELocalSupportedStates; // [rsp+140h] [rbp-40h] BYREF
  unsigned __int64 LELocalSupportedFeatures; // [rsp+148h] [rbp-38h] BYREF
  unsigned __int64 lmpSupportedFeatures; // [rsp+150h] [rbp-30h] BYREF
  unsigned __int64 v64; // [rsp+158h] [rbp-28h] BYREF
  __int64 v65; // [rsp+160h] [rbp-20h] BYREF
  void *v66; // [rsp+168h] [rbp-18h] BYREF
  int v67; // [rsp+170h] [rbp-10h]
  void *SupportedCodecResult; // [rsp+178h] [rbp-8h] BYREF
  int v69; // [rsp+180h] [rbp+0h]
  unsigned __int64 p_SupportedCommandsMap; // [rsp+188h] [rbp+8h] BYREF
  int v71; // [rsp+190h] [rbp+10h]
  AvdtpOffload *v72; // [rsp+1F0h] [rbp+70h] BYREF
  unsigned __int8 lmpVersion; // [rsp+1F8h] [rbp+78h] BYREF
  unsigned __int8 hciVersion; // [rsp+200h] [rbp+80h] BYREF
  unsigned __int16 lmpSubversion; // [rsp+208h] [rbp+88h] BYREF

  DevExt = a1->DevExt;
  _InterlockedExchange(&a1->CriticalCommandRetry.Count, 0);
  v3 = 0;
  if ( a1->FirstTimeInit )
  {
    LEBufferSize = a1->LEBufferSize;
    MaxBytesPerAclDataPacket = a1->MaxBytesPerAclDataPacket;
    v3 = 1;
    if ( MaxBytesPerAclDataPacket <= LEBufferSize )
      MaxBytesPerAclDataPacket = LEBufferSize;
    ExInitializeNPagedLookasideList(
      &a1->WritePacketLookasideList,
      0,
      0,
      0x200u,
      MaxBytesPerAclDataPacket + 4,
      0x54494348u,
      0);
    a1->LookasideListInitialized = 1;
    HCI_CacheDeviceAddress(a1);
    HCI_LoadRadioCompatibilitySettings(a1);
    HCI_StampLocalRadioProperties(a1);
    DevExt->Hci->FirstTimeInit = 0;
  }
  wil::acquire_kspin_lock(&v66, &a1->HciLock);
  if ( a1->ControllerState != Failed )
    a1->ControllerState = Started;
  *(_OWORD *)a1->LECurrentHighPriorityAdvertisingBuffer = 0;
  *(_OWORD *)&a1->LECurrentHighPriorityAdvertisingBuffer[15] = 0;
  a1->LECurrentHighPriorityAdvertisingBufferLength = 0;
  *(_WORD *)&a1->LECurrentHighPriorityAdvertisingParameters.Connectable = 0;
  HIBYTE(a1->LECurrentHighPriorityAdvertisingParameters.AdvertisementInterval) = 0;
  *(_OWORD *)a1->LECurrentLowPriorityAdvertisingBuffer = 0;
  *(_OWORD *)&a1->LECurrentLowPriorityAdvertisingBuffer[15] = 0;
  a1->LECurrentLowPriorityAdvertisingBufferLength = 0;
  *(_WORD *)&a1->LECurrentLowPriorityAdvertisingParameters.Connectable = 0;
  HIBYTE(a1->LECurrentLowPriorityAdvertisingParameters.AdvertisementInterval) = 0;
  *(_WORD *)&a1->LECurrentScanningState = 0;
  a1->LECurrentScanningFilterPolicy = 0;
  a1->LECurrentScanningParameters = 0;
  v6 = a1->DevExt;
  a1->VsMsftFilterInfo.ControllerAdvFilterState = 2;
  HostSupportedFeatures = v6->HostSupportedFeatures;
  if ( a1->LEEnabled )
    v8 = HostSupportedFeatures | 4;
  else
    v8 = HostSupportedFeatures & 0xFFFFFFFFFFFFFFFBuLL;
  v6->HostSupportedFeatures = v8;
  if ( (a1->SupportedCommandsMap.RawMap[29] & 8) != 0 )
    a1->DevExt->HostSupportedFeatures |= 0x20u;
  if ( ScoInt_IsInBandSupported(a1->DevExt->Sco) )
  {
    *(_QWORD *)(v9 + 504) |= 8uLL;
  }
  else if ( ScoInt_IsSideBandSupported(v10) )
  {
    *(_QWORD *)(v11 + 504) |= 0x10uLL;
  }
  v12 = a1->DevExt;
  if ( v12->TransportCapabilities.ScoCanAlignData )
    v12->HostSupportedFeatures |= 0x40u;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&v66);
  if ( a1->VsMsftInfo.VsMsftDebugModeOn || SLOBYTE(a1->VsMsftInfo.SupportedFeatures) < 0 )
  {
    AvdtpOffload::Make(&v72);
    v15 = v72;
    if ( !v72 )
    {
      LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v14) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v14,
        a1->IfrLog,
        2,
        2,
        130,
        (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
      Controller::OnControllerInitializationComplete((Controller *)&a1->DevExt[-2].AvdtpOffload, 0);
      utl::unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>::~unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>(&v72);
      return;
    }
    wil::acquire_kspin_lock(&v66, &a1->HciLock);
    v17 = a1->DevExt;
    if ( v17->AvdtpOffload._MyDat._MyRealVal )
    {
      v18 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v16) = 1;
      LOBYTE(v17) = v18;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v17,
        v16,
        a1->IfrLog,
        4,
        2,
        131,
        (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
        a1->DevExt);
    }
    else
    {
      v72 = 0;
      v17->AvdtpOffload._MyDat._MyRealVal = v15;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&v66);
    utl::unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>::~unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>(&v72);
  }
  wil::acquire_kspin_lock(&v66, &a1->HciLock);
  NextCommand = HCI_GetNextCommand(a1);
  HCI_StartIdleTimer(a1, 1u);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&v66);
  if ( v3 )
  {
    IsIdlePowerDownCapable = PowerCoordinator::IsIdlePowerDownCapable((PowerCoordinator *)&DevExt[1].BtDevice.PhysicalDeviceObject);
    if ( (unsigned int)Feature_49201598__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( (unsigned int)Feature_56664216__private_IsEnabledDeviceUsageNoInline() )
      {
        if ( (unsigned int)dword_140197150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x800000000111LL) )
        {
          v21 = a1->DevExt;
          LOBYTE(v72) = a1->RadioCapacity.LESupportedMaxNumberOfAdvertisingSets;
          SupportedFeatures = a1->VsMsftInfo.SupportedFeatures;
          SupportedResetTypes = ErrorRecovery::GetSupportedResetTypes(&v21->ErrorRecoveryHandler);
          tlvTelemetryEnabled = a1->VsMsftInfo.tlvTelemetryEnabled;
          v59 = *(_QWORD *)(v22 + 504);
          classOfDevice = a1->LocalInfo.localInfo.classOfDevice;
          SupportedCodecResult = a1->SupportedCodecResult;
          LOWORD(v69) = a1->SupportedCodecResultSize;
          v24 = (a1->LocalInfo.localInfo.address >> 24) & 0xFFFFFF;
          v53 = IsIdlePowerDownCapable;
          v54 = v24;
          BroadcastIsoEnabled = a1->IsoInitializationState.BroadcastIsoEnabled;
          ConnectedIsoEnabled = a1->IsoInitializationState.ConnectedIsoEnabled;
          v60 = *(_QWORD *)a1->OptInFeatureFlags;
          LELocalSupportedStates = a1->LELocalSupportedStates;
          LELocalSupportedFeatures = a1->LELocalSupportedFeatures;
          lmpSupportedFeatures = a1->LocalInfo.radioInfo.lmpSupportedFeatures;
          v50[0] = a1->LocalInfo.radioInfo.lmpSubversion;
          lmpVersion = a1->LocalInfo.radioInfo.lmpVersion;
          mfg = a1->LocalInfo.radioInfo.mfg;
          p_SupportedCommandsMap = (unsigned __int64)&a1->SupportedCommandsMap;
          v47 = (classOfDevice >> 2) & 0x3F;
          v48 = (classOfDevice >> 8) & 0x1F;
          LOBYTE(v24) = a1->LocalInfo.localInfo.classOfDevice & 3;
          v71 = 64;
          hciVersion = v24;
          hciRevision = a1->LocalInfo.hciRevision;
          LOBYTE(lmpSubversion) = a1->LocalInfo.hciVersion;
          v64 = v22 + 720;
          v57 = (classOfDevice >> 13) & 0x7FF;
          v65 = 50333696;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
            v57,
            (unsigned int)byte_14018A909,
            v25,
            v26,
            (__int64)&v65,
            (__int64)&v64,
            (__int64)&lmpSubversion,
            (__int64)&hciRevision,
            (__int64)&hciVersion,
            (__int64)&v57,
            (__int64)&v48,
            (__int64)&v47,
            (__int64)&mfg,
            (__int64)&lmpVersion,
            (__int64)v50,
            (__int64)&lmpSupportedFeatures,
            (__int64)&LELocalSupportedFeatures,
            (__int64)&LELocalSupportedStates,
            (__int64)&v60,
            (__int64)&ConnectedIsoEnabled,
            (__int64)&BroadcastIsoEnabled,
            (__int64)&v54,
            (__int64)&SupportedCodecResult,
            (__int64)&p_SupportedCommandsMap,
            (__int64)&v53,
            (__int64)&v59,
            (__int64)&tlvTelemetryEnabled,
            (__int64)&SupportedResetTypes,
            (__int64)&SupportedFeatures,
            (__int64)&v72);
        }
      }
      else if ( (unsigned int)dword_140197150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x800000000111LL) )
      {
        v27 = a1->DevExt;
        address = a1->LocalInfo.localInfo.address;
        LOBYTE(v72) = a1->RadioCapacity.LESupportedMaxNumberOfAdvertisingSets;
        v29 = a1->VsMsftInfo.SupportedFeatures;
        v65 = address;
        v64 = v29;
        v30 = ErrorRecovery::GetSupportedResetTypes(&v27->ErrorRecoveryHandler);
        v31 = a1->LocalInfo.localInfo.classOfDevice;
        v57 = v30;
        ConnectedIsoEnabled = a1->VsMsftInfo.tlvTelemetryEnabled;
        lmpSupportedFeatures = *(_QWORD *)(v32 + 504);
        v66 = a1->SupportedCodecResult;
        LOWORD(v67) = a1->SupportedCodecResultSize;
        v53 = a1->IsoInitializationState.BroadcastIsoEnabled;
        tlvTelemetryEnabled = a1->IsoInitializationState.ConnectedIsoEnabled;
        LELocalSupportedFeatures = *(_QWORD *)a1->OptInFeatureFlags;
        LELocalSupportedStates = a1->LELocalSupportedStates;
        v60 = a1->LELocalSupportedFeatures;
        v59 = a1->LocalInfo.radioInfo.lmpSupportedFeatures;
        hciRevision = a1->LocalInfo.radioInfo.lmpSubversion;
        lmpVersion = a1->LocalInfo.radioInfo.lmpVersion;
        v48 = a1->LocalInfo.radioInfo.mfg;
        v47 = (v31 >> 2) & 0x3F;
        BroadcastIsoEnabled = IsIdlePowerDownCapable;
        mfg = (v31 >> 8) & 0x1F;
        LOBYTE(v30) = a1->LocalInfo.localInfo.classOfDevice & 3;
        SupportedCodecResult = &a1->SupportedCommandsMap;
        hciVersion = v30;
        v50[0] = a1->LocalInfo.hciRevision;
        LOBYTE(lmpSubversion) = a1->LocalInfo.hciVersion;
        SupportedFeatures = v32 + 720;
        v69 = 64;
        v54 = (v33 >> 24) & 0xFFFFFF;
        SupportedResetTypes = (v31 >> 13) & 0x7FF;
        p_SupportedCommandsMap = 50333696;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
          SupportedResetTypes,
          (unsigned int)&dword_14018A6CC,
          v32,
          v34,
          (__int64)&p_SupportedCommandsMap,
          (__int64)&SupportedFeatures,
          (__int64)&lmpSubversion,
          (__int64)v50,
          (__int64)&hciVersion,
          (__int64)&SupportedResetTypes,
          (__int64)&mfg,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&lmpVersion,
          (__int64)&hciRevision,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&LELocalSupportedStates,
          (__int64)&LELocalSupportedFeatures,
          (__int64)&tlvTelemetryEnabled,
          (__int64)&v53,
          (__int64)&v54,
          (__int64)&v66,
          (__int64)&SupportedCodecResult,
          (__int64)&BroadcastIsoEnabled,
          (__int64)&lmpSupportedFeatures,
          (__int64)&ConnectedIsoEnabled,
          (__int64)&v57,
          (__int64)&v64,
          (__int64)&v65,
          (__int64)&v72);
      }
    }
    else if ( (unsigned int)dword_140197150 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140197150, 0x800000000111LL) )
    {
      v35 = a1->VsMsftInfo.SupportedFeatures;
      v36 = a1->DevExt;
      p_SupportedCommandsMap = a1->LocalInfo.localInfo.address;
      v65 = v35;
      v57 = ErrorRecovery::GetSupportedResetTypes(&v36->ErrorRecoveryHandler);
      v37 = a1->LocalInfo.localInfo.classOfDevice;
      ConnectedIsoEnabled = a1->VsMsftInfo.tlvTelemetryEnabled;
      v64 = *(_QWORD *)(v38 + 504);
      SupportedCodecResult = a1->SupportedCodecResult;
      LOWORD(v69) = a1->SupportedCodecResultSize;
      v53 = a1->IsoInitializationState.BroadcastIsoEnabled;
      tlvTelemetryEnabled = a1->IsoInitializationState.ConnectedIsoEnabled;
      lmpSupportedFeatures = *(_QWORD *)a1->OptInFeatureFlags;
      LELocalSupportedFeatures = a1->LELocalSupportedStates;
      LELocalSupportedStates = a1->LELocalSupportedFeatures;
      v60 = a1->LocalInfo.radioInfo.lmpSupportedFeatures;
      lmpSubversion = a1->LocalInfo.radioInfo.lmpSubversion;
      LOBYTE(v72) = a1->LocalInfo.radioInfo.lmpVersion;
      hciRevision = a1->LocalInfo.radioInfo.mfg;
      v48 = (v37 >> 2) & 0x3F;
      BroadcastIsoEnabled = IsIdlePowerDownCapable;
      v47 = (v37 >> 8) & 0x1F;
      v40 = a1->LocalInfo.localInfo.classOfDevice & 3;
      v66 = &a1->SupportedCommandsMap;
      lmpVersion = v40;
      mfg = a1->LocalInfo.hciRevision;
      hciVersion = a1->LocalInfo.hciVersion;
      v59 = v38 + 720;
      v67 = 64;
      v54 = (v39 >> 24) & 0xFFFFFF;
      SupportedResetTypes = (v37 >> 13) & 0x7FF;
      SupportedFeatures = 50333696;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        SupportedResetTypes,
        (unsigned int)&word_14018A4AE,
        v38,
        v41,
        (__int64)&SupportedFeatures,
        (__int64)&v59,
        (__int64)&hciVersion,
        (__int64)&mfg,
        (__int64)&lmpVersion,
        (__int64)&SupportedResetTypes,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&hciRevision,
        (__int64)&v72,
        (__int64)&lmpSubversion,
        (__int64)&v60,
        (__int64)&LELocalSupportedStates,
        (__int64)&LELocalSupportedFeatures,
        (__int64)&lmpSupportedFeatures,
        (__int64)&tlvTelemetryEnabled,
        (__int64)&v53,
        (__int64)&v54,
        (__int64)&SupportedCodecResult,
        (__int64)&v66,
        (__int64)&BroadcastIsoEnabled,
        (__int64)&v64,
        (__int64)&ConnectedIsoEnabled,
        (__int64)&v57,
        (__int64)&v65,
        (__int64)&p_SupportedCommandsMap);
    }
  }
  if ( ScoInt_IsInBandSupported(a1->DevExt->Sco) )
    *(_QWORD *)(v42 + 504) &= ~0x20uLL;
  if ( NextCommand )
  {
    LOBYTE(v42) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v43) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v42,
      v43,
      a1->IfrLog,
      4,
      7,
      132,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      NextCommand);
    HCI_WriteCommand(a1, NextCommand);
  }
  HCI_LEResetScanParameters(a1, SniffModeAllowed, 0);
  HciLE_ResumeRandomAddressTimer(a1);
  if ( !a1->IsLEExtendedAdvertisingEnabled )
    KeSetEvent(&a1->ThreadEvents[8], 0, 0);
  LOBYTE(v44) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v45) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v44,
    v45,
    a1->IfrLog,
    4,
    2,
    133,
    (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
  Controller::OnControllerInitializationComplete((Controller *)&a1->DevExt[-2].AvdtpOffload, 1);
}

```

## disassembly

```asm
0x1400751ac  push    rbp
0x1400751ae  push    rbx
0x1400751af  push    rsi
0x1400751b0  push    rdi
0x1400751b1  push    r12
0x1400751b3  push    r13
0x1400751b5  push    r14
0x1400751b7  push    r15
0x1400751b9  lea     rbp, [rsp-28h]
0x1400751be  sub     rsp, 1A8h
0x1400751c5  mov     r15, [rcx+4A8h]
0x1400751cc  xor     ebx, ebx
0x1400751ce  mov     eax, ebx
0x1400751d0  mov     rdi, rcx
0x1400751d3  xchg    eax, [rcx+7ACh]
0x1400751d9  mov     r12b, bl
0x1400751dc  cmp     [rcx+0D3Dh], bl
0x1400751e2  jz      short loc_140075258
0x1400751e4  movzx   eax, word ptr [rcx+0DA0h]
0x1400751eb  mov     r9d, 200h; Flags
0x1400751f1  mov     ecx, [rcx+788h]
0x1400751f7  mov     r12b, 1
0x1400751fa  cmp     ecx, eax
0x1400751fc  mov     [rsp+1E0h+Depth], bx; Depth
0x140075201  mov     [rsp+1E0h+Tag], 54494348h; Tag
0x140075209  cmovbe  ecx, eax
0x14007520c  xor     r8d, r8d; Free
0x14007520f  xor     edx, edx; Allocate
0x140075211  lea     eax, [rcx+4]
0x140075214  lea     rcx, [rdi+0A00h]; Lookaside
0x14007521b  mov     [rsp+1E0h+Size], rax; Size
0x140075220  call    cs:__imp_ExInitializeNPagedLookasideList
0x140075227  nop     dword ptr [rax+rax+00h]
0x14007522c  mov     rcx, rdi; struct HCI_INTERFACE *
0x14007522f  mov     [rdi+0D18h], r12b
0x140075236  call    ?HCI_CacheDeviceAddress@@YAJPEAUHCI_INTERFACE@@@Z; HCI_CacheDeviceAddress(HCI_INTERFACE *)
0x14007523b  mov     rcx, rdi; struct HCI_INTERFACE *
0x14007523e  call    ?HCI_LoadRadioCompatibilitySettings@@YAXPEAUHCI_INTERFACE@@@Z; HCI_LoadRadioCompatibilitySettings(HCI_INTERFACE *)
0x140075243  mov     rcx, rdi; struct HCI_INTERFACE *
0x140075246  call    ?HCI_StampLocalRadioProperties@@YAXPEAUHCI_INTERFACE@@@Z; HCI_StampLocalRadioProperties(HCI_INTERFACE *)
0x14007524b  mov     rax, [r15+170h]
0x140075252  mov     [rax+0D3Dh], bl
0x140075258  lea     r14, [rdi+7B0h]
0x14007525f  mov     rdx, r14
0x140075262  lea     rcx, [rbp+60h+var_78]
0x140075266  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14007526b  cmp     dword ptr [rdi+20h], 3
0x14007526f  jz      short loc_140075274
0x140075271  mov     [rdi+20h], ebx
0x140075274  xor     eax, eax
0x140075276  xorps   xmm0, xmm0
0x140075279  movups  xmmword ptr [rdi+0EC4h], xmm0
0x140075280  movups  xmmword ptr [rdi+0ED3h], xmm0
0x140075287  mov     [rdi+0EE3h], bl
0x14007528d  mov     [rdi+0EE4h], ax
0x140075294  mov     [rdi+0EE6h], al
0x14007529a  movups  xmmword ptr [rdi+0EE7h], xmm0
0x1400752a1  movups  xmmword ptr [rdi+0EF6h], xmm0
0x1400752a8  mov     [rdi+0F06h], bl
0x1400752ae  mov     [rdi+0F07h], ax
0x1400752b5  mov     [rdi+0F09h], al
0x1400752bb  mov     [rdi+0E29h], bx
0x1400752c2  mov     [rdi+0E2Bh], bl
0x1400752c8  mov     [rdi+0E2Ch], eax
0x1400752ce  mov     rcx, [rdi+4A8h]
0x1400752d5  mov     byte ptr [rdi+1050h], 2
0x1400752dc  mov     rax, [rcx+1F8h]
0x1400752e3  cmp     [rdi+0D78h], bl
0x1400752e9  jz      short loc_1400752F1
0x1400752eb  or      rax, 4
0x1400752ef  jmp     short loc_1400752F5
0x1400752f1  and     rax, 0FFFFFFFFFFFFFFFBh
0x1400752f5  lea     r13, [rdi+0CC8h]
0x1400752fc  mov     [rcx+1F8h], rax
0x140075303  test    byte ptr [r13+1Dh], 8
0x140075308  jz      short loc_140075319
0x14007530a  mov     rax, [rdi+4A8h]
0x140075311  or      qword ptr [rax+1F8h], 20h
0x140075319  mov     rdx, [rdi+4A8h]
0x140075320  mov     rcx, [rdx+188h]; struct _SCO_INTERFACE *
0x140075327  call    ?ScoInt_IsInBandSupported@@YAEPEAU_SCO_INTERFACE@@@Z; ScoInt_IsInBandSupported(_SCO_INTERFACE *)
0x14007532c  test    al, al
0x14007532e  jz      short loc_14007533A
0x140075330  or      qword ptr [rdx+1F8h], 8
0x140075338  jmp     short loc_14007534B
0x14007533a  call    ?ScoInt_IsSideBandSupported@@YAEPEAU_SCO_INTERFACE@@@Z; ScoInt_IsSideBandSupported(_SCO_INTERFACE *)
0x14007533f  test    al, al
0x140075341  jz      short loc_14007534B
0x140075343  or      qword ptr [rdx+1F8h], 10h
0x14007534b  mov     rax, [rdi+4A8h]
0x140075352  cmp     [rax+220h], bl
0x140075358  jz      short loc_140075362
0x14007535a  or      qword ptr [rax+1F8h], 40h
0x140075362  lea     rcx, [rbp+60h+var_78]
0x140075366  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14007536b  lea     rsi, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140075372  cmp     [rdi+1033h], bl
0x140075378  jnz     short loc_140075388
0x14007537a  mov     al, [rdi+1040h]
0x140075380  test    al, al
0x140075382  jns     loc_140075497
0x140075388  lea     rcx, [rbp+60h+arg_0]
0x14007538c  call    ?Make@AvdtpOffload@@SA?AV?$unique_ptr@VAvdtpOffload@@U?$default_delete@VAvdtpOffload@@@utl@@@utl@@XZ; AvdtpOffload::Make(void)
0x140075391  mov     rbx, [rbp+60h+arg_0]
0x140075395  test    rbx, rbx
0x140075398  jnz     short loc_14007540A
0x14007539a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400753a1  mov     eax, [rcx+2Ch]
0x1400753a4  test    al, 2
0x1400753a6  jz      short loc_1400753B2
0x1400753a8  cmp     byte ptr [rcx+29h], 2
0x1400753ac  jb      short loc_1400753B2
0x1400753ae  mov     dl, 1
0x1400753b0  jmp     short loc_1400753B4
0x1400753b2  xor     dl, dl
0x1400753b4  mov     r9, [rdi+10B0h]
0x1400753bb  lea     rsi, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x1400753c2  mov     rcx, [rcx+18h]
0x1400753c6  mov     r8b, 1
0x1400753c9  mov     [rsp+1E0h+var_1A8], rsi
0x1400753ce  mov     [rsp+1E0h+Depth], 82h
0x1400753d5  mov     [rsp+1E0h+Tag], 2
0x1400753dd  mov     byte ptr [rsp+1E0h+Size], 2
0x1400753e2  call    WPP_RECORDER_AND_TRACE_SF_
0x1400753e7  mov     rcx, [rdi+4A8h]
0x1400753ee  xor     edx, edx; bool
0x1400753f0  sub     rcx, 300h; this
0x1400753f7  call    ?OnControllerInitializationComplete@Controller@@QEAAX_N@Z; Controller::OnControllerInitializationComplete(bool)
0x1400753fc  lea     rcx, [rbp+60h+arg_0]
0x140075400  call    ??1?$unique_ptr@VAvdtpOffload@@U?$default_delete@VAvdtpOffload@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>::~unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>(void)
0x140075405  jmp     loc_140075DBF
0x14007540a  mov     rdx, r14
0x14007540d  lea     rcx, [rbp+60h+var_78]
0x140075411  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x140075416  mov     rdx, [rdi+4A8h]
0x14007541d  cmp     qword ptr [rdx+2E0h], 0
0x140075425  jnz     short loc_140075438
0x140075427  mov     [rbp+60h+arg_0], 0
0x14007542f  mov     [rdx+2E0h], rbx
0x140075436  jmp     short loc_140075485
0x140075438  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14007543f  mov     eax, [rcx+2Ch]
0x140075442  test    al, 2
0x140075444  jz      short loc_140075450
0x140075446  cmp     byte ptr [rcx+29h], 4
0x14007544a  jb      short loc_140075450
0x14007544c  mov     al, 1
0x14007544e  jmp     short loc_140075452
0x140075450  xor     al, al
0x140075452  mov     r9, [rdi+10B0h]
0x140075459  mov     r8b, 1
0x14007545c  mov     rcx, [rcx+18h]
0x140075460  mov     [rsp+1E0h+var_1A0], rdx
0x140075465  mov     dl, al
0x140075467  mov     [rsp+1E0h+var_1A8], rsi
0x14007546c  mov     [rsp+1E0h+Depth], 83h
0x140075473  mov     [rsp+1E0h+Tag], 2
0x14007547b  mov     byte ptr [rsp+1E0h+Size], 4
0x140075480  call    WPP_RECORDER_AND_TRACE_SF_q
0x140075485  lea     rcx, [rbp+60h+var_78]
0x140075489  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14007548e  lea     rcx, [rbp+60h+arg_0]
0x140075492  call    ??1?$unique_ptr@VAvdtpOffload@@U?$default_delete@VAvdtpOffload@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>::~unique_ptr<AvdtpOffload,utl::default_delete<AvdtpOffload>>(void)
0x140075497  mov     rdx, r14
0x14007549a  lea     rcx, [rbp+60h+var_78]
0x14007549e  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x1400754a3  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400754a6  call    ?HCI_GetNextCommand@@YAPEAU_BIP@@PEAUHCI_INTERFACE@@@Z; HCI_GetNextCommand(HCI_INTERFACE *)
0x1400754ab  mov     dl, 1; unsigned __int8
0x1400754ad  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400754b0  mov     rbx, rax
0x1400754b3  call    ?HCI_StartIdleTimer@@YAXPEAUHCI_INTERFACE@@E@Z; HCI_StartIdleTimer(HCI_INTERFACE *,uchar)
0x1400754b8  lea     rcx, [rbp+60h+var_78]
0x1400754bc  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x1400754c1  test    r12b, r12b
0x1400754c4  jz      loc_140075CB2
0x1400754ca  lea     rcx, [r15+300h]; this
0x1400754d1  call    ?IsIdlePowerDownCapable@PowerCoordinator@@QEBA_NXZ; PowerCoordinator::IsIdlePowerDownCapable(void)
0x1400754d6  movzx   r14d, al
0x1400754da  call    Feature_49201598__private_IsEnabledDeviceUsageNoInline
0x1400754df  test    eax, eax
0x1400754e1  jz      loc_140075A29
0x1400754e7  call    Feature_56664216__private_IsEnabledDeviceUsageNoInline
0x1400754ec  test    eax, eax
0x1400754ee  jz      loc_140075786
0x1400754f4  mov     ecx, cs:dword_140197150
0x1400754fa  cmp     ecx, 4
0x1400754fd  jbe     loc_140075CB2
0x140075503  mov     rdx, 800000000111h
0x14007550d  lea     rcx, dword_140197150
0x140075514  call    _tlgKeywordOn
0x140075519  test    al, al
0x14007551b  jz      loc_140075CB2
0x140075521  mov     al, [rdi+0DD6h]
0x140075527  mov     rdx, [rdi+4A8h]
0x14007552e  mov     byte ptr [rbp+60h+arg_0], al
0x140075531  mov     rax, [rdi+1040h]
0x140075538  mov     [rbp+60h+var_B8], rax
0x14007553c  lea     rcx, [rdx+258h]; this
0x140075543  call    ?GetSupportedResetTypes@ErrorRecovery@@QEAAKXZ; ErrorRecovery::GetSupportedResetTypes(void)
0x140075548  mov     [rbp+60h+var_D4], eax
0x14007554b  movzx   eax, byte ptr [rdi+1048h]
0x140075552  mov     [rbp+60h+var_D0], eax
0x140075555  mov     rax, [rdx+1F8h]
0x14007555c  mov     [rbp+60h+var_B0], rax
0x140075560  mov     rax, [rdi+0F50h]
0x140075567  mov     ecx, [rdi+12Ch]
0x14007556d  mov     [rbp+60h+var_68], rax
0x140075571  movzx   eax, word ptr [rdi+0F48h]
0x140075578  mov     word ptr [rbp+60h+var_60], ax
0x14007557c  mov     rax, [rdi+124h]
0x140075583  shr     rax, 18h
0x140075587  and     eax, 0FFFFFFh
0x14007558c  mov     [rbp+60h+var_CC], r14d
0x140075590  mov     [rbp+60h+var_C8], eax
0x140075593  movzx   eax, byte ptr [rdi+1219h]
0x14007559a  mov     [rbp+60h+var_C4], eax
0x14007559d  movzx   eax, byte ptr [rdi+1218h]
0x1400755a4  mov     [rbp+60h+var_C0], eax
0x1400755a7  mov     rax, [rdi+0DC0h]
0x1400755ae  mov     [rbp+60h+var_A8], rax
0x1400755b2  mov     rax, [rdi+0DB8h]
0x1400755b9  mov     [rbp+60h+var_A0], rax
0x1400755bd  mov     rax, [rdi+0DB0h]
0x1400755c4  mov     [rbp+60h+var_98], rax
0x1400755c8  mov     rax, [rdi+233h]
0x1400755cf  mov     [rbp+60h+var_90], rax
0x1400755d3  movzx   eax, word ptr [rdi+23Dh]
0x1400755da  mov     [rbp+60h+var_D8], ax
0x1400755de  mov     al, [rdi+23Fh]
0x1400755e4  mov     [rbp+60h+arg_8], al
0x1400755e7  movzx   eax, word ptr [rdi+23Bh]
0x1400755ee  mov     [rbp+60h+var_E0], ax
0x1400755f2  mov     eax, ecx
0x1400755f4  shr     eax, 2
0x1400755f7  and     ax, 3Fh
0x1400755fb  mov     [rbp+60h+var_58], r13
0x1400755ff  mov     [rbp+60h+var_DE], ax
0x140075603  mov     eax, ecx
0x140075605  shr     eax, 8
0x140075608  and     ax, 1Fh
0x14007560c  shr     ecx, 0Dh
0x14007560f  mov     [rbp+60h+var_DC], ax
0x140075613  and     ecx, 7FFh
0x140075619  mov     al, [rdi+12Ch]
0x14007561f  and     al, 3
0x140075621  mov     [rbp+60h+var_50], 40h ; '@'
0x140075628  mov     [rbp+60h+arg_10], al
0x14007562e  movzx   eax, word ptr [rdi+230h]
0x140075635  mov     [rbp+60h+var_DA], ax
0x140075639  mov     al, [rdi+232h]
0x14007563f  mov     byte ptr [rbp+60h+arg_18], al
0x140075645  lea     rax, [rdx+2D0h]
0x14007564c  mov     [rbp+60h+var_88], rax
0x140075650  lea     rax, [rbp+60h+arg_0]
0x140075654  mov     [rsp+1E0h+var_F8], rax
0x14007565c  lea     rax, [rbp+60h+var_B8]
0x140075660  mov     [rsp+1E0h+var_100], rax
0x140075668  lea     rax, [rbp+60h+var_D4]
0x14007566c  mov     [rsp+1E0h+var_108], rax
0x140075674  lea     rax, [rbp+60h+var_D0]
0x140075678  mov     [rsp+1E0h+var_110], rax
0x140075680  lea     rax, [rbp+60h+var_B0]
0x140075684  mov     [rsp+1E0h+var_118], rax
0x14007568c  lea     rax, [rbp+60h+var_CC]
0x140075690  mov     [rsp+1E0h+var_120], rax
0x140075698  lea     rax, [rbp+60h+var_58]
0x14007569c  mov     [rsp+1E0h+var_128], rax
0x1400756a4  lea     rax, [rbp+60h+var_68]
0x1400756a8  mov     [rsp+1E0h+var_130], rax
0x1400756b0  lea     rax, [rbp+60h+var_C8]
0x1400756b4  mov     [rsp+1E0h+var_138], rax
0x1400756bc  mov     [rbp+60h+var_BC], ecx
0x1400756bf  mov     [rbp+60h+var_80], 3000800h
0x1400756c7  lea     rax, [rbp+60h+var_C4]
0x1400756cb  mov     [rsp+1E0h+var_140], rax
0x1400756d3  lea     rdx, byte_14018A909
0x1400756da  lea     rax, [rbp+60h+var_C0]
0x1400756de  mov     [rsp+1E0h+var_148], rax
0x1400756e6  lea     rax, [rbp+60h+var_A8]
0x1400756ea  mov     [rsp+1E0h+var_150], rax
0x1400756f2  lea     rax, [rbp+60h+var_A0]
0x1400756f6  mov     [rsp+1E0h+var_158], rax
0x1400756fe  lea     rax, [rbp+60h+var_98]
0x140075702  mov     [rsp+1E0h+var_160], rax
0x14007570a  lea     rax, [rbp+60h+var_90]
0x14007570e  mov     [rsp+1E0h+var_168], rax
0x140075713  lea     rax, [rbp+60h+var_D8]
0x140075717  mov     [rsp+1E0h+var_170], rax
0x14007571c  lea     rax, [rbp+60h+arg_8]
0x140075720  mov     [rsp+1E0h+var_178], rax
0x140075725  lea     rax, [rbp+60h+var_E0]
0x140075729  mov     [rsp+1E0h+var_180], rax
0x14007572e  lea     rax, [rbp+60h+var_DE]
0x140075732  mov     [rsp+1E0h+var_188], rax
0x140075737  lea     rax, [rbp+60h+var_DC]
0x14007573b  mov     [rsp+1E0h+var_190], rax
0x140075740  lea     rax, [rbp+60h+var_BC]
0x140075744  mov     [rsp+1E0h+var_198], rax
0x140075749  lea     rax, [rbp+60h+arg_10]
  ... truncated ...
```
