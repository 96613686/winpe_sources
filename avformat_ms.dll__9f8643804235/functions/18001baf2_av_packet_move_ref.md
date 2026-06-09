# av_packet_move_ref

- ea: `0x18001baf2`
- end: `0x18001baf8`
- name: `av_packet_move_ref`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180012cf4`

## import_xrefs

- `avcodec_ms!av_packet_move_ref` at `0x18001baf2`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_move_ref()
{
  return __imp_av_packet_move_ref();
}

```

## disassembly

```asm
0x18001baf2  jmp     cs:__imp_av_packet_move_ref
```
