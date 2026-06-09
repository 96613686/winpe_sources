# Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(void)

- ea: `0x180046f1c`
- end: `0x180046f2f`
- name: `??1_TaskWorkItemRAIILogger@details@Concurrency@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger **this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180059ce6`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180046f23`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180046f23`

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
0x180046f1c  sub     rsp, 28h
0x180046f20  mov     rcx, [rcx]
0x180046f23  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180046f29  nop
0x180046f2a  add     rsp, 28h
0x180046f2e  retn
```
