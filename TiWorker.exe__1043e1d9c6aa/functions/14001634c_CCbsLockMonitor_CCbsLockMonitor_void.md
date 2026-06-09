# CCbsLockMonitor::~CCbsLockMonitor(void)

- ea: `0x14001634c`
- end: `0x14001636c`
- name: `??1CCbsLockMonitor@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002aea0`

## callees

- `0x14001629c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016359`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016359`

## pseudocode

```c
void __fastcall CCbsLockMonitor::~CCbsLockMonitor(CCbsLockMonitor *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::~CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>(this);
}

```

## disassembly

```asm
0x14001634c  push    rbx
0x14001634e  sub     rsp, 20h
0x140016352  mov     rbx, rcx
0x140016355  add     rcx, 40h ; '@'; lpCriticalSection
0x140016359  call    cs:__imp_DeleteCriticalSection
0x14001635f  mov     rcx, rbx
0x140016362  add     rsp, 20h
0x140016366  pop     rbx
0x140016367  jmp     ??1?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@MEAA@XZ; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::~CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>(void)
```
