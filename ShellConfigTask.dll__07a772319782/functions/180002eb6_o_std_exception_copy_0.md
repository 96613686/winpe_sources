# _o___std_exception_copy_0

- ea: `0x180002eb6`
- end: `0x180002ebc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b3c`
- `0x180004d18`
- `0x180012fec`
- `0x180013058`
- `0x1800135ac`
- `0x1800135f0`
- `0x180027560`
- `0x180027758`
- `0x1800277ac`
- `0x1800279f0`
- `0x180027a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002eb6`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180002eb6  jmp     cs:__imp__o___std_exception_copy
```
