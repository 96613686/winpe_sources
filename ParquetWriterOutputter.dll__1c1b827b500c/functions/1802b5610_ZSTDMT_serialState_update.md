# ZSTDMT_serialState_update

- ea: `0x1802b5610`
- end: `0x1802b57d0`
- name: `ZSTDMT_serialState_update`
- size: `448`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1802b31d0`

## callees

- `0x1802abbb0`
- `0x1802b26a0`
- `0x1802b5610`
- `0x1802e7160`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1802b5638`
- `KERNEL32!EnterCriticalSection` at `0x1802b5726`
- `KERNEL32!EnterCriticalSection` at `0x1802b5638`
- `KERNEL32!EnterCriticalSection` at `0x1802b5726`
- `KERNEL32!LeaveCriticalSection` at `0x1802b5755`
- `KERNEL32!LeaveCriticalSection` at `0x1802b5791`
- `KERNEL32!LeaveCriticalSection` at `0x1802b5755`
- `KERNEL32!LeaveCriticalSection` at `0x1802b5791`
- `KERNEL32!WakeConditionVariable` at `0x1802b5748`
- `KERNEL32!WakeConditionVariable` at `0x1802b5748`
- `KERNEL32!WakeAllConditionVariable` at `0x1802b5788`
- `KERNEL32!WakeAllConditionVariable` at `0x1802b5788`
- `KERNEL32!SleepConditionVariableCS` at `0x1802b565d`
- `KERNEL32!SleepConditionVariableCS` at `0x1802b565d`

## pseudocode

```c

```
