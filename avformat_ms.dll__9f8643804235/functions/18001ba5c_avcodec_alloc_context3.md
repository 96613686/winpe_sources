# avcodec_alloc_context3

- ea: `0x18001ba5c`
- end: `0x18001ba62`
- name: `avcodec_alloc_context3`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007dd8`
- `0x18000e06c`
- `0x18000e598`
- `0x1800167b0`
- `0x180019330`

## import_xrefs

- `avcodec_ms!avcodec_alloc_context3` at `0x18001ba5c`

## pseudocode

```c
// attributes: thunk
__int64 avcodec_alloc_context3()
{
  return __imp_avcodec_alloc_context3();
}

```

## disassembly

```asm
0x18001ba5c  jmp     cs:__imp_avcodec_alloc_context3
```
