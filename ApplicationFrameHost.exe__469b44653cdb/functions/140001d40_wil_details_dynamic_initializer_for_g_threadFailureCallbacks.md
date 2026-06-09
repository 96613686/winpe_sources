# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x140001d40`
- end: `0x140001d4c`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003424`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit((void (__cdecl *)())wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x140001d40  lea     rcx, wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__
0x140001d47  jmp     atexit
```
