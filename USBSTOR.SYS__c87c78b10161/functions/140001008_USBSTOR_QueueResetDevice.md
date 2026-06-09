# USBSTOR_QueueResetDevice

- ea: `0x140001008`
- end: `0x140001128`
- name: `USBSTOR_QueueResetDevice`
- size: `288`
- prototype: `__int64 __fastcall(PVOID Object, PVOID Context)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x140001de0`
- `0x1400023b0`
- `0x140002a70`
- `0x140002fd0`
- `0x140003e10`
- `0x140007900`
- `0x1400094b0`
- `0x140009860`
- `0x140009cb0`
- `0x14000a500`
- `0x14000c120`
- `0x14000d8cc`
- `0x14000f640`
- `0x14000fafc`
- `0x1400124f0`

## callees

- `0x140001008`
- `0x140003630`
- `0x14000ca68`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001083`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001083`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001112`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001112`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001063`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001063`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400010a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400010f6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400010a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400010f6`

## pseudocode

```c
void __fastcall USBSTOR_QueueResetDevice(_QWORD *Object, PVOID Context)
{
  __int64 v4; // rbx
  int v5; // eax
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  USBSTOR_LogEntry(1146311249, Object, 0, 0);
  v4 = Object[8];
  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 1832), USBSTOR_ResetDeviceWorkItem, File, 1u, 0x20u) >= 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 144), &LockHandle);
    v5 = *(_DWORD *)(v4 + 128);
    if ( (v5 & 8) != 0 )
    {
      USBSTOR_LogEntry(1146311246, Object, *(unsigned int *)(v4 + 128), 0);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 1832), USBSTOR_ResetDeviceWorkItem, 0x20u);
    }
    else
    {
      *(_DWORD *)(v4 + 128) = v5 | 8;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      USBSTOR_QueueWorkItem(
        Object,
        *(PLIST_ENTRY *)(v4 + 368),
        (PIO_WORKITEM_ROUTINE_EX)USBSTOR_ResetDeviceWorkItem,
        Context,
        *(_BYTE *)(v4 + 1876) == 0);
    }
  }
}

```

## disassembly

```asm
0x140001008  push    rbx
0x14000100a  push    rbp
0x14000100b  push    rsi
0x14000100c  push    rdi
0x14000100d  sub     rsp, 58h
0x140001011  mov     rbp, rdx
0x140001014  mov     rdi, rcx
0x140001017  mov     rdx, rcx
0x14000101a  xorps   xmm0, xmm0
0x14000101d  xor     eax, eax
0x14000101f  mov     ecx, 44535251h
0x140001024  xor     r9d, r9d
0x140001027  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000102c  xor     r8d, r8d
0x14000102f  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140001034  call    USBSTOR_LogEntry
0x140001039  mov     rbx, [rdi+40h]
0x14000103d  lea     r8, File; File
0x140001044  mov     r9d, 1; Line
0x14000104a  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140001052  lea     rdx, USBSTOR_ResetDeviceWorkItem; Tag
0x140001059  lea     rsi, [rbx+728h]
0x140001060  mov     rcx, rsi; RemoveLock
0x140001063  call    cs:__imp_IoAcquireRemoveLockEx
0x14000106a  nop     dword ptr [rax+rax+00h]
0x14000106f  test    eax, eax
0x140001071  js      loc_14000111E
0x140001077  lea     rcx, [rbx+90h]; SpinLock
0x14000107e  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140001083  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000108a  nop     dword ptr [rax+rax+00h]
0x14000108f  mov     eax, [rbx+80h]
0x140001095  test    al, 8
0x140001097  jnz     short loc_1400010DE
0x140001099  or      eax, 8
0x14000109c  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400010a1  mov     [rbx+80h], eax
0x1400010a7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400010ae  nop     dword ptr [rax+rax+00h]
0x1400010b3  cmp     byte ptr [rbx+754h], 0
0x1400010ba  lea     r8, USBSTOR_ResetDeviceWorkItem; WorkerRoutine
0x1400010c1  mov     rdx, [rbx+170h]; Entry
0x1400010c8  mov     rcx, rdi; Object
0x1400010cb  setz    al
0x1400010ce  mov     [rsp+78h+var_50], al; char
0x1400010d2  mov     qword ptr [rsp+78h+RemlockSize], rbp; Context
0x1400010d7  call    USBSTOR_QueueWorkItem
0x1400010dc  jmp     short loc_14000111E
0x1400010de  mov     r8, rax
0x1400010e1  xor     r9d, r9d
0x1400010e4  mov     rdx, rdi
0x1400010e7  mov     ecx, 4453524Eh
0x1400010ec  call    USBSTOR_LogEntry
0x1400010f1  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400010f6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400010fd  nop     dword ptr [rax+rax+00h]
0x140001102  mov     r8d, 20h ; ' '; RemlockSize
0x140001108  lea     rdx, USBSTOR_ResetDeviceWorkItem; Tag
0x14000110f  mov     rcx, rsi; RemoveLock
0x140001112  call    cs:__imp_IoReleaseRemoveLockEx
0x140001119  nop     dword ptr [rax+rax+00h]
0x14000111e  add     rsp, 58h
0x140001122  pop     rdi
0x140001123  pop     rsi
0x140001124  pop     rbp
0x140001125  pop     rbx
0x140001126  retn
```
