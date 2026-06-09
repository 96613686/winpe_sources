# _get_startup_argv_mode

- ea: `0x1400016b0`
- end: `0x1400016b6`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `_crt_argv_mode __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## pseudocode

```c
_crt_argv_mode __cdecl get_startup_argv_mode()
{
  return 1;
}

```

## disassembly

```asm
0x1400016b0  mov     eax, 1
0x1400016b5  retn
```
