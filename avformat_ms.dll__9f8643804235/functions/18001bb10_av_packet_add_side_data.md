# av_packet_add_side_data

- ea: `0x18001bb10`
- end: `0x18001bb16`
- name: `av_packet_add_side_data`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1800148e0`

## import_xrefs

- `avcodec_ms!av_packet_add_side_data` at `0x18001bb10`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_add_side_data()
{
  return __imp_av_packet_add_side_data();
}

```

## disassembly

```asm
0x18001bb10  jmp     cs:__imp_av_packet_add_side_data
```
