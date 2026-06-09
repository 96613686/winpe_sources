# _dynamic_initializer_for__Updater__

- ea: `0x1800024f0`
- end: `0x1800024fc`
- name: `_dynamic_initializer_for__Updater__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002f58`

## pseudocode

```c
int dynamic_initializer_for__Updater__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Updater__);
}

```

## disassembly

```asm
0x1800024f0  lea     rcx, _dynamic_atexit_destructor_for__Updater__
0x1800024f7  jmp     atexit
```
