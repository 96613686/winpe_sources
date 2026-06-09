# HCI_EirUpdateData(HCI_INTERFACE *,uchar,_GUID *)

- ea: `0x14006a708`
- end: `0x14006ac9d`
- name: `?HCI_EirUpdateData@@YAJPEAUHCI_INTERFACE@@EPEAU_GUID@@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, unsigned __int8, struct _GUID *)`
- caller_count: `6`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001e010`
- `0x14006a458`
- `0x14006aca4`
- `0x1400ac9f0`
- `0x1401c23a0`
- `0x1401c2400`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140005c04`
- `0x14000abf4`
- `0x1400272a4`
- `0x14005f448`
- `0x14006a708`
- `0x14006aca4`
- `0x140165640`
- `0x1401c2238`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14006aae9`
- `ntoskrnl!IoAllocateWorkItem` at `0x14006abd6`
- `ntoskrnl!IoAllocateWorkItem` at `0x14006aae9`
- `ntoskrnl!IoAllocateWorkItem` at `0x14006abd6`
- `ntoskrnl!IoQueueWorkItem` at `0x14006ac1e`
- `ntoskrnl!IoQueueWorkItem` at `0x14006ac1e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14006ab50`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14006ab50`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006aa89`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006ab8e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006aa89`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14006ab8e`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006ab6d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14006ab6d`
- `ntoskrnl!RtlCompareMemory` at `0x14006a958`
- `ntoskrnl!RtlCompareMemory` at `0x14006a958`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa39`
- `ntoskrnl!ExAllocatePool2` at `0x14006a875`
- `ntoskrnl!ExAllocatePool2` at `0x14006a875`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006a83e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006a83e`

## pseudocode

```c
__int64 __fastcall HCI_EirUpdateData(struct HCI_INTERFACE *a1, char a2, struct _GUID *a3)
{
  char v5; // bl
  char v6; // dl
  __int16 DeviceType; // ax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  NTSTATUS v12; // edi
  unsigned __int8 EirCbSize; // di
  size_t v14; // rbp
  unsigned __int8 *Pool2; // rax
  int v16; // edx
  int v17; // r8d
  unsigned __int8 *v18; // r14
  int v19; // edx
  __int64 *v20; // r8
  int v21; // edx
  PDEVICE_OBJECT v22; // rcx
  __int64 *v23; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  struct _IO_REMOVE_LOCK *p_RemoveLock; // rcx
  IO_WORKITEM_ROUTINE *v26; // r15
  int v27; // edx
  int v28; // r8d
  PDEVICE_OBJECT v29; // rcx
  struct Driver *Instance; // rax
  struct _IO_WORKITEM *WorkItem; // rax
  int v32; // edx
  int v33; // r8d
  PDEVICE_OBJECT v34; // rcx
  struct _IO_WORKITEM *v35; // rax
  __int16 v36; // ax
  __int16 v38; // [rsp+30h] [rbp-78h]
  __int16 v39; // [rsp+30h] [rbp-78h]
  __int16 v40; // [rsp+30h] [rbp-78h]
  _QWORD v41[11]; // [rsp+50h] [rbp-58h] BYREF

  v5 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v6 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v6 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v6 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      24,
      (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids,
      (char)a1);
  if ( !HCI_EirIsSupported(a1) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      LOBYTE(v8) = 0;
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      2,
      25,
      (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
    v12 = -1073741637;
    goto LABEL_70;
  }
  if ( !a1->EirInfo.EirCbSize )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
      LOBYTE(v8) = 0;
    LOBYTE(v9) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      2,
      26,
      (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
    v12 = 0;
    goto LABEL_70;
  }
  if ( a2 || KeGetCurrentIrql() > 1u )
  {
    IsEnabledDeviceUsageNoInline = Feature_59215879__private_IsEnabledDeviceUsageNoInline();
    p_RemoveLock = &a1->DevExt->RemoveLock;
    if ( IsEnabledDeviceUsageNoInline )
    {
      v26 = (IO_WORKITEM_ROUTINE *)HCI_EirUpdateDataWorker;
      v12 = IoAcquireRemoveLockEx(
              p_RemoveLock,
              HCI_EirUpdateDataWorker,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcieir.cpp",
              0x282u,
              0x20u);
      if ( v12 < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v27) = 0;
        v39 = 27;
LABEL_50:
        LOBYTE(v28) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          v29->AttachedDevice,
          v27,
          v28,
          v29->DeviceExtension,
          2,
          2,
          v39,
          (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
        goto LABEL_70;
      }
      Instance = Driver::GetInstance();
      WorkItem = IoAllocateWorkItem(Instance->m_controlDevice);
      if ( !WorkItem )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v32) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v32) = 0;
        v40 = 28;
LABEL_56:
        LOBYTE(v33) = 1;
        WPP_RECORDER_AND_TRACE_SF_(
          v34->AttachedDevice,
          v32,
          v33,
          v34->DeviceExtension,
          2,
          2,
          v40,
          (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
        v12 = -1073741670;
        IoReleaseRemoveLockEx(&a1->DevExt->RemoveLock, v26, 0x20u);
        goto LABEL_70;
      }
      IoQueueWorkItemEx(WorkItem, HCI_EirUpdateDataWorker, DelayedWorkQueue, a1);
    }
    else
    {
      v26 = HCI_EirUpdateDataWorkerOld;
      v12 = IoAcquireRemoveLockEx(
              p_RemoveLock,
              HCI_EirUpdateDataWorkerOld,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcieir.cpp",
              0x298u,
              0x20u);
      if ( v12 < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v27) = 0;
        v39 = 29;
        goto LABEL_50;
      }
      v35 = IoAllocateWorkItem(a1->DevExt->BtDevice.FunctionalDeviceObject);
      if ( !v35 )
      {
        v34 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v32) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v32) = 0;
        v40 = 30;
        goto LABEL_56;
      }
      IoQueueWorkItem(v35, HCI_EirUpdateDataWorkerOld, DelayedWorkQueue, v35);
    }
    v12 = 259;
    goto LABEL_70;
  }
  EirCbSize = a1->EirInfo.EirCbSize;
  if ( EirCbSize > 0xF0u )
    EirCbSize = -16;
  v14 = EirCbSize;
  Pool2 = (unsigned __int8 *)ExAllocatePool2(64, EirCbSize, 1346917442);
  v18 = Pool2;
  if ( Pool2 )
  {
    v12 = HCI_EirBuildData(a1, Pool2, EirCbSize);
    if ( v12 < 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v19) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v19) = 0;
      v20 = WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids;
      LOBYTE(v20) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v19,
        (_DWORD)v20,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        32,
        (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids,
        v12);
      goto LABEL_43;
    }
    wil::acquire_kspin_lock(v41, &a1->HciLock);
    if ( v14 == RtlCompareMemory(&a1->EirInfo, v18, v14) )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v21) = 0;
      v23 = WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids;
      v38 = 33;
    }
    else
    {
      if ( !a1->EirInfo.EirWriteInProgress )
      {
        a1->EirInfo.EirWriteInProgress = 1;
        memmove(&a1->EirInfo, v18, v14);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v41);
        v41[0] = v18;
        v41[1] = v14;
        HCI_EirWrite(a1);
        goto LABEL_43;
      }
      a1->EirInfo.EirRewrite = 1;
      v12 = 259;
      v22 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        LOBYTE(v21) = 0;
      v23 = WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids;
      v38 = 34;
    }
    LOBYTE(v23) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v22->AttachedDevice,
      v21,
      (_DWORD)v23,
      v22->DeviceExtension,
      4,
      2,
      v38,
      (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v41);
LABEL_43:
    ExFreePoolWithTag(v18, 0);
    goto LABEL_70;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    LOBYTE(v16) = 0;
  LOBYTE(v17) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v16,
    v17,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    2,
    31,
    (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids);
  v12 = -1073741670;
LABEL_70:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v5 = 0;
  v36 = WPP_GLOBAL_Control->DeviceType;
  if ( v5 || v36 )
  {
    LOBYTE(v10) = v5;
    LOBYTE(v11) = v36 != 0;
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      35,
      (__int64)WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids,
      (char)a1,
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14006a708  push    rbx
0x14006a70a  push    rbp
0x14006a70b  push    rsi
0x14006a70c  push    rdi
0x14006a70d  push    r12
0x14006a70f  push    r13
0x14006a711  push    r14
0x14006a713  push    r15
0x14006a715  sub     rsp, 68h
0x14006a719  mov     dil, dl
0x14006a71c  mov     rsi, rcx
0x14006a71f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a726  xor     r13d, r13d
0x14006a729  mov     eax, [rcx+2Ch]
0x14006a72c  lea     r12d, [r13+2]
0x14006a730  lea     ebx, [r13+1]
0x14006a734  test    r12b, al
0x14006a737  jz      short loc_14006A741
0x14006a739  cmp     byte ptr [rcx+29h], 5
0x14006a73d  mov     dl, bl
0x14006a73f  jnb     short loc_14006A744
0x14006a741  mov     dl, r13b
0x14006a744  movzx   eax, word ptr [rcx+48h]
0x14006a748  lea     r14, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006a74f  test    ax, ax
0x14006a752  setnz   r8b
0x14006a756  test    dl, dl
0x14006a758  jnz     short loc_14006A75F
0x14006a75a  test    ax, ax
0x14006a75d  jz      short loc_14006A787
0x14006a75f  mov     r9, [rcx+40h]
0x14006a763  mov     rcx, [rcx+18h]
0x14006a767  mov     [rsp+0A8h+var_68], rsi
0x14006a76c  mov     [rsp+0A8h+var_70], r14
0x14006a771  mov     [rsp+0A8h+var_78], 18h
0x14006a778  mov     [rsp+0A8h+var_80], r12d
0x14006a77d  mov     byte ptr [rsp+0A8h+RemlockSize], 5
0x14006a782  call    WPP_RECORDER_AND_TRACE_SF_q
0x14006a787  mov     rcx, rsi; struct HCI_INTERFACE *
0x14006a78a  call    ?HCI_EirIsSupported@@YAEPEAUHCI_INTERFACE@@@Z; HCI_EirIsSupported(HCI_INTERFACE *)
0x14006a78f  test    al, al
0x14006a791  jnz     short loc_14006A7DD
0x14006a793  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a79a  mov     eax, [rcx+2Ch]
0x14006a79d  test    r12b, al
0x14006a7a0  jz      short loc_14006A7AA
0x14006a7a2  cmp     byte ptr [rcx+29h], 3
0x14006a7a6  mov     dl, bl
0x14006a7a8  jnb     short loc_14006A7AD
0x14006a7aa  mov     dl, r13b
0x14006a7ad  mov     r9, [rcx+40h]
0x14006a7b1  mov     r8b, bl
0x14006a7b4  mov     rcx, [rcx+18h]
0x14006a7b8  mov     [rsp+0A8h+var_70], r14
0x14006a7bd  mov     [rsp+0A8h+var_78], 19h
0x14006a7c4  mov     [rsp+0A8h+var_80], r12d
0x14006a7c9  mov     byte ptr [rsp+0A8h+RemlockSize], 3
0x14006a7ce  call    WPP_RECORDER_AND_TRACE_SF_
0x14006a7d3  mov     edi, 0C00000BBh
0x14006a7d8  jmp     loc_14006AC2F
0x14006a7dd  lea     r15, [rsi+2A8h]
0x14006a7e4  cmp     [r15+0F0h], r13b
0x14006a7eb  jnz     short loc_14006A835
0x14006a7ed  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a7f4  mov     eax, [rcx+2Ch]
0x14006a7f7  test    r12b, al
0x14006a7fa  jz      short loc_14006A804
0x14006a7fc  cmp     byte ptr [rcx+29h], 4
0x14006a800  mov     dl, bl
0x14006a802  jnb     short loc_14006A807
0x14006a804  mov     dl, r13b
0x14006a807  mov     r9, [rcx+40h]
0x14006a80b  mov     r8b, bl
0x14006a80e  mov     rcx, [rcx+18h]
0x14006a812  mov     [rsp+0A8h+var_70], r14
0x14006a817  mov     [rsp+0A8h+var_78], 1Ah
0x14006a81e  mov     [rsp+0A8h+var_80], r12d
0x14006a823  mov     byte ptr [rsp+0A8h+RemlockSize], 4
0x14006a828  call    WPP_RECORDER_AND_TRACE_SF_
0x14006a82d  mov     edi, r13d
0x14006a830  jmp     loc_14006AC2F
0x14006a835  test    dil, dil
0x14006a838  jnz     loc_14006AA51
0x14006a83e  call    cs:__imp_KeGetCurrentIrql
0x14006a845  nop     dword ptr [rax+rax+00h]
0x14006a84a  cmp     al, bl
0x14006a84c  ja      loc_14006AA51
0x14006a852  movzx   edi, byte ptr [rsi+398h]
0x14006a859  mov     eax, 0F0h
0x14006a85e  cmp     dil, al
0x14006a861  mov     r8d, 50485442h
0x14006a867  mov     ecx, 40h ; '@'
0x14006a86c  cmova   edi, eax
0x14006a86f  movzx   ebp, dil
0x14006a873  mov     edx, ebp
0x14006a875  call    cs:__imp_ExAllocatePool2
0x14006a87c  nop     dword ptr [rax+rax+00h]
0x14006a881  mov     r14, rax
0x14006a884  test    rax, rax
0x14006a887  jnz     short loc_14006A8DA
0x14006a889  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a890  mov     eax, [rcx+2Ch]
0x14006a893  test    r12b, al
0x14006a896  jz      short loc_14006A8A0
0x14006a898  mov     dl, bl
0x14006a89a  cmp     [rcx+29h], r12b
0x14006a89e  jnb     short loc_14006A8A3
0x14006a8a0  mov     dl, r13b
0x14006a8a3  mov     r9, [rcx+40h]
0x14006a8a7  lea     r14, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006a8ae  mov     rcx, [rcx+18h]
0x14006a8b2  mov     r8b, bl
0x14006a8b5  mov     [rsp+0A8h+var_70], r14
0x14006a8ba  mov     [rsp+0A8h+var_78], 1Fh
0x14006a8c1  mov     [rsp+0A8h+var_80], r12d
0x14006a8c6  mov     byte ptr [rsp+0A8h+RemlockSize], r12b
0x14006a8cb  call    WPP_RECORDER_AND_TRACE_SF_
0x14006a8d0  mov     edi, 0C000009Ah
0x14006a8d5  jmp     loc_14006AC2F
0x14006a8da  mov     r8b, dil; unsigned __int8
0x14006a8dd  mov     rdx, r14; unsigned __int8 *
0x14006a8e0  mov     rcx, rsi; struct HCI_INTERFACE *
0x14006a8e3  call    ?HCI_EirBuildData@@YAJPEAUHCI_INTERFACE@@PEAEE@Z; HCI_EirBuildData(HCI_INTERFACE *,uchar *,uchar)
0x14006a8e8  mov     edi, eax
0x14006a8ea  test    eax, eax
0x14006a8ec  jns     short loc_14006A93E
0x14006a8ee  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a8f5  mov     ecx, [rax+2Ch]
0x14006a8f8  test    r12b, cl
0x14006a8fb  jz      short loc_14006A905
0x14006a8fd  mov     dl, bl
0x14006a8ff  cmp     [rax+29h], r12b
0x14006a903  jnb     short loc_14006A908
0x14006a905  mov     dl, r13b
0x14006a908  mov     r9, [rax+40h]
0x14006a90c  lea     r8, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006a913  mov     rcx, [rax+18h]
0x14006a917  mov     dword ptr [rsp+0A8h+var_68], edi
0x14006a91b  mov     [rsp+0A8h+var_70], r8
0x14006a920  mov     r8b, bl
0x14006a923  mov     [rsp+0A8h+var_78], 20h ; ' '
0x14006a92a  mov     [rsp+0A8h+var_80], r12d
0x14006a92f  mov     byte ptr [rsp+0A8h+RemlockSize], r12b
0x14006a934  call    WPP_RECORDER_AND_TRACE_SF_d
0x14006a939  jmp     loc_14006AA34
0x14006a93e  lea     rdx, [rsi+7B0h]
0x14006a945  lea     rcx, [rsp+0A8h+var_58]
0x14006a94a  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14006a94f  mov     r8, rbp; Length
0x14006a952  mov     rdx, r14; Source2
0x14006a955  mov     rcx, r15; Source1
0x14006a958  call    cs:__imp_RtlCompareMemory
0x14006a95f  nop     dword ptr [rax+rax+00h]
0x14006a964  cmp     rbp, rax
0x14006a967  jnz     short loc_14006A9BC
0x14006a969  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a970  mov     eax, [rcx+2Ch]
0x14006a973  test    r12b, al
0x14006a976  jz      short loc_14006A980
0x14006a978  cmp     byte ptr [rcx+29h], 4
0x14006a97c  mov     dl, bl
0x14006a97e  jnb     short loc_14006A983
0x14006a980  mov     dl, r13b
0x14006a983  lea     r8, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006a98a  mov     [rsp+0A8h+var_70], r8
0x14006a98f  mov     [rsp+0A8h+var_78], 21h ; '!'
0x14006a996  mov     r9, [rcx+40h]
0x14006a99a  mov     r8b, bl
0x14006a99d  mov     rcx, [rcx+18h]
0x14006a9a1  mov     [rsp+0A8h+var_80], r12d
0x14006a9a6  mov     byte ptr [rsp+0A8h+RemlockSize], 4
0x14006a9ab  call    WPP_RECORDER_AND_TRACE_SF_
0x14006a9b0  lea     rcx, [rsp+0A8h+var_58]
0x14006a9b5  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14006a9ba  jmp     short loc_14006AA34
0x14006a9bc  cmp     [rsi+470h], r13b
0x14006a9c3  jz      short loc_14006A9FF
0x14006a9c5  mov     [rsi+471h], bl
0x14006a9cb  mov     edi, 103h
0x14006a9d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006a9d7  mov     eax, [rcx+2Ch]
0x14006a9da  test    r12b, al
0x14006a9dd  jz      short loc_14006A9E7
0x14006a9df  cmp     byte ptr [rcx+29h], 4
0x14006a9e3  mov     dl, bl
0x14006a9e5  jnb     short loc_14006A9EA
0x14006a9e7  mov     dl, r13b
0x14006a9ea  lea     r8, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006a9f1  mov     [rsp+0A8h+var_70], r8
0x14006a9f6  mov     [rsp+0A8h+var_78], 22h ; '"'
0x14006a9fd  jmp     short loc_14006A996
0x14006a9ff  mov     r8, rbp; Size
0x14006aa02  mov     [rsi+470h], bl
0x14006aa08  mov     rdx, r14; Src
0x14006aa0b  mov     rcx, r15; void *
0x14006aa0e  call    memmove
0x14006aa13  lea     rcx, [rsp+0A8h+var_58]
0x14006aa18  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14006aa1d  lea     rdx, [rsp+0A8h+var_58]
0x14006aa22  mov     [rsp+0A8h+var_58], r14
0x14006aa27  mov     rcx, rsi; struct HCI_INTERFACE *
0x14006aa2a  mov     [rsp+0A8h+var_50], rbp
0x14006aa2f  call    ?HCI_EirWrite@@YAXPEAUHCI_INTERFACE@@V?$span@E$0?0@utl@@@Z; HCI_EirWrite(HCI_INTERFACE *,utl::span<uchar,-1>)
0x14006aa34  xor     edx, edx; Tag
0x14006aa36  mov     rcx, r14; P
0x14006aa39  call    cs:__imp_ExFreePoolWithTag
0x14006aa40  nop     dword ptr [rax+rax+00h]
0x14006aa45  lea     r14, WPP_9a25735bedf1311bf65b0d2d91465f50_Traceguids
0x14006aa4c  jmp     loc_14006AC2F
0x14006aa51  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x14006aa56  mov     rcx, [rsi+4A8h]
0x14006aa5d  lea     r8, aOnecoreDrivers_40; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14006aa64  add     rcx, 38h ; '8'; RemoveLock
0x14006aa68  mov     ebp, 20h ; ' '
0x14006aa6d  mov     [rsp+0A8h+RemlockSize], ebp; RemlockSize
0x14006aa71  test    eax, eax
0x14006aa73  jz      loc_14006AB7E
0x14006aa79  lea     r15, ?HCI_EirUpdateDataWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; HCI_EirUpdateDataWorker(void *,void *,_IO_WORKITEM *)
0x14006aa80  mov     r9d, 282h; Line
0x14006aa86  mov     rdx, r15; Tag
0x14006aa89  call    cs:__imp_IoAcquireRemoveLockEx
0x14006aa90  nop     dword ptr [rax+rax+00h]
0x14006aa95  mov     edi, eax
0x14006aa97  test    eax, eax
0x14006aa99  jns     short loc_14006AAE0
0x14006aa9b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006aaa2  mov     eax, [rcx+2Ch]
0x14006aaa5  test    r12b, al
0x14006aaa8  jz      short loc_14006AAB2
0x14006aaaa  mov     dl, bl
0x14006aaac  cmp     [rcx+29h], r12b
0x14006aab0  jnb     short loc_14006AAB5
0x14006aab2  mov     dl, r13b
0x14006aab5  mov     [rsp+0A8h+var_70], r14
0x14006aaba  mov     [rsp+0A8h+var_78], 1Bh
0x14006aac1  mov     r9, [rcx+40h]
0x14006aac5  mov     r8b, bl
0x14006aac8  mov     rcx, [rcx+18h]
0x14006aacc  mov     [rsp+0A8h+var_80], r12d
0x14006aad1  mov     byte ptr [rsp+0A8h+RemlockSize], r12b
0x14006aad6  call    WPP_RECORDER_AND_TRACE_SF_
0x14006aadb  jmp     loc_14006AC2F
0x14006aae0  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x14006aae5  mov     rcx, [rax+10h]; DeviceObject
0x14006aae9  call    cs:__imp_IoAllocateWorkItem
0x14006aaf0  nop     dword ptr [rax+rax+00h]
0x14006aaf5  test    rax, rax
0x14006aaf8  jnz     short loc_14006AB61
0x14006aafa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006ab01  mov     eax, [rcx+2Ch]
0x14006ab04  test    r12b, al
0x14006ab07  jz      short loc_14006AB11
0x14006ab09  mov     dl, bl
0x14006ab0b  cmp     [rcx+29h], r12b
0x14006ab0f  jnb     short loc_14006AB14
0x14006ab11  mov     dl, r13b
0x14006ab14  mov     [rsp+0A8h+var_70], r14
0x14006ab19  mov     [rsp+0A8h+var_78], 1Ch
0x14006ab20  mov     r9, [rcx+40h]
0x14006ab24  mov     r8b, bl
0x14006ab27  mov     rcx, [rcx+18h]
0x14006ab2b  mov     [rsp+0A8h+var_80], r12d
0x14006ab30  mov     byte ptr [rsp+0A8h+RemlockSize], r12b
0x14006ab35  call    WPP_RECORDER_AND_TRACE_SF_
0x14006ab3a  mov     rcx, [rsi+4A8h]
0x14006ab41  mov     r8d, ebp; RemlockSize
0x14006ab44  add     rcx, 38h ; '8'; RemoveLock
0x14006ab48  mov     rdx, r15; Tag
0x14006ab4b  mov     edi, 0C000009Ah
0x14006ab50  call    cs:__imp_IoReleaseRemoveLockEx
0x14006ab57  nop     dword ptr [rax+rax+00h]
0x14006ab5c  jmp     loc_14006AC2F
0x14006ab61  mov     r9, rsi; Context
0x14006ab64  mov     r8d, ebx; QueueType
0x14006ab67  mov     rdx, r15; WorkerRoutine
0x14006ab6a  mov     rcx, rax; IoWorkItem
0x14006ab6d  call    cs:__imp_IoQueueWorkItemEx
0x14006ab74  nop     dword ptr [rax+rax+00h]
0x14006ab79  jmp     loc_14006AC2A
0x14006ab7e  lea     r15, ?HCI_EirUpdateDataWorkerOld@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; HCI_EirUpdateDataWorkerOld(_DEVICE_OBJECT *,void *)
0x14006ab85  mov     r9d, 298h; Line
0x14006ab8b  mov     rdx, r15; Tag
0x14006ab8e  call    cs:__imp_IoAcquireRemoveLockEx
0x14006ab95  nop     dword ptr [rax+rax+00h]
0x14006ab9a  mov     edi, eax
0x14006ab9c  test    eax, eax
0x14006ab9e  jns     short loc_14006ABCB
0x14006aba0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006aba7  mov     eax, [rcx+2Ch]
0x14006abaa  test    r12b, al
0x14006abad  jz      short loc_14006ABB7
0x14006abaf  mov     dl, bl
0x14006abb1  cmp     [rcx+29h], r12b
0x14006abb5  jnb     short loc_14006ABBA
0x14006abb7  mov     dl, r13b
0x14006abba  mov     [rsp+0A8h+var_70], r14
0x14006abbf  mov     [rsp+0A8h+var_78], 1Dh
0x14006abc6  jmp     loc_14006AAC1
0x14006abcb  mov     rcx, [rsi+4A8h]
0x14006abd2  mov     rcx, [rcx+8]; DeviceObject
  ... truncated ...
```
