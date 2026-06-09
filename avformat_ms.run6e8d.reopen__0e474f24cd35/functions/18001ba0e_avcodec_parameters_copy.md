# avcodec_parameters_copy

- ea: `0x18001ba0e`
- end: `0x18001ba14`
- name: `avcodec_parameters_copy`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800092d0`

## import_xrefs

- `avcodec_ms!avcodec_parameters_copy` at `0x18001ba0e`

## pseudocode

```c
// attributes: thunk
__int64 avcodec_parameters_copy()
{
  return __imp_avcodec_parameters_copy();
}

```

## disassembly

```asm
0x18001ba0e  jmp     cs:__imp_avcodec_parameters_copy
```
