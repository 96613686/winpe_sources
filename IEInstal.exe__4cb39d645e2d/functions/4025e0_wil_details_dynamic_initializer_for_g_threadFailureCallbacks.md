# wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__

- ea: `0x4025e0`
- end: `0x4025ec`
- name: `wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40cd9f`

## pseudocode

```c
int wil::details::_dynamic_initializer_for__g_threadFailureCallbacks__()
{
  return atexit(wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__);
}

```

## disassembly

```asm
0x4025e0  push    offset wil__details___dynamic_atexit_destructor_for__g_threadFailureCallbacks__; void (__cdecl *)()
0x4025e5  call    _atexit
0x4025ea  pop     ecx
0x4025eb  retn
```
