# HCI_CommandCreditReturnTimeoutDpc(_KDPC *,void *,void *,void *)

- ea: `0x140032ea0`
- end: `0x140032fdb`
- name: `?HCI_CommandCreditReturnTimeoutDpc@@YAXPEAU_KDPC@@PEAX11@Z`
- size: `315`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005608`
- `0x14000abf4`
- `0x1400272a4`
- `0x140032ea0`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140032ebf`
- `ntoskrnl!IoAllocateWorkItem` at `0x140032f72`
- `ntoskrnl!IoAllocateWorkItem` at `0x140032ebf`
- `ntoskrnl!IoAllocateWorkItem` at `0x140032f72`
- `ntoskrnl!IoQueueWorkItem` at `0x140032fc8`
- `ntoskrnl!IoQueueWorkItem` at `0x140032fc8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140032f35`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140032f35`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140032f59`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140032f59`

## pseudocode

```c
void __fastcall HCI_CommandCreditReturnTimeoutDpc(
        struct _KDPC *Dpc,
        _QWORD *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct Driver *Instance; // rax
  struct _IO_WORKITEM *WorkItem; // rax
  int v7; // edx
  int v8; // r8d
  PDEVICE_OBJECT v9; // rcx
  struct _IO_WORKITEM *v10; // rax
  __int16 v11; // [rsp+30h] [rbp-18h]

  if ( (unsigned int)Feature_59215879__private_IsEnabledDeviceUsageNoInline(Dpc, DeferredContext, SystemArgument1) )
  {
    Instance = Driver::GetInstance();
    WorkItem = IoAllocateWorkItem(Instance->m_controlDevice);
    if ( !WorkItem )
    {
      v9 = WPP_GLOBAL_Control;
      LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v11 = 22;
LABEL_8:
      LOBYTE(v8) = 1;
      WPP_RECORDER_AND_TRACE_SF_(
        v9->AttachedDevice,
        v7,
        v8,
        DeferredContext[534],
        2,
        2,
        v11,
        (__int64)WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids);
      IoReleaseRemoveLockEx(
        (PIO_REMOVE_LOCK)(DeferredContext[149] + 56LL),
        HCI_StartCommandCreditReturnTimerLocked,
        0x20u);
      return;
    }
    IoQueueWorkItemEx(
      WorkItem,
      (PIO_WORKITEM_ROUTINE_EX)HCI_CommandCreditReturnTimeoutWorker,
      DelayedWorkQueue,
      DeferredContext);
  }
  else
  {
    v10 = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(DeferredContext[149] + 8LL));
    if ( !v10 )
    {
      v9 = WPP_GLOBAL_Control;
      LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      v11 = 23;
      goto LABEL_8;
    }
    IoQueueWorkItem(v10, (PIO_WORKITEM_ROUTINE)HCI_CommandCreditReturnTimeoutWorkerOld, DelayedWorkQueue, v10);
  }
}

```

## disassembly

```asm
0x140032ea0  push    rbx
0x140032ea2  sub     rsp, 40h
0x140032ea6  mov     rbx, rdx
0x140032ea9  call    Feature_59215879__private_IsEnabledDeviceUsageNoInline
0x140032eae  test    eax, eax
0x140032eb0  jz      loc_140032F67
0x140032eb6  call    ?GetInstance@Driver@@SAAEAV1@XZ; Driver::GetInstance(void)
0x140032ebb  mov     rcx, [rax+10h]; DeviceObject
0x140032ebf  call    cs:__imp_IoAllocateWorkItem
0x140032ec6  nop     dword ptr [rax+rax+00h]
0x140032ecb  test    rax, rax
0x140032ece  jnz     short loc_140032F46
0x140032ed0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032ed7  mov     eax, [rcx+2Ch]
0x140032eda  test    al, 2
0x140032edc  jz      short loc_140032EE8
0x140032ede  cmp     byte ptr [rcx+29h], 2
0x140032ee2  jb      short loc_140032EE8
0x140032ee4  mov     dl, 1
0x140032ee6  jmp     short loc_140032EEA
0x140032ee8  xor     dl, dl
0x140032eea  lea     rax, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x140032ef1  mov     [rsp+48h+var_10], rax
0x140032ef6  mov     [rsp+48h+var_18], 16h
0x140032efd  mov     r9, [rbx+10B0h]
0x140032f04  mov     r8b, 1
0x140032f07  mov     rcx, [rcx+18h]
0x140032f0b  mov     [rsp+48h+var_20], 2
0x140032f13  mov     [rsp+48h+var_28], 2
0x140032f18  call    WPP_RECORDER_AND_TRACE_SF_
0x140032f1d  mov     rcx, [rbx+4A8h]
0x140032f24  lea     rdx, ?HCI_StartCommandCreditReturnTimerLocked@@YAXPEAUHCI_INTERFACE@@W4HciCommandCreditReturnTimeoutReason@@@Z; Tag
0x140032f2b  add     rcx, 38h ; '8'; RemoveLock
0x140032f2f  mov     r8d, 20h ; ' '; RemlockSize
0x140032f35  call    cs:__imp_IoReleaseRemoveLockEx
0x140032f3c  nop     dword ptr [rax+rax+00h]
0x140032f41  jmp     loc_140032FD4
0x140032f46  mov     r9, rbx; Context
0x140032f49  lea     rdx, ?HCI_CommandCreditReturnTimeoutWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x140032f50  mov     r8d, 1; QueueType
0x140032f56  mov     rcx, rax; IoWorkItem
0x140032f59  call    cs:__imp_IoQueueWorkItemEx
0x140032f60  nop     dword ptr [rax+rax+00h]
0x140032f65  jmp     short loc_140032FD4
0x140032f67  mov     rcx, [rbx+4A8h]
0x140032f6e  mov     rcx, [rcx+8]; DeviceObject
0x140032f72  call    cs:__imp_IoAllocateWorkItem
0x140032f79  nop     dword ptr [rax+rax+00h]
0x140032f7e  test    rax, rax
0x140032f81  jnz     short loc_140032FB5
0x140032f83  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032f8a  mov     eax, [rcx+2Ch]
0x140032f8d  test    al, 2
0x140032f8f  jz      short loc_140032F9B
0x140032f91  cmp     byte ptr [rcx+29h], 2
0x140032f95  jb      short loc_140032F9B
0x140032f97  mov     dl, 1
0x140032f99  jmp     short loc_140032F9D
0x140032f9b  xor     dl, dl
0x140032f9d  lea     rax, WPP_c48b0dc8ee6a3df9d32113d0eb8b4ac6_Traceguids
0x140032fa4  mov     [rsp+48h+var_10], rax
0x140032fa9  mov     [rsp+48h+var_18], 17h
0x140032fb0  jmp     loc_140032EFD
0x140032fb5  mov     r9, rax; Context
0x140032fb8  lea     rdx, ?HCI_CommandCreditReturnTimeoutWorkerOld@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x140032fbf  mov     r8d, 1; QueueType
0x140032fc5  mov     rcx, rax; IoWorkItem
0x140032fc8  call    cs:__imp_IoQueueWorkItem
0x140032fcf  nop     dword ptr [rax+rax+00h]
0x140032fd4  add     rsp, 40h
0x140032fd8  pop     rbx
0x140032fd9  retn
```
