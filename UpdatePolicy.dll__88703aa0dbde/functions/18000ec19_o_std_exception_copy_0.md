# _o___std_exception_copy_0

- ea: `0x18000ec19`
- end: `0x18000ec1f`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001418`
- `0x1800014b0`
- `0x1800015ac`
- `0x1800017f8`
- `0x180001918`
- `0x180001978`
- `0x1800026f8`
- `0x180002d6c`
- `0x180007960`
- `0x1800079a4`
- `0x180007bb8`
- `0x18000896c`
- `0x18000db64`
- `0x18000dbe0`
- `0x18000dc84`
- `0x18000dcf0`
- `0x180013434`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000ec19`

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
0x18000ec19  jmp     cs:__imp__o___std_exception_copy
```
