# AdvancedInstallProgressHandler::WaitForCompletion(void *,ulong)

- ea: `0x14004eb60`
- end: `0x14004ece6`
- name: `?WaitForCompletion@AdvancedInstallProgressHandler@@QEAAXPEAXK@Z`
- size: `390`
- prototype: `void __fastcall(AdvancedInstallProgressHandler *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140053df0`

## callees

- `0x140005f30`
- `0x14000d850`
- `0x140029eb8`
- `0x14002a2c0`
- `0x14002a3e8`
- `0x14004cb5c`
- `0x14004e1e8`
- `0x14004e72c`
- `0x14004eb60`
- `0x1400550c8`
- `0x140055774`
- `0x1400573d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004ebe1`
- `KERNEL32!GetLastError` at `0x14004ebe1`
- `KERNEL32!WaitForMultipleObjects` at `0x14004ebaa`
- `KERNEL32!WaitForMultipleObjects` at `0x14004ebaa`
- `KERNEL32!CancelWaitableTimer` at `0x14004ecab`
- `KERNEL32!CancelWaitableTimer` at `0x14004ecab`

## pseudocode

```c

```
