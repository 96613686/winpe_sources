# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x180030054`
- end: `0x1800302bd`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033150`

## callees

- `0x180018f20`
- `0x1800237e8`
- `0x18002b438`
- `0x180030054`
- `0x1800359ac`
- `0x180036084`
- `0x180039a5a`
- `0x180039a72`
- `0x18003d5c8`
- `0x180059235`

## import_xrefs

- `ntdll!_wcslwr` at `0x1800301dd`
- `ntdll!_wcslwr` at `0x1800301dd`
- `ntdll!ZwClose` at `0x180030100`
- `ntdll!ZwClose` at `0x18003028e`
- `ntdll!ZwClose` at `0x18003029d`
- `ntdll!ZwClose` at `0x180030100`
- `ntdll!ZwClose` at `0x18003028e`
- `ntdll!ZwClose` at `0x18003029d`
- `ntdll!ZwEnumerateKey` at `0x180030163`
- `ntdll!ZwEnumerateKey` at `0x180030163`
- `ntdll!RtlAllocateHeap` at `0x18003009c`
- `ntdll!RtlAllocateHeap` at `0x1800300c9`
- `ntdll!RtlAllocateHeap` at `0x18003009c`
- `ntdll!RtlAllocateHeap` at `0x1800300c9`

## string_xrefs

- `0x1800300da`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x1800301c2`: `ProfileImagePath`

## pseudocode

```c

```
