# av_packet_side_data_new

- ea: `0x18001bb46`
- end: `0x18001bb4c`
- name: `av_packet_side_data_new`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180019a0c`

## import_xrefs

- `avcodec_ms!av_packet_side_data_new` at `0x18001bb46`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_side_data_new()
{
  return __imp_av_packet_side_data_new();
}

```

## disassembly

```asm
0x18001bb46  jmp     cs:__imp_av_packet_side_data_new
```
