# av_packet_side_data_free

- ea: `0x18001b9e2`
- end: `0x18001b9e8`
- name: `av_packet_side_data_free`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180002268`

## import_xrefs

- `avcodec_ms!av_packet_side_data_free` at `0x18001b9e2`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_side_data_free()
{
  return __imp_av_packet_side_data_free();
}

```

## disassembly

```asm
0x18001b9e2  jmp     cs:__imp_av_packet_side_data_free
```
