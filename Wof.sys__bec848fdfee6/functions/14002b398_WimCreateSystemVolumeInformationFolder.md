# WimCreateSystemVolumeInformationFolder

- ea: `0x14002b398`
- end: `0x14002b44b`
- name: `WimCreateSystemVolumeInformationFolder`
- size: `179`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003cab0`

## callees

- `0x14002b398`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002b42f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b42f`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b3c0`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b3c0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002b40d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002b40d`
- `ntoskrnl!KeInitializeEvent` at `0x14002b3e7`
- `ntoskrnl!KeInitializeEvent` at `0x14002b3e7`

## pseudocode

```c
__int64 __fastcall WimCreateSystemVolumeInformationFolder(__int64 a1)
{
  struct _IO_WORKITEM *WorkItem; // rbx
  _BYTE Event[32]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v5; // [rsp+50h] [rbp-18h]

  memset(Event, 0, sizeof(Event));
  v5 = 0;
  WorkItem = IoAllocateWorkItem(DeviceObject);
  if ( !WorkItem )
    return 3221225626LL;
  KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
  *(_QWORD *)&Event[24] = a1;
  IoQueueWorkItemEx(WorkItem, WimCreateSystemVolumeInfoWork, DelayedWorkQueue, Event);
  KeWaitForSingleObject(Event, Executive, 0, 0, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002b398  mov     [rsp+arg_0], rbx
0x14002b39d  push    rdi
0x14002b39e  sub     rsp, 60h
0x14002b3a2  xorps   xmm0, xmm0
0x14002b3a5  mov     rdi, rcx
0x14002b3a8  mov     rcx, cs:DeviceObject; DeviceObject
0x14002b3af  xor     eax, eax
0x14002b3b1  movups  xmmword ptr [rsp+68h+Event], xmm0
0x14002b3b6  mov     [rsp+68h+var_18], rax
0x14002b3bb  movups  xmmword ptr [rsp+68h+Event+10h], xmm0
0x14002b3c0  call    cs:__imp_IoAllocateWorkItem
0x14002b3c7  nop     dword ptr [rax+rax+00h]
0x14002b3cc  mov     rbx, rax
0x14002b3cf  test    rax, rax
0x14002b3d2  jnz     short loc_14002B3DB
0x14002b3d4  mov     eax, 0C000009Ah
0x14002b3d9  jmp     short loc_14002B43F
0x14002b3db  xor     r8d, r8d; State
0x14002b3de  lea     rcx, [rsp+68h+Event]; Event
0x14002b3e3  lea     edx, [r8+1]; Type
0x14002b3e7  call    cs:__imp_KeInitializeEvent
0x14002b3ee  nop     dword ptr [rax+rax+00h]
0x14002b3f3  lea     r9, [rsp+68h+Event]; Context
0x14002b3f8  mov     qword ptr [rsp+68h+Event+18h], rdi
0x14002b3fd  mov     r8d, 1; QueueType
0x14002b403  lea     rdx, WimCreateSystemVolumeInfoWork; WorkerRoutine
0x14002b40a  mov     rcx, rbx; IoWorkItem
0x14002b40d  call    cs:__imp_IoQueueWorkItemEx
0x14002b414  nop     dword ptr [rax+rax+00h]
0x14002b419  xor     r9d, r9d; Alertable
0x14002b41c  mov     [rsp+68h+Timeout], 0; Timeout
0x14002b425  xor     r8d, r8d; WaitMode
0x14002b428  lea     rcx, [rsp+68h+Event]; Object
0x14002b42d  xor     edx, edx; WaitReason
0x14002b42f  call    cs:__imp_KeWaitForSingleObject
0x14002b436  nop     dword ptr [rax+rax+00h]
0x14002b43b  mov     eax, dword ptr [rsp+68h+var_18]
0x14002b43f  mov     rbx, [rsp+68h+arg_0]
0x14002b444  add     rsp, 60h
0x14002b448  pop     rdi
0x14002b449  retn
```
