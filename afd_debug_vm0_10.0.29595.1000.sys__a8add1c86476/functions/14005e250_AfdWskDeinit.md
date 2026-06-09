# AfdWskDeinit

- ea: `0x14005e250`
- end: `0x14005e350`
- name: `AfdWskDeinit`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14005e250`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e318`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e32b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e318`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14005e32b`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005e33e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005e33e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005e26a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14005e26a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e2ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e2bc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e2ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e2bc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e282`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005e282`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e2df`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e2f2`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e305`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e2df`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e2f2`
- `NETIO!NetioShutdownWorkQueue` at `0x14005e305`

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
0x14005e250  sub     rsp, 48h
0x14005e254  mov     rcx, cs:AfdGlobalData; Resource
0x14005e25b  xorps   xmm0, xmm0
0x14005e25e  xor     eax, eax
0x14005e260  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x14005e265  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x14005e26a  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14005e271  nop     dword ptr [rax+rax+00h]
0x14005e276  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x14005e27b  lea     rcx, AfdWskClientSpinLock; SpinLock
0x14005e282  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005e289  nop     dword ptr [rax+rax+00h]
0x14005e28e  lea     rax, AfdWskClientListHead
0x14005e295  mov     cs:qword_140087BB8, 0
0x14005e2a0  cmp     cs:AfdWskClientListHead, rax
0x14005e2a7  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x14005e2ac  jz      short loc_14005E2BC
0x14005e2ae  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e2b5  nop     dword ptr [rax+rax+00h]
0x14005e2ba  jmp     short loc_14005E337
0x14005e2bc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e2c3  nop     dword ptr [rax+rax+00h]
0x14005e2c8  cmp     cs:AfdWskInitialized, 0
0x14005e2cf  jz      short loc_14005E337
0x14005e2d1  lea     rcx, WskTdiWQEndpointCreate
0x14005e2d8  mov     cs:AfdWskInitialized, 0
0x14005e2df  call    cs:__imp_NetioShutdownWorkQueue
0x14005e2e6  nop     dword ptr [rax+rax+00h]
0x14005e2eb  lea     rcx, WskTdiWQEndpointBind
0x14005e2f2  call    cs:__imp_NetioShutdownWorkQueue
0x14005e2f9  nop     dword ptr [rax+rax+00h]
0x14005e2fe  lea     rcx, WskTdiWQEndpointClose
0x14005e305  call    cs:__imp_NetioShutdownWorkQueue
0x14005e30c  nop     dword ptr [rax+rax+00h]
0x14005e311  lea     rcx, Lookaside; Lookaside
0x14005e318  call    cs:__imp_ExDeleteNPagedLookasideList
0x14005e31f  nop     dword ptr [rax+rax+00h]
0x14005e324  lea     rcx, stru_1400877C0; Lookaside
0x14005e32b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14005e332  nop     dword ptr [rax+rax+00h]
0x14005e337  mov     rcx, cs:AfdGlobalData; Resource
0x14005e33e  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005e345  nop     dword ptr [rax+rax+00h]
0x14005e34a  add     rsp, 48h
0x14005e34e  retn
```
