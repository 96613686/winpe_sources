# AutoMonitoredCritSec::~AutoMonitoredCritSec(void)

- ea: `0x14001bee0`
- end: `0x14001bf00`
- name: `??1AutoMonitoredCritSec@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014100`

## callees

- `0x14001c564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001bef9`

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
0x14001bee0  push    rbx
0x14001bee2  sub     rsp, 20h
0x14001bee6  mov     rdx, rcx; struct _RTL_CRITICAL_SECTION *
0x14001bee9  mov     rbx, rcx
0x14001beec  call    ?RemoveLock@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; CCbsLockMonitor::RemoveLock(_RTL_CRITICAL_SECTION *)
0x14001bef1  mov     rcx, rbx
0x14001bef4  add     rsp, 20h
0x14001bef8  pop     rbx
0x14001bef9  jmp     cs:__imp_DeleteCriticalSection
```
