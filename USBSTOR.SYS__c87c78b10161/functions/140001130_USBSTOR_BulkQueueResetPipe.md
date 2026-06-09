# USBSTOR_BulkQueueResetPipe

- ea: `0x140001130`
- end: `0x1400012c5`
- name: `USBSTOR_BulkQueueResetPipe`
- size: `405`
- prototype: `__int64 __fastcall(PVOID Object, PVOID Context)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023b0`
- `0x140003e10`

## callees

- `0x140001130`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14000128b`
- `ntoskrnl!ObfReferenceObject` at `0x14000128b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001165`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001165`
- `ntoskrnl!KeInsertQueue` at `0x1400012b4`
- `ntoskrnl!KeInsertQueue` at `0x1400012b4`
- `ntoskrnl!IoSizeofWorkItem` at `0x140001277`
- `ntoskrnl!IoSizeofWorkItem` at `0x140001277`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14000125d`
- `ntoskrnl!IoTryQueueWorkItem` at `0x14000125d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001229`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140001229`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400011fd`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400011fd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400011c7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400011c7`

## pseudocode

```c
void __fastcall USBSTOR_BulkQueueResetPipe(_QWORD *Object, PVOID Context)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1347637841;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Context;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v4 = qword_14001A198 - 32;
    else
      v4 = qword_14001A190 - 32;
    qword_14001A190 = v4;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v5 = Object[8];
  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v5 + 1832), USBSTOR_BulkResetPipeWorkItem, File, 1u, 0x20u) >= 0 )
  {
    v6 = *(_QWORD *)(v5 + 368);
    if ( !*(_BYTE *)(v5 + 1876) )
    {
LABEL_7:
      IoQueueWorkItemEx(
        (PIO_WORKITEM)v6,
        (PIO_WORKITEM_ROUTINE_EX)USBSTOR_BulkResetPipeWorkItem,
        CriticalWorkQueue,
        Context);
      return;
    }
    if ( !(unsigned __int8)IoTryQueueWorkItem(*(_QWORD *)(v5 + 368), USBSTOR_BulkResetPipeWorkItem, 0, Context) )
    {
      if ( EmergencyWorkerThread && IoSizeofWorkItem() >= 0x28 )
      {
        ObfReferenceObject(Object);
        *(_QWORD *)(v6 + 24) = Object;
        *(_QWORD *)(v6 + 16) = USBSTOR_BulkResetPipeWorkItem;
        *(_QWORD *)(v6 + 32) = Context;
        *(_QWORD *)(v6 + 8) = v6;
        *(_QWORD *)v6 = v6;
        KeInsertQueue(&EmergencyWorkQueue, (PLIST_ENTRY)v6);
        return;
      }
      goto LABEL_7;
    }
  }
}

```

## disassembly

```asm
0x140001130  push    rbx
0x140001132  push    rbp
0x140001133  push    rsi
0x140001134  push    rdi
0x140001135  push    r15
0x140001137  sub     rsp, 50h
0x14000113b  xor     eax, eax
0x14000113d  xorps   xmm0, xmm0
0x140001140  cmp     cs:P, rax
0x140001147  mov     rdi, rdx
0x14000114a  mov     rbp, rcx
0x14000114d  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140001152  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140001157  jz      short loc_1400011D3
0x140001159  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000115e  lea     rcx, SpinLock; SpinLock
0x140001165  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000116c  nop     dword ptr [rax+rax+00h]
0x140001171  mov     rax, cs:qword_14001A190
0x140001178  mov     dword ptr [rax], 50535251h
0x14000117e  mov     rax, cs:qword_14001A190
0x140001185  mov     [rax+8], rbp
0x140001189  mov     rax, cs:qword_14001A190
0x140001190  mov     [rax+10h], rdi
0x140001194  mov     rax, cs:qword_14001A190
0x14000119b  mov     qword ptr [rax+18h], 0
0x1400011a3  mov     rax, cs:qword_14001A190
0x1400011aa  cmp     rax, cs:P
0x1400011b1  jbe     loc_140001241
0x1400011b7  sub     rax, 20h ; ' '
0x1400011bb  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400011c0  mov     cs:qword_14001A190, rax
0x1400011c7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400011ce  nop     dword ptr [rax+rax+00h]
0x1400011d3  mov     rsi, [rbp+40h]
0x1400011d7  lea     r15, USBSTOR_BulkResetPipeWorkItem
0x1400011de  mov     r9d, 1; Line
0x1400011e4  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1400011ec  lea     r8, File; File
0x1400011f3  mov     rdx, r15; Tag
0x1400011f6  lea     rcx, [rsi+728h]; RemoveLock
0x1400011fd  call    cs:__imp_IoAcquireRemoveLockEx
0x140001204  nop     dword ptr [rax+rax+00h]
0x140001209  test    eax, eax
0x14000120b  js      short loc_140001235
0x14000120d  cmp     byte ptr [rsi+754h], 0
0x140001214  mov     rbx, [rsi+170h]
0x14000121b  jnz     short loc_140001251
0x14000121d  mov     r9, rdi; Context
0x140001220  xor     r8d, r8d; QueueType
0x140001223  mov     rdx, r15; WorkerRoutine
0x140001226  mov     rcx, rbx; IoWorkItem
0x140001229  call    cs:__imp_IoQueueWorkItemEx
0x140001230  nop     dword ptr [rax+rax+00h]
0x140001235  add     rsp, 50h
0x140001239  pop     r15
0x14000123b  pop     rdi
0x14000123c  pop     rsi
0x14000123d  pop     rbp
0x14000123e  pop     rbx
0x14000123f  retn
0x140001241  mov     rax, cs:qword_14001A198
0x140001248  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000124c  jmp     loc_1400011BB
0x140001251  mov     r9, rdi
0x140001254  xor     r8d, r8d
0x140001257  mov     rdx, r15
0x14000125a  mov     rcx, rbx
0x14000125d  call    cs:__imp_IoTryQueueWorkItem
0x140001264  nop     dword ptr [rax+rax+00h]
0x140001269  test    al, al
0x14000126b  jnz     short loc_140001235
0x14000126d  cmp     cs:EmergencyWorkerThread, 0
0x140001275  jz      short loc_14000121D
0x140001277  call    cs:__imp_IoSizeofWorkItem
0x14000127e  nop     dword ptr [rax+rax+00h]
0x140001283  cmp     eax, 28h ; '('
0x140001286  jb      short loc_14000121D
0x140001288  mov     rcx, rbp; Object
0x14000128b  call    cs:__imp_ObfReferenceObject
0x140001292  nop     dword ptr [rax+rax+00h]
0x140001297  mov     [rbx+18h], rbp
0x14000129b  lea     rcx, EmergencyWorkQueue; Queue
0x1400012a2  mov     [rbx+10h], r15
0x1400012a6  mov     rdx, rbx; Entry
0x1400012a9  mov     [rbx+20h], rdi
0x1400012ad  mov     [rbx+8], rbx
0x1400012b1  mov     [rbx], rbx
0x1400012b4  call    cs:__imp_KeInsertQueue
0x1400012bb  nop     dword ptr [rax+rax+00h]
0x1400012c0  jmp     loc_140001235
```
