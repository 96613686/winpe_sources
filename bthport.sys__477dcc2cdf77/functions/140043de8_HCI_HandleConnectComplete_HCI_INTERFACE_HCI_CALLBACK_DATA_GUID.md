# HCI_HandleConnectComplete(HCI_INTERFACE *,_HCI_CALLBACK_DATA *,_GUID *)

- ea: `0x140043de8`
- end: `0x140044876`
- name: `?HCI_HandleConnectComplete@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CALLBACK_DATA@@PEAU_GUID@@@Z`
- size: `2702`
- prototype: `void __fastcall(struct HCI_INTERFACE *, struct _HCI_CALLBACK_DATA *, struct _GUID *)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140037780`
- `0x140039b10`

## callees

- `0x140004368`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005b4c`
- `0x14000764c`
- `0x140011814`
- `0x140020298`
- `0x1400202d8`
- `0x140036a88`
- `0x140036cf8`
- `0x14003a890`
- `0x14003d5e4`
- `0x14003db44`
- `0x14003fe84`
- `0x140043de8`
- `0x140049b60`
- `0x14004b86c`
- `0x14004c0c8`
- `0x14004cd80`
- `0x14005fe30`
- `0x1400a5550`
- `0x14015ce38`
- `0x140161d7c`
- `0x1401630a8`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400443ae`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x1400443ae`
- `ntoskrnl!KeCancelTimer` at `0x14004405d`
- `ntoskrnl!KeCancelTimer` at `0x14004405d`

## string_xrefs

- `0x1400447d4`: `Multi-step operation not scheduled, leak possible.`

## pseudocode

```c
void __fastcall HCI_HandleConnectComplete(struct HCI_INTERFACE *a1, struct _HCI_CALLBACK_DATA *a2, struct _GUID *a3)
{
  _HCI_CONNECTION *Cxn; // rdx
  struct _GUID *v5; // r13
  __int64 v7; // rdx
  int v8; // edx
  int v9; // r8d
  int *v10; // rbx
  _HCI_EVENT *Event; // rcx
  _BTH_AUTHENTICATION_RESULT_CONTEXT *v12; // r12
  unsigned int Flags; // eax
  char v14; // bl
  unsigned int v15; // r15d
  _BTH_AUTHENTICATION_RESULT_CONTEXT *AuthenticationResultContext; // rcx
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rdx
  int v20; // edx
  int v21; // edx
  int v22; // r8d
  int v23; // edx
  int v24; // r8d
  struct _HCI_CONNECTION_ACTIVITY_ID_CONTEXT *v25; // r12
  int BtStatus; // r8d
  __int16 DeviceType; // ax
  DEVICE_INFO_BLOCK *Dib; // rdi
  DEVICE_INFO_BLOCK *v29; // rbx
  unsigned int v30; // eax
  struct _LIST_ENTRY *v31; // rax
  struct _LIST_ENTRY *v32; // rdx
  int v33; // eax
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *v34; // rcx
  _LIST_ENTRY *v35; // rax
  _LIST_ENTRY *v36; // r8
  __int64 p_DisposableDeviceList; // rax
  _LIST_ENTRY *v38; // r8
  struct _LIST_ENTRY *v39; // rcx
  struct _LIST_ENTRY *v40; // rax
  _LIST_ENTRY *v41; // r8
  __int64 v42; // rax
  _LIST_ENTRY *v43; // rdx
  struct _HCI_CONNECTION *v44; // rcx
  Microsoft::Bluetooth::Foundation::intrusive_list_hook *p_DisposableListEntry; // rax
  _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY **p_Hci; // rcx
  _LIST_ENTRY *Blink; // rdx
  HCI_INTERFACE *Hci; // rdx
  unsigned int NumberOfDisposableDevices; // eax
  struct _LIST_ENTRY *LinkedDib; // rax
  struct _LIST_ENTRY *v52; // rcx
  _LIST_ENTRY *v53; // rdx
  _LIST_ENTRY *v54; // r8
  _LIST_ENTRY *v55; // rcx
  int v56; // eax
  struct _HCI_CONNECTION *v57; // rdx
  int *v58; // rcx
  int v59; // edx
  int v60; // r8d
  enum TrafficType v61; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v62[2]; // [rsp+28h] [rbp-D8h]
  int v63; // [rsp+30h] [rbp-D0h]
  int v64; // [rsp+38h] [rbp-C8h]
  __int64 v65; // [rsp+60h] [rbp-A0h] BYREF
  struct _HCI_CONNECTION *v66; // [rsp+68h] [rbp-98h]
  int *v67; // [rsp+70h] [rbp-90h] BYREF
  struct _HCI_CONNECTION_ACTIVITY_ID_CONTEXT *v68[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v69[2]; // [rsp+88h] [rbp-78h] BYREF
  char v70; // [rsp+98h] [rbp-68h]
  int *v71; // [rsp+A0h] [rbp-60h]
  struct _HCI_CONNECTION_INFO v72; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v73[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v74[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v75[2]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v76[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v77[2]; // [rsp+160h] [rbp+60h] BYREF
  int v78; // [rsp+170h] [rbp+70h]
  _DWORD v79[27]; // [rsp+174h] [rbp+74h] BYREF

  v69[1] = a2;
  Cxn = a2->Cxn;
  v69[0] = a1;
  v5 = a3;
  if ( !Cxn )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(Cxn) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(Cxn) = 0;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)Cxn,
      (_DWORD)a3,
      a1->IfrLog,
      2,
      2,
      153,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
    goto LABEL_6;
  }
  _MakeWithAddRef___RefObjReference_U_HCI_CONNECTION___07_M__T0A__M__T0A___SA_AV1_PEAU_HCI_CONNECTION__PEBX_Z(
    &v65,
    Cxn,
    Hci_CxnPostConnectMultiStepComplete);
  utl::make_unique<_HCI_POST_CONNECT_PROCESS_CONTEXT,,0>(&v67, v7);
  v10 = v67;
  v71 = v67;
  if ( !v67 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v8) = 0;
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      a1->IfrLog,
      2,
      2,
      154,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
    goto LABEL_12;
  }
  *v67 = a2->Status;
  *((_BYTE *)v10 + 4) = a2->BtStatus;
  *((_BYTE *)v10 + 16) = 0;
  memset(v79, 0, sizeof(v79));
  v73[1] = v73;
  v73[0] = v73;
  v74[1] = v74;
  v74[0] = v74;
  v75[1] = v75;
  v75[0] = v75;
  v76[1] = v76;
  v76[0] = v76;
  v77[1] = v77;
  v77[0] = v77;
  memset(&v79[1], 0, 0x68u);
  Event = a2->Event;
  v78 = 0;
  if ( Event )
  {
    LOWORD(v79[11]) = Event->Event_ConnectionComplete.Connection_Handle;
    v10[2] = Event->Event_Generic.Event_Parameter[10];
    v10[3] = a2->Event->Event_Generic.Event_Parameter[9];
  }
  v12 = 0;
  wil::acquire_kspin_lock(v68, &v66->StateLock);
  Flags = v66->Flags;
  if ( (Flags & 4) != 0 )
  {
    v14 = 1;
  }
  else
  {
    v14 = 0;
    v66->Flags = Flags | 4;
  }
  v15 = v66->Flags;
  if ( a2->BtStatus )
    goto LABEL_117;
  HCI_CxnSetInfoLocked(v66, (struct _HCI_CONNECTION_INFO *)&v79[1], 0x100u);
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline() && !v14 && (v15 & 8) == 0 )
    _InterlockedIncrement((volatile signed __int32 *)&a1->PerfCounters.m_counters.ClassicAclConnectionCount);
  if ( a2->BtStatus )
  {
LABEL_117:
    if ( (v15 & 8) == 0 && !v14 )
    {
      AuthenticationResultContext = v66->AuthenticationResultContext;
      if ( AuthenticationResultContext )
      {
        if ( KeCancelTimer(&AuthenticationResultContext->Timer) )
        {
          v12 = v66->AuthenticationResultContext;
          v66->AuthenticationResultContext = 0;
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v68);
  if ( v14 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v17) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      LOBYTE(v17) = 0;
    LOBYTE(v18) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v18,
      v66->Dib->IfrLog,
      4,
      2,
      155,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      v66);
    goto LABEL_114;
  }
  wil::acquire_kspin_lock(v68, &a1->HciLock);
  v66->Dib->LastConnectionStatus = a2->BtStatus;
  v66->Dib->LastConnectionBlockedBySystem = 0;
  if ( !a2->BtStatus )
    v66->Dib->LastConnectionIdentifier = v66->Identifier;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v68);
  if ( a2->BtStatus )
  {
    memset(&v72, 0, sizeof(v72));
    HCI_CxnGetInfo(v66, &v72);
    LOBYTE(v20) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_qLD(
      WPP_GLOBAL_Control->AttachedDevice,
      v20,
      (_DWORD)v66,
      v66->Dib->IfrLog,
      4,
      2,
      156,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
      (char)v66,
      v72.State,
      a2->BtStatus);
    if ( (v15 & 8) != 0 )
    {
      LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v22) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        v22,
        v66->Dib->IfrLog,
        4,
        2,
        157,
        (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
        v66);
      goto LABEL_12;
    }
    if ( v12 )
    {
      HCI_CxnAuthComplete(v66, 5u, 0, 0);
      HCI_DeleteAuthenticationResultContext(v12);
    }
    HCI_CxnMakeZombie(v66);
    RefObj_ReleaseEx(
      &v66->RefObj,
      v66,
      5515,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciconnection.cpp");
  }
  utl::make_unique<_HCI_POST_CONNECT_PROCESS_CONTEXT,,0>(v68, v19);
  v25 = v68[0];
  if ( !v68[0] )
  {
    LOBYTE(v23) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v24) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v23,
      v24,
      v66->Dib->IfrLog,
      2,
      2,
      158,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
    utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(v68);
LABEL_12:
    utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v67);
    _Reset___RefObjReference_U_HCI_CONNECTION___07_M__T0A__M__T0A___QEAAXPEAU_HCI_CONNECTION__PEBX_Z(&v65, 0, 0);
LABEL_6:
    v70 = 0;
    lambda_f2b11b09d4f9c993158efe3f1e82ebd9_::operator()(v69);
    return;
  }
  *(_QWORD *)v68[0] = v66;
  if ( v5 )
    *(struct _GUID *)((char *)v25 + 8) = *v5;
  else
    *(_OWORD *)((char *)v25 + 8) = 0;
  BtStatus = a2->BtStatus;
  if ( !(_BYTE)BtStatus )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v23) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      LOBYTE(v23) = 0;
    DeviceType = WPP_GLOBAL_Control->DeviceType;
    if ( (_BYTE)v23 || DeviceType )
    {
      LOBYTE(BtStatus) = DeviceType != 0;
      WPP_RECORDER_AND_TRACE_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        v23,
        BtStatus,
        a1->IfrLog,
        5,
        2,
        159,
        (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids,
        (char)a1,
        a2->Cxn);
    }
    wil::acquire_kspin_lock(v68, &a1->HciLock);
    Dib = v66->Dib;
    Dib->LastSeenTimestamp.QuadPart = MEMORY[0xFFFFF78000000014];
    ExSystemTimeToLocalTime(&Dib->LastSeenTimestamp, &Dib->LastSeenTimestamp);
    Dib->LastConnectedTimestamp.QuadPart = Dib->LastSeenTimestamp.QuadPart;
    if ( !a1->CacheEntryDisposableLimit )
      goto LABEL_89;
    v29 = v66->Dib;
    v30 = v29->DeviceInfo.flags;
    if ( (v30 & 0x4000) != 0 && !v29->LinkedDibAddress
      || (v30 & 0x1030038) != 0
      || (v29->DibFlags._MyVal & 8) != 0
      || v29->ListEntry.Flink == &v29->ListEntry )
    {
      p_DisposableListEntry = &v29->DisposableListEntry;
      Flink = v29->DisposableListEntry.Flink;
      if ( Flink == &v29->DisposableListEntry )
      {
        p_Hci = (struct _LIST_ENTRY **)&v29->Hci;
      }
      else
      {
        if ( Flink->Blink != p_DisposableListEntry )
          goto LABEL_102;
        Blink = v29->DisposableListEntry.Blink;
        if ( Blink->Flink != p_DisposableListEntry )
          goto LABEL_102;
        Blink->Flink = Flink;
        Flink->Blink = Blink;
        p_Hci = (struct _LIST_ENTRY **)&v29->Hci;
        v29->DisposableListEntry.Blink = &v29->DisposableListEntry;
        p_DisposableListEntry->Flink = p_DisposableListEntry;
        Hci = v29->Hci;
        NumberOfDisposableDevices = Hci->NumberOfDisposableDevices;
        if ( NumberOfDisposableDevices )
          Hci->NumberOfDisposableDevices = NumberOfDisposableDevices - 1;
      }
      LinkedDib = HCI_FindLinkedDib(*p_Hci + 129, v29);
      if ( !LinkedDib )
        goto LABEL_89;
      v52 = LinkedDib + 53;
      v53 = LinkedDib[53].Flink;
      if ( v53 == &LinkedDib[53] )
        goto LABEL_89;
      if ( v53->Blink == v52 )
      {
        v54 = LinkedDib[53].Blink;
        if ( v54->Flink == v52 )
        {
          v54->Flink = v53;
          v53->Blink = v54;
          LinkedDib[53].Blink = LinkedDib + 53;
          v52->Flink = v52;
          v55 = LinkedDib[55].Blink;
          v56 = (int)v55[140].Flink;
          if ( v56 )
            LODWORD(v55[140].Flink) = v56 - 1;
          goto LABEL_89;
        }
      }
    }
    else
    {
      v31 = HCI_FindLinkedDib(&v29->Hci->DeviceList, v66->Dib);
      v32 = v31;
      if ( !v31
        || ((v33 = (int)v31[1].Blink, (v33 & 0x4000) == 0) || v32[142].Blink)
        && (v33 & 0x1030038) == 0
        && ((__int64)v32[54].Blink & 8) == 0 )
      {
        v34 = &v29->DisposableListEntry;
        v35 = v29->DisposableListEntry.Flink;
        if ( v35 == &v29->DisposableListEntry )
        {
          ++v29->Hci->NumberOfDisposableDevices;
        }
        else
        {
          if ( v35->Blink != v34 )
            goto LABEL_102;
          v36 = v29->DisposableListEntry.Blink;
          if ( v36->Flink != v34 )
            goto LABEL_102;
          v36->Flink = v35;
          v35->Blink = v36;
          v29->DisposableListEntry.Blink = &v29->DisposableListEntry;
          v34->Flink = v34;
        }
        p_DisposableDeviceList = (__int64)&v29->Hci->DisposableDeviceList;
        v38 = *(_LIST_ENTRY **)p_DisposableDeviceList;
        if ( *(_QWORD *)(*(_QWORD *)p_DisposableDeviceList + 8LL) != p_DisposableDeviceList )
          goto LABEL_102;
        v34->Flink = v38;
        v29->DisposableListEntry.Blink = (_LIST_ENTRY *)p_DisposableDeviceList;
        v38->Blink = v34;
        *(_QWORD *)p_DisposableDeviceList = v34;
        if ( !v32 )
          goto LABEL_89;
      }
      v39 = v32 + 53;
      v40 = v32[53].Flink;
      if ( v40 == &v32[53] )
      {
LABEL_89:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v68);
        Controller::InformOfConnection(
          (Controller *)&a1->DevExt[-2].AvdtpOffload,
          v66->Info.ConnectionHandle,
          v66->Dib->DeviceInfo.address,
          v66->Dib->DeviceInfo.LEAddressType,
          LECis,
          0);
        v44 = v66;
        v68[0] = 0;
        v67 = 0;
        v66->ConfigOp.Steps = 0;
        v44->ConfigOp.NumSteps = 0;
        v44->ConfigOp.FnTerminate = 0;
        v44->ConfigOp.CmdContext = 0;
        *(_WORD *)&v44->ConfigOp.InProgress = 0;
        v44->ConfigOp.CurrentStep = -1;
        *(_QWORD *)&v44->ConfigOp.Status = 0;
        v44->ConfigOp.Data = 0;
        v44->ConfigOp.Steps = (const _MULTI_STEP_CMD_ENTRY *)&off_1401691C0;
        v44->ConfigOp.FnTerminate = (int (__fastcall *)(void *, int))Hci_CxnPostConnectMultiStepComplete;
        v44->ConfigOp.NumSteps = 5;
        v44->ConfigOp.CmdContext = v25;
        v44->ConfigOp.InProgress = 1;
        v66->ConfigOp.Data = v71;
        MultiStepOperation_StepComplete(&v66->ConfigOp, 0);
        goto LABEL_108;
      }
      if ( v40->Blink == v39 )
      {
        v41 = v32[53].Blink;
        if ( v41->Flink == v39 )
        {
          v41->Flink = v40;
          v40->Blink = v41;
          v32[53].Blink = v32 + 53;
          v39->Flink = v39;
          v42 = (__int64)&v32[55].Blink[139];
          v43 = *(_LIST_ENTRY **)v42;
          if ( *(_QWORD *)(*(_QWORD *)v42 + 8LL) == v42 )
          {
            v39->Flink = v43;
            v39->Blink = (_LIST_ENTRY *)v42;
            v43->Blink = v39;
            *(_QWORD *)v42 = v39;
            goto LABEL_89;
          }
        }
      }
    }
LABEL_102:
    __fastfail(3u);
  }
  if ( (v15 & 8) != 0 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Multi-step operation not scheduled, leak possible.");
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v59) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v59) = 0;
    LOBYTE(v60) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v59,
      v60,
      v66->Dib->IfrLog,
      2,
      2,
      161,
      (__int64)WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids);
    goto LABEL_113;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v23) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v23) = 0;
  WPP_RECORDER_AND_TRACE_SF_Lqq(
    WPP_GLOBAL_Control->AttachedDevice,
    v23,
    BtStatus,
    a1->IfrLog,
    v61,
    *(_DWORD *)v62,
    v63,
    v64,
    BtStatus,
    (char)a1,
    (char)a2->Cxn);
  v57 = v66;
  v58 = v71;
  v67 = 0;
  v68[0] = 0;
  v66->ConfigOp.Steps = 0;
  v57->ConfigOp.NumSteps = 0;
  v57->ConfigOp.FnTerminate = 0;
  v57->ConfigOp.CmdContext = 0;
  *(_WORD *)&v57->ConfigOp.InProgress = 0;
  v57->ConfigOp.CurrentStep = -1;
  *(_QWORD *)&v57->ConfigOp.Status = 0;
  v57->ConfigOp.Data = 0;
  v57->ConfigOp.Steps = (const _MULTI_STEP_CMD_ENTRY *)&off_1401691C0;
  v57->ConfigOp.FnTerminate = (int (__fastcall *)(void *, int))Hci_CxnPostConnectMultiStepComplete;
  v57->ConfigOp.NumSteps = 5;
  v57->ConfigOp.CmdContext = v25;
  v57->ConfigOp.InProgress = 1;
  v66->ConfigOp.Data = v58;
  Hci_CxnPostConnectMultiStepComplete(v25, -1073741667);
LABEL_108:
  v66 = 0;
  v65 = 0;
LABEL_113:
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(v68);
LABEL_114:
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(&v67);
  _Reset___RefObjReference_U_HCI_CONNECTION___07_M__T0A__M__T0A___QEAAXPEAU_HCI_CONNECTION__PEBX_Z(&v65, 0, 0);
}

```

## disassembly

```asm
0x140043de8  mov     [rsp-8+arg_10], rbx
0x140043ded  push    rbp
0x140043dee  push    rsi
0x140043def  push    rdi
0x140043df0  push    r12
0x140043df2  push    r13
0x140043df4  push    r14
0x140043df6  push    r15
0x140043df8  lea     rbp, [rsp-0F0h]
0x140043e00  sub     rsp, 1F0h
0x140043e07  mov     rax, cs:__security_cookie
0x140043e0e  xor     rax, rsp
0x140043e11  mov     [rbp+120h+var_40], rax
0x140043e18  mov     rdi, rdx
0x140043e1b  mov     [rbp+120h+var_190], rdx
0x140043e1f  mov     rdx, [rdx+10h]
0x140043e23  xor     esi, esi
0x140043e25  mov     [rbp+120h+var_198], rcx
0x140043e29  mov     r13, r8
0x140043e2c  mov     r14, rcx
0x140043e2f  test    rdx, rdx
0x140043e32  jnz     short loc_140043E8F
0x140043e34  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043e3b  lea     ebx, [rsi+2]
0x140043e3e  mov     eax, [rcx+2Ch]
0x140043e41  test    bl, al
0x140043e43  jz      short loc_140043E4C
0x140043e45  mov     dl, 1
0x140043e47  cmp     [rcx+29h], bl
0x140043e4a  jnb     short loc_140043E4F
0x140043e4c  mov     dl, sil
0x140043e4f  mov     r9, [r14+10B0h]
0x140043e56  lea     rsi, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x140043e5d  mov     rcx, [rcx+18h]
0x140043e61  mov     r8b, 1
0x140043e64  mov     [rsp+220h+var_1E8], rsi
0x140043e69  mov     [rsp+220h+var_1F0], 99h
0x140043e70  mov     dword ptr [rsp+220h+var_1F8], ebx
0x140043e74  mov     byte ptr [rsp+220h+var_200], bl
0x140043e78  call    WPP_RECORDER_AND_TRACE_SF_
0x140043e7d  lea     rcx, [rbp+120h+var_198]
0x140043e81  mov     [rbp+120h+var_188], 0
0x140043e85  call    _lambda_f2b11b09d4f9c993158efe3f1e82ebd9___operator__
0x140043e8a  jmp     loc_14004484B
0x140043e8f  lea     r8, ?Hci_CxnPostConnectMultiStepComplete@@YAJPEAXJ@Z; Hci_CxnPostConnectMultiStepComplete(void *,long)
0x140043e96  lea     rcx, [rsp+220h+var_1C0]
0x140043e9b  call    ?MakeWithAddRef@?$RefObjReference@U_HCI_CONNECTION@@$07$M$$T0A@$M$$T0A@@@SA?AV1@PEAU_HCI_CONNECTION@@PEBX@Z
0x140043ea0  lea     rcx, [rsp+220h+var_1B0]
0x140043ea5  call    ??$make_unique@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@U?$default_delete@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@@utl@@@0@XZ; utl::make_unique<_HCI_POST_CONNECT_PROCESS_CONTEXT,,0>(void)
0x140043eaa  mov     rbx, [rsp+220h+var_1B0]
0x140043eaf  mov     [rbp+120h+var_180], rbx
0x140043eb3  test    rbx, rbx
0x140043eb6  jnz     short loc_140043F21
0x140043eb8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043ebf  mov     ebx, 2
0x140043ec4  mov     eax, [rcx+2Ch]
0x140043ec7  test    bl, al
0x140043ec9  jz      short loc_140043ED2
0x140043ecb  mov     dl, 1
0x140043ecd  cmp     [rcx+29h], bl
0x140043ed0  jnb     short loc_140043ED5
0x140043ed2  mov     dl, sil
0x140043ed5  mov     r9, [r14+10B0h]
0x140043edc  lea     rsi, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x140043ee3  mov     rcx, [rcx+18h]
0x140043ee7  mov     r8b, 1
0x140043eea  mov     [rsp+220h+var_1E8], rsi
0x140043eef  mov     [rsp+220h+var_1F0], 9Ah
0x140043ef6  mov     dword ptr [rsp+220h+var_1F8], ebx
0x140043efa  mov     byte ptr [rsp+220h+var_200], bl
0x140043efe  call    WPP_RECORDER_AND_TRACE_SF_
0x140043f03  lea     rcx, [rsp+220h+var_1B0]
0x140043f08  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UProcedureUpdateRequest@LESelectiveConnectionEstablishmentProcedure@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<LESelectiveConnectionEstablishmentProcedure::ProcedureUpdateRequest>>>(void)
0x140043f0d  xor     r8d, r8d
0x140043f10  lea     rcx, [rsp+220h+var_1C0]
0x140043f15  xor     edx, edx
0x140043f17  call    ?Reset@?$RefObjReference@U_HCI_CONNECTION@@$07$M$$T0A@$M$$T0A@@@QEAAXPEAU_HCI_CONNECTION@@PEBX@Z
0x140043f1c  jmp     loc_140043E7D
0x140043f21  mov     eax, [rdi+18h]
0x140043f24  lea     rcx, [rbp+120h+var_AC]; void *
0x140043f28  mov     [rbx], eax
0x140043f2a  xor     edx, edx; Val
0x140043f2c  mov     al, [rdi+1Ch]
0x140043f2f  mov     [rbx+4], al
0x140043f32  mov     [rbx+10h], sil
0x140043f36  lea     r8d, [rdx+6Ch]; Size
0x140043f3a  call    memset
0x140043f3f  lea     rax, [rbp+120h+var_100]
0x140043f43  xor     edx, edx; Val
0x140043f45  mov     [rbp+120h+var_F8], rax
0x140043f49  lea     rcx, [rbp+120h+var_A8]; void *
0x140043f4d  lea     rax, [rbp+120h+var_100]
0x140043f51  mov     [rbp+120h+var_100], rax
0x140043f55  lea     rax, [rbp+120h+var_F0]
0x140043f59  mov     [rbp+120h+var_E8], rax
0x140043f5d  lea     r8d, [rdx+68h]; Size
0x140043f61  lea     rax, [rbp+120h+var_F0]
0x140043f65  mov     [rbp+120h+var_F0], rax
0x140043f69  lea     rax, [rbp+120h+var_E0]
0x140043f6d  mov     [rbp+120h+var_D8], rax
0x140043f71  lea     rax, [rbp+120h+var_E0]
0x140043f75  mov     [rbp+120h+var_E0], rax
0x140043f79  lea     rax, [rbp+120h+var_D0]
0x140043f7d  mov     [rbp+120h+var_C8], rax
0x140043f81  lea     rax, [rbp+120h+var_D0]
0x140043f85  mov     [rbp+120h+var_D0], rax
0x140043f89  lea     rax, [rbp+120h+var_C0]
0x140043f8d  mov     [rbp+120h+var_B8], rax
0x140043f91  lea     rax, [rbp+120h+var_C0]
0x140043f95  mov     [rbp+120h+var_C0], rax
0x140043f99  call    memset
0x140043f9e  mov     rcx, [rdi+8]
0x140043fa2  mov     [rbp+120h+var_B0], esi
0x140043fa5  test    rcx, rcx
0x140043fa8  jz      short loc_140043FC7
0x140043faa  movzx   eax, word ptr [rcx+3]
0x140043fae  mov     [rbp+120h+var_A8.ConnectionHandle], ax
0x140043fb5  movzx   eax, byte ptr [rcx+0Ch]
0x140043fb9  mov     [rbx+8], eax
0x140043fbc  mov     rax, [rdi+8]
0x140043fc0  movzx   ecx, byte ptr [rax+0Bh]
0x140043fc4  mov     [rbx+0Ch], ecx
0x140043fc7  mov     rdx, [rsp+220h+var_1B8]
0x140043fcc  lea     rcx, [rsp+220h+var_1A8]
0x140043fd1  add     rdx, 50h ; 'P'
0x140043fd5  mov     r12, rsi
0x140043fd8  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x140043fdd  mov     rcx, [rsp+220h+var_1B8]
0x140043fe2  mov     eax, [rcx+1D8h]
0x140043fe8  test    al, 4
0x140043fea  jz      short loc_140043FF0
0x140043fec  mov     bl, 1
0x140043fee  jmp     short loc_140043FFC
0x140043ff0  or      eax, 4
0x140043ff3  mov     bl, sil
0x140043ff6  mov     [rcx+1D8h], eax
0x140043ffc  mov     rcx, [rsp+220h+var_1B8]; struct _HCI_CONNECTION *
0x140044001  mov     r15d, [rcx+1D8h]
0x140044008  cmp     [rdi+1Ch], sil
0x14004400c  jnz     short loc_14004403E
0x14004400e  mov     r8d, 100h; unsigned int
0x140044014  lea     rdx, [rbp+120h+var_A8]; struct _HCI_CONNECTION_INFO *
0x140044018  call    ?HCI_CxnSetInfoLocked@@YAXPEAU_HCI_CONNECTION@@PEAU_HCI_CONNECTION_INFO@@K@Z; HCI_CxnSetInfoLocked(_HCI_CONNECTION *,_HCI_CONNECTION_INFO *,ulong)
0x14004401d  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140044022  test    eax, eax
0x140044024  jz      short loc_140044038
0x140044026  test    bl, bl
0x140044028  jnz     short loc_140044038
0x14004402a  test    r15b, 8
0x14004402e  jnz     short loc_140044038
0x140044030  lock inc dword ptr [r14+0ADCh]
0x140044038  cmp     [rdi+1Ch], sil
0x14004403c  jz      short loc_140044080
0x14004403e  test    r15b, 8
0x140044042  jnz     short loc_140044080
0x140044044  test    bl, bl
0x140044046  jnz     short loc_140044080
0x140044048  mov     rax, [rsp+220h+var_1B8]
0x14004404d  mov     rcx, [rax+2D8h]
0x140044054  test    rcx, rcx
0x140044057  jz      short loc_140044080
0x140044059  add     rcx, 40h ; '@'; PKTIMER
0x14004405d  call    cs:__imp_KeCancelTimer
0x140044064  nop     dword ptr [rax+rax+00h]
0x140044069  test    al, al
0x14004406b  jz      short loc_140044080
0x14004406d  mov     rax, [rsp+220h+var_1B8]
0x140044072  mov     r12, [rax+2D8h]
0x140044079  mov     [rax+2D8h], rsi
0x140044080  lea     rcx, [rsp+220h+var_1A8]
0x140044085  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14004408a  test    bl, bl
0x14004408c  jz      short loc_1400440EE
0x14004408e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044095  mov     ebx, 2
0x14004409a  mov     eax, [rcx+2Ch]
0x14004409d  test    bl, al
0x14004409f  jz      short loc_1400440A9
0x1400440a1  cmp     byte ptr [rcx+29h], 4
0x1400440a5  mov     dl, 1
0x1400440a7  jnb     short loc_1400440AC
0x1400440a9  mov     dl, sil
0x1400440ac  mov     rax, [rsp+220h+var_1B8]
0x1400440b1  lea     rsi, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x1400440b8  mov     rcx, [rcx+18h]
0x1400440bc  mov     r8b, 1
0x1400440bf  mov     [rsp+220h+var_1E0], rax
0x1400440c4  mov     [rsp+220h+var_1E8], rsi
0x1400440c9  mov     r9, [rax+30h]
0x1400440cd  mov     [rsp+220h+var_1F0], 9Bh
0x1400440d4  mov     dword ptr [rsp+220h+var_1F8], ebx
0x1400440d8  mov     byte ptr [rsp+220h+var_200], 4
0x1400440dd  mov     r9, [r9+838h]
0x1400440e4  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400440e9  jmp     loc_140044832
0x1400440ee  lea     rdx, [r14+7B0h]
0x1400440f5  lea     rcx, [rsp+220h+var_1A8]
0x1400440fa  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x1400440ff  mov     rax, [rsp+220h+var_1B8]
0x140044104  mov     rcx, [rax+30h]
0x140044108  mov     al, [rdi+1Ch]
0x14004410b  mov     [rcx+5B7h], al
0x140044111  mov     rax, [rsp+220h+var_1B8]
0x140044116  mov     rcx, [rax+30h]
0x14004411a  mov     [rcx+5B8h], sil
0x140044121  cmp     [rdi+1Ch], sil
0x140044125  jnz     short loc_14004413C
0x140044127  mov     rax, [rsp+220h+var_1B8]
0x14004412c  mov     rcx, [rax+30h]
0x140044130  mov     eax, [rax+0C0h]
0x140044136  mov     [rcx+5BCh], eax
0x14004413c  lea     rcx, [rsp+220h+var_1A8]
0x140044141  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x140044146  cmp     byte ptr [rdi+1Ch], 0
0x14004414a  lea     rsi, WPP_00e3905cb5d731155da0de3c434dc4e5_Traceguids
0x140044151  mov     ebx, 2
0x140044156  jz      loc_14004421F
0x14004415c  xor     edx, edx; Val
0x14004415e  lea     r8d, [rbx+66h]; Size
0x140044162  lea     rcx, [rbp+120h+var_170]; void *
0x140044166  call    memset
0x14004416b  mov     rcx, [rsp+220h+var_1B8]; struct _HCI_CONNECTION *
0x140044170  lea     rdx, [rbp+120h+var_170]; struct _HCI_CONNECTION_INFO *
0x140044174  call    ?HCI_CxnGetInfo@@YAXPEAU_HCI_CONNECTION@@PEAU_HCI_CONNECTION_INFO@@@Z; HCI_CxnGetInfo(_HCI_CONNECTION *,_HCI_CONNECTION_INFO *)
0x140044179  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044180  mov     eax, [rcx+2Ch]
0x140044183  test    bl, al
0x140044185  jz      short loc_140044191
0x140044187  cmp     byte ptr [rcx+29h], 4
0x14004418b  jb      short loc_140044191
0x14004418d  mov     dl, 1
0x14004418f  jmp     short loc_140044193
0x140044191  xor     dl, dl
0x140044193  mov     r8, [rsp+220h+var_1B8]
0x140044198  movzx   eax, byte ptr [rdi+1Ch]
0x14004419c  mov     rcx, [rcx+18h]
0x1400441a0  mov     dword ptr [rsp+220h+var_1D0], eax
0x1400441a4  mov     r9, [r8+30h]
0x1400441a8  mov     eax, [rbp+120h+var_170.State]
0x1400441ab  mov     dword ptr [rsp+220h+var_1D8], eax
0x1400441af  mov     [rsp+220h+var_1E0], r8
0x1400441b4  mov     r9, [r9+838h]
0x1400441bb  mov     [rsp+220h+var_1E8], rsi
0x1400441c0  mov     [rsp+220h+var_1F0], 9Ch
0x1400441c7  mov     dword ptr [rsp+220h+var_1F8], ebx
0x1400441cb  mov     byte ptr [rsp+220h+var_200], 4
0x1400441d0  call    WPP_RECORDER_AND_TRACE_SF_qLD
0x1400441d5  test    r15b, 8
0x1400441d9  jnz     short loc_14004424E
0x1400441db  test    r12, r12
0x1400441de  jz      short loc_1400441FA
0x1400441e0  mov     rcx, [rsp+220h+var_1B8]; struct _HCI_CONNECTION *
0x1400441e5  xor     r9d, r9d; struct _GUID *
0x1400441e8  xor     r8d, r8d; unsigned __int8
0x1400441eb  mov     dl, 5; unsigned __int8
0x1400441ed  call    ?HCI_CxnAuthComplete@@YAXPEAU_HCI_CONNECTION@@EEPEAU_GUID@@@Z; HCI_CxnAuthComplete(_HCI_CONNECTION *,uchar,uchar,_GUID *)
0x1400441f2  mov     rcx, r12; P
0x1400441f5  call    ?HCI_DeleteAuthenticationResultContext@@YAXPEAU_BTH_AUTHENTICATION_RESULT_CONTEXT@@@Z; HCI_DeleteAuthenticationResultContext(_BTH_AUTHENTICATION_RESULT_CONTEXT *)
0x1400441fa  mov     rcx, [rsp+220h+var_1B8]; struct _HCI_CONNECTION *
0x1400441ff  call    ?HCI_CxnMakeZombie@@YAXPEAU_HCI_CONNECTION@@@Z; HCI_CxnMakeZombie(_HCI_CONNECTION *)
0x140044204  mov     rdx, [rsp+220h+var_1B8]
0x140044209  lea     r9, aOnecoreDrivers_26; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140044210  mov     r8d, 158Bh
0x140044216  lea     rcx, [rdx+8]
0x14004421a  call    RefObj_ReleaseEx
0x14004421f  lea     rcx, [rsp+220h+var_1A8]
0x140044224  call    ??$make_unique@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@$$V$0A@@utl@@YA?AV?$unique_ptr@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@U?$default_delete@U_HCI_POST_CONNECT_PROCESS_CONTEXT@@@utl@@@0@XZ; utl::make_unique<_HCI_POST_CONNECT_PROCESS_CONTEXT,,0>(void)
0x140044229  mov     r12, [rsp+220h+var_1A8]
0x14004422e  test    r12, r12
0x140044231  jnz     loc_1400442E4
0x140044237  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004423e  mov     eax, [rcx+2Ch]
0x140044241  test    bl, al
0x140044243  jz      short loc_1400442A3
0x140044245  cmp     [rcx+29h], bl
0x140044248  jb      short loc_1400442A3
0x14004424a  mov     dl, 1
0x14004424c  jmp     short loc_1400442A5
0x14004424e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044255  mov     eax, [rcx+2Ch]
0x140044258  test    bl, al
0x14004425a  jz      short loc_140044266
0x14004425c  cmp     byte ptr [rcx+29h], 4
0x140044260  jb      short loc_140044266
0x140044262  mov     dl, 1
0x140044264  jmp     short loc_140044268
0x140044266  xor     dl, dl
0x140044268  mov     rax, [rsp+220h+var_1B8]
0x14004426d  mov     r8b, 1
0x140044270  mov     rcx, [rcx+18h]
0x140044274  mov     [rsp+220h+var_1E0], rax
0x140044279  mov     [rsp+220h+var_1E8], rsi
0x14004427e  mov     r9, [rax+30h]
0x140044282  mov     [rsp+220h+var_1F0], 9Dh
0x140044289  mov     dword ptr [rsp+220h+var_1F8], ebx
0x14004428d  mov     byte ptr [rsp+220h+var_200], 4
0x140044292  mov     r9, [r9+838h]
0x140044299  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004429e  jmp     loc_140043F03
0x1400442a3  xor     dl, dl
  ... truncated ...
```
