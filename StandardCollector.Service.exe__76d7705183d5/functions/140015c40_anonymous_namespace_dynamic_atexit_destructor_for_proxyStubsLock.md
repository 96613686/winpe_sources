# _anonymous_namespace_::_dynamic_atexit_destructor_for__proxyStubsLock__

- ea: `0x140015c40`
- end: `0x140015c4e`
- name: `_anonymous_namespace_::_dynamic_atexit_destructor_for__proxyStubsLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140015c47`

## pseudocode

```c
void anonymous_namespace_::_dynamic_atexit_destructor_for__proxyStubsLock__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140015c40  lea     rcx, CriticalSection
0x140015c47  jmp     cs:__imp_DeleteCriticalSection
```
