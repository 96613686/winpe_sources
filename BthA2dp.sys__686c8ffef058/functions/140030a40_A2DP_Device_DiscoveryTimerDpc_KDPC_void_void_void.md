# A2DP_Device::DiscoveryTimerDpc(_KDPC *,void *,void *,void *)

- ea: `0x140030a40`
- end: `0x140030ab5`
- name: `?DiscoveryTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z`
- size: `117`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140030a40`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x140030aa2`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140030aa2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140030a6c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140030a6c`
- `ntoskrnl!IoAllocateWorkItem` at `0x140030a83`
- `ntoskrnl!IoAllocateWorkItem` at `0x140030a83`

## pseudocode

```c
void __fastcall A2DP_Device::DiscoveryTimerDpc(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct _IO_WORKITEM *WorkItem; // rax

  if ( IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(DeferredContext + 824),
         A2DP_Device::DiscoveryTimerDpc,
         "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\btha2dp\\a2dp\\a2dp_device.cpp",
         0xF33u,
         0x20u) >= 0 )
  {
    WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)DeferredContext + 48));
    IoQueueWorkItemEx(WorkItem, A2DP_Device::DiscoveryTimerWorkerStatic, DelayedWorkQueue, DeferredContext);
  }
}

```

## disassembly

```asm
0x140030a40  push    rbx
0x140030a42  sub     rsp, 30h
0x140030a46  mov     rbx, rdx
0x140030a49  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x140030a51  lea     rcx, [rdx+338h]; RemoveLock
0x140030a58  mov     r9d, 0F33h; Line
0x140030a5e  lea     rdx, ?DiscoveryTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z; Tag
0x140030a65  lea     r8, VoidFileName; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x140030a6c  call    cs:__imp_IoAcquireRemoveLockEx
0x140030a73  nop     dword ptr [rax+rax+00h]
0x140030a78  test    eax, eax
0x140030a7a  js      short loc_140030AAE
0x140030a7c  mov     rcx, [rbx+180h]; DeviceObject
0x140030a83  call    cs:__imp_IoAllocateWorkItem
0x140030a8a  nop     dword ptr [rax+rax+00h]
0x140030a8f  mov     r9, rbx; Context
0x140030a92  lea     rdx, ?DiscoveryTimerWorkerStatic@A2DP_Device@@CAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x140030a99  mov     rcx, rax; IoWorkItem
0x140030a9c  mov     r8d, 1; QueueType
0x140030aa2  call    cs:__imp_IoQueueWorkItemEx
0x140030aa9  nop     dword ptr [rax+rax+00h]
0x140030aae  add     rsp, 30h
0x140030ab2  pop     rbx
0x140030ab3  retn
```
