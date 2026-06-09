# CDbOperationManager::IsFatalJetError(long,int *)

- ea: `0x1800ea298`
- end: `0x1800ea50a`
- name: `?IsFatalJetError@CDbOperationManager@@AEAAHJPEAH@Z`
- size: `626`
- prototype: `__int64 __fastcall(CDbOperationManager *__hidden this, int, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800e8adc`
- `0x1800e9a58`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x18002dad0`
- `0x180041984`
- `0x1800e8120`
- `0x1800e8410`
- `0x1800ea298`
- `0x1800eba68`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800ea44f`
- `KERNEL32!CreateFileW` at `0x1800ea44f`
- `KERNEL32!CloseHandle` at `0x1800ea45e`
- `KERNEL32!CloseHandle` at `0x1800ea45e`
- `KERNEL32!GetLastError` at `0x1800ea466`
- `KERNEL32!GetLastError` at `0x1800ea466`
- `ESENT!JetGetErrorInfoW` at `0x1800ea320`
- `ESENT!JetGetErrorInfoW` at `0x1800ea320`

## pseudocode

```c

```
