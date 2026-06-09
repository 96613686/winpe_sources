# av_channel_layout_compare

- ea: `0x180022848`
- end: `0x18002284e`
- name: `av_channel_layout_compare`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009948`

## import_xrefs

- `avutil_ms!av_channel_layout_compare` at `0x180022848`

## pseudocode

```c
// attributes: thunk
__int64 av_channel_layout_compare()
{
  return __imp_av_channel_layout_compare();
}

```

## disassembly

```asm
0x180022848  jmp     cs:__imp_av_channel_layout_compare
```
