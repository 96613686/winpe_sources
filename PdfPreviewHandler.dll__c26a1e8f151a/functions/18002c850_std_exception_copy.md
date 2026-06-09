# __std_exception_copy

- ea: `0x18002c850`
- end: `0x18002c856`
- name: `__std_exception_copy`
- size: `6`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180013700`
- `0x180013740`
- `0x1800137e0`
- `0x180013820`
- `0x180013890`
- `0x180013910`
- `0x180013950`
- `0x1800139a0`
- `0x180013b50`
- `0x180013bd0`
- `0x180013df0`
- `0x18002b880`
- `0x18002b90a`

## import_xrefs

- `VCRUNTIME140!__std_exception_copy` at `0x18002c850`

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
0x18002c850  jmp     cs:__imp___std_exception_copy
```
