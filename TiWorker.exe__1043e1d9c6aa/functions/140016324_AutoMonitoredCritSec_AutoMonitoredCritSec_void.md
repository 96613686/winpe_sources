# AutoMonitoredCritSec::~AutoMonitoredCritSec(void)

- ea: `0x140016324`
- end: `0x140016344`
- name: `??1AutoMonitoredCritSec@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000619c`
- `0x14000a0e4`

## callees

- `0x140016af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001633d`

## pseudocode

```c
void __fastcall AutoMonitoredCritSec::~AutoMonitoredCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  CCbsLockMonitor::RemoveLock((CCbsLockMonitor *)this, this);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140016324  push    rbx
0x140016326  sub     rsp, 20h
0x14001632a  mov     rdx, rcx; struct _RTL_CRITICAL_SECTION *
0x14001632d  mov     rbx, rcx
0x140016330  call    ?RemoveLock@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; CCbsLockMonitor::RemoveLock(_RTL_CRITICAL_SECTION *)
0x140016335  mov     rcx, rbx
0x140016338  add     rsp, 20h
0x14001633c  pop     rbx
0x14001633d  jmp     cs:__imp_DeleteCriticalSection
```
