# _o___std_exception_copy_0

- ea: `0x180001ff6`
- end: `0x180001ffc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e40`
- `0x18000301c`
- `0x180003088`
- `0x180003188`
- `0x1800031cc`
- `0x180009574`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001ff6`

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
0x180001ff6  jmp     cs:__imp__o___std_exception_copy
```
