# ServiceWatchdog::~ServiceWatchdog(void)

- ea: `0x1800124b4`
- end: `0x1800124de`
- name: `??1ServiceWatchdog@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012350`
- `0x180023bdb`

## callees

- `0x18001e910`
- `0x1800225f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800124d7`

## pseudocode

```c
void __fastcall ServiceWatchdog::~ServiceWatchdog(struct _RTL_CRITICAL_SECTION *this)
{
  std::_Func_class<void,bool,unsigned int>::_Tidy(&this[1].SpinCount);
  TimerQueue::~TimerQueue((TimerQueue *)&this[1]);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800124b4  push    rbx
0x1800124b6  sub     rsp, 20h
0x1800124ba  mov     rbx, rcx
0x1800124bd  add     rcx, 48h ; 'H'
0x1800124c1  call    ?_Tidy@?$_Func_class@X_NI@std@@IEAAXXZ; std::_Func_class<void,bool,uint>::_Tidy(void)
0x1800124c6  lea     rcx, [rbx+28h]; this
0x1800124ca  call    ??1TimerQueue@@QEAA@XZ; TimerQueue::~TimerQueue(void)
0x1800124cf  mov     rcx, rbx
0x1800124d2  add     rsp, 20h
0x1800124d6  pop     rbx
0x1800124d7  jmp     cs:__imp_DeleteCriticalSection
```
