# BfsIdleCheckTimerCallback

- ea: `0x140007830`
- end: `0x140007872`
- name: `BfsIdleCheckTimerCallback`
- size: `66`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140007840`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007840`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000785f`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000785f`

## pseudocode

```c
void __fastcall BfsIdleCheckTimerCallback(__int64 a1, void *a2)
{
  struct _IO_WORKITEM *WorkItem; // rax

  WorkItem = IoAllocateWorkItem(gBfsDeviceObject);
  IoQueueWorkItemEx(WorkItem, BfsIdleCheckWorkitemRoutine, DelayedWorkQueue, a2);
}

```

## disassembly

```asm
0x140007830  push    rbx
0x140007832  sub     rsp, 20h
0x140007836  mov     rcx, cs:gBfsDeviceObject; DeviceObject
0x14000783d  mov     rbx, rdx
0x140007840  call    cs:__imp_IoAllocateWorkItem
0x140007847  nop     dword ptr [rax+rax+00h]
0x14000784c  mov     r9, rbx; Context
0x14000784f  lea     rdx, BfsIdleCheckWorkitemRoutine; WorkerRoutine
0x140007856  mov     rcx, rax; IoWorkItem
0x140007859  mov     r8d, 1; QueueType
0x14000785f  call    cs:__imp_IoQueueWorkItemEx
0x140007866  nop     dword ptr [rax+rax+00h]
0x14000786b  add     rsp, 20h
0x14000786f  pop     rbx
0x140007870  retn
```
