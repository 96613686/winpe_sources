# _o___std_exception_copy

- ea: `0x1400077fe`
- end: `0x140007804`
- name: `_o___std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f0b8`
- `0x14000f1cc`
- `0x140012774`
- `0x1400127b8`
- `0x14002bf08`
- `0x14002bf4c`
- `0x14002bfa8`
- `0x1400bdcec`
- `0x1400bde10`
- `0x1400bde90`
- `0x1400bdf40`
- `0x1400bdf84`
- `0x1400bdfe0`
- `0x1400be024`
- `0x1400be068`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400077fe`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1400077fe  jmp     cs:__imp__o___std_exception_copy
```
