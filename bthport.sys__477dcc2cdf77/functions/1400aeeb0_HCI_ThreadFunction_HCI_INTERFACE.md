# HCI_ThreadFunction(HCI_INTERFACE *)

- ea: `0x1400aeeb0`
- end: `0x1400af91e`
- name: `?HCI_ThreadFunction@@YAJPEAUHCI_INTERFACE@@@Z`
- size: `2670`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400af930`

## callees

- `0x1400043d0`
- `0x1400054dc`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x140005dd8`
- `0x1400250c8`
- `0x1400469c0`
- `0x140077a20`
- `0x140078e30`
- `0x14007e804`
- `0x14007ee94`
- `0x140080ae8`
- `0x140086860`
- `0x1400868b0`
- `0x140086900`
- `0x140086950`
- `0x1400869a0`
- `0x140098250`
- `0x1400aa380`
- `0x1400ab004`
- `0x1400ae4b4`
- `0x1400ae570`
- `0x1400aeeb0`
- `0x14014e234`
- `0x14015b100`
- `0x14015ce38`
- `0x14015da5c`
- `0x140162478`
- `0x140165540`
- `0x140165580`
- `0x1401d3324`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400af0bd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400af0bd`
- `ntoskrnl!KeClearEvent` at `0x1400af171`
- `ntoskrnl!KeClearEvent` at `0x1400af1e5`
- `ntoskrnl!KeClearEvent` at `0x1400af205`
- `ntoskrnl!KeClearEvent` at `0x1400af2c1`
- `ntoskrnl!KeClearEvent` at `0x1400af300`
- `ntoskrnl!KeClearEvent` at `0x1400af347`
- `ntoskrnl!KeClearEvent` at `0x1400af367`
- `ntoskrnl!KeClearEvent` at `0x1400af387`
- `ntoskrnl!KeClearEvent` at `0x1400af3ab`
- `ntoskrnl!KeClearEvent` at `0x1400af3d0`
- `ntoskrnl!KeClearEvent` at `0x1400af45f`
- `ntoskrnl!KeClearEvent` at `0x1400af4bf`
- `ntoskrnl!KeClearEvent` at `0x1400af54a`
- `ntoskrnl!KeClearEvent` at `0x1400af5cf`
- `ntoskrnl!KeClearEvent` at `0x1400af654`
- `ntoskrnl!KeClearEvent` at `0x1400af6d9`
- `ntoskrnl!KeClearEvent` at `0x1400af6fd`
- `ntoskrnl!KeClearEvent` at `0x1400af861`
- `ntoskrnl!KeClearEvent` at `0x1400af882`
- `ntoskrnl!KeClearEvent` at `0x1400af8a3`
- `ntoskrnl!KeClearEvent` at `0x1400af8d4`
- `ntoskrnl!KeClearEvent` at `0x1400af171`
- `ntoskrnl!KeClearEvent` at `0x1400af1e5`
- `ntoskrnl!KeClearEvent` at `0x1400af205`
- `ntoskrnl!KeClearEvent` at `0x1400af2c1`
- `ntoskrnl!KeClearEvent` at `0x1400af300`
- `ntoskrnl!KeClearEvent` at `0x1400af347`
- `ntoskrnl!KeClearEvent` at `0x1400af367`
- `ntoskrnl!KeClearEvent` at `0x1400af387`
- `ntoskrnl!KeClearEvent` at `0x1400af3ab`
- `ntoskrnl!KeClearEvent` at `0x1400af3d0`
- `ntoskrnl!KeClearEvent` at `0x1400af45f`
- `ntoskrnl!KeClearEvent` at `0x1400af4bf`
- `ntoskrnl!KeClearEvent` at `0x1400af54a`
- `ntoskrnl!KeClearEvent` at `0x1400af5cf`
- `ntoskrnl!KeClearEvent` at `0x1400af654`
- `ntoskrnl!KeClearEvent` at `0x1400af6d9`
- `ntoskrnl!KeClearEvent` at `0x1400af6fd`
- `ntoskrnl!KeClearEvent` at `0x1400af861`
- `ntoskrnl!KeClearEvent` at `0x1400af882`
- `ntoskrnl!KeClearEvent` at `0x1400af8a3`
- `ntoskrnl!KeClearEvent` at `0x1400af8d4`
- `ntoskrnl!KeSetEvent` at `0x1400aefa2`
- `ntoskrnl!KeSetEvent` at `0x1400af02a`
- `ntoskrnl!KeSetEvent` at `0x1400af07b`
- `ntoskrnl!KeSetEvent` at `0x1400af84c`
- `ntoskrnl!KeSetEvent` at `0x1400aefa2`
- `ntoskrnl!KeSetEvent` at `0x1400af02a`
- `ntoskrnl!KeSetEvent` at `0x1400af07b`
- `ntoskrnl!KeSetEvent` at `0x1400af84c`

## string_xrefs

- `0x1400af5b7`: `HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_UPDATE_COMPLETE cannot be signaled if refactor is not enabled.`
- `0x1400af63c`: `HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_PAUSE_COMPLETE cannot be signaled if refactor is not enabled.`
- `0x1400af532`: `HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_PAUSE_TOKEN_RELEASE cannot be signaled if refactor is not enabled.`

## pseudocode

```c
__int64 __fastcall HCI_ThreadFunction(struct HCI_INTERFACE *a1, __int16 a2)
{
  __m128i si128; // xmm6
  __int16 v4; // dx
  __int16 v6; // dx
  PVOID *v7; // r14
  unsigned __int64 i; // rdx
  struct _KWAIT_BLOCK *WaitBlockArray; // r12
  ULONG v10; // esi
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rbx
  __int64 *v15; // r8
  int v16; // edx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  char *v20; // rax
  char v21; // bl
  DEVICE_EXTENSION *DevExt; // rcx
  __int64 v23; // rax
  _LIST_ENTRY *p_BipQueue; // rcx
  struct HCI_INTERFACE **Flink; // rax
  _LIST_ENTRY *v26; // rdx
  struct _BIP *v27; // rbx
  __int16 v28; // dx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  __int16 v33; // dx
  SmFx::StateMachineEngine::StateMachineEngineImpl **MyRealVal; // rcx
  unsigned __int16 v35; // dx
  __int16 v36; // dx
  __int16 v37; // dx
  __int16 v38; // dx
  __int64 *v39; // r8
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-A8h] BYREF
  PVOID *__attribute__((__org_arrdim(0,0))) Object_8[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h]
  PKWAIT_BLOCK v44[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+98h] [rbp-70h]
  __int64 v46; // [rsp+A0h] [rbp-68h] BYREF
  utl::_RefCountBase *v47; // [rsp+A8h] [rbp-60h]
  _BYTE v48[16]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int8 v49[16]; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int8 v50[16]; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v51; // [rsp+E0h] [rbp-28h]
  __int128 v52; // [rsp+F0h] [rbp-18h]
  __int64 v53; // [rsp+100h] [rbp-8h]

  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    a2,
    1,
    a1->IfrLog,
    4,
    2,
    12,
    (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)v44 = si128;
  v45 = -1;
  if ( !(unsigned __int8)utl::vector<_KWAIT_BLOCK,utl::allocator<_KWAIT_BLOCK>>::_Resize<,0>(v44) )
  {
    LOBYTE(v4) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      1,
      a1->IfrLog,
      2,
      2,
      13,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
    KeSetEvent(&a1->SynchThreadEvent, 0, 0);
LABEL_11:
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(v44);
    return 3221225626LL;
  }
  v43 = -1;
  *(__m128i *)Object_8 = si128;
  if ( !(unsigned __int8)utl::vector<void *,utl::allocator<void *>>::_Resize<,0>(Object_8) )
  {
    LOBYTE(v6) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      1,
      a1->IfrLog,
      2,
      2,
      14,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
    KeSetEvent(&a1->SynchThreadEvent, 0, 0);
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(Object_8);
    goto LABEL_11;
  }
  v7 = Object_8[0];
  for ( i = 0; i < 0x15; ++i )
    v7[i] = &a1->ThreadEvents[i];
  a1->ThreadInitialized = 1;
  KeSetEvent(&a1->SynchThreadEvent, 0, 0);
  WaitBlockArray = v44[0];
  v10 = Object_8[1] - v7 - 1;
  while ( 1 )
  {
    v11 = KeWaitForMultipleObjects(v10, v7, WaitAny, Executive, 0, 0, 0, WaitBlockArray);
    v14 = v11;
    if ( v11 >= 21 )
    {
      if ( v11 >= v10 )
      {
        LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        LOBYTE(v13) = 1;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          a1->IfrLog,
          2,
          2,
          17,
          (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
          v11);
      }
      else
      {
        LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v13) = 1;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          a1->IfrLog,
          4,
          2,
          16,
          (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
          v11 - 21);
      }
LABEL_118:
      switch ( (_DWORD)v14 )
      {
        case 0x12:
          KeClearEvent(&a1->ThreadEvents[18]);
          HciLEAdvertisingRequestCoordinator::OnRadioReady(&a1->leAdvertisingRequestCoordinator);
          break;
        case 0x13:
          KeClearEvent(&a1->ThreadEvents[19]);
          HciLEAdvertisingRequestCoordinator::OnRadioReset(&a1->leAdvertisingRequestCoordinator);
          break;
        case 0x14:
          KeClearEvent(&a1->ThreadEvents[20]);
          HciLEAdvertisingRequestCoordinator::ProcessRandomAddressCompletion(&a1->leAdvertisingRequestCoordinator);
          break;
        case 0x15:
          LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          v39 = WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids;
          LOBYTE(v39) = 1;
          WPP_RECORDER_AND_TRACE_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            v16,
            (_DWORD)v39,
            a1->IfrLog,
            4,
            2,
            23,
            (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
            21);
          v7[v14] = 0;
          --v10;
          KeSetEvent((PRKEVENT)&a1->DebugMode, 0, 0);
          break;
      }
      goto LABEL_130;
    }
    LOBYTE(v12) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    v15 = WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids;
    LOBYTE(v15) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v12,
      (_DWORD)v15,
      a1->IfrLog,
      4,
      2,
      15,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
      v11);
    if ( (int)v14 <= 11 )
      break;
    if ( (int)v14 > 17 )
      goto LABEL_118;
    if ( (_DWORD)v14 == 17 )
    {
      KeClearEvent(&a1->ThreadEvents[17]);
      HciLE_HandleSetLERandomAddressEvent(a1);
    }
    else
    {
      v29 = v14 - 12;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( v32 )
            {
              if ( v32 != 1 )
                goto LABEL_130;
              KeClearEvent(&a1->ThreadEvents[16]);
              MyRealVal = (SmFx::StateMachineEngine::StateMachineEngineImpl **)a1->DeviceListProcessorModule._MyDat._MyRealVal;
              if ( MyRealVal )
              {
                v35 = 7;
LABEL_78:
                SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEvent(*MyRealVal, v35);
                goto LABEL_130;
              }
              LOBYTE(v33) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              WPP_RECORDER_AND_TRACE_SF_(
                WPP_GLOBAL_Control->AttachedDevice,
                v33,
                1,
                a1->IfrLog,
                2,
                2,
                22,
                (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
              MicrosoftTelemetryAssertTriggeredMsgKM(
                "HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_PAUSE_TOKEN_RELEASE cannot be signaled if refactor is not enabled.");
            }
            else
            {
              KeClearEvent(&a1->ThreadEvents[15]);
              MyRealVal = (SmFx::StateMachineEngine::StateMachineEngineImpl **)a1->DeviceListProcessorModule._MyDat._MyRealVal;
              if ( MyRealVal )
              {
                v35 = 11;
                goto LABEL_78;
              }
              LOBYTE(v36) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              WPP_RECORDER_AND_TRACE_SF_(
                WPP_GLOBAL_Control->AttachedDevice,
                v36,
                1,
                a1->IfrLog,
                2,
                2,
                21,
                (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
              MicrosoftTelemetryAssertTriggeredMsgKM("HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_UPDATE_COMPLETE cannot be signaled if refactor is not enabled.");
            }
          }
          else
          {
            KeClearEvent(&a1->ThreadEvents[14]);
            MyRealVal = (SmFx::StateMachineEngine::StateMachineEngineImpl **)a1->DeviceListProcessorModule._MyDat._MyRealVal;
            if ( MyRealVal )
            {
              v35 = 6;
              goto LABEL_78;
            }
            LOBYTE(v37) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            WPP_RECORDER_AND_TRACE_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              v37,
              1,
              a1->IfrLog,
              2,
              2,
              20,
              (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
            MicrosoftTelemetryAssertTriggeredMsgKM("HCI_EVENT_DEVICE_LIST_PROCESSOR_SCAN_PAUSE_COMPLETE cannot be signaled if refactor is not enabled.");
          }
        }
        else
        {
          KeClearEvent(&a1->ThreadEvents[13]);
          MyRealVal = (SmFx::StateMachineEngine::StateMachineEngineImpl **)a1->DeviceListProcessorModule._MyDat._MyRealVal;
          if ( MyRealVal )
          {
            v35 = 4;
            goto LABEL_78;
          }
          LOBYTE(v38) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v38,
            1,
            a1->IfrLog,
            2,
            2,
            19,
            (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
          MicrosoftTelemetryAssertTriggeredMsgKM("HCI_EVENT_DEVICE_LIST_PROCESSOR_PROCESS_REQUEST cannot be signaled if refactor is not enabled.");
        }
      }
      else
      {
        KeClearEvent(&a1->ThreadEvents[12]);
        HciLEAdvertisingRequestCoordinator::OnLegacyAdvertisingTerminatedDueToConnectionComplete(&a1->leAdvertisingRequestCoordinator);
      }
    }
LABEL_130:
    HCI_StartIdleTimer(a1, 0);
  }
  if ( (_DWORD)v14 == 11 )
  {
    KeClearEvent(&a1->ThreadEvents[11]);
    HciDebugModeExpired(a1);
    goto LABEL_130;
  }
  if ( (int)v14 > 5 )
  {
    switch ( (_DWORD)v14 )
    {
      case 6:
        KeClearEvent((PRKEVENT)((char *)a1->ThreadEvents + 16 * v14 + 8 * v14));
        DeviceListProcessor::RequestDeviceListProcessing(a1->DeviceListProcessorModule._MyDat._MyRealVal, &v46, 0);
        if ( !v46 )
        {
          LOBYTE(v28) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v28,
            1,
            a1->IfrLog,
            3,
            2,
            18,
            (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids);
        }
        if ( v47 )
          utl::_RefCountBase::_DecStrong(v47);
        break;
      case 7:
        KeClearEvent(&a1->ThreadEvents[7]);
        HCI_ProcessSniffModeManagerEvent(a1);
        break;
      case 8:
        KeClearEvent(&a1->ThreadEvents[8]);
        HciLEAdvertisingRequestCoordinator::OnProcessAdvertisingRequestsEvent(&a1->leAdvertisingRequestCoordinator);
        break;
      case 9:
        KeClearEvent(&a1->ThreadEvents[9]);
        HciLEAdv_ProcessTimeSlicingTimer(a1);
        break;
      default:
        KeClearEvent(&a1->ThreadEvents[10]);
        HciLE_GenerateNewRandomAddresses(a1);
        break;
    }
    goto LABEL_130;
  }
  if ( (_DWORD)v14 == 5 )
  {
    KeClearEvent(&a1->ThreadEvents[5]);
    SMPInt_ProcessSMPEvent(a1->DevExt);
    goto LABEL_130;
  }
  if ( (_DWORD)v14 )
  {
    v17 = v14 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          if ( v19 == 1 )
          {
            KeClearEvent(&a1->ThreadEvents[4]);
            *(_OWORD *)v50 = 0;
            v53 = 0;
            v51 = 0;
            v52 = 0;
            wil::acquire_kspin_lock(v48, &a1->HciLock);
            LOWORD(v20) = HCI_GetNextConnectRequest(
                            (struct HCI_INTERFACE *)&v40,
                            (struct _HCI_CONNECT_REQUEST *)a1,
                            0,
                            (unsigned __int8)v50);
            v21 = *v20;
            wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v48);
            if ( v21 )
              HCI_ProcessConnectRequest(a1, (struct _HCI_CONNECT_REQUEST *)v50);
          }
        }
        else
        {
          KeClearEvent(&a1->ThreadEvents[3]);
          HCI_HandleSSPRemoteNameRequest(a1);
        }
      }
      else
      {
        KeClearEvent(&a1->ThreadEvents[2]);
        DevExt = a1->DevExt;
        v41[1] = v41;
        v41[0] = v41;
        IrpList_Drain(&DevExt->PassiveRequestQueue, v41);
        while ( 1 )
        {
          v23 = Microsoft::Bluetooth::Foundation::Details::list_impl<Microsoft::Bluetooth::Foundation::intrusive_offset_hook_traits<_IRP,168>,Microsoft::Bluetooth::Foundation::intrusive_list_t<Microsoft::Bluetooth::Foundation::intrusive_offset_hook_traits<_IRP,168>>>::try_pop_front(Object_8);
          if ( !v23 )
            break;
          (*(void (__fastcall **)(DEVICE_EXTENSION *, __int64))(v23 + 120))(a1->DevExt, v23);
        }
      }
    }
    else
    {
      wil::acquire_kspin_lock(v49, &a1->HciLock);
      p_BipQueue = &a1->BipQueue;
      Flink = (struct HCI_INTERFACE **)a1->BipQueue.Flink;
      if ( Flink[1] != (struct HCI_INTERFACE *)&a1->BipQueue
        || (v26 = (_LIST_ENTRY *)*Flink, *(struct HCI_INTERFACE ***)&(*Flink)->RefObj.Count != Flink) )
      {
        __fastfail(3u);
      }
      p_BipQueue->Flink = v26;
      v26->Blink = p_BipQueue;
      if ( Flink == (struct HCI_INTERFACE **)p_BipQueue )
      {
        v27 = 0;
      }
      else
      {
        Flink[1] = (struct HCI_INTERFACE *)Flink;
        v27 = (struct _BIP *)(Flink - 11);
        *Flink = (struct HCI_INTERFACE *)Flink;
      }
      if ( p_BipQueue->Flink == p_BipQueue )
      {
        KeClearEvent(&a1->ThreadEvents[1]);
        HCI_StartIdleTimer(a1, 1u);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v49);
      if ( v27 )
        HCI_ProcessBip(a1, v27);
    }
    goto LABEL_130;
  }
  KeClearEvent(a1->ThreadEvents);
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(Object_8);
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(v44);
  return 0;
}

```

## disassembly

```asm
0x1400aeeb0  mov     rax, rsp
0x1400aeeb3  push    rbp
0x1400aeeb4  push    rbx
0x1400aeeb5  push    rsi
0x1400aeeb6  push    rdi
0x1400aeeb7  push    r12
0x1400aeeb9  push    r13
0x1400aeebb  push    r14
0x1400aeebd  push    r15
0x1400aeebf  lea     rbp, [rax-68h]
0x1400aeec3  sub     rsp, 128h
0x1400aeeca  movaps  xmmword ptr [rax-58h], xmm6
0x1400aeece  mov     rax, cs:__security_cookie
0x1400aeed5  xor     rax, rsp
0x1400aeed8  mov     [rbp+60h+var_60], rax
0x1400aeedc  mov     rdi, rcx
0x1400aeedf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aeee6  mov     r13d, 2
0x1400aeeec  mov     eax, [rcx+2Ch]
0x1400aeeef  test    r13b, al
0x1400aeef2  jz      short loc_1400AEEFE
0x1400aeef4  cmp     byte ptr [rcx+29h], 4
0x1400aeef8  jb      short loc_1400AEEFE
0x1400aeefa  mov     dl, 1
0x1400aeefc  jmp     short loc_1400AEF00
0x1400aeefe  xor     dl, dl
0x1400aef00  mov     r9, [rdi+10B0h]
0x1400aef07  lea     rsi, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1400aef0e  mov     rcx, [rcx+18h]
0x1400aef12  mov     r8b, 1
0x1400aef15  mov     [rsp+160h+WaitBlockArray], rsi
0x1400aef1a  mov     word ptr [rsp+160h+Timeout], 0Ch
0x1400aef21  mov     dword ptr [rsp+160h+Alertable], r13d
0x1400aef26  mov     [rsp+160h+WaitMode], 4
0x1400aef2b  call    WPP_RECORDER_AND_TRACE_SF_
0x1400aef30  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400aef38  lea     rcx, [rbp+60h+var_E0]
0x1400aef3c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400aef40  movdqu  xmmword ptr [rbp+60h+var_E0], xmm6
0x1400aef45  mov     [rbp+60h+var_D0], rbx
0x1400aef49  call    ??$_Resize@$$V$0A@@?$vector@U_KWAIT_BLOCK@@V?$allocator@U_KWAIT_BLOCK@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<_KWAIT_BLOCK,utl::allocator<_KWAIT_BLOCK>>::_Resize<,0>(unsigned __int64)
0x1400aef4e  test    al, al
0x1400aef50  jnz     short loc_1400AEFC1
0x1400aef52  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aef59  mov     eax, [rcx+2Ch]
0x1400aef5c  test    r13b, al
0x1400aef5f  jz      short loc_1400AEF6B
0x1400aef61  cmp     [rcx+29h], r13b
0x1400aef65  jb      short loc_1400AEF6B
0x1400aef67  mov     dl, 1
0x1400aef69  jmp     short loc_1400AEF6D
0x1400aef6b  xor     dl, dl
0x1400aef6d  mov     r9, [rdi+10B0h]
0x1400aef74  mov     r8b, 1
0x1400aef77  mov     rcx, [rcx+18h]
0x1400aef7b  mov     [rsp+160h+WaitBlockArray], rsi
0x1400aef80  mov     word ptr [rsp+160h+Timeout], 0Dh
0x1400aef87  mov     dword ptr [rsp+160h+Alertable], r13d
0x1400aef8c  mov     [rsp+160h+WaitMode], r13b
0x1400aef91  call    WPP_RECORDER_AND_TRACE_SF_
0x1400aef96  lea     rcx, [rdi+4C0h]; Event
0x1400aef9d  xor     r8d, r8d; Wait
0x1400aefa0  xor     edx, edx; Increment
0x1400aefa2  call    cs:__imp_KeSetEvent
0x1400aefa9  nop     dword ptr [rax+rax+00h]
0x1400aefae  lea     rcx, [rbp+60h+var_E0]
0x1400aefb2  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x1400aefb7  mov     eax, 0C000009Ah
0x1400aefbc  jmp     loc_1400AF8F5
0x1400aefc1  lea     rcx, [rsp+160h+Object+8]
0x1400aefc6  mov     [rsp+160h+var_E8], rbx
0x1400aefcb  movdqu  xmmword ptr [rsp+160h+Object+8], xmm6
0x1400aefd1  call    ??$_Resize@$$V$0A@@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_N_K@Z; utl::vector<void *,utl::allocator<void *>>::_Resize<,0>(unsigned __int64)
0x1400aefd6  test    al, al
0x1400aefd8  jnz     short loc_1400AF045
0x1400aefda  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aefe1  mov     eax, [rcx+2Ch]
0x1400aefe4  test    r13b, al
0x1400aefe7  jz      short loc_1400AEFF3
0x1400aefe9  cmp     [rcx+29h], r13b
0x1400aefed  jb      short loc_1400AEFF3
0x1400aefef  mov     dl, 1
0x1400aeff1  jmp     short loc_1400AEFF5
0x1400aeff3  xor     dl, dl
0x1400aeff5  mov     r9, [rdi+10B0h]
0x1400aeffc  mov     r8b, 1
0x1400aefff  mov     rcx, [rcx+18h]
0x1400af003  mov     [rsp+160h+WaitBlockArray], rsi
0x1400af008  mov     word ptr [rsp+160h+Timeout], 0Eh
0x1400af00f  mov     dword ptr [rsp+160h+Alertable], r13d
0x1400af014  mov     [rsp+160h+WaitMode], r13b
0x1400af019  call    WPP_RECORDER_AND_TRACE_SF_
0x1400af01e  lea     rcx, [rdi+4C0h]; Event
0x1400af025  xor     r8d, r8d; Wait
0x1400af028  xor     edx, edx; Increment
0x1400af02a  call    cs:__imp_KeSetEvent
0x1400af031  nop     dword ptr [rax+rax+00h]
0x1400af036  lea     rcx, [rsp+160h+Object+8]
0x1400af03b  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x1400af040  jmp     loc_1400AEFAE
0x1400af045  mov     r14, [rsp+160h+Object+8]
0x1400af04a  lea     r15, [rdi+4F0h]
0x1400af051  xor     edx, edx
0x1400af053  lea     rax, [rdx+rdx*2]
0x1400af057  lea     rcx, [r15+rax*8]
0x1400af05b  mov     [r14+rdx*8], rcx
0x1400af05f  inc     rdx
0x1400af062  cmp     rdx, 15h
0x1400af066  jb      short loc_1400AF053
0x1400af068  lea     rcx, [rdi+4C0h]; Event
0x1400af06f  mov     byte ptr [rdi+0D13h], 1
0x1400af076  xor     r8d, r8d; Wait
0x1400af079  xor     edx, edx; Increment
0x1400af07b  call    cs:__imp_KeSetEvent
0x1400af082  nop     dword ptr [rax+rax+00h]
0x1400af087  mov     rsi, [rsp+160h+var_F0]
0x1400af08c  mov     r12, [rbp+60h+var_E0]
0x1400af090  sub     rsi, r14
0x1400af093  sar     rsi, 3
0x1400af097  dec     esi
0x1400af099  mov     [rsp+160h+WaitBlockArray], r12; WaitBlockArray
0x1400af09e  xor     r9d, r9d; WaitReason
0x1400af0a1  mov     [rsp+160h+Timeout], 0; Timeout
0x1400af0aa  mov     rdx, r14; Object
0x1400af0ad  mov     [rsp+160h+Alertable], 0; Alertable
0x1400af0b2  mov     ecx, esi; Count
0x1400af0b4  mov     [rsp+160h+WaitMode], 0; WaitMode
0x1400af0b9  lea     r8d, [r9+1]; WaitType
0x1400af0bd  call    cs:__imp_KeWaitForMultipleObjects
0x1400af0c4  nop     dword ptr [rax+rax+00h]
0x1400af0c9  movsxd  rbx, eax
0x1400af0cc  cmp     ebx, 15h
0x1400af0cf  jge     loc_1400AF716
0x1400af0d5  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400af0dc  mov     ecx, [rax+2Ch]
0x1400af0df  test    r13b, cl
0x1400af0e2  jz      short loc_1400AF0EE
0x1400af0e4  cmp     byte ptr [rax+29h], 4
0x1400af0e8  jb      short loc_1400AF0EE
0x1400af0ea  mov     dl, 1
0x1400af0ec  jmp     short loc_1400AF0F0
0x1400af0ee  xor     dl, dl
0x1400af0f0  mov     r9, [rdi+10B0h]
0x1400af0f7  lea     r8, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1400af0fe  mov     rcx, [rax+18h]
0x1400af102  mov     [rsp+40h], ebx
0x1400af106  mov     [rsp+160h+WaitBlockArray], r8
0x1400af10b  mov     r8b, 1
0x1400af10e  mov     word ptr [rsp+160h+Timeout], 0Fh
0x1400af115  mov     dword ptr [rsp+160h+Alertable], r13d
0x1400af11a  mov     [rsp+160h+WaitMode], 4
0x1400af11f  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400af124  cmp     ebx, 0Bh
0x1400af127  jg      loc_1400AF478
0x1400af12d  jz      loc_1400AF458
0x1400af133  cmp     ebx, 5
0x1400af136  jg      loc_1400AF31D
0x1400af13c  jz      loc_1400AF2F9
0x1400af142  test    ebx, ebx
0x1400af144  jz      loc_1400AF8D1
0x1400af14a  sub     ebx, 1
0x1400af14d  jz      loc_1400AF269
0x1400af153  sub     ebx, 1
0x1400af156  jz      loc_1400AF1FE
0x1400af15c  sub     ebx, 1
0x1400af15f  jz      short loc_1400AF1DE
0x1400af161  cmp     ebx, 1
0x1400af164  jnz     loc_1400AF8BB
0x1400af16a  lea     rcx, [rdi+550h]; Event
0x1400af171  call    cs:__imp_KeClearEvent
0x1400af178  nop     dword ptr [rax+rax+00h]
0x1400af17d  xorps   xmm0, xmm0
0x1400af180  lea     rdx, [rdi+7B0h]
0x1400af187  xor     eax, eax
0x1400af189  lea     rcx, [rbp+60h+var_B8]
0x1400af18d  movups  xmmword ptr [rbp+60h+var_98], xmm0
0x1400af191  mov     [rbp+60h+var_68], rax
0x1400af195  movups  [rbp+60h+var_88], xmm0
0x1400af199  movups  [rbp+60h+var_78], xmm0
0x1400af19d  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x1400af1a2  lea     r9, [rbp+60h+var_98]; unsigned __int8
0x1400af1a6  mov     [rsp+160h+WaitMode], bl
0x1400af1aa  xor     r8d, r8d; struct _HCI_CONNECT_REQUEST *
0x1400af1ad  lea     rcx, [rsp+160h+var_110]; struct HCI_INTERFACE *
0x1400af1b2  mov     rdx, rdi; struct _HCI_CONNECT_REQUEST *
0x1400af1b5  call    ?HCI_GetNextConnectRequest@@YA?AUProcessConnectRequestInfo@@PEAUHCI_INTERFACE@@PEAU_HCI_CONNECT_REQUEST@@1E@Z; HCI_GetNextConnectRequest(HCI_INTERFACE *,_HCI_CONNECT_REQUEST *,_HCI_CONNECT_REQUEST *,uchar)
0x1400af1ba  lea     rcx, [rbp+60h+var_B8]
0x1400af1be  mov     bl, [rax]
0x1400af1c0  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x1400af1c5  test    bl, bl
0x1400af1c7  jz      loc_1400AF8BB
0x1400af1cd  lea     rdx, [rbp+60h+var_98]; struct _HCI_CONNECT_REQUEST *
0x1400af1d1  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af1d4  call    ?HCI_ProcessConnectRequest@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECT_REQUEST@@@Z; HCI_ProcessConnectRequest(HCI_INTERFACE *,_HCI_CONNECT_REQUEST *)
0x1400af1d9  jmp     loc_1400AF8BB
0x1400af1de  lea     rcx, [rdi+538h]; Event
0x1400af1e5  call    cs:__imp_KeClearEvent
0x1400af1ec  nop     dword ptr [rax+rax+00h]
0x1400af1f1  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af1f4  call    ?HCI_HandleSSPRemoteNameRequest@@YAJPEAUHCI_INTERFACE@@@Z; HCI_HandleSSPRemoteNameRequest(HCI_INTERFACE *)
0x1400af1f9  jmp     loc_1400AF8BB
0x1400af1fe  lea     rcx, [rdi+520h]; Event
0x1400af205  call    cs:__imp_KeClearEvent
0x1400af20c  nop     dword ptr [rax+rax+00h]
0x1400af211  mov     rcx, [rdi+4A8h]
0x1400af218  lea     rax, [rsp+160h+var_108]
0x1400af21d  mov     [rsp+160h+Object], rax
0x1400af222  lea     rdx, [rsp+160h+var_108]
0x1400af227  lea     rax, [rsp+160h+var_108]
0x1400af22c  add     rcx, 130h
0x1400af233  mov     [rsp+160h+var_108], rax
0x1400af238  call    IrpList_Drain
0x1400af23d  jmp     short loc_1400AF252
0x1400af23f  mov     rax, [r8+78h]
0x1400af243  mov     rdx, r8
0x1400af246  mov     rcx, [rdi+4A8h]
0x1400af24d  call    _guard_dispatch_icall
0x1400af252  lea     rcx, [rsp+160h+Object+8]
0x1400af257  call    ?try_pop_front@?$list_impl@U?$intrusive_offset_hook_traits@U_IRP@@$0KI@@Foundation@Bluetooth@Microsoft@@V?$intrusive_list_t@U?$intrusive_offset_hook_traits@U_IRP@@$0KI@@Foundation@Bluetooth@Microsoft@@@234@@Details@Foundation@Bluetooth@Microsoft@@QEAAPEAU_IRP@@XZ; Microsoft::Bluetooth::Foundation::Details::list_impl<Microsoft::Bluetooth::Foundation::intrusive_offset_hook_traits<_IRP,168>,Microsoft::Bluetooth::Foundation::intrusive_list_t<Microsoft::Bluetooth::Foundation::intrusive_offset_hook_traits<_IRP,168>>>::try_pop_front(void)
0x1400af25c  mov     r8, rax
0x1400af25f  test    rax, rax
0x1400af262  jnz     short loc_1400AF23F
0x1400af264  jmp     loc_1400AF8BB
0x1400af269  lea     rdx, [rdi+7B0h]
0x1400af270  lea     rcx, [rbp+60h+var_A8]
0x1400af274  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x1400af279  lea     rcx, [rdi+9A0h]
0x1400af280  mov     rax, [rcx]
0x1400af283  cmp     [rax+8], rcx
0x1400af287  jnz     loc_1400AF8CA
0x1400af28d  mov     rdx, [rax]
0x1400af290  cmp     [rdx+8], rax
0x1400af294  jnz     loc_1400AF8CA
0x1400af29a  mov     [rcx], rdx
0x1400af29d  mov     [rdx+8], rcx
0x1400af2a1  cmp     rax, rcx
0x1400af2a4  jnz     short loc_1400AF2AA
0x1400af2a6  xor     ebx, ebx
0x1400af2a8  jmp     short loc_1400AF2B5
0x1400af2aa  mov     [rax+8], rax
0x1400af2ae  lea     rbx, [rax-58h]
0x1400af2b2  mov     [rax], rax
0x1400af2b5  cmp     [rcx], rcx
0x1400af2b8  jnz     short loc_1400AF2D7
0x1400af2ba  lea     rcx, [rdi+508h]; Event
0x1400af2c1  call    cs:__imp_KeClearEvent
0x1400af2c8  nop     dword ptr [rax+rax+00h]
0x1400af2cd  mov     dl, 1; unsigned __int8
0x1400af2cf  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af2d2  call    ?HCI_StartIdleTimer@@YAXPEAUHCI_INTERFACE@@E@Z; HCI_StartIdleTimer(HCI_INTERFACE *,uchar)
0x1400af2d7  lea     rcx, [rbp+60h+var_A8]
0x1400af2db  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x1400af2e0  test    rbx, rbx
0x1400af2e3  jz      loc_1400AF8BB
0x1400af2e9  mov     rdx, rbx; struct _BIP *
0x1400af2ec  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af2ef  call    ?HCI_ProcessBip@@YAXPEAUHCI_INTERFACE@@PEAU_BIP@@@Z; HCI_ProcessBip(HCI_INTERFACE *,_BIP *)
0x1400af2f4  jmp     loc_1400AF8BB
0x1400af2f9  lea     rcx, [rdi+568h]; Event
0x1400af300  call    cs:__imp_KeClearEvent
0x1400af307  nop     dword ptr [rax+rax+00h]
0x1400af30c  mov     rcx, [rdi+4A8h]; struct DEVICE_EXTENSION *
0x1400af313  call    ?SMPInt_ProcessSMPEvent@@YAXPEAUDEVICE_EXTENSION@@@Z; SMPInt_ProcessSMPEvent(DEVICE_EXTENSION *)
0x1400af318  jmp     loc_1400AF8BB
0x1400af31d  mov     ecx, ebx
0x1400af31f  sub     ecx, 6
0x1400af322  jz      loc_1400AF3C4
0x1400af328  sub     ecx, 1
0x1400af32b  jz      short loc_1400AF3A4
0x1400af32d  sub     ecx, 1
0x1400af330  jz      short loc_1400AF380
0x1400af332  sub     ecx, 1
0x1400af335  jz      short loc_1400AF360
0x1400af337  cmp     ecx, 1
0x1400af33a  jnz     loc_1400AF8BB
0x1400af340  lea     rcx, [rdi+5E0h]; Event
0x1400af347  call    cs:__imp_KeClearEvent
0x1400af34e  nop     dword ptr [rax+rax+00h]
0x1400af353  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af356  call    ?HciLE_GenerateNewRandomAddresses@@YAJPEAUHCI_INTERFACE@@@Z; HciLE_GenerateNewRandomAddresses(HCI_INTERFACE *)
0x1400af35b  jmp     loc_1400AF8BB
0x1400af360  lea     rcx, [rdi+5C8h]; Event
0x1400af367  call    cs:__imp_KeClearEvent
0x1400af36e  nop     dword ptr [rax+rax+00h]
0x1400af373  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af376  call    ?HciLEAdv_ProcessTimeSlicingTimer@@YAXPEAUHCI_INTERFACE@@@Z; HciLEAdv_ProcessTimeSlicingTimer(HCI_INTERFACE *)
0x1400af37b  jmp     loc_1400AF8BB
0x1400af380  lea     rcx, [rdi+5B0h]; Event
0x1400af387  call    cs:__imp_KeClearEvent
0x1400af38e  nop     dword ptr [rax+rax+00h]
0x1400af393  lea     rcx, [rdi+11C8h]; this
0x1400af39a  call    ?OnProcessAdvertisingRequestsEvent@HciLEAdvertisingRequestCoordinator@@UEAAXXZ; HciLEAdvertisingRequestCoordinator::OnProcessAdvertisingRequestsEvent(void)
0x1400af39f  jmp     loc_1400AF8BB
0x1400af3a4  lea     rcx, [rdi+598h]; Event
0x1400af3ab  call    cs:__imp_KeClearEvent
0x1400af3b2  nop     dword ptr [rax+rax+00h]
0x1400af3b7  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400af3ba  call    ?HCI_ProcessSniffModeManagerEvent@@YAXPEAUHCI_INTERFACE@@@Z; HCI_ProcessSniffModeManagerEvent(HCI_INTERFACE *)
0x1400af3bf  jmp     loc_1400AF8BB
0x1400af3c4  lea     rcx, [rbx+4Fh]
  ... truncated ...
```
