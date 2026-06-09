# _dynamic_atexit_destructor_for__AppMon::AppMonitor::s_instLock__

- ea: `0x18000fc30`
- end: `0x18000fc3e`
- name: `_dynamic_atexit_destructor_for__AppMon::AppMonitor::s_instLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fc37`

## pseudocode

```c
void dynamic_atexit_destructor_for__AppMon::AppMonitor::s_instLock__()
{
  DeleteCriticalSection(&AppMon::AppMonitor::s_instLock);
}

```

## disassembly

```asm
0x18000fc30  lea     rcx, ?s_instLock@AppMonitor@AppMon@@0Vcritical_section@wil@@A; wil::critical_section AppMon::AppMonitor::s_instLock
0x18000fc37  jmp     cs:__imp_DeleteCriticalSection
```
