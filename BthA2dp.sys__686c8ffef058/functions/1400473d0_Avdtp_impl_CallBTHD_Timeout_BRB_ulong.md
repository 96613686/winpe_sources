# Avdtp_impl::CallBTHD_Timeout(_BRB *,ulong)

- ea: `0x1400473d0`
- end: `0x140047e4a`
- name: `?CallBTHD_Timeout@Avdtp_impl@@AEAAJPEAU_BRB@@K@Z`
- size: `2682`
- prototype: `__int64 __fastcall(Avdtp_impl *__hidden this, struct _BRB *, unsigned int)`
- caller_count: `4`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400494f0`
- `0x14004dc70`
- `0x14004f694`
- `0x14005120c`

## callees

- `0x140003530`
- `0x140005030`
- `0x140006a88`
- `0x14000f570`
- `0x14000f600`
- `0x14000f7e0`
- `0x14000f950`
- `0x14002d890`
- `0x14002d8e8`
- `0x140036494`
- `0x140037ee4`
- `0x14003b244`
- `0x1400426b0`
- `0x140046b04`
- `0x1400473d0`
- `0x140049a40`
- `0x14004a244`
- `0x14004ccf4`
- `0x14004f964`
- `0x1400528bc`
- `0x140053688`
- `0x140053814`
- `0x14005393c`
- `0x140053b24`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004778e`
- `ntoskrnl!ExAllocatePool2` at `0x14004778e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004785f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004785f`
- `ntoskrnl!IofCallDriver` at `0x140047965`
- `ntoskrnl!IofCallDriver` at `0x140047965`
- `ntoskrnl!IoAllocateIrp` at `0x14004773c`
- `ntoskrnl!IoAllocateIrp` at `0x14004773c`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14004792c`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14004792c`
- `ntoskrnl!IoCancelIrp` at `0x140047ab2`
- `ntoskrnl!IoCancelIrp` at `0x140047ab2`
- `ntoskrnl!IoFreeIrp` at `0x14004784b`
- `ntoskrnl!IoFreeIrp` at `0x140047df6`
- `ntoskrnl!IoFreeIrp` at `0x14004784b`
- `ntoskrnl!IoFreeIrp` at `0x140047df6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400478ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400478f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400478ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400478f8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004789d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004789d`
- `ntoskrnl!KeInitializeEvent` at `0x140047774`
- `ntoskrnl!KeInitializeEvent` at `0x140047774`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400479bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047bb5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047bdb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400479bb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047bb5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047bdb`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::CallBTHD_Timeout(
        volatile signed __int32 ***this,
        struct _BRB *a2,
        __int64 a3,
        __int64 a4)
{
  struct _BRB *v4; // rsi
  Avdtp_impl *v5; // r13
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  PDEVICE_OBJECT v13; // rcx
  PDEVICE_OBJECT v14; // rsi
  char v15; // di
  int IfrRecorderLog; // eax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // eax
  int v20; // eax
  PDEVICE_OBJECT v21; // rsi
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  unsigned int Status; // esi
  __int64 v26; // rdx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 Pool2; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  volatile signed __int32 *v35; // r13
  int IsEnabledDeviceUsageNoInline; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  KSPIN_LOCK *v38; // rsi
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  Avdtp_impl *v42; // rsi
  IRP *v43; // rbx
  volatile signed __int32 **v44; // rcx
  KIRQL v45; // dl
  volatile signed __int32 **v46; // rcx
  struct _IO_STACK_LOCATION *v47; // rax
  __int64 v48; // rdx
  PDEVICE_OBJECT v49; // rcx
  __int64 v50; // r8
  __int64 v51; // r9
  union _LARGE_INTEGER v52; // rcx
  int v53; // edx
  int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  int v59; // edx
  int v60; // r8d
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // r10
  int v66; // edx
  unsigned int v67; // eax
  BOOLEAN InvokeOnSuccess[4]; // [rsp+28h] [rbp-79h]
  int InvokeOnError; // [rsp+30h] [rbp-71h]
  __int64 *v71; // [rsp+40h] [rbp-61h]
  PIRP Irp; // [rsp+88h] [rbp-19h]
  __int64 v73; // [rsp+90h] [rbp-11h] BYREF
  __int64 v74; // [rsp+98h] [rbp-9h]
  char v75; // [rsp+A0h] [rbp-1h]
  struct _KEVENT Event; // [rsp+A8h] [rbp+7h] BYREF
  unsigned int v79; // [rsp+118h] [rbp+77h]
  union _LARGE_INTEGER Timeout; // [rsp+120h] [rbp+7Fh] BYREF

  v79 = a3;
  v4 = a2;
  v5 = (Avdtp_impl *)this;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    LOBYTE(Timeout.LowPart) = IsCriticalBrb(v4);
    GetBtAddressAndChannelHandle(&v73, v4);
    if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12) )
    {
      if ( v75 )
      {
        v14 = WPP_GLOBAL_Control;
        v15 = 1;
        LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          IfrRecorderLog = GetIfrRecorderLog(2, v6, v7);
          WPP_RECORDER_AND_TRACE_SF_Lbth_addrqlq(v14->AttachedDevice, v17, v18, IfrRecorderLog);
        }
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        v15 = 1;
        LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = GetIfrRecorderLog(2, v6, v7);
          v71 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
          WPP_RECORDER_AND_TRACE_SF_Llq(v21->AttachedDevice, v23, v24, v22);
        }
      }
      v4 = a2;
    }
    else if ( v75 )
    {
      v13 = WPP_GLOBAL_Control;
      v15 = 1;
      LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_Lbth_addrqqq(
          WPP_GLOBAL_Control->AttachedDevice,
          v6,
          v7,
          WPP_GLOBAL_Control->DeviceExtension);
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      v15 = 1;
      LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v71 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        WPP_RECORDER_AND_TRACE_SF_Lqq(WPP_GLOBAL_Control->AttachedDevice, v6, v7, WPP_GLOBAL_Control->DeviceExtension);
      }
    }
  }
  else
  {
    LOBYTE(Timeout.LowPart) = 0;
    v13 = WPP_GLOBAL_Control;
    v15 = 1;
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_LD(WPP_GLOBAL_Control->AttachedDevice, v6, v7, WPP_GLOBAL_Control->DeviceExtension);
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v13, v6, v7, v8) )
  {
    v19 = Avdtp_impl::GetRemoveLockClient(v4->BrbHeader.Type);
    v20 = Avdtp_impl::AcquireRemoveLock(v5, v19);
  }
  else
  {
    v20 = Avdtp_impl::AcquireRemoveLock(v5);
  }
  Status = v20;
  if ( v20 >= 0 )
  {
    Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)v5 + 137) + 76LL), 0);
    if ( !Irp )
    {
      Status = -1073741670;
      goto LABEL_146;
    }
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    Pool2 = ExAllocatePool2(64, 48, 1096172628);
    v35 = (volatile signed __int32 *)Pool2;
    if ( !Pool2 )
    {
      IoFreeIrp(Irp);
      Status = -1073741670;
LABEL_145:
      v5 = (Avdtp_impl *)this;
LABEL_146:
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v27, v26, v28, v29) )
      {
        v67 = Avdtp_impl::GetRemoveLockClient(a2->BrbHeader.Type);
        Avdtp_impl::ReleaseRemoveLock(v5, v67);
      }
      else
      {
        Avdtp_impl::ReleaseRemoveLock(v5);
      }
      return Status;
    }
    *(_QWORD *)(Pool2 + 32) = this;
    *(_QWORD *)(Pool2 + 40) = &Event;
    *(_QWORD *)(Pool2 + 16) = Irp;
    *(_DWORD *)(Pool2 + 24) = 1;
    IsEnabledDeviceUsageNoInline = Feature_55795972__private_IsEnabledDeviceUsageNoInline(v32, v31, v33, v34);
    *((_BYTE *)v35 + 28) = IsEnabledDeviceUsageNoInline != 0 ? LOBYTE(Timeout.LowPart) : 0;
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].MajorFunction = 15;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
    CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)a2;
    v38 = (KSPIN_LOCK *)(this + 222);
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(a2, v39, v40, v41) )
    {
      wil::acquire_kspin_lock(&v73, v38);
      v42 = (Avdtp_impl *)this;
      if ( *((_DWORD *)this + 446) && !*((_BYTE *)v35 + 28) )
      {
        Status = -1073741661;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&v73);
LABEL_57:
        v43 = Irp;
        goto LABEL_58;
      }
      v44 = this[221];
      if ( *v44 == (volatile signed __int32 *)(this + 220) )
      {
        *((_QWORD *)v35 + 1) = v44;
        *(_QWORD *)v35 = this + 220;
        *v44 = v35;
        this[221] = (volatile signed __int32 **)v35;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(&v73);
        goto LABEL_67;
      }
    }
    else
    {
      v45 = KeAcquireSpinLockRaiseToDpc(v38);
      if ( *((_DWORD *)this + 446) == 1 )
      {
        KeReleaseSpinLock(v38, v45);
        Status = -1073741661;
        goto LABEL_57;
      }
      v46 = this[221];
      if ( *v46 == (volatile signed __int32 *)(this + 220) )
      {
        *((_QWORD *)v35 + 1) = v46;
        *(_QWORD *)v35 = this + 220;
        *v46 = v35;
        this[221] = (volatile signed __int32 **)v35;
        KeReleaseSpinLock(v38, v45);
        v42 = (Avdtp_impl *)this;
LABEL_67:
        if ( IoSetCompletionRoutineEx(
               *((PDEVICE_OBJECT *)v42 + 136),
               Irp,
               Avdtp_impl::CallBTHD_Completion,
               (PVOID)v35,
               1u,
               1u,
               1u) < 0 )
        {
          v47 = Irp->Tail.Overlay.CurrentStackLocation;
          v47[-1].CompletionRoutine = Avdtp_impl::CallBTHD_Completion;
          v47[-1].Context = (PVOID)v35;
          v47[-1].Control = -32;
        }
        Status = IofCallDriver(*((PDEVICE_OBJECT *)v42 + 137), Irp);
        if ( Status == 259 )
        {
          Timeout.QuadPart = 0;
          if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline() )
            v52.QuadPart = -10000000LL * v79;
          else
            v52.QuadPart = -10000000 * v79;
          Timeout = v52;
          Status = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
          if ( Status == 258 )
          {
            if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v49, v48, v50, v51) )
            {
              LOBYTE(v53) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
              if ( (_BYTE)v53 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v54) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_Dq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v53,
                  v54,
                  WPP_GLOBAL_Control->DeviceExtension,
                  4,
                  4,
                  34,
                  (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
                  a2->BrbHeader.Type);
              }
            }
            else
            {
              LOBYTE(v53) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
              if ( (_BYTE)v53 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v54) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v53,
                  v54,
                  WPP_GLOBAL_Control->DeviceExtension,
                  4,
                  4,
                  35,
                  (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
              }
            }
            if ( IoCancelIrp(Irp) )
            {
              if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v56, v55, v57, v58) )
              {
                LOBYTE(v59) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                if ( (_BYTE)v59 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v60) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_Dq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v59,
                    v60,
                    WPP_GLOBAL_Control->DeviceExtension,
                    4,
                    4,
                    36,
                    (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
                    a2->BrbHeader.Type);
                }
              }
              else
              {
                LOBYTE(v59) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                if ( (_BYTE)v59 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v60) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v59,
                    v60,
                    WPP_GLOBAL_Control->DeviceExtension,
                    4,
                    4,
                    37,
                    (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
                }
              }
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
            }
            else
            {
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              Status = Irp->IoStatus.Status;
              if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v62, v61, v63, v64) )
              {
                v49 = WPP_GLOBAL_Control;
                LOBYTE(v48) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                LOBYTE(v50) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                if ( (_BYTE)v48 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_AND_TRACE_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v48,
                    v50,
                    WPP_GLOBAL_Control->DeviceExtension,
                    4,
                    4,
                    38,
                    (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
                    (char)this);
              }
              else
              {
                v49 = WPP_GLOBAL_Control;
                LOBYTE(v48) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                LOBYTE(v50) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                if ( (_BYTE)v48 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_AND_TRACE_SF_(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v48,
                    v50,
                    WPP_GLOBAL_Control->DeviceExtension,
                    4,
                    4,
                    39,
                    (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
              }
            }
          }
          else
          {
            Status = Irp->IoStatus.Status;
          }
        }
        if ( !(unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v49, v48, v50, v51) )
          goto LABEL_57;
        GetBtAddressAndChannelHandle(&v73, a2);
        if ( v75 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v15 = 0;
          }
          LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_57;
          LOBYTE(v26) = v15;
          v43 = Irp;
          WPP_RECORDER_AND_TRACE_SF_Lbth_addrqddqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v26,
            v28,
            WPP_GLOBAL_Control->DeviceExtension,
            *(_DWORD *)InvokeOnSuccess,
            InvokeOnError,
            40,
            (_DWORD)v71,
            *(_WORD *)(v65 + 22),
            v73,
            v74,
            Irp->IoStatus.Status,
            *(_DWORD *)(v65 + 28),
            v65,
            (char)this);
        }
        else
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v15 = 0;
          }
          LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( !v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_57;
          v66 = *(unsigned __int16 *)(v65 + 22);
          v43 = Irp;
          LOBYTE(v66) = v15;
          WPP_RECORDER_AND_TRACE_SF_Lddqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v66,
            v28,
            WPP_GLOBAL_Control->DeviceExtension,
            *(_DWORD *)InvokeOnSuccess,
            InvokeOnError,
            41,
            (_DWORD)v71,
            *(_WORD *)(v65 + 22),
            Irp->IoStatus.Status,
            *(_DWORD *)(v65 + 28),
            v65,
            (char)this);
        }
LABEL_58:
        if ( _InterlockedExchangeAdd(v35 + 6, 0xFFFFFFFF) == 1 )
        {
          IoFreeIrp(v43);
          ExFreePoolWithTag((PVOID)v35, 0x41564454u);
        }
        goto LABEL_145;
      }
    }
    __fastfail(3u);
  }
  return Status;
}

```

## disassembly

```asm
0x1400473d0  mov     rax, rsp
0x1400473d3  mov     [rax+18h], r8d
0x1400473d7  mov     [rax+10h], rdx
0x1400473db  mov     [rax+8], rcx
0x1400473df  push    rbp
0x1400473e0  push    rbx
0x1400473e1  push    rsi
0x1400473e2  push    rdi
0x1400473e3  push    r12
0x1400473e5  push    r13
0x1400473e7  push    r15
0x1400473e9  lea     rbp, [rax-5Fh]
0x1400473ed  sub     rsp, 0C0h
0x1400473f4  mov     rsi, rdx
0x1400473f7  mov     r13, rcx
0x1400473fa  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400473ff  test    eax, eax
0x140047401  jz      loc_1400476AA
0x140047407  mov     rcx, rsi; struct _BRB *
0x14004740a  call    ?IsCriticalBrb@@YA_NPEBU_BRB@@@Z; IsCriticalBrb(_BRB const *)
0x14004740f  lea     rcx, [rbp+57h+var_68]
0x140047413  mov     byte ptr [rbp+57h+Timeout], al
0x140047416  mov     rdx, rsi
0x140047419  call    ?GetBtAddressAndChannelHandle@@YA?AV?$optional@U?$pair@_KPEAX@utl@@@utl@@PEAU_BRB@@@Z; GetBtAddressAndChannelHandle(_BRB *)
0x14004741e  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140047423  test    eax, eax
0x140047425  jz      loc_14004758C
0x14004742b  cmp     [rbp+57h+var_58], 0
0x14004742f  jz      loc_1400474F0
0x140047435  mov     rsi, cs:WPP_GLOBAL_Control
0x14004743c  lea     r15, WPP_GLOBAL_Control
0x140047443  mov     edi, 1
0x140047448  lea     ebx, [rdi+3]
0x14004744b  cmp     rsi, r15
0x14004744e  jz      short loc_140047461
0x140047450  mov     eax, [rsi+2Ch]
0x140047453  test    al, 8
0x140047455  jz      short loc_140047461
0x140047457  cmp     [rsi+29h], bl
0x14004745a  jb      short loc_140047461
0x14004745c  mov     dl, dil
0x14004745f  jmp     short loc_140047463
0x140047461  xor     dl, dl
0x140047463  lea     r12, WPP_RECORDER_INITIALIZED
0x14004746a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140047471  setnz   r8b
0x140047475  test    dl, dl
0x140047477  jnz     short loc_14004747E
0x140047479  test    r8b, r8b
0x14004747c  jz      short loc_1400474C7
0x14004747e  mov     rcx, [rbp+57h+arg_8]
0x140047482  movzx   r10d, byte ptr [rbp+57h+Timeout]
0x140047487  movzx   r11d, word ptr [rcx+16h]
0x14004748c  mov     ecx, 2
0x140047491  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140047496  mov     rcx, [rsi+18h]
0x14004749a  mov     r9, rax
0x14004749d  mov     rax, [rbp+57h+arg_8]
0x1400474a1  mov     [rsp+0F0h+var_90], rax
0x1400474a6  mov     rax, [rbp+57h+var_60]
0x1400474aa  mov     dword ptr [rsp+0F0h+var_98], r10d
0x1400474af  mov     [rsp+0F0h+var_A0], rax
0x1400474b4  mov     rax, [rbp+57h+var_68]
0x1400474b8  mov     [rsp+0F0h+var_A8], rax
0x1400474bd  mov     dword ptr [rsp+0F0h+var_B0], r11d
0x1400474c2  call    WPP_RECORDER_AND_TRACE_SF_Lbth_addrqlq
0x1400474c7  mov     rsi, [rbp+57h+arg_8]
0x1400474cb  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400474d0  test    eax, eax
0x1400474d2  jz      loc_14004771E
0x1400474d8  movzx   ecx, word ptr [rsi+16h]
0x1400474dc  call    ?GetRemoveLockClient@Avdtp_impl@@CA?AW4RemoveLockClient@1@G@Z; Avdtp_impl::GetRemoveLockClient(ushort)
0x1400474e1  mov     edx, eax
0x1400474e3  mov     rcx, r13
0x1400474e6  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJW4RemoveLockClient@1@@Z; Avdtp_impl::AcquireRemoveLock(Avdtp_impl::RemoveLockClient)
0x1400474eb  jmp     loc_140047726
0x1400474f0  mov     rsi, cs:WPP_GLOBAL_Control
0x1400474f7  lea     r15, WPP_GLOBAL_Control
0x1400474fe  mov     edi, 1
0x140047503  lea     ebx, [rdi+3]
0x140047506  cmp     rsi, r15
0x140047509  jz      short loc_14004751C
0x14004750b  mov     eax, [rsi+2Ch]
0x14004750e  test    al, 8
0x140047510  jz      short loc_14004751C
0x140047512  cmp     [rsi+29h], bl
0x140047515  jb      short loc_14004751C
0x140047517  mov     dl, dil
0x14004751a  jmp     short loc_14004751E
0x14004751c  xor     dl, dl
0x14004751e  lea     r12, WPP_RECORDER_INITIALIZED
0x140047525  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14004752c  setnz   r8b
0x140047530  test    dl, dl
0x140047532  jnz     short loc_140047539
0x140047534  test    r8b, r8b
0x140047537  jz      short loc_1400474C7
0x140047539  mov     rax, [rbp+57h+arg_8]
0x14004753d  mov     ecx, 2
0x140047542  movzx   r10d, byte ptr [rbp+57h+Timeout]
0x140047547  movzx   r11d, word ptr [rax+16h]
0x14004754c  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140047551  mov     rcx, [rsi+18h]
0x140047555  mov     r9, rax
0x140047558  mov     rax, [rbp+57h+arg_8]
0x14004755c  mov     [rsp+0F0h+var_A0], rax
0x140047561  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140047568  mov     dword ptr [rsp+0F0h+var_A8], r10d
0x14004756d  mov     dword ptr [rsp+0F0h+var_B0], r11d
0x140047572  mov     [rsp+0F0h+var_B8], rax
0x140047577  mov     word ptr [rsp+0F0h+InvokeOnCancel], 1Eh
0x14004757e  mov     dword ptr [rsp+0F0h+InvokeOnError], ebx
0x140047582  call    WPP_RECORDER_AND_TRACE_SF_Llq
0x140047587  jmp     loc_1400474C7
0x14004758c  cmp     [rbp+57h+var_58], 0
0x140047590  jz      loc_140047622
0x140047596  mov     rcx, cs:WPP_GLOBAL_Control
0x14004759d  lea     r15, WPP_GLOBAL_Control
0x1400475a4  mov     edi, 1
0x1400475a9  lea     ebx, [rdi+3]
0x1400475ac  cmp     rcx, r15
0x1400475af  jz      short loc_1400475C2
0x1400475b1  mov     eax, [rcx+2Ch]
0x1400475b4  test    al, 8
0x1400475b6  jz      short loc_1400475C2
0x1400475b8  cmp     [rcx+29h], bl
0x1400475bb  jb      short loc_1400475C2
0x1400475bd  mov     dl, dil
0x1400475c0  jmp     short loc_1400475C4
0x1400475c2  xor     dl, dl
0x1400475c4  lea     r12, WPP_RECORDER_INITIALIZED
0x1400475cb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400475d2  setnz   r8b
0x1400475d6  test    dl, dl
0x1400475d8  jnz     short loc_1400475E3
0x1400475da  test    r8b, r8b
0x1400475dd  jz      loc_1400474CB
0x1400475e3  movzx   r9d, word ptr [rsi+16h]
0x1400475e8  mov     rax, [rbp+57h+var_60]
0x1400475ec  mov     [rsp+0F0h+var_90], r13
0x1400475f1  mov     [rsp+0F0h+var_98], rsi
0x1400475f6  mov     [rsp+0F0h+var_A0], rax
0x1400475fb  mov     rax, [rbp+57h+var_68]
0x1400475ff  mov     [rsp+0F0h+var_A8], rax
0x140047604  mov     dword ptr [rsp+0F0h+var_B0], r9d
0x140047609  mov     r9, [rcx+40h]
0x14004760d  mov     rcx, [rcx+18h]
0x140047611  mov     word ptr [rsp+0F0h+InvokeOnCancel], 1Fh
0x140047618  call    WPP_RECORDER_AND_TRACE_SF_Lbth_addrqqq
0x14004761d  jmp     loc_1400474CB
0x140047622  mov     rcx, cs:WPP_GLOBAL_Control
0x140047629  lea     r15, WPP_GLOBAL_Control
0x140047630  mov     edi, 1
0x140047635  lea     ebx, [rdi+3]
0x140047638  cmp     rcx, r15
0x14004763b  jz      short loc_14004764E
0x14004763d  mov     eax, [rcx+2Ch]
0x140047640  test    al, 8
0x140047642  jz      short loc_14004764E
0x140047644  cmp     [rcx+29h], bl
0x140047647  jb      short loc_14004764E
0x140047649  mov     dl, dil
0x14004764c  jmp     short loc_140047650
0x14004764e  xor     dl, dl
0x140047650  lea     r12, WPP_RECORDER_INITIALIZED
0x140047657  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14004765e  setnz   r8b
0x140047662  test    dl, dl
0x140047664  jnz     short loc_14004766F
0x140047666  test    r8b, r8b
0x140047669  jz      loc_1400474CB
0x14004766f  movzx   eax, word ptr [rsi+16h]
0x140047673  mov     r9, [rcx+40h]
0x140047677  mov     rcx, [rcx+18h]
0x14004767b  mov     [rsp+0F0h+var_A0], r13
0x140047680  mov     [rsp+0F0h+var_A8], rsi
0x140047685  mov     dword ptr [rsp+0F0h+var_B0], eax
0x140047689  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140047690  mov     [rsp+0F0h+var_B8], rax
0x140047695  mov     word ptr [rsp+0F0h+InvokeOnCancel], 20h ; ' '
0x14004769c  mov     dword ptr [rsp+0F0h+InvokeOnError], ebx
0x1400476a0  call    WPP_RECORDER_AND_TRACE_SF_Lqq
0x1400476a5  jmp     loc_1400474CB
0x1400476aa  mov     byte ptr [rbp+57h+Timeout], 0
0x1400476ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400476b5  lea     r15, WPP_GLOBAL_Control
0x1400476bc  mov     edi, 1
0x1400476c1  lea     ebx, [rdi+3]
0x1400476c4  cmp     rcx, r15
0x1400476c7  jz      short loc_1400476DA
0x1400476c9  mov     eax, [rcx+2Ch]
0x1400476cc  test    al, 8
0x1400476ce  jz      short loc_1400476DA
0x1400476d0  cmp     [rcx+29h], bl
0x1400476d3  jb      short loc_1400476DA
0x1400476d5  mov     dl, dil
0x1400476d8  jmp     short loc_1400476DC
0x1400476da  xor     dl, dl
0x1400476dc  lea     r12, WPP_RECORDER_INITIALIZED
0x1400476e3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400476ea  setnz   r8b
0x1400476ee  test    dl, dl
0x1400476f0  jnz     short loc_1400476FB
0x1400476f2  test    r8b, r8b
0x1400476f5  jz      loc_1400474CB
0x1400476fb  mov     r9d, [rbp+57h+arg_10]
0x1400476ff  movzx   eax, word ptr [rsi+16h]
0x140047703  mov     dword ptr [rsp+0F0h+var_A8], r9d
0x140047708  mov     r9, [rcx+40h]
0x14004770c  mov     rcx, [rcx+18h]
0x140047710  mov     dword ptr [rsp+0F0h+var_B0], eax
0x140047714  call    WPP_RECORDER_AND_TRACE_SF_LD
0x140047719  jmp     loc_1400474CB
0x14004771e  mov     rcx, r13; this
0x140047721  call    ?AcquireRemoveLock@Avdtp_impl@@QEAAJXZ; Avdtp_impl::AcquireRemoveLock(void)
0x140047726  mov     esi, eax
0x140047728  test    eax, eax
0x14004772a  js      loc_140047E35
0x140047730  mov     rcx, [r13+448h]
0x140047737  xor     edx, edx; ChargeQuota
0x140047739  mov     cl, [rcx+4Ch]; StackSize
0x14004773c  call    cs:__imp_IoAllocateIrp
0x140047743  nop     dword ptr [rax+rax+00h]
0x140047748  mov     [rbp+57h+Irp], rax
0x14004774c  mov     rsi, rax
0x14004774f  test    rax, rax
0x140047752  jnz     short loc_14004775E
0x140047754  mov     esi, 0C000009Ah
0x140047759  jmp     loc_140047E0B
0x14004775e  xorps   xmm0, xmm0
0x140047761  lea     rcx, [rbp+57h+Event]; Event
0x140047765  xor     eax, eax
0x140047767  xor     r8d, r8d; State
0x14004776a  xor     edx, edx; Type
0x14004776c  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140047770  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140047774  call    cs:__imp_KeInitializeEvent
0x14004777b  nop     dword ptr [rax+rax+00h]
0x140047780  mov     edx, 30h ; '0'
0x140047785  mov     r8d, 41564454h
0x14004778b  lea     ecx, [rdx+10h]
0x14004778e  call    cs:__imp_ExAllocatePool2
0x140047795  nop     dword ptr [rax+rax+00h]
0x14004779a  mov     r13, rax
0x14004779d  test    rax, rax
0x1400477a0  jz      loc_140047DF3
0x1400477a6  mov     rsi, [rbp+57h+arg_0]
0x1400477aa  mov     [rax+20h], rsi
0x1400477ae  lea     rax, [rbp+57h+Event]
0x1400477b2  mov     [r13+28h], rax
0x1400477b6  mov     rax, [rbp+57h+Irp]
0x1400477ba  mov     [r13+10h], rax
0x1400477be  mov     [r13+18h], edi
0x1400477c2  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400477c7  neg     eax
0x1400477c9  mov     rax, [rbp+57h+Irp]
0x1400477cd  sbb     cl, cl
0x1400477cf  and     cl, byte ptr [rbp+57h+Timeout]
0x1400477d2  mov     [r13+1Ch], cl
0x1400477d6  mov     rax, [rax+0B8h]
0x1400477dd  mov     rcx, [rbp+57h+arg_8]
0x1400477e1  mov     byte ptr [rax-48h], 0Fh
0x1400477e5  mov     dword ptr [rax-30h], 410003h
0x1400477ec  mov     [rax-40h], rcx
0x1400477f0  add     rsi, 6F0h
0x1400477f7  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400477fc  test    eax, eax
0x1400477fe  jz      loc_14004789A
0x140047804  mov     rdx, rsi
0x140047807  lea     rcx, [rbp+57h+var_68]
0x14004780b  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x140047810  mov     rsi, [rbp+57h+arg_0]
0x140047814  cmp     dword ptr [rsi+6F8h], 0
0x14004781b  jz      short loc_140047870
0x14004781d  cmp     byte ptr [r13+1Ch], 0
0x140047822  jnz     short loc_140047870
0x140047824  lea     rcx, [rbp+57h+var_68]
0x140047828  mov     esi, 0C00000A3h
0x14004782d  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x140047832  mov     rbx, [rbp+57h+Irp]
0x140047836  or      eax, 0FFFFFFFFh
0x140047839  lock xadd [r13+18h], eax
0x14004783f  cmp     eax, 1
0x140047842  jnz     loc_140047E07
0x140047848  mov     rcx, rbx; Irp
0x14004784b  call    cs:__imp_IoFreeIrp
0x140047852  nop     dword ptr [rax+rax+00h]
0x140047857  mov     edx, 41564454h; Tag
0x14004785c  mov     rcx, r13; P
0x14004785f  call    cs:__imp_ExFreePoolWithTag
0x140047866  nop     dword ptr [rax+rax+00h]
0x14004786b  jmp     loc_140047E07
0x140047870  lea     rax, [rsi+6E0h]
0x140047877  mov     rcx, [rax+8]
0x14004787b  cmp     [rcx], rax
0x14004787e  jnz     short loc_1400478DF
0x140047880  mov     [r13+8], rcx
0x140047884  mov     [r13+0], rax
0x140047888  mov     [rcx], r13
0x14004788b  lea     rcx, [rbp+57h+var_68]
  ... truncated ...
```
