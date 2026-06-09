# SecureInput::Manager::CreateSecureBuffer(_GUID const &,ulong,std::shared_ptr<SecureInput::Buffer> *)

- ea: `0x140002f40`
- end: `0x140003146`
- name: `?CreateSecureBuffer@Manager@SecureInput@@SAJAEBU_GUID@@KPEAV?$shared_ptr@VBuffer@SecureInput@@@std@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(unsigned __int64 *, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001a660`

## callees

- `0x140002f40`
- `0x140003150`
- `0x14000a2e4`
- `0x14000a420`
- `0x14000d640`
- `0x140011e58`
- `0x140013640`
- `0x14001bd40`
- `0x140062bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000303a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000303a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400030df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400030df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003118`

## string_xrefs

- `0x140002f99`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002fc3`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x140002fee`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`
- `0x1400030b5`: `onecore\ds\security\biometrics\service\trustlet\exe\secureinput.cpp`

## pseudocode

```c

```
