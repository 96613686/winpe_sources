# A2DP_Device::ServiceReadyTimerDpc(_KDPC *,void *,void *,void *)

- ea: `0x1400333d0`
- end: `0x140033439`
- name: `?ServiceReadyTimerDpc@A2DP_Device@@CAXPEAU_KDPC@@PEAX11@Z`
- size: `105`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140006b70`
- `0x14002d7a4`
- `0x1400333d0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x140033426`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140033426`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400333e0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400333e0`

## string_xrefs

- `0x140033402`: `ServiceReadyTimerDpc`

## pseudocode

```c
void __fastcall A2DP_Device::ServiceReadyTimerDpc(
        struct _KDPC *Dpc,
        PDEVICE_OBJECT *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  struct _IO_WORKITEM *WorkItem; // rax

  WorkItem = IoAllocateWorkItem(DeferredContext[48]);
  if ( WorkItem )
  {
    IoQueueWorkItemEx(
      WorkItem,
      (PIO_WORKITEM_ROUTINE_EX)A2DP_Device::ServiceReadyTimerWorkerStatic,
      DelayedWorkQueue,
      DeferredContext);
  }
  else
  {
    wil::operation_guard::release((wil::operation_guard *)(DeferredContext + 422));
    A2DP_Device::Release((A2DP_Device *)DeferredContext, 1, "ServiceReadyTimerDpc");
  }
}

```

## disassembly

```asm
0x1400333d0  push    rbx
0x1400333d2  sub     rsp, 20h
0x1400333d6  mov     rcx, [rdx+180h]; DeviceObject
0x1400333dd  mov     rbx, rdx
0x1400333e0  call    cs:__imp_IoAllocateWorkItem
0x1400333e7  nop     dword ptr [rax+rax+00h]
0x1400333ec  test    rax, rax
0x1400333ef  jnz     short loc_140033413
0x1400333f1  lea     rcx, [rbx+0D30h]; this
0x1400333f8  call    ?release@operation_guard@wil@@QEAAXXZ; wil::operation_guard::release(void)
0x1400333fd  mov     edx, 1; __int16
0x140033402  lea     r8, aServicereadyti; "ServiceReadyTimerDpc"
0x140033409  mov     rcx, rbx; this
0x14003340c  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x140033411  jmp     short loc_140033432
0x140033413  mov     r9, rbx; Context
0x140033416  lea     rdx, ?ServiceReadyTimerWorkerStatic@A2DP_Device@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x14003341d  mov     r8d, 1; QueueType
0x140033423  mov     rcx, rax; IoWorkItem
0x140033426  call    cs:__imp_IoQueueWorkItemEx
0x14003342d  nop     dword ptr [rax+rax+00h]
0x140033432  add     rsp, 20h
0x140033436  pop     rbx
0x140033437  retn
```
