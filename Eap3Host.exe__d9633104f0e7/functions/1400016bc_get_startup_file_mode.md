# _get_startup_file_mode

- ea: `0x1400016bc`
- end: `0x1400016c2`
- name: `_get_startup_file_mode`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## pseudocode

```c
__int64 get_startup_file_mode()
{
  return 0x4000;
}

```

## disassembly

```asm
0x1400016bc  mov     eax, 4000h
0x1400016c1  retn
```
