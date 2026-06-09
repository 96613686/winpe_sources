# av_frame_side_data_get_c

- ea: `0x18002280c`
- end: `0x180022812`
- name: `av_frame_side_data_get_c`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18000a670`

## import_xrefs

- `avutil_ms!av_frame_side_data_get_c` at `0x18002280c`

## pseudocode

```c
// attributes: thunk
__int64 av_frame_side_data_get_c()
{
  return __imp_av_frame_side_data_get_c();
}

```

## disassembly

```asm
0x18002280c  jmp     cs:__imp_av_frame_side_data_get_c
```
