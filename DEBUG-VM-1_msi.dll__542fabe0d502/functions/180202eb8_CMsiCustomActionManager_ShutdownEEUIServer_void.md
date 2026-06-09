# CMsiCustomActionManager::ShutdownEEUIServer(void)

- ea: `0x180202eb8`
- end: `0x180202fce`
- name: `?ShutdownEEUIServer@CMsiCustomActionManager@@QEAAIXZ`
- size: `278`
- prototype: `unsigned int __fastcall(CMsiCustomActionManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1801739ac`
- `0x1801b2eb0`
- `0x1801c6bc0`

## callees

- `0x18009a1f8`
- `0x180202eb8`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180202fa9`
- `KERNEL32!CloseHandle` at `0x180202fa9`
- `KERNEL32!LeaveCriticalSection` at `0x180202fbd`
- `KERNEL32!LeaveCriticalSection` at `0x180202fbd`
- `KERNEL32!EnterCriticalSection` at `0x180202ece`
- `KERNEL32!EnterCriticalSection` at `0x180202ece`
- `USER32!MsgWaitForMultipleObjects` at `0x180202f98`
- `USER32!MsgWaitForMultipleObjects` at `0x180202f98`
- `USER32!PeekMessageW` at `0x180202f79`
- `USER32!PeekMessageW` at `0x180202f79`
- `USER32!TranslateMessage` at `0x180202f57`
- `USER32!TranslateMessage` at `0x180202f57`
- `USER32!DispatchMessageW` at `0x180202f62`
- `USER32!DispatchMessageW` at `0x180202f62`

## pseudocode

```c

```
