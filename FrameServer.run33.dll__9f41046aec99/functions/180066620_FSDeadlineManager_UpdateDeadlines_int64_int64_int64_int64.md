# FSDeadlineManager::UpdateDeadlines(__int64,__int64,__int64,__int64)

- ea: `0x180066620`
- end: `0x180066794`
- name: `?UpdateDeadlines@FSDeadlineManager@@QEAAJ_J000@Z`
- size: `372`
- prototype: `__int64 __usercall@<rax>(FSDeadlineManager *__hidden this@<rcx>, __int64@<rdx>, __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800431a0`

## callees

- `0x180004d68`
- `0x180004dd4`
- `0x180066314`
- `0x180066434`
- `0x180066620`
- `0x18006679c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006676e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006676e`
- `RTWorkQ!RtwqSetDeadline2` at `0x180066646`
- `RTWorkQ!RtwqSetDeadline2` at `0x18006669d`
- `RTWorkQ!RtwqSetDeadline2` at `0x180066646`
- `RTWorkQ!RtwqSetDeadline2` at `0x18006669d`

## pseudocode

```c

```
