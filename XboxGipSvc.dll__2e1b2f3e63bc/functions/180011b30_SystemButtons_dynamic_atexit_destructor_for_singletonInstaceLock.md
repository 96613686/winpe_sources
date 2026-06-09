# SystemButtons::_dynamic_atexit_destructor_for__singletonInstaceLock__

- ea: `0x180011b30`
- end: `0x180011b3e`
- name: `SystemButtons::_dynamic_atexit_destructor_for__singletonInstaceLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011b37`

## pseudocode

```c
void SystemButtons::_dynamic_atexit_destructor_for__singletonInstaceLock__()
{
  DeleteCriticalSection(&SystemButtons::singletonInstaceLock);
}

```

## disassembly

```asm
0x180011b30  lea     rcx, ?singletonInstaceLock@SystemButtons@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemButtons::singletonInstaceLock
0x180011b37  jmp     cs:__imp_DeleteCriticalSection
```
