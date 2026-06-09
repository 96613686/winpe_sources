# HciDebugMode::ExtendDebugModeExpiration(void)

- ea: `0x14001bfec`
- end: `0x14001c0f2`
- name: `?ExtendDebugModeExpiration@HciDebugMode@@QEAAXXZ`
- size: `262`
- prototype: `void __fastcall(HciDebugMode *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1401d239c`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x14000f27c`
- `0x14000fab4`
- `0x14001bfec`
- `0x14001c348`
- `0x14001c3e4`
- `0x140209168`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14001c0a6`
- `ntoskrnl!ZwSetValueKey` at `0x14001c0a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c078`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001c078`

## string_xrefs

- `0x14001c054`: `\Registry\Machine\System\CurrentControlSet\Services\BTHPORT\Parameters`

## pseudocode

```c

```
