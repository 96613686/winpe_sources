# HCI_ProcessNewEnumerator(HCI_INTERFACE *,_BTH_ENUMERATOR_INTERFACE *,_ENUMERATOR_INFO *,PDO_EXTENSION *)

- ea: `0x140063970`
- end: `0x140063d54`
- name: `?HCI_ProcessNewEnumerator@@YAJPEAUHCI_INTERFACE@@PEAU_BTH_ENUMERATOR_INTERFACE@@PEAU_ENUMERATOR_INFO@@PEAUPDO_EXTENSION@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _BTH_ENUMERATOR_INTERFACE *, struct _ENUMERATOR_INFO *, struct PDO_EXTENSION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1401e2610`

## callees

- `0x140005608`
- `0x140005c04`
- `0x140059630`
- `0x14005f46c`
- `0x140063970`
- `0x14013e364`
- `0x140161a44`
- `0x140161d7c`
- `0x140165540`
- `0x140165580`
- `0x1401de370`
- `0x1401e629c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063c4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063c4a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140063c3e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140063c3e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140063c02`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140063c02`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063bec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140063bec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400639c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063c75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400639c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140063c75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063bd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063cd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063bd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140063cd0`

## pseudocode

```c

```
