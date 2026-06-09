# RIMReadInput

- ea: `0x14006fb90`
- end: `0x14007037c`
- name: `RIMReadInput`
- size: `2028`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14006f7c0`
- `0x140157d10`

## callees

- `0x14006fb90`
- `0x140070384`
- `0x1400704e0`
- `0x140070758`
- `0x1400707b0`
- `0x140071258`
- `0x140071828`
- `0x1400718f0`
- `0x140076420`
- `0x1401aa4fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14007025c`
- `ntoskrnl!ZwClose` at `0x14007025c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006fcc8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006fdb7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006fcc8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006fdb7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fcb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fda2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fcb6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006fda2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ff28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ff4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ff28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006ff4a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ff1c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ff3e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ff1c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ff3e`
- `ntoskrnl!ExEventObjectType` at `0x14006fcfd`
- `ntoskrnl!ExEventObjectType` at `0x14006fd56`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14006fd75`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14006fd75`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x14006fc53`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006fc82`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006fd2b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006fc82`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006fd2b`
- `ntoskrnl!ObfDereferenceObject` at `0x14006fd8e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ff59`
- `ntoskrnl!ObfDereferenceObject` at `0x14007004a`
- `ntoskrnl!ObfDereferenceObject` at `0x14006fd8e`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ff59`
- `ntoskrnl!ObfDereferenceObject` at `0x14007004a`
- `WIN32K!W32GetUserSessionState` at `0x14006fbfa`
- `WIN32K!W32GetUserSessionState` at `0x14006fea3`
- `WIN32K!W32GetUserSessionState` at `0x14006ffc0`
- `WIN32K!W32GetUserSessionState` at `0x14007015e`
- `WIN32K!W32GetUserSessionState` at `0x1400701a1`
- `WIN32K!W32GetUserSessionState` at `0x14007028a`
- `WIN32K!W32GetUserSessionState` at `0x14007032c`
- `WIN32K!W32GetUserSessionState` at `0x14006fbfa`
- `WIN32K!W32GetUserSessionState` at `0x14006fea3`
- `WIN32K!W32GetUserSessionState` at `0x14006ffc0`
- `WIN32K!W32GetUserSessionState` at `0x14007015e`
- `WIN32K!W32GetUserSessionState` at `0x1400701a1`
- `WIN32K!W32GetUserSessionState` at `0x14007028a`
- `WIN32K!W32GetUserSessionState` at `0x14007032c`

## pseudocode

```c

```
