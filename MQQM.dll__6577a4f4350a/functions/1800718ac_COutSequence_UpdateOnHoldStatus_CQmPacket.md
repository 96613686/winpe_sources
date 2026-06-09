# COutSequence::UpdateOnHoldStatus(CQmPacket *)

- ea: `0x1800718ac`
- end: `0x180071a36`
- name: `?UpdateOnHoldStatus@COutSequence@@QEAAXPEAVCQmPacket@@@Z`
- size: `394`
- prototype: `void __fastcall(COutSequence *__hidden this, struct CQmPacket *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18006f3d0`
- `0x1800700a0`

## callees

- `0x18006efa0`
- `0x1800718ac`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!UnhandledExceptionFilter` at `0x180071a03`
- `KERNEL32!UnhandledExceptionFilter` at `0x180071a03`
- `ntdll!NtDeviceIoControlFile` at `0x180071956`
- `ntdll!NtDeviceIoControlFile` at `0x18007199a`
- `ntdll!NtDeviceIoControlFile` at `0x180071956`
- `ntdll!NtDeviceIoControlFile` at `0x18007199a`

## pseudocode

```c

```
