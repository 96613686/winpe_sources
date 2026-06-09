# CCbsLockMonitor::~CCbsLockMonitor(void)

- ea: `0x14001bf08`
- end: `0x14001bf28`
- name: `??1CCbsLockMonitor@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CCbsLockMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002ab60`

## callees

- `0x14001be58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001bf15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001bf15`

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
0x14001bf08  push    rbx
0x14001bf0a  sub     rsp, 20h
0x14001bf0e  mov     rbx, rcx
0x14001bf11  add     rcx, 40h ; '@'; lpCriticalSection
0x14001bf15  call    cs:__imp_DeleteCriticalSection
0x14001bf1b  mov     rcx, rbx
0x14001bf1e  add     rsp, 20h
0x14001bf22  pop     rbx
0x14001bf23  jmp     ??1?$CCbsArrayBase@UCCbsLock@@V?$CCbsArray@UCCbsLock@@@@@@MEAA@XZ; CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>::~CCbsArrayBase<CCbsLock,CCbsArray<CCbsLock>>(void)
```
