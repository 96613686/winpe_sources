# CommonUtil::_dynamic_initializer_for__gs_aTimeoutEvent__

- ea: `0x1400012b0`
- end: `0x1400012bc`
- name: `CommonUtil::_dynamic_initializer_for__gs_aTimeoutEvent__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400018e0`

## pseudocode

```c
int CommonUtil::_dynamic_initializer_for__gs_aTimeoutEvent__()
{
  return atexit((void (__cdecl *)())CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__);
}

```

## disassembly

```asm
0x1400012b0  lea     rcx, CommonUtil___dynamic_atexit_destructor_for__gs_aTimeoutEvent__
0x1400012b7  jmp     atexit
```
