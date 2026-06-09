# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18000bb80`
- end: `0x18000c1b1`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `1585`
- prototype: `__int64 __fastcall(struct _PII_FILTER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cde8`

## callees

- `0x18000b058`
- `0x18000bb80`
- `0x18000c470`
- `0x180361d9c`
- `0x1803a4cb0`
- `0x1803a5744`
- `0x1803a5750`
- `0x1803a57e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bf61`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000bf61`
- `ntdll!RtlInitUnicodeString` at `0x18000bdd2`
- `ntdll!RtlInitUnicodeString` at `0x18000bdd2`
- `ntdll!RtlAllocateHeap` at `0x18000bbda`
- `ntdll!RtlAllocateHeap` at `0x18000bc0c`
- `ntdll!RtlAllocateHeap` at `0x18000be26`
- `ntdll!RtlAllocateHeap` at `0x18000bbda`
- `ntdll!RtlAllocateHeap` at `0x18000bc0c`
- `ntdll!RtlAllocateHeap` at `0x18000be26`
- `ntdll!ZwEnumerateKey` at `0x18000bd05`
- `ntdll!ZwEnumerateKey` at `0x18000bd05`
- `ntdll!ZwClose` at `0x18000bc99`
- `ntdll!ZwClose` at `0x18000c02b`
- `ntdll!ZwClose` at `0x18000c1a6`
- `ntdll!ZwClose` at `0x18000bc99`
- `ntdll!ZwClose` at `0x18000c02b`
- `ntdll!ZwClose` at `0x18000c1a6`
- `ntdll!ZwOpenKey` at `0x18000bc7d`
- `ntdll!ZwOpenKey` at `0x18000bda9`
- `ntdll!ZwOpenKey` at `0x18000bc7d`
- `ntdll!ZwOpenKey` at `0x18000bda9`
- `ntdll!ZwQueryValueKey` at `0x18000bdf5`
- `ntdll!ZwQueryValueKey` at `0x18000be58`
- `ntdll!ZwQueryValueKey` at `0x18000bdf5`
- `ntdll!ZwQueryValueKey` at `0x18000be58`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000bc38`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000bd6c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000bc38`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000bd6c`
- `ntdll!RtlFreeHeap` at `0x18000bcba`
- `ntdll!RtlFreeHeap` at `0x18000beaf`
- `ntdll!RtlFreeHeap` at `0x18000bfb7`
- `ntdll!RtlFreeHeap` at `0x18000bfcf`
- `ntdll!RtlFreeHeap` at `0x18000c014`
- `ntdll!RtlFreeHeap` at `0x18000c102`
- `ntdll!RtlFreeHeap` at `0x18000bcba`
- `ntdll!RtlFreeHeap` at `0x18000beaf`
- `ntdll!RtlFreeHeap` at `0x18000bfb7`
- `ntdll!RtlFreeHeap` at `0x18000bfcf`
- `ntdll!RtlFreeHeap` at `0x18000c014`
- `ntdll!RtlFreeHeap` at `0x18000c102`

## string_xrefs

- `0x18000bdbb`: `ProfileImagePath`
- `0x18000bc29`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x18000c07d`: `AslRegistryGetString`
- `0x18000c0a4`: `AslRegistryGetString`
- `0x18000c0cb`: `AslRegistryGetString`
- `0x18000c168`: `AslRegistryGetString`
- `0x18000c18b`: `AslRegistryGetString`
- `0x18000c11e`: `AslRegistryOpenKey`
- `0x18000c10d`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18000c145`: `AslRegistryOpenSubKey`
- `0x18000c134`: `AslRegistryOpenSubKey passed bad Path [%x]`

## pseudocode

```c

```
