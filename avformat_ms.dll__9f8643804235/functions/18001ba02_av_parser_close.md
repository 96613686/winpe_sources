# av_parser_close

- ea: `0x18001ba02`
- end: `0x18001ba08`
- name: `av_parser_close`
- size: `6`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000219c`
- `0x180008cf4`
- `0x18000a378`
- `0x18000a920`
- `0x18000be8c`
- `0x1800167b0`
- `0x18001a9a4`

## import_xrefs

- `avcodec_ms!av_parser_close` at `0x18001ba02`

## pseudocode

```c
// attributes: thunk
__int64 av_parser_close(void)
{
  return __imp_av_parser_close();
}

```

## disassembly

```asm
0x18001ba02  jmp     cs:__imp_av_parser_close
```
