# AppReadiness::Groups::InstallPackage::CreateStoreFlow(void)

- ea: `0x180036270`
- end: `0x180036483`
- name: `?CreateStoreFlow@InstallPackage@Groups@AppReadiness@@AEAAXXZ`
- size: `531`
- prototype: `void __fastcall(AppReadiness::Groups::InstallPackage *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x180004470`

## callees

- `0x180002958`
- `0x180005270`
- `0x18000a470`
- `0x180027a4c`
- `0x180036270`
- `0x18003648c`
- `0x180036550`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036381`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036381`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036367`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036367`

## string_xrefs

- `0x1800363c8`: `onecoreuap\shell\appreadiness\src\groups\installpackage.cpp`
- `0x1800363db`: `MakeAndInitialize<Tasks::StoreInstall>(&installTask, GetUser(), packageInfo)`
- `0x1800363d4`: `AppReadiness::Groups::InstallPackage::CreateStoreFlow`

## pseudocode

```c

```
