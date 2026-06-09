# HCI_EnumerateLocalServiceClasses

- ea: `0x1401de3d0`
- end: `0x1401de53e`
- name: `HCI_EnumerateLocalServiceClasses`
- size: `366`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1401de328`
- `0x1401de370`
- `0x1401de94c`

## callees

- `0x140165540`
- `0x140165580`
- `0x1401de3d0`
- `0x140209168`
- `0x1402091b8`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x1401de465`
- `ntoskrnl!ZwEnumerateKey` at `0x1401de465`
- `ntoskrnl!RtlGUIDFromString` at `0x1401de4c8`
- `ntoskrnl!RtlGUIDFromString` at `0x1401de4c8`
- `ntoskrnl!ZwClose` at `0x1401de4f2`
- `ntoskrnl!ZwClose` at `0x1401de50d`
- `ntoskrnl!ZwClose` at `0x1401de4f2`
- `ntoskrnl!ZwClose` at `0x1401de50d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401de4b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401de4b4`

## string_xrefs

- `0x1401de41f`: `LocalServices`

## pseudocode

```c

```
