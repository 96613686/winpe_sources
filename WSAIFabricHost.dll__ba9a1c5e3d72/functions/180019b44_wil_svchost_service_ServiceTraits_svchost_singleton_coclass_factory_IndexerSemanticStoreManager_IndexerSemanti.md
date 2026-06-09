# wil::svchost_service<ServiceTraits,svchost_singleton_coclass_factory<IndexerSemanticStoreManager,IndexerSemanticStoreManagerImpl>,svchost_singleton_coclass_factory<IndexerSemanticSearchServices,IndexerSemanticSearchServicesImpl>,svchost_singleton_coclass_factory<SessionManagerBroker,SessionManagerBrokerImpl>,svchost_singleton_coclass_factory<AIFabricResourceManager,AIFabricResourceManagerImpl>>::stop(ulong)

- ea: `0x180019b44`
- end: `0x180019c35`
- name: `?stop@?$svchost_service@UServiceTraits@@U?$svchost_singleton_coclass_factory@VIndexerSemanticStoreManager@@UIndexerSemanticStoreManagerImpl@@@@U?$svchost_singleton_coclass_factory@VIndexerSemanticSearchServices@@UIndexerSemanticSearchServicesImpl@@@@U?$svchost_singleton_coclass_factory@VSessionManagerBroker@@USessionManagerBrokerImpl@@@@U?$svchost_singleton_coclass_factory@VAIFabricResourceManager@@UAIFabricResourceManagerImpl@@@@@wil@@AEAAXK@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011af0`
- `0x1800801f6`

## callees

- `0x180005140`
- `0x18000c018`
- `0x180014754`
- `0x18001896c`
- `0x180019b44`
- `0x180019f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019ba9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019b7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019ba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b9d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180019b73`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180019b73`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180019bbb`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180019bbb`

## string_xrefs

- `0x180019c23`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180019bcd`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c

```
