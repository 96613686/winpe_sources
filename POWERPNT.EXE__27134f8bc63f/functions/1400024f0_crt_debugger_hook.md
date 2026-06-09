# __crt_debugger_hook

- ea: `0x1400024f0`
- end: `0x1400024fb`
- name: `__crt_debugger_hook`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400024fc`

## pseudocode

```c
void _crt_debugger_hook()
{
  _scrt_debugger_hook_flag = 0;
}

```

## disassembly

```asm
0x1400024f0  mov     cs:__scrt_debugger_hook_flag, 0
0x1400024fa  retn
```
