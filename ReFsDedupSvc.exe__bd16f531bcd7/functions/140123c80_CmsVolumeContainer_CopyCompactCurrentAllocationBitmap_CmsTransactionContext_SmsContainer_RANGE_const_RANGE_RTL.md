# CmsVolumeContainer::CopyCompactCurrentAllocationBitmap(CmsTransactionContext *,SmsContainer *,_RANGE const &,_RANGE *,_RTL_BITMAP *,ulong *)

- ea: `0x140123c80`
- end: `0x140123f08`
- name: `?CopyCompactCurrentAllocationBitmap@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@AEBU_RANGE@@PEAU4@PEAU_RTL_BITMAP@@PEAK@Z`
- size: `648`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, struct SmsContainer *, const struct _RANGE *, struct _RANGE *, struct _RTL_BITMAP *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140122354`
- `0x140123664`

## callees

- `0x140081bf4`
- `0x140082f98`
- `0x1400a9b80`
- `0x1400c323c`
- `0x140123c80`

## import_xrefs

- `ntdll!RtlSetAllBits` at `0x140123e5c`
- `ntdll!RtlSetAllBits` at `0x140123e5c`
- `ntdll!RtlClearBit` at `0x140123ea8`
- `ntdll!RtlClearBit` at `0x140123ea8`
- `ntdll!RtlTestBit` at `0x140123e12`
- `ntdll!RtlTestBit` at `0x140123e7b`
- `ntdll!RtlTestBit` at `0x140123e91`
- `ntdll!RtlTestBit` at `0x140123e12`
- `ntdll!RtlTestBit` at `0x140123e7b`
- `ntdll!RtlTestBit` at `0x140123e91`
- `ntdll!RtlInitializeBitMap` at `0x140123d29`
- `ntdll!RtlInitializeBitMap` at `0x140123d80`
- `ntdll!RtlInitializeBitMap` at `0x140123d29`
- `ntdll!RtlInitializeBitMap` at `0x140123d80`

## pseudocode

```c

```
