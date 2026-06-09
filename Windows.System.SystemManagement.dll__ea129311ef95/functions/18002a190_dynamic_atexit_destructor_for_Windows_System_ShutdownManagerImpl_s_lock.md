# _dynamic_atexit_destructor_for__Windows::System::ShutdownManagerImpl::s_lock__

- ea: `0x18002a190`
- end: `0x18002a19e`
- name: `_dynamic_atexit_destructor_for__Windows::System::ShutdownManagerImpl::s_lock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a197`

## pseudocode

```c
void dynamic_atexit_destructor_for__Windows::System::ShutdownManagerImpl::s_lock__()
{
  DeleteCriticalSection(&Windows::System::ShutdownManagerImpl::s_lock);
}

```

## disassembly

```asm
0x18002a190  lea     rcx, ?s_lock@ShutdownManagerImpl@System@Windows@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection Windows::System::ShutdownManagerImpl::s_lock
0x18002a197  jmp     cs:__imp_DeleteCriticalSection
```
