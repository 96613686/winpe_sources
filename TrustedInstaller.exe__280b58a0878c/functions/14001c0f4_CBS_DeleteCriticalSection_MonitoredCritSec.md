# CBS_DeleteCriticalSection(MonitoredCritSec *)

- ea: `0x14001c0f4`
- end: `0x14001c116`
- name: `?CBS_DeleteCriticalSection@@YAXPEAUMonitoredCritSec@@@Z`
- size: `34`
- prototype: `void __fastcall(struct MonitoredCritSec *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001681c`
- `0x1400168ac`

## callees

- `0x14001c564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001c10f`

## pseudocode

```c
void __fastcall CBS_DeleteCriticalSection(struct MonitoredCritSec *a1)
{
  CCbsLockMonitor::RemoveLock(a1, &stru_1400406F8);
  DeleteCriticalSection(&stru_1400406F8);
}

```

## disassembly

```asm
0x14001c0f4  sub     rsp, 28h
0x14001c0f8  lea     rdx, stru_1400406F8; struct _RTL_CRITICAL_SECTION *
0x14001c0ff  call    ?RemoveLock@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; CCbsLockMonitor::RemoveLock(_RTL_CRITICAL_SECTION *)
0x14001c104  lea     rcx, stru_1400406F8
0x14001c10b  add     rsp, 28h
0x14001c10f  jmp     cs:__imp_DeleteCriticalSection
```
