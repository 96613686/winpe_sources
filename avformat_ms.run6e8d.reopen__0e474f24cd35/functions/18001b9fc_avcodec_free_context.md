# avcodec_free_context

- ea: `0x18001b9fc`
- end: `0x18001ba02`
- name: `avcodec_free_context`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000219c`
- `0x180007dd8`
- `0x18000e06c`
- `0x18000e598`
- `0x1800167b0`

## import_xrefs

- `avcodec_ms!avcodec_free_context` at `0x18001b9fc`

## pseudocode

```c
// attributes: thunk
__int64 avcodec_free_context()
{
  return __imp_avcodec_free_context();
}

```

## disassembly

```asm
0x18001b9fc  jmp     cs:__imp_avcodec_free_context
```
