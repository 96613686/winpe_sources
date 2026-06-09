# WindowsWaitForThreadResult::WaitForResult(uint)

- ea: `0x1800a0980`
- end: `0x1800a0a67`
- name: `?WaitForResult@WindowsWaitForThreadResult@@UEAAJI@Z`
- size: `231`
- prototype: `int(WindowsWaitForThreadResult *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800a0980`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1801c1590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a09eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a09eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a0995`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a0995`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a09af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a09af`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a09e1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800a09e1`

## string_xrefs

- `0x1800a09fd`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800a0a2a`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`
- `0x1800a0a42`: `onecoreuap\shell\cloudstore\common\src\cloudstoreutilities.cpp`

## pseudocode

```c

```
