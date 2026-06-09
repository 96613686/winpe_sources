# av_packet_copy_props

- ea: `0x18001baf8`
- end: `0x18001bafe`
- name: `av_packet_copy_props`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800121d0`

## import_xrefs

- `avcodec_ms!av_packet_copy_props` at `0x18001baf8`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_copy_props()
{
  return __imp_av_packet_copy_props();
}

```

## disassembly

```asm
0x18001baf8  jmp     cs:__imp_av_packet_copy_props
```
