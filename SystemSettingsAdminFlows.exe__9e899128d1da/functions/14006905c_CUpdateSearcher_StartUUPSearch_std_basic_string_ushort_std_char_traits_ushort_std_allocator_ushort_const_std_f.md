# CUpdateSearcher::StartUUPSearch(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (ATL::CComPtr<IUpdateCollection> &,long)> const &,CUpdateSearcher::SEARCH_TYPE)

- ea: `0x14006905c`
- end: `0x1400692f2`
- name: `?StartUUPSearch@CUpdateSearcher@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AXAEAV?$CComPtr@UIUpdateCollection@@@ATL@@J@Z@3@W4SEARCH_TYPE@1@@Z`
- size: `662`
- prototype: `__int64 __fastcall(CUpdateSearcher *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400415ac`

## callees

- `0x140005f30`
- `0x140006d1c`
- `0x14002a360`
- `0x14003aed0`
- `0x1400414e8`
- `0x1400430c0`
- `0x140059d0c`
- `0x14005fdd0`
- `0x14006881c`
- `0x140068960`
- `0x140068a24`
- `0x140068bf4`
- `0x140068d18`
- `0x140069020`
- `0x14006905c`
- `0x1400693f8`
- `0x14007d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400690e0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400692a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400690e0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400692a6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140069279`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400692b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140069279`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400692b7`
- `OLEAUT32!__imp_VariantInit` at `0x1400690be`
- `OLEAUT32!__imp_VariantInit` at `0x1400690be`

## pseudocode

```c

```
