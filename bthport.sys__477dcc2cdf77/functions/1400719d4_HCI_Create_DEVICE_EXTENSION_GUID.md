# HCI_Create(DEVICE_EXTENSION *,_GUID *)

- ea: `0x1400719d4`
- end: `0x140072689`
- name: `?HCI_Create@@YAPEAUHCI_INTERFACE@@PEAUDEVICE_EXTENSION@@PEAU_GUID@@@Z`
- size: `3253`
- prototype: `struct HCI_INTERFACE *__fastcall(struct DEVICE_EXTENSION *, struct _GUID *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002a5b8`

## callees

- `0x140005608`
- `0x140005690`
- `0x140006200`
- `0x14000abf4`
- `0x14000f94c`
- `0x1400272a4`
- `0x14002b2b4`
- `0x14006886c`
- `0x1400702bc`
- `0x1400704e0`
- `0x140070a90`
- `0x1400719d4`
- `0x140074960`
- `0x14015b9d8`
- `0x140161c78`
- `0x140161d7c`
- `0x140162f00`
- `0x140165540`
- `0x140165580`
- `0x1401b3990`
- `0x1401b9a2c`
- `0x1401b9c3c`
- `0x1401ca898`
- `0x1401d239c`
- `0x1401d2fe4`
- `0x1401e3c34`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140071e37`
- `ntoskrnl!IoAllocateWorkItem` at `0x140071e37`
- `ntoskrnl!KeInitializeTimer` at `0x140072006`
- `ntoskrnl!KeInitializeTimer` at `0x140072006`
- `ntoskrnl!KeInitializeDpc` at `0x140072023`
- `ntoskrnl!KeInitializeDpc` at `0x140072253`
- `ntoskrnl!KeInitializeDpc` at `0x14007242a`
- `ntoskrnl!KeInitializeDpc` at `0x140072023`
- `ntoskrnl!KeInitializeDpc` at `0x140072253`
- `ntoskrnl!KeInitializeDpc` at `0x14007242a`
- `ntoskrnl!KeInitializeTimerEx` at `0x140072236`
- `ntoskrnl!KeInitializeTimerEx` at `0x14007240d`
- `ntoskrnl!KeInitializeTimerEx` at `0x140072236`
- `ntoskrnl!KeInitializeTimerEx` at `0x14007240d`
- `ntoskrnl!ExAllocatePool2` at `0x140071a3a`
- `ntoskrnl!ExAllocatePool2` at `0x140071ac1`
- `ntoskrnl!ExAllocatePool2` at `0x140071a3a`
- `ntoskrnl!ExAllocatePool2` at `0x140071ac1`
- `ntoskrnl!KeInitializeSpinLock` at `0x140071d4a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140071d4a`
- `ntoskrnl!KeInitializeEvent` at `0x1400721d6`
- `ntoskrnl!KeInitializeEvent` at `0x1400721ee`
- `ntoskrnl!KeInitializeEvent` at `0x14007220e`
- `ntoskrnl!KeInitializeEvent` at `0x1400721d6`
- `ntoskrnl!KeInitializeEvent` at `0x1400721ee`
- `ntoskrnl!KeInitializeEvent` at `0x14007220e`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140071bcf`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140071c95`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140071bcf`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140071c95`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140071bb8`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140071c7e`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140071bb8`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x140071c7e`

## pseudocode

```c
struct HCI_INTERFACE *__fastcall HCI_Create(struct DEVICE_EXTENSION *a1, struct _GUID *a2)
{
  DeviceListProcessor *Pool2; // rax
  int v4; // edx
  int v5; // r8d
  DeviceListProcessor *v6; // rax
  DeviceListProcessor *v7; // r15
  PDEVICE_OBJECT v8; // rcx
  HCI_INTERFACE *v9; // rax
  HCI_INTERFACE *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rbx
  const char *v13; // r8
  __int128 *v14; // rcx
  __int64 v15; // rax
  __int128 *v16; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 Default; // rax
  const char *v19; // rax
  __int64 v20; // rdx
  __int128 *v21; // rcx
  __int128 *v22; // rax
  __int64 v23; // rax
  struct _DEVICE_OBJECT *m_controlDevice; // rcx
  PIO_WORKITEM WorkItem; // rax
  int v26; // edx
  int v27; // r8d
  int v28; // eax
  int v29; // edx
  int v30; // r8d
  unsigned int v31; // eax
  __int64 i; // rbx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  int v36; // ebx
  PDEVICE_OBJECT v37; // rcx
  struct _GUID *v38; // rbx
  unsigned int *v39; // r8
  DeviceListProcessor *MyRealVal; // rdx
  __int16 v42; // [rsp+30h] [rbp-D0h]
  __int16 v43; // [rsp+30h] [rbp-D0h]
  DeviceListProcessor *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  struct _GUID *v49; // [rsp+88h] [rbp-78h]
  __int128 v50; // [rsp+90h] [rbp-70h] BYREF
  __int128 v51; // [rsp+A0h] [rbp-60h]
  __int128 v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v54[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v55; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v56; // [rsp+F8h] [rbp-8h]
  __int128 v57; // [rsp+108h] [rbp+8h] BYREF
  __int64 v58; // [rsp+118h] [rbp+18h]
  char v59[8]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v60[14]; // [rsp+128h] [rbp+28h] BYREF

  v49 = a2;
  v58 = 0;
  v45 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  Pool2 = (DeviceListProcessor *)ExAllocatePool2(64, 408, 1346917442);
  if ( !Pool2 )
  {
    v44 = 0;
LABEL_75:
    v8 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v42 = 10;
    goto LABEL_79;
  }
  v6 = DeviceListProcessor::DeviceListProcessor(Pool2, (struct Fdo *)&a1[-2].EtwLogger);
  v44 = v6;
  v7 = v6;
  if ( !v6 )
    goto LABEL_75;
  if ( (int)DeviceListProcessor::Initialize(v6) < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v42 = 11;
LABEL_79:
    LOBYTE(v5) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v8->AttachedDevice,
      v4,
      v5,
      v8->DeviceExtension,
      2,
      2,
      v42,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
    goto LABEL_80;
  }
  v9 = (HCI_INTERFACE *)ExAllocatePool2(64, 4864, 1346917442);
  v10 = v9;
  if ( !v9 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v4) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v4) = 0;
    v42 = 12;
    goto LABEL_79;
  }
  HCI_INTERFACE::HCI_INTERFACE(v9, a1);
  v10->Signature = 1229538120;
  v11 = 16;
  HIDWORD(v56) = 16;
  v12 = 2147483646;
  v10->BtDevice = &a1->BtDevice;
  LODWORD(v55) = 56;
  v13 = "Default";
  LOBYTE(v57) = 0;
  v14 = &v57;
  *(_QWORD *)&v56 = 0;
  BYTE8(v56) = 0;
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*v13 )
      break;
    *(_BYTE *)v14 = *v13++;
    v14 = (__int128 *)((char *)v14 + 1);
    --v15;
    --v11;
  }
  while ( v11 );
  v16 = (__int128 *)((char *)v14 - 1);
  if ( v11 )
    v16 = v14;
  v17 = WPP_GLOBAL_Control;
  *(_BYTE *)v16 = 0;
  v58 = 0x200000002LL;
  *(_QWORD *)((char *)&v55 + 4) = 0x200050485442LL;
  HIDWORD(v55) = 512;
  if ( (unsigned int)imp_WppRecorderLogCreate(v17, &v55, &v45) )
  {
    Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    v45 = Default;
  }
  else
  {
    Default = v45;
  }
  v10->IfrLog = (RECORDER_LOG__ *)Default;
  HIDWORD(v56) = 16;
  v19 = "HCI";
  v20 = 16;
  LODWORD(v55) = 56;
  v21 = &v57;
  LOBYTE(v57) = 0;
  *(_QWORD *)&v56 = 0;
  BYTE8(v56) = 0;
  do
  {
    if ( !v12 )
      break;
    if ( !*v19 )
      break;
    *(_BYTE *)v21 = *v19++;
    v21 = (__int128 *)((char *)v21 + 1);
    --v12;
    --v20;
  }
  while ( v20 );
  v22 = (__int128 *)((char *)v21 - 1);
  if ( v20 )
    v22 = v21;
  *(_BYTE *)v22 = 0;
  v58 = 0x200000002LL;
  *(_QWORD *)((char *)&v55 + 4) = 0x200050485442LL;
  HIDWORD(v55) = 512;
  wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(
    &v10->HciIfr,
    0);
  if ( (unsigned int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v55, &v10->HciIfr) )
  {
    v23 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(
      &v10->HciIfr,
      v23);
  }
  RefObj_InitEx(
    (_DWORD)v10 + 8,
    (unsigned int)HCI_RefDestroy,
    (_DWORD)v10,
    130,
    (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciinterface.cpp",
    BthLib_RefObjDebugEnabled);
  *(_WORD *)&v10->IfLinkKeyAuthenticate = 256;
  v10->AlwaysChangeKeys = 0;
  v10->AuthenticationRequirementOverride = MITMProtectionNotDefined;
  v10->IoCapabilityOverride = IoCaps_Undefined;
  v10->HciPacketTypes = -13288;
  v10->IoCapability = IoCaps_NoInputNoOutput;
  v10->BLE_IoCapability = IoCaps_NoInputNoOutput;
  *(_WORD *)&v10->SimplePairingMode = 1;
  *(_WORD *)&v10->AssumeBRSCKeysAreValidated = 256;
  v10->SimplePairingForceIncomingEncryption = 1;
  v10->IsAutomaticLEEncryptionEnabled = 1;
  v10->BondableMode = 1;
  v10->DefaultAuthenticationRequirements = MITMProtectionNotRequired;
  KeInitializeSpinLock(&v10->HciLock);
  v10->NumDevices = 0;
  v10->CmdSentList.Blink = &v10->CmdSentList;
  v10->CmdSentList.Flink = &v10->CmdSentList;
  v10->CmdPendingQueue.Blink = &v10->CmdPendingQueue;
  v10->CmdPendingQueue.Flink = &v10->CmdPendingQueue;
  v10->InitCmdPendingQueue.Blink = &v10->InitCmdPendingQueue;
  v10->InitCmdPendingQueue.Flink = &v10->InitCmdPendingQueue;
  v10->BestEffortCxnWriteQueue.Blink = &v10->BestEffortCxnWriteQueue;
  v10->BestEffortCxnWriteQueue.Flink = &v10->BestEffortCxnWriteQueue;
  v10->GuaranteedCxnWriteQueue.Blink = &v10->GuaranteedCxnWriteQueue;
  v10->GuaranteedCxnWriteQueue.Flink = &v10->GuaranteedCxnWriteQueue;
  v10->BipQueue.Blink = &v10->BipQueue;
  v10->BipQueue.Flink = &v10->BipQueue;
  v10->HciCxnList.Blink = &v10->HciCxnList;
  v10->HciCxnList.Flink = &v10->HciCxnList;
  v10->HciCxnPending.Blink = &v10->HciCxnPending;
  v10->HciCxnPending.Flink = &v10->HciCxnPending;
  v10->HciCxnZombie.Blink = &v10->HciCxnZombie;
  v10->HciCxnZombie.Flink = &v10->HciCxnZombie;
  v10->HciPendedAclList.Blink = &v10->HciPendedAclList;
  v10->HciPendedAclList.Flink = &v10->HciPendedAclList;
  v10->DeviceList.Blink = &v10->DeviceList;
  v10->DeviceList.Flink = &v10->DeviceList;
  v10->DisposableDeviceList.Blink = &v10->DisposableDeviceList;
  v10->DisposableDeviceList.Flink = &v10->DisposableDeviceList;
  v10->VsMsftFilterInfo.TrackedFiltersListEntry.Blink = &v10->VsMsftFilterInfo.TrackedFiltersListEntry;
  v10->VsMsftFilterInfo.TrackedFiltersListEntry.Flink = &v10->VsMsftFilterInfo.TrackedFiltersListEntry;
  v10->NumberOfDisposableDevices = 0;
  if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline() )
    m_controlDevice = Driver::GetInstance()->m_controlDevice;
  else
    m_controlDevice = v10->BtDevice->FunctionalDeviceObject;
  WorkItem = IoAllocateWorkItem(m_controlDevice);
  wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&void IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::reset(
    &v10->DibDestructionWorkItem,
    WorkItem);
  if ( !v10->DibDestructionWorkItem.m_ptr )
  {
    v37 = WPP_GLOBAL_Control;
    LOBYTE(v26) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v43 = 13;
LABEL_63:
    LOBYTE(v27) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v37->AttachedDevice,
      v26,
      v27,
      v10->IfrLog,
      2,
      2,
      v43,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids);
LABEL_49:
    RefObj_ReleaseEx(
      &v10->RefObj,
      v10,
      646,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciinterface.cpp");
LABEL_80:
    utl::unique_ptr<DeviceListProcessor,utl::default_delete<DeviceListProcessor>>::~unique_ptr<DeviceListProcessor,utl::default_delete<DeviceListProcessor>>(&v44);
    return 0;
  }
  LockedList_Init(&v10->InquiryList, &v10->HciLock);
  v10->InquiryList.CancelRoutine = BthInquiryCancelRoutine;
  v10->InquiryList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(&v10->LEConnectionSpeedBoostRequestList, &v10->HciLock);
  v10->LEConnectionSpeedBoostRequestList.CancelRoutine = (void (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HciLE_ConnectionSpeedBoostRequestCancel;
  v10->LEConnectionSpeedBoostRequestList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(&v10->SensitiveTrafficRequests, &v10->HciLock);
  v10->SensitiveTrafficRequests.CancelRoutine = (void (__fastcall *)(_DEVICE_OBJECT *, _IRP *))SensitiveTrafficRequestCancel;
  v10->SensitiveTrafficRequests.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(&v10->VendorIrpList, &v10->VendorIrpList.LockedList.SpinLock);
  v10->VendorIrpList.CancelRoutine = HCI_CancelVendorIrp;
  v10->VendorIrpList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(
    &v10->VsMsftFilterInfo.HWOffloadedFilteringIrpList,
    &v10->VsMsftFilterInfo.HWOffloadedFilteringIrpList.LockedList.SpinLock);
  v10->VsMsftFilterInfo.HWOffloadedFilteringIrpList.CancelRoutine = (void (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HCI_CancelVsMsftIrp;
  v10->VsMsftFilterInfo.HWOffloadedFilteringIrpList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(&v10->IoCapList, &v10->IoCapList.LockedList.SpinLock);
  v10->IoCapList.CancelRoutine = HCI_HandleClientIoCapRequestCancel;
  v10->IoCapList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  LockedList_Init(&v10->WriteScanEnableQueue, &v10->WriteScanEnableQueue.IrpList.LockedList.SpinLock);
  v10->WriteScanEnableQueue.IrpList.CancelRoutine = HCI_WriteScanEnableCancelRoutine;
  v10->WriteScanEnableQueue.IrpList.IrpCompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, int))BthCompleteRequestExternal;
  v10->WriteScanEnableQueue.CurrentIrp = 0;
  v10->WriteScanEnableQueue.AbortStatus = 0;
  v10->WriteScanEnableQueue.Busy = 0;
  v10->WriteScanEnableQueue.SimpleQueue = 0;
  *(_DWORD *)&v10->PassivePageScanWindow = 67108882;
  v10->PassivePageScanType = 1;
  *(_DWORD *)&v10->ActivePageScanWindow = 67108882;
  v10->ActivePageScanType = 1;
  *(_DWORD *)&v10->InquiryScanWindow = 134217746;
  v10->NumInquiryCycleCleanup = 1;
  v10->InquiryScanType = 1;
  v10->MaxUnknownConnectRequests = 15;
  v10->RemoteNameSupported = 1;
  v10->NonFlushablePacketBoundaryFlagEnabled = 1;
  v10->InquirySupportLevel = BthInquiryResultExtendedSupport;
  *(_DWORD *)&v10->EirInfo.EirCbSize = 19434736;
  v10->CommandPacketsAllowedOverride = 1;
  KeInitializeTimer(&v10->CommandCreditReturnTimer);
  KeInitializeDpc(&v10->CommandCreditReturnTimerDpc, HCI_CommandCreditReturnTimeoutDpc, v10);
  v48 = 0;
  v46 = 0;
  v47 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x37 )
      LODWORD(v46) = -1;
    else
      LODWORD(v46) = *(_DWORD *)(WdfStructures + 440);
  }
  else
  {
    LODWORD(v46) = 40;
  }
  LODWORD(v47) = 0;
  *((_QWORD *)&v46 + 1) = HCI_PendingCommandTimeout;
  BYTE4(v47) = 1;
  DWORD2(v47) = 0;
  v53 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v50) = -1;
    else
      LODWORD(v50) = *(_DWORD *)(WdfStructures + 304);
  }
  else
  {
    LODWORD(v50) = 56;
  }
  *(_QWORD *)&v52 = a1[-2].EtwLogger.m_lock.m_kSpinLock;
  *((_QWORD *)&v51 + 1) = 0x100000001LL;
  v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int128 *, WDFTIMER__ **))(WdfFunctions_01031 + 2544))(
          WdfDriverGlobals,
          &v46,
          &v50,
          &v10->PendingCommandTimer);
  if ( v28 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v29) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v29) = 0;
    LOBYTE(v30) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v29,
      v30,
      v10->IfrLog,
      2,
      2,
      14,
      (__int64)WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids,
      v28);
    goto LABEL_49;
  }
  v31 = v10->LocalInfo.localInfo.classOfDevice & 0xFF000107;
  v10->LocalInfo.localInfo.flags = 7;
  v10->CountInquiryScan = 1;
  v10->LocalInfo.localInfo.classOfDevice = v31 | 0x104;
  v10->DisconnectTimeout = 3000;
  v10->GuaranteedRatio = 9;
  v10->GuaranteedTokens = 9;
  KeInitializeEvent(&v10->SynchThreadEvent, SynchronizationEvent, 0);
  KeInitializeEvent(&v10->ResumeThreadEvent, SynchronizationEvent, 0);
  for ( i = 0; i != 21; ++i )
    KeInitializeEvent((PRKEVENT)((char *)v10->ThreadEvents + 16 * i + 8 * i), NotificationEvent, 0);
  v10->CacheCleanupDelay = 1440;
  KeInitializeTimerEx(&v10->CacheCleanupTimer, NotificationTimer);
  KeInitializeDpc(&v10->CacheCleanupDpc, HCI_CacheCleanupTimerDpc, 0);
  v10->CacheEntryDisposableLimit = 500;
  v10->MaxBytesPerScoDataPacket = 512;
  v33 = 0;
  v10->MaxBytesPerAclDataPacket = 512;
  do
  {
    v34 = v33;
    v10->ProcessWWIrp[v34].Context = 0;
    v10->ProcessWWIrp[v34].Function = 0;
    v35 = v33++;
    v10->ProcessWWIrp[v35].ReferenceContext = 0;
  }
  while ( v33 != 2 );
  *(_WORD *)&v10->SniffSubratingEnabled = 1;
  *(_DWORD *)&v10->PageTimeout = 209723392;
  *(_DWORD *)&v10->MinimumLinkSupervisionTimeout = -62336;
  v10->EncryptionChangeNotificationWaitTimeout = 1000;
  *(_WORD *)&v10->LocalRadioMaxEncryptionKeySize = 1808;
  v10->EnableMinimumEncryptionKeySize = 0;
  v10->DevicePowerDownSupportLevel = 0;
  v10->DevicePowerDownIdleTimeout = 2;
  v10->SniffModeDevicePowerDownIdleTimeout = 2;
  *(_DWORD *)&v10->El2capMaxSDUSize = 16850752;
  *(_DWORD *)&v10->IsLEExtendedAdvertisingEnabled = 0x1000000;
  v10->LEConnectionTimeout = 7680;
  v10->LEDefaultLowDutyCycleScanParameters = (_BTHLE_SCAN_PARAMETERS)12386333;
  v10->LEDefaultHighDutyCycleScanParameters = (_BTHLE_SCAN_PARAMETERS)1179666;
  v10->LECurrentScanningFilterPolicy = 0;
  if ( v10->LEMergedDibLowDutyCycleScanParameters._MyHasVal )
    v10->LEMergedDibLowDutyCycleScanParameters._MyHasVal = 0;
  if ( v10->LEMergedDibHighDutyCycleScanParameters._MyHasVal )
    v10->LEMergedDibHighDutyCycleScanParameters._MyHasVal = 0;
  *(_DWORD *)&v10->LEDefaultConnectionParameters.LSTO = 960;
  *(_DWORD *)&v10->LEDefaultConnectionParameters.ConnectionIntervalMin = 3145750;
  *(_DWORD *)&v10->LEBufferSize = 0;
  v10->LEUseBRWriteCredits = 0;
  *(_DWORD *)&v10->LEWriteCredits = 0;
  v10->LEAdvertisementPwrLvl = 0;
  v10->LELocalSupportedFeatures = 0;
  *(_QWORD *)v10->OptInFeatureFlags = 0;
  v10->LELocalSupportedStates = 0;
  *(_DWORD *)&v10->RadioCapacity.LESupportedMaxTxOctets = 21495835;
  v10->RadioCapacity.LESupportedMaxAdvertisementSize = 31;
  *(_WORD *)&v10->RadioCapacity.LEPeriodicAdvertiserListSize = 0;
  v10->LESetAdvertisementMsoInProgress = 0;
  *(_WORD *)&v10->LECurrentScanningState = 0;
  v10->LEWhiteListUsed = 0;
  v10->LEWhiteListEnabled = 1;
  v10->PageScanEnableCount = 0;
  v10->RegistryScanEnableFlags = 0;
  v10->SupportedCodecResultSize = 0;
  v10->SupportedCodecResult = 0;
  *(_DWORD *)&v10->VsMsftInfo.OpCode = 0;
  v10->VsMsftInfo.SupportedFeatures = 0;
  v10->VsMsftInfo.EventPrefixLength = 0;
  v10->VsMsftInfo.EventPrefix = 0;
  v10->VsMsftFilterInfo.ControllerAdvFilterState = 2;
  KeInitializeTimerEx(&v10->LEAdvTimeSlicingTimer, NotificationTimer);
  KeInitializeDpc(&v10->LEAdvTimeSlicingTimerDpc, HciLEAdv_TimeSlicingTimeoutDpc, 0);
  *(_QWORD *)&v10->LERandomAddressInfo.NonResolvableAddrRefCount = 0;
  v10->LERandomAddressInfo.RegenerationTimeout = 900000;
  v10->LERandomAddressInfo.regenerationTimeoutToleranceInMs = 60000;
  v60[0] = off_140169C08;
  v10->LERandomAddressInfo.Regenerate = 1;
  v60[13] = v60;
  v10->LERandomAddressInfo.RandomAddress = 0;
  v60[1] = v10;
  v36 = IdleResilientTimer::Initialize(&v10->LERandomAddressInfo.timer, v59);
  wistd::function<void (utl::list<LinkManagerLELogicalTransportAclManager::ConnectRequestContext,utl::allocator<LinkManagerLELogicalTransportAclManager::ConnectRequestContext>> &)>::~function<void (utl::list<LinkManagerLELogicalTransportAclManager::ConnectRequestContext,utl::allocator<LinkManagerLELogicalTransportAclManager::ConnectRequestContext>> &)>(v59);
  if ( v36 < 0 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v26) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v26) = 0;
    v43 = 15;
    goto LABEL_63;
  }
  *(_WORD *)&v10->LEPrivacyMode = 4;
  v10->leAdvertisingRequestCoordinator.m_hci = v10;
  *(_DWORD *)&v10->LEDefaultSubrateParameters.subrateMin = 6553601;
  *(_DWORD *)&v10->LEDefaultSubrateParameters.maxLatency = 4;
  v10->LEDefaultSubrateParameters.supervisionTimeout = 3200;
  HCI_InitDefaultLocalRadioName(v10);
  v38 = v49;
  *(_WORD *)&v10->RoleChangeEnabled = 1;
  v10->LinkManagerProcedureConnectionInProgress = 0;
  HCI_ReadStoredSettings(v10, v38);
  HCI_UpdateFromRegistry(v10, 0x3FFFu, v39, 1, v38);
  BthGetDeviceStringProperty(v54, v10->DevExt, &DEVPKEY_Device_DriverDesc);
  RadioPerfCounters::Initialize(&v10->PerfCounters.m_counterInstanceHandle, v54[0]);
  if ( (int)HCI_CreateThread(v10) < 0 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v54);
    goto LABEL_49;
  }
  MyRealVal = v10->DeviceListProcessorModule._MyDat._MyRealVal;
  v44 = 0;
  v10->DeviceListProcessorModule._MyDat._MyRealVal = v7;
  if ( MyRealVal )
    utl::default_delete<DeviceListProcessor>::operator()();
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v54);
  utl::unique_ptr<DeviceListProcessor,utl::default_delete<DeviceListProcessor>>::~unique_ptr<DeviceListProcessor,utl::default_delete<DeviceListProcessor>>(&v44);
  return v10;
}

```

## disassembly

```asm
0x1400719d4  mov     [rsp-8+arg_10], rbx
0x1400719d9  push    rbp
0x1400719da  push    rsi
0x1400719db  push    rdi
0x1400719dc  push    r12
0x1400719de  push    r13
0x1400719e0  push    r14
0x1400719e2  push    r15
0x1400719e4  lea     rbp, [rsp-0A0h]
0x1400719ec  sub     rsp, 1A0h
0x1400719f3  mov     rax, cs:__security_cookie
0x1400719fa  xor     rax, rsp
0x1400719fd  mov     [rbp+0D0h+var_38], rax
0x140071a04  xorps   xmm0, xmm0
0x140071a07  mov     [rbp+0D0h+var_148], rdx
0x140071a0b  xor     eax, eax
0x140071a0d  mov     r13, rcx
0x140071a10  mov     ebx, 50485442h
0x140071a15  mov     [rbp+0D0h+var_B8], rax
0x140071a19  xor     r12d, r12d
0x140071a1c  mov     r8d, ebx
0x140071a1f  mov     edx, 198h
0x140071a24  mov     [rsp+1D0h+var_178], r12
0x140071a29  lea     edi, [rax+40h]
0x140071a2c  mov     ecx, edi
0x140071a2e  movups  [rbp+0D0h+var_E8], xmm0
0x140071a32  movups  [rbp+0D0h+var_D8], xmm0
0x140071a36  movups  [rbp+0D0h+var_C8], xmm0
0x140071a3a  call    cs:__imp_ExAllocatePool2
0x140071a41  nop     dword ptr [rax+rax+00h]
0x140071a46  test    rax, rax
0x140071a49  jz      loc_1400725FC
0x140071a4f  lea     rdx, [r13-330h]; struct Fdo *
0x140071a56  mov     rcx, rax; this
0x140071a59  call    ??0DeviceListProcessor@@QEAA@AEAVFdo@@@Z; DeviceListProcessor::DeviceListProcessor(Fdo &)
0x140071a5e  mov     [rsp+1D0h+var_180], rax
0x140071a63  mov     r15, rax
0x140071a66  test    rax, rax
0x140071a69  jz      loc_140072601
0x140071a6f  mov     rcx, rax; this
0x140071a72  call    ?Initialize@DeviceListProcessor@@QEAAJXZ; DeviceListProcessor::Initialize(void)
0x140071a77  test    eax, eax
0x140071a79  jns     short loc_140071AB6
0x140071a7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071a82  lea     r14d, [r12+2]
0x140071a87  lea     esi, [rdi-3Fh]
0x140071a8a  mov     eax, [rcx+2Ch]
0x140071a8d  test    r14b, al
0x140071a90  jz      short loc_140071A9B
0x140071a92  mov     dl, sil
0x140071a95  cmp     [rcx+29h], r14b
0x140071a99  jnb     short loc_140071A9E
0x140071a9b  mov     dl, r12b
0x140071a9e  lea     rax, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140071aa5  mov     [rsp+1D0h+var_198], rax
0x140071aaa  mov     [rsp+1D0h+var_1A0], 0Bh
0x140071ab1  jmp     loc_140072638
0x140071ab6  mov     r8d, ebx
0x140071ab9  mov     edx, 1300h
0x140071abe  mov     rcx, rdi
0x140071ac1  call    cs:__imp_ExAllocatePool2
0x140071ac8  nop     dword ptr [rax+rax+00h]
0x140071acd  mov     rdi, rax
0x140071ad0  test    rax, rax
0x140071ad3  jnz     short loc_140071B0F
0x140071ad5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140071adc  lea     r14d, [rdi+2]
0x140071ae0  lea     esi, [rdi+1]
0x140071ae3  mov     eax, [rcx+2Ch]
0x140071ae6  test    r14b, al
0x140071ae9  jz      short loc_140071AF4
0x140071aeb  mov     dl, sil
0x140071aee  cmp     [rcx+29h], r14b
0x140071af2  jnb     short loc_140071AF7
0x140071af4  mov     dl, r12b
0x140071af7  lea     rax, WPP_3eab8638b8d43e2e8e0c930b28aa0c7e_Traceguids
0x140071afe  mov     [rsp+1D0h+var_198], rax
0x140071b03  mov     [rsp+1D0h+var_1A0], 0Ch
0x140071b0a  jmp     loc_140072638
0x140071b0f  mov     rdx, r13; struct DEVICE_EXTENSION *
0x140071b12  mov     rcx, rdi; this
0x140071b15  call    ??0HCI_INTERFACE@@QEAA@PEAUDEVICE_EXTENSION@@@Z; HCI_INTERFACE::HCI_INTERFACE(DEVICE_EXTENSION *)
0x140071b1a  mov     ecx, 10h
0x140071b1f  mov     dword ptr [rdi], 49494348h
0x140071b25  mov     edx, ecx
0x140071b27  mov     dword ptr [rbp+0D0h+var_D8+0Ch], ecx
0x140071b2a  mov     ebx, 7FFFFFFEh
0x140071b2f  mov     [rdi+4B0h], r13
0x140071b36  mov     dword ptr [rbp+0D0h+var_E8], 38h ; '8'
0x140071b3d  lea     r8, aDefault; "Default"
0x140071b44  mov     byte ptr [rbp+0D0h+var_C8], r12b
0x140071b48  lea     rcx, [rbp+0D0h+var_C8]
0x140071b4c  lea     esi, [rdx-0Fh]
0x140071b4f  mov     qword ptr [rbp+0D0h+var_D8], r12
0x140071b53  mov     byte ptr [rbp+0D0h+var_D8+8], r12b
0x140071b57  mov     eax, ebx
0x140071b59  test    rax, rax
0x140071b5c  jz      short loc_140071B77
0x140071b5e  mov     r9b, [r8]
0x140071b61  test    r9b, r9b
0x140071b64  jz      short loc_140071B77
0x140071b66  mov     [rcx], r9b
0x140071b69  add     r8, rsi
0x140071b6c  add     rcx, rsi
0x140071b6f  sub     rax, rsi
0x140071b72  sub     rdx, rsi
0x140071b75  jnz     short loc_140071B59
0x140071b77  test    rdx, rdx
0x140071b7a  lea     rax, [rcx-1]
0x140071b7e  mov     r14d, 2
0x140071b84  lea     r8, [rsp+1D0h+var_178]
0x140071b89  cmovnz  rax, rcx
0x140071b8d  lea     rdx, [rbp+0D0h+var_E8]
0x140071b91  mov     rcx, cs:WPP_GLOBAL_Control
0x140071b98  mov     [rax], r12b
0x140071b9b  mov     dword ptr [rbp+0D0h+var_B8], r14d
0x140071b9f  mov     dword ptr [rbp+0D0h+var_B8+4], r14d
0x140071ba3  mov     dword ptr [rbp+0D0h+var_E8+4], 50485442h
0x140071baa  mov     dword ptr [rbp+0D0h+var_E8+8], 2000h
0x140071bb1  mov     dword ptr [rbp+0D0h+var_E8+0Ch], 200h
0x140071bb8  call    cs:__imp_imp_WppRecorderLogCreate
0x140071bbf  nop     dword ptr [rax+rax+00h]
0x140071bc4  test    eax, eax
0x140071bc6  jz      short loc_140071BE2
0x140071bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140071bcf  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140071bd6  nop     dword ptr [rax+rax+00h]
0x140071bdb  mov     [rsp+1D0h+var_178], rax
0x140071be0  jmp     short loc_140071BE7
0x140071be2  mov     rax, [rsp+1D0h+var_178]
0x140071be7  mov     ecx, 10h
0x140071bec  mov     [rdi+10B0h], rax
0x140071bf3  mov     dword ptr [rbp+0D0h+var_D8+0Ch], ecx
0x140071bf6  lea     rax, aHci; "HCI"
0x140071bfd  mov     edx, ecx
0x140071bff  mov     dword ptr [rbp+0D0h+var_E8], 38h ; '8'
0x140071c06  lea     rcx, [rbp+0D0h+var_C8]
0x140071c0a  mov     byte ptr [rbp+0D0h+var_C8], r12b
0x140071c0e  mov     qword ptr [rbp+0D0h+var_D8], r12
0x140071c12  mov     byte ptr [rbp+0D0h+var_D8+8], r12b
0x140071c16  test    rbx, rbx
0x140071c19  jz      short loc_140071C34
0x140071c1b  mov     r8b, [rax]
0x140071c1e  test    r8b, r8b
0x140071c21  jz      short loc_140071C34
0x140071c23  mov     [rcx], r8b
0x140071c26  add     rax, rsi
0x140071c29  add     rcx, rsi
0x140071c2c  sub     rbx, rsi
0x140071c2f  sub     rdx, rsi
0x140071c32  jnz     short loc_140071C16
0x140071c34  test    rdx, rdx
0x140071c37  lea     rax, [rcx-1]
0x140071c3b  lea     rbx, [rdi+10B8h]
0x140071c42  cmovnz  rax, rcx
0x140071c46  xor     edx, edx
0x140071c48  mov     rcx, rbx
0x140071c4b  mov     [rax], r12b
0x140071c4e  mov     dword ptr [rbp+0D0h+var_B8], r14d
0x140071c52  mov     dword ptr [rbp+0D0h+var_B8+4], r14d
0x140071c56  mov     dword ptr [rbp+0D0h+var_E8+4], 50485442h
0x140071c5d  mov     dword ptr [rbp+0D0h+var_E8+8], 2000h
0x140071c64  mov     dword ptr [rbp+0D0h+var_E8+0Ch], 200h
0x140071c6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAURECORDER_LOG__@@@Z; wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(RECORDER_LOG__ *)
0x140071c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c77  lea     rdx, [rbp+0D0h+var_E8]
0x140071c7b  mov     r8, rbx
0x140071c7e  call    cs:__imp_imp_WppRecorderLogCreate
0x140071c85  nop     dword ptr [rax+rax+00h]
0x140071c8a  test    eax, eax
0x140071c8c  jz      short loc_140071CAC
0x140071c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140071c95  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140071c9c  nop     dword ptr [rax+rax+00h]
0x140071ca1  mov     rdx, rax
0x140071ca4  mov     rcx, rbx
0x140071ca7  call    ?reset@?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAURECORDER_LOG__@@@Z; wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(RECORDER_LOG__ *)
0x140071cac  mov     al, cs:BthLib_RefObjDebugEnabled
0x140071cb2  lea     r12, [rdi+8]
0x140071cb6  mov     byte ptr [rsp+1D0h+var_1A8], al
0x140071cba  lea     rdx, ?HCI_RefDestroy@@YAXPEAU_REF_OBJ@@@Z; HCI_RefDestroy(_REF_OBJ *)
0x140071cc1  lea     rax, aOnecoreDrivers_38; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140071cc8  mov     r9d, 82h
0x140071cce  mov     r8, rdi
0x140071cd1  mov     [rsp+1D0h+var_1B0], rax
0x140071cd6  mov     rcx, r12
0x140071cd9  call    RefObj_InitEx
0x140071cde  xor     ebx, ebx
0x140071ce0  mov     word ptr [rdi+0D3Ch], 100h
0x140071ce9  mov     ecx, 0FFh
0x140071cee  mov     [rdi+0D17h], bl
0x140071cf4  mov     [rdi+0D38h], ecx
0x140071cfa  mov     [rdi+0D2Ch], ecx
0x140071d00  lea     rcx, [rdi+7B0h]; SpinLock
0x140071d07  lea     eax, [rbx+3]
0x140071d0a  mov     word ptr [rdi+0BF4h], 0CC18h
0x140071d13  mov     [rdi+0D24h], eax
0x140071d19  mov     [rdi+0D28h], eax
0x140071d1f  mov     [rdi+0D19h], si
0x140071d26  mov     word ptr [rdi+0D1Ch], 100h
0x140071d2f  mov     [rdi+0D1Eh], sil
0x140071d36  mov     [rdi+0D20h], sil
0x140071d3d  mov     [rdi+0D30h], sil
0x140071d44  mov     [rdi+0D34h], ebx
0x140071d4a  call    cs:__imp_KeInitializeSpinLock
0x140071d51  nop     dword ptr [rax+rax+00h]
0x140071d56  lea     rax, [rdi+970h]
0x140071d5d  mov     [rdi+820h], ebx
0x140071d63  mov     [rax+8], rax
0x140071d67  mov     [rax], rax
0x140071d6a  lea     rax, [rdi+980h]
0x140071d71  mov     [rax+8], rax
0x140071d75  mov     [rax], rax
0x140071d78  lea     rax, [rdi+990h]
0x140071d7f  mov     [rax+8], rax
0x140071d83  mov     [rax], rax
0x140071d86  lea     rax, [rdi+9C0h]
0x140071d8d  mov     [rax+8], rax
0x140071d91  mov     [rax], rax
0x140071d94  lea     rax, [rdi+9D0h]
0x140071d9b  mov     [rax+8], rax
0x140071d9f  mov     [rax], rax
0x140071da2  lea     rax, [rdi+9A0h]
0x140071da9  mov     [rax+8], rax
0x140071dad  mov     [rax], rax
0x140071db0  lea     rax, [rdi+7B8h]
0x140071db7  mov     [rax+8], rax
0x140071dbb  mov     [rax], rax
0x140071dbe  lea     rax, [rdi+7D8h]
0x140071dc5  mov     [rax+8], rax
0x140071dc9  mov     [rax], rax
0x140071dcc  lea     rax, [rdi+7C8h]
0x140071dd3  mov     [rax+8], rax
0x140071dd7  mov     [rax], rax
0x140071dda  lea     rax, [rdi+7F0h]
0x140071de1  mov     [rax+8], rax
0x140071de5  mov     [rax], rax
0x140071de8  lea     rax, [rdi+810h]
0x140071def  mov     [rax+8], rax
0x140071df3  mov     [rax], rax
0x140071df6  lea     rax, [rdi+8B0h]
0x140071dfd  mov     [rax+8], rax
0x140071e01  mov     [rax], rax
0x140071e04  lea     rax, [rdi+1090h]
0x140071e0b  mov     [rax+8], rax
0x140071e0f  mov     [rax], rax
0x140071e12  mov     [rdi+8C0h], ebx
0x140071e18  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x140071e1d  test    eax, eax
0x140071e1f  jnz     short loc_140071E2E
0x140071e21  mov     rcx, [rdi+4B0h]
0x140071e28  mov     rcx, [rcx+8]
0x140071e2c  jmp     short loc_140071E37
0x140071e2e  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x140071e33  mov     rcx, [rax+10h]; DeviceObject
0x140071e37  call    cs:__imp_IoAllocateWorkItem
0x140071e3e  nop     dword ptr [rax+rax+00h]
0x140071e43  lea     rbx, [rdi+8D8h]
0x140071e4a  mov     rdx, rax
0x140071e4d  mov     rcx, rbx
0x140071e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_IO_WORKITEM@@P6AXPEAU1@@Z$1?IoFreeWorkItem@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_IO_WORKITEM@@@Z; wil::details::unique_storage<wil::details::resource_policy<_IO_WORKITEM *,void (*)(_IO_WORKITEM *),&IoFreeWorkItem(_IO_WORKITEM *),wistd::integral_constant<unsigned __int64,1>,_IO_WORKITEM *,_IO_WORKITEM *,0,std::nullptr_t>>::reset(_IO_WORKITEM *)
0x140071e55  cmp     qword ptr [rbx], 0
0x140071e59  jz      loc_1400725C8
0x140071e5f  lea     rbx, [rdi+8E0h]
0x140071e66  mov     rcx, rbx
0x140071e69  lea     rdx, [rdi+7B0h]
0x140071e70  call    LockedList_Init
0x140071e75  lea     rax, ?BthInquiryCancelRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; BthInquiryCancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x140071e7c  mov     [rbx+28h], rax
0x140071e80  lea     rdx, [rdi+7B0h]
0x140071e87  lea     rax, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x140071e8e  mov     [rbx+30h], rax
0x140071e92  lea     rbx, [rdi+918h]
0x140071e99  mov     rcx, rbx
0x140071e9c  call    LockedList_Init
0x140071ea1  lea     rax, ?HciLE_ConnectionSpeedBoostRequestCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; HciLE_ConnectionSpeedBoostRequestCancel(_DEVICE_OBJECT *,_IRP *)
0x140071ea8  mov     [rbx+28h], rax
0x140071eac  lea     rdx, [rdi+7B0h]
0x140071eb3  lea     rax, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x140071eba  mov     [rbx+30h], rax
0x140071ebe  lea     rbx, [rdi+1150h]
0x140071ec5  mov     rcx, rbx
0x140071ec8  call    LockedList_Init
0x140071ecd  lea     rax, ?SensitiveTrafficRequestCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; SensitiveTrafficRequestCancel(_DEVICE_OBJECT *,_IRP *)
0x140071ed4  mov     [rbx+28h], rax
0x140071ed8  lea     rax, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x140071edf  mov     [rbx+30h], rax
0x140071ee3  lea     rbx, [rdi+0A80h]
0x140071eea  lea     rdx, [rbx+10h]
0x140071eee  mov     rcx, rbx
0x140071ef1  call    LockedList_Init
0x140071ef6  lea     rax, ?HCI_CancelVendorIrp@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; HCI_CancelVendorIrp(_DEVICE_OBJECT *,_IRP *)
0x140071efd  mov     [rbx+28h], rax
0x140071f01  lea     rdx, [rdi+1068h]
0x140071f08  lea     rax, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x140071f0f  mov     [rbx+30h], rax
0x140071f13  lea     rbx, [rdi+1058h]
0x140071f1a  mov     rcx, rbx
0x140071f1d  call    LockedList_Init
0x140071f22  lea     rax, ?HCI_CancelVsMsftIrp@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; HCI_CancelVsMsftIrp(_DEVICE_OBJECT *,_IRP *)
  ... truncated ...
```
