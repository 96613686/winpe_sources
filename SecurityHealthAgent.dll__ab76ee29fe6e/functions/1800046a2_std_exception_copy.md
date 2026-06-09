# __std_exception_copy

- ea: `0x1800046a2`
- end: `0x1800046a8`
- name: `__std_exception_copy`
- size: `6`
- prototype: `__int64()`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180006960`
- `0x18000e330`
- `0x18000e380`
- `0x1800182c0`
- `0x180029d50`
- `0x1800305d0`
- `0x180035c20`
- `0x18003f540`
- `0x18003f6b0`
- `0x18003f7e0`
- `0x18003fa10`
- `0x1800427a0`
- `0x180043050`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x1800046a2`

## pseudocode

```c
// attributes: thunk
__int64 _std_exception_copy()
{
  return __std_exception_copy();
}

```

## disassembly

```asm
0x1800046a2  jmp     cs:__imp___std_exception_copy
```
