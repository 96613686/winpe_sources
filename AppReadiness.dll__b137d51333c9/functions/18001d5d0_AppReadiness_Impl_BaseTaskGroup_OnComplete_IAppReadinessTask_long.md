# AppReadiness::Impl::BaseTaskGroup::OnComplete(IAppReadinessTask *,long)

- ea: `0x18001d5d0`
- end: `0x18001da5e`
- name: `?OnComplete@BaseTaskGroup@Impl@AppReadiness@@UEAAJPEAUIAppReadinessTask@@J@Z`
- size: `1166`
- prototype: `int(AppReadiness::Impl::BaseTaskGroup *__hidden this, struct IAppReadinessTask *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d690`
- `0x18001d5d0`
- `0x18001da64`
- `0x18001dafc`
- `0x180027a4c`
- `0x180029a38`
- `0x18003ecb4`
- `0x180061f30`
- `0x18006213c`
- `0x180062238`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d764`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d764`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d723`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d723`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001da10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18001da10`

## string_xrefs

- `0x18001d61d`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x18001d630`: `taskInf->QueryInterface(task.GetAddressOf())`
- `0x18001d629`: `AppReadiness::Impl::BaseTaskGroup::OnComplete`

## pseudocode

```c

```
