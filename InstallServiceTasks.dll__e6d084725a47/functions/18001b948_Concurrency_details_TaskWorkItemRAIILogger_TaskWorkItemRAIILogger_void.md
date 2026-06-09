# Concurrency::details::_TaskWorkItemRAIILogger::~_TaskWorkItemRAIILogger(void)

- ea: `0x18001b948`
- end: `0x18001b95b`
- name: `??1_TaskWorkItemRAIILogger@details@Concurrency@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(Concurrency::details::_TaskEventLogger **this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041740`

## import_xrefs

- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b94f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001b94f`

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
0x18001b948  sub     rsp, 28h
0x18001b94c  mov     rcx, [rcx]
0x18001b94f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001b955  nop
0x18001b956  add     rsp, 28h
0x18001b95a  retn
```
