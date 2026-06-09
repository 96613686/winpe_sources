# BiLoadHive

- ea: `0x1801c91c4`
- end: `0x1801c95cd`
- name: `BiLoadHive`
- size: `1033`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1801c500c`

## callees

- `0x180008570`
- `0x1801c91c4`
- `0x1801c979c`
- `0x1801ca054`
- `0x1801ca330`
- `0x1801ce028`
- `0x1801ce244`
- `0x18021f010`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1801c94ef`
- `ntdll!ZwOpenKey` at `0x1801c94ef`
- `ntdll!ZwClose` at `0x1801c9552`
- `ntdll!ZwClose` at `0x1801c9552`
- `ntdll!RtlInitUnicodeString` at `0x1801c92ab`
- `ntdll!RtlInitUnicodeString` at `0x1801c9368`
- `ntdll!RtlInitUnicodeString` at `0x1801c93a9`
- `ntdll!RtlInitUnicodeString` at `0x1801c92ab`
- `ntdll!RtlInitUnicodeString` at `0x1801c9368`
- `ntdll!RtlInitUnicodeString` at `0x1801c93a9`
- `ntdll!ZwQueryAttributesFile` at `0x1801c92fb`
- `ntdll!ZwQueryAttributesFile` at `0x1801c92fb`
- `ntdll!ZwLoadKey` at `0x1801c9497`
- `ntdll!ZwLoadKey` at `0x1801c9497`
- `ntdll!ZwUnloadKey` at `0x1801c9513`
- `ntdll!ZwUnloadKey` at `0x1801c9513`

## string_xrefs

- `0x1801c9322`: `\Registry\Machine`
- `0x1801c933d`: `\Registry\Machine`
- `0x1801c9409`: `\Registry\Machine`
- `0x1801c9344`: `Failed open key %ws. Status: %x`
- `0x1801c9530`: `Failed open newly loaded key %ws. Flags: 0x%x Status: %x`

## pseudocode

```c

```
