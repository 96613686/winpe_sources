# AfdWskDeinit

- ea: `0x14005e0b0`
- end: `0x14005e1b0`
- name: `AfdWskDeinit`
- size: `256`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14005e0b0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e178`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e18b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e178`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e18b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005e19e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005e19e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005e0ca`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005e0ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e10e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e11c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e10e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e11c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e0e2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e0e2`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e13f`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e152`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e165`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e13f`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e152`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e165`

## pseudocode

```c
void AfdWskDeinit()
{
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
  KeAcquireInStackQueuedSpinLock(&AfdWskClientSpinLock, &LockHandle);
  qword_140087BB8 = 0;
  if ( (__int64 *)AfdWskClientListHead == &AfdWskClientListHead )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( AfdWskInitialized )
    {
      AfdWskInitialized = 0;
      NetioShutdownWorkQueue(WskTdiWQEndpointCreate);
      NetioShutdownWorkQueue(WskTdiWQEndpointBind);
      NetioShutdownWorkQueue(WskTdiWQEndpointClose);
      ExDeleteNPagedLookasideList(&Lookaside);
      ExDeleteNPagedLookasideList(&stru_1400877C0);
    }
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
}

```

## disassembly

```asm
0x14005e0b0  sub     rsp, 48h
0x14005e0b4  mov     rcx, cs:AfdGlobalData; Resource
0x14005e0bb  xorps   xmm0, xmm0
0x14005e0be  xor     eax, eax
0x14005e0c0  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14005e0c5  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14005e0ca  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14005e0d1  nop     dword ptr [rax+rax+00h]
0x14005e0d6  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14005e0db  lea     rcx, AfdWskClientSpinLock; SpinLock
0x14005e0e2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e0e9  nop     dword ptr [rax+rax+00h]
0x14005e0ee  lea     rax, AfdWskClientListHead
0x14005e0f5  mov     cs:qword_140087BB8, 0
0x14005e100  cmp     cs:AfdWskClientListHead, rax
0x14005e107  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005e10c  jz      short loc_14005E11C
0x14005e10e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e115  nop     dword ptr [rax+rax+00h]
0x14005e11a  jmp     short loc_14005E197
0x14005e11c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e123  nop     dword ptr [rax+rax+00h]
0x14005e128  cmp     cs:AfdWskInitialized, 0
0x14005e12f  jz      short loc_14005E197
0x14005e131  lea     rcx, WskTdiWQEndpointCreate
0x14005e138  mov     cs:AfdWskInitialized, 0
0x14005e13f  call    cs:__imp_NetioShutdownWorkQueue
0x14005e146  nop     dword ptr [rax+rax+00h]
0x14005e14b  lea     rcx, WskTdiWQEndpointBind
0x14005e152  call    cs:__imp_NetioShutdownWorkQueue
0x14005e159  nop     dword ptr [rax+rax+00h]
0x14005e15e  lea     rcx, WskTdiWQEndpointClose
0x14005e165  call    cs:__imp_NetioShutdownWorkQueue
0x14005e16c  nop     dword ptr [rax+rax+00h]
0x14005e171  lea     rcx, Lookaside; Lookaside
0x14005e178  call    cs:__imp_ExDeleteNPagedLookasideList
0x14005e17f  nop     dword ptr [rax+rax+00h]
0x14005e184  lea     rcx, stru_1400877C0; Lookaside
0x14005e18b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14005e192  nop     dword ptr [rax+rax+00h]
0x14005e197  mov     rcx, cs:AfdGlobalData; Resource
0x14005e19e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005e1a5  nop     dword ptr [rax+rax+00h]
0x14005e1aa  add     rsp, 48h
0x14005e1ae  retn
```
