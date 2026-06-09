# Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(void)

- ea: `0x180011f2c`
- end: `0x180011f3f`
- name: `??1_TaskWorkItemRAIILogger@details@Concurrency@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger **this)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800233b0`
- `0x1800240db`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180011f33`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180011f33`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(
        Concurrency::details::_TaskEventLogger **this)
{
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(*this);
}

```

## disassembly

```asm
0x180011f2c  sub     rsp, 28h
0x180011f30  mov     rcx, [rcx]
0x180011f33  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180011f39  nop
0x180011f3a  add     rsp, 28h
0x180011f3e  retn
```
