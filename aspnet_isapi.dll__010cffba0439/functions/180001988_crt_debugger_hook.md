# __crt_debugger_hook

- ea: `0x180001988`
- end: `0x180001990`
- name: `__crt_debugger_hook`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001990`

## pseudocode

```c
void _crt_debugger_hook()
{
  _scrt_debugger_hook_flag = 0;
}

```

## disassembly

```asm
0x180001988  and     cs:__scrt_debugger_hook_flag, 0
0x18000198f  retn
```
