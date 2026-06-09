# Appx::Packaging::BlockMap::AppxBlockMapBlock::ValidateBlockHash(Common::AutoPtr<Appx::Packaging::HashEngine,&Common::AutoPtrDeallocate<Appx::Packaging::HashEngine>(Appx::Packaging::HashEngine *)> &,uint,uchar const *)

- ea: `0x18004c180`
- end: `0x18004c468`
- name: `?ValidateBlockHash@AppxBlockMapBlock@BlockMap@Packaging@Appx@@QEAAJAEAV?$AutoPtr@VHashEngine@Packaging@Appx@@$1??$AutoPtrDeallocate@VHashEngine@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@IPEBE@Z`
- size: `744`
- prototype: `__int64(__int64, _QWORD *, ULONG, ...)`
- caller_count: `11`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004c02c`
- `0x1800625e4`
- `0x1800628bc`
- `0x180062cb0`
- `0x180068970`
- `0x180068c10`
- `0x180078724`
- `0x1800788e0`
- `0x18007c6dc`
- `0x1800cda6c`
- `0x1800e6db0`

## callees

- `0x1800133fc`
- `0x18004c180`
- `0x18005309c`
- `0x180071f50`
- `0x1800cda48`
- `0x1800e6c0c`
- `0x1800e6c34`
- `0x1801051d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c32c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c370`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c3ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c32c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c370`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004c3ac`
- `ntdll!RtlNtStatusToDosError` at `0x18004c31e`
- `ntdll!RtlNtStatusToDosError` at `0x18004c362`
- `ntdll!RtlNtStatusToDosError` at `0x18004c31e`
- `ntdll!RtlNtStatusToDosError` at `0x18004c362`
- `bcrypt!BCryptHashData` at `0x18004c20f`
- `bcrypt!BCryptHashData` at `0x18004c20f`
- `bcrypt!BCryptFinishHash` at `0x18004c25c`
- `bcrypt!BCryptFinishHash` at `0x18004c25c`
- `bcrypt!BCryptDestroyHash` at `0x18004c28c`
- `bcrypt!BCryptDestroyHash` at `0x18004c28c`
- `bcrypt!BCryptCreateHash` at `0x18004c1ed`
- `bcrypt!BCryptCreateHash` at `0x18004c1ed`

## pseudocode

```c

```
