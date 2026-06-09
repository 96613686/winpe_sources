# _o___std_exception_destroy_0

- ea: `0x14000a293`
- end: `0x14000a299`
- name: `_o___std_exception_destroy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001360`
- `0x14000248c`
- `0x14000d440`
- `0x14000d460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_destroy` at `0x14000a293`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_destroy_0()
{
  return __std_exception_destroy();
}

```

## disassembly

```asm
0x14000a293  jmp     cs:__imp___std_exception_destroy
```
