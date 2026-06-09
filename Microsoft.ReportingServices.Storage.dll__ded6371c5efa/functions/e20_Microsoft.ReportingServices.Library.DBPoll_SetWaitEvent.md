# Microsoft.ReportingServices.Library.DBPoll::SetWaitEvent

- ea: `0xe20`
- end: `0xe2c`
- name: `Microsoft.ReportingServices.Library.DBPoll::SetWaitEvent`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xc40`
- `0x13f0`
- `0x1830`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Library.DBPoll::m_resetEvent
0xe25  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xe2a  pop
0xe2b  ret
```
