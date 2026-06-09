# _get_startup_argv_mode

- ea: `0x180001bec`
- end: `0x180001bf2`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `_crt_argv_mode __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001598`

## pseudocode

```c
_crt_argv_mode __cdecl get_startup_argv_mode()
{
  return 1;
}

```

## disassembly

```asm
0x180001bec  mov     eax, 1
0x180001bf1  retn
```
