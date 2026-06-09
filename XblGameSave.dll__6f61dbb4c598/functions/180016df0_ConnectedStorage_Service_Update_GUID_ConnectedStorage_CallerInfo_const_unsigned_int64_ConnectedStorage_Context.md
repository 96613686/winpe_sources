# ConnectedStorage::Service::Update(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::vector<ConnectedStorage::UpdateDesc,std::allocator<ConnectedStorage::UpdateDesc>> &&,std::vector<ConnectedStorage::SimpleHStringWrapper,std::allocator<ConnectedStorage::SimpleHStringWrapper>> &&,ISequentialStream *,uint,IStorageOperationHandler *)

- ea: `0x180016df0`
- end: `0x180016fa4`
- name: `?Update@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@4$$QEAV?$vector@UUpdateDesc@ConnectedStorage@@V?$allocator@UUpdateDesc@ConnectedStorage@@@std@@@std@@$$QEAV?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@8@PEAUISequentialStream@@IPEAUIStorageOperationHandler@@@Z`
- size: `436`
- prototype: `__int64 __usercall@<rax>(struct ConnectedStorage::Mutex *@<rcx>, struct ConnectedStorage::ContextDesc *, __int64, __int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180025610`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000ffbc`
- `0x180010f28`
- `0x1800113bc`
- `0x180012278`
- `0x180012e34`
- `0x180012e64`
- `0x180012ed8`
- `0x180016df0`
- `0x180016fac`
- `0x180027d6c`
- `0x180034dc8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f8e`

## string_xrefs

- `0x180016e28`: `Container::Update: handler`
- `0x180016e4c`: `Container::Update: invalid container name`

## pseudocode

```c

```
