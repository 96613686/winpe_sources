# StatusUpdate::SetStatusString(ushort const *)

- ea: `0x14004bd20`
- end: `0x14004bdb1`
- name: `?SetStatusString@StatusUpdate@@QEAAXPEBG@Z`
- size: `145`
- prototype: `void(StatusUpdate *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140010258`
- `0x14001a54c`

## callees

- `0x140003611`
- `0x140040bf0`
- `0x14004bc38`
- `0x14004bd20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004bd30`
- `KERNEL32!EnterCriticalSection` at `0x14004bd30`
- `KERNEL32!LeaveCriticalSection` at `0x14004bdaa`
- `KERNEL32!SetEvent` at `0x14004bd86`
- `KERNEL32!SetEvent` at `0x14004bd86`
- `KERNEL32!WaitForSingleObject` at `0x14004bd98`
- `KERNEL32!WaitForSingleObject` at `0x14004bd98`

## pseudocode

```c

```
