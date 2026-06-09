# TransferMonitor::~TransferMonitor(void)

- ea: `0x1800124e4`
- end: `0x18001250d`
- name: `??1TransferMonitor@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(TransferMonitor *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012350`
- `0x180023bf4`

## callees

- `0x18001e910`
- `0x1800225f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800124f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800124f1`

## pseudocode

```c
void __fastcall TransferMonitor::~TransferMonitor(TransferMonitor *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  TimerQueue::~TimerQueue((TransferMonitor *)((char *)this + 64));
  std::_Func_class<void,bool,unsigned int>::_Tidy(this);
}

```

## disassembly

```asm
0x1800124e4  push    rbx
0x1800124e6  sub     rsp, 20h
0x1800124ea  mov     rbx, rcx
0x1800124ed  add     rcx, 60h ; '`'; lpCriticalSection
0x1800124f1  call    cs:__imp_DeleteCriticalSection
0x1800124f7  lea     rcx, [rbx+40h]; this
0x1800124fb  call    ??1TimerQueue@@QEAA@XZ; TimerQueue::~TimerQueue(void)
0x180012500  mov     rcx, rbx
0x180012503  add     rsp, 20h
0x180012507  pop     rbx
0x180012508  jmp     ?_Tidy@?$_Func_class@X_NI@std@@IEAAXXZ; std::_Func_class<void,bool,uint>::_Tidy(void)
```
