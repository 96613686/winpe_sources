# BfsIdleCheckTimerCallback

- ea: `0x1400076a0`
- end: `0x1400076e2`
- name: `BfsIdleCheckTimerCallback`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x1400076b0`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400076b0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400076cf`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400076cf`

## pseudocode

```c
void __fastcall BfsIdleCheckTimerCallback(__int64 a1, void *a2)
{
  struct _IO_WORKITEM *WorkItem; // rax

  WorkItem = IoAllocateWorkItem(gBfsDeviceObject);
  IoQueueWorkItemEx(WorkItem, (PIO_WORKITEM_ROUTINE_EX)BfsIdleCheckWorkitemRoutine, DelayedWorkQueue, a2);
}

```

## disassembly

```asm
0x1400076a0  push    rbx
0x1400076a2  sub     rsp, 20h
0x1400076a6  mov     rcx, cs:gBfsDeviceObject; DeviceObject
0x1400076ad  mov     rbx, rdx
0x1400076b0  call    cs:__imp_IoAllocateWorkItem
0x1400076b7  nop     dword ptr [rax+rax+00h]
0x1400076bc  mov     r9, rbx; Context
0x1400076bf  lea     rdx, BfsIdleCheckWorkitemRoutine; WorkerRoutine
0x1400076c6  mov     rcx, rax; IoWorkItem
0x1400076c9  mov     r8d, 1; QueueType
0x1400076cf  call    cs:__imp_IoQueueWorkItemEx
0x1400076d6  nop     dword ptr [rax+rax+00h]
0x1400076db  add     rsp, 20h
0x1400076df  pop     rbx
0x1400076e0  retn
```
