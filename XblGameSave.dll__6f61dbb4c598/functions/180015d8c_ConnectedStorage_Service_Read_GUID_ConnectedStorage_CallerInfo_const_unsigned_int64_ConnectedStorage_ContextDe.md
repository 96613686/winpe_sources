# ConnectedStorage::Service::Read(_GUID,ConnectedStorage::CallerInfo const &,unsigned __int64,ConnectedStorage::ContextDesc const &,ConnectedStorage::SimpleHStringWrapper const &,std::vector<ConnectedStorage::SimpleHStringWrapper,std::allocator<ConnectedStorage::SimpleHStringWrapper>> &&,IStorageReadHandler *)

- ea: `0x180015d8c`
- end: `0x180015ed5`
- name: `?Read@Service@ConnectedStorage@@QEAAXU_GUID@@AEBVCallerInfo@2@_KAEBVContextDesc@2@AEBVSimpleHStringWrapper@2@$$QEAV?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@PEAUIStorageReadHandler@@@Z`
- size: `329`
- prototype: `__int64 __usercall@<rax>(struct ConnectedStorage::Mutex *@<rcx>, struct ConnectedStorage::ContextDesc *, struct ConnectedStorage::SimpleHStringWrapper *, __int64, HSTRING newString)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180023e80`

## callees

- `0x18000aae4`
- `0x18000cb9c`
- `0x18000ff00`
- `0x180010f28`
- `0x1800113bc`
- `0x180011b94`
- `0x180012278`
- `0x180015d8c`
- `0x180016fac`
- `0x180027d6c`
- `0x1800344b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015eb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015eb7`

## string_xrefs

- `0x180015dc7`: `Container::Read: handler`
- `0x180015deb`: `Container::Read: invalid container name`

## pseudocode

```c

```
