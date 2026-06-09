# SMPInt_RegUpdateLEMasterIRKOverride(_SMP_INTERFACE *)

- ea: `0x1401f43cc`
- end: `0x1401f459f`
- name: `?SMPInt_RegUpdateLEMasterIRKOverride@@YAJPEAU_SMP_INTERFACE@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct _SMP_INTERFACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140075de0`

## callees

- `0x140005608`
- `0x140005690`
- `0x140165540`
- `0x1401f43cc`
- `0x140209168`
- `0x1402093a8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f451b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401f451b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f450f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1401f450f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f446b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1401f446b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f4458`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401f4458`
- `ntoskrnl!ZwClose` at `0x1401f44f9`
- `ntoskrnl!ZwClose` at `0x1401f44f9`

## string_xrefs

- `0x1401f44a3`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`

## pseudocode

```c

```
