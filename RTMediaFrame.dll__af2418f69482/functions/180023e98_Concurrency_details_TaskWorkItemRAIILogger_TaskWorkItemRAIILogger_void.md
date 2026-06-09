# Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(void)

- ea: `0x180023e98`
- end: `0x180023eab`
- name: `??1_TaskWorkItemRAIILogger@details@Concurrency@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::details::_TaskWorkItemRAIILogger *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f701`
- `0x1800502fc`
- `0x18005037a`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023e9f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180023e9f`

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
0x180023e98  sub     rsp, 28h
0x180023e9c  mov     rcx, [rcx]
0x180023e9f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180023ea5  nop
0x180023ea6  add     rsp, 28h
0x180023eaa  retn
```
