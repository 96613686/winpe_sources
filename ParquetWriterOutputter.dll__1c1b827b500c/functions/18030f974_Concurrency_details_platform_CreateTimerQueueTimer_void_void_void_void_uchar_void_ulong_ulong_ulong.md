# Concurrency::details::platform::__CreateTimerQueueTimer(void * *,void *,void (*)(void *,uchar),void *,ulong,ulong,ulong)

- ea: `0x18030f974`
- end: `0x18030f97b`
- name: `?__CreateTimerQueueTimer@platform@details@Concurrency@@YAHPEAPEAXPEAXP6AX1E@Z1KKK@Z`
- size: `7`
- prototype: `BOOL __stdcall(PHANDLE phNewTimer, HANDLE TimerQueue, WAITORTIMERCALLBACK Callback, PVOID Parameter, DWORD DueTime, DWORD Period, ULONG Flags)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18030d698`
- `0x18030ec38`
- `0x18030f354`
- `0x180315214`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18030f974`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall Concurrency::details::platform::__CreateTimerQueueTimer(
        PHANDLE phNewTimer,
        HANDLE TimerQueue,
        WAITORTIMERCALLBACK Callback,
        PVOID Parameter,
        DWORD DueTime,
        DWORD Period,
        ULONG Flags)
{
  return CreateTimerQueueTimer(phNewTimer, TimerQueue, Callback, Parameter, DueTime, Period, Flags);
}

```

## disassembly

```asm
0x18030f974  jmp     cs:__imp_CreateTimerQueueTimer
```
