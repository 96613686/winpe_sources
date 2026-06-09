# AfdCommonDelAddressHandler

- ea: `0x140003164`
- end: `0x14000332f`
- name: `AfdCommonDelAddressHandler`
- size: `459`
- prototype: `void __fastcall(__int64, __int64, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002d20`
- `0x140034100`

## callees

- `0x140002ad4`
- `0x140003164`
- `0x1400035c0`
- `0x1400036ac`
- `0x1400932cc`
- `0x140093a70`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000318d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14000318d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000322c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400032a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000322c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400032a8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400031a9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400031a9`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000323f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400032bb`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14000323f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400032bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003258`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003258`

## pseudocode

```c

```
