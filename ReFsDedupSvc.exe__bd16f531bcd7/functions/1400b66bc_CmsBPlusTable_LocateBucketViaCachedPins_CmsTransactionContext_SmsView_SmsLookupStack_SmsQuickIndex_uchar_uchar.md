# CmsBPlusTable::LocateBucketViaCachedPins(CmsTransactionContext *,SmsView *,SmsLookupStack *,_SmsQuickIndex *,uchar,uchar,long *,uchar *,CmsKeyRange *,SmsPage * *,_LCN_TUPLE *)

- ea: `0x1400b66bc`
- end: `0x1400b6a27`
- name: `?LocateBucketViaCachedPins@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEAUSmsLookupStack@@PEAU_SmsQuickIndex@@EEPEAJPEAEPEAVCmsKeyRange@@PEAPEAUSmsPage@@PEAT_LCN_TUPLE@@@Z`
- size: `875`
- prototype: `int(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct SmsView *, struct SmsLookupStack *, struct _SmsQuickIndex *, unsigned __int8, unsigned __int8, int *, unsigned __int8 *, struct CmsKeyRange *, struct SmsPage **, union _LCN_TUPLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400b2758`

## callees

- `0x1400afd24`
- `0x1400b06f4`
- `0x1400b135c`
- `0x1400b2254`
- `0x1400b66bc`
- `0x1400baa38`

## import_xrefs

- `ntdll!RtlTryAcquireSRWLockShared` at `0x1400b6788`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x1400b6788`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b67f0`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400b67f0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b69ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400b69ee`

## pseudocode

```c

```
