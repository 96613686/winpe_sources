# CmsHashTable::DeleteFromIndex(CmsTransactionCore *,unsigned __int64,long (*)(CmsTransactionCore *,_CmsRow *,void *),void *,EmsHashTableFlags,_SmsQuickIndex *,_SmsHashOverflow * *)

- ea: `0x14011a2ec`
- end: `0x14011a460`
- name: `?DeleteFromIndex@CmsHashTable@@QEAAJPEAVCmsTransactionCore@@_KP6AJ0PEAU_CmsRow@@PEAX@Z3W4EmsHashTableFlags@@PEAU_SmsQuickIndex@@PEAPEAU_SmsHashOverflow@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14008c8a0`
- `0x1400a1708`
- `0x1400d7678`
- `0x1400ee984`
- `0x1400f233c`
- `0x1400f2524`
- `0x1400f4c94`
- `0x14011ae2c`

## callees

- `0x14008356c`
- `0x14011a2ec`
- `0x14011a468`
- `0x14011a7a0`
- `0x14011ada0`
- `0x1401b9010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x14011a42f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14011a42f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14011a43d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14011a43d`
- `ntdll!RtlAcquireSRWLockShared` at `0x14011a333`
- `ntdll!RtlAcquireSRWLockShared` at `0x14011a333`

## pseudocode

```c

```
