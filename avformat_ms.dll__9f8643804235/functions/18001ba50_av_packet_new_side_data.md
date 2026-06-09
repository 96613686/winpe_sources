# av_packet_new_side_data

- ea: `0x18001ba50`
- end: `0x18001ba56`
- name: `av_packet_new_side_data`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18000a920`
- `0x1800148e0`

## import_xrefs

- `avcodec_ms!av_packet_new_side_data` at `0x18001ba50`

## pseudocode

```c
// attributes: thunk
__int64 av_packet_new_side_data()
{
  return __imp_av_packet_new_side_data();
}

```

## disassembly

```asm
0x18001ba50  jmp     cs:__imp_av_packet_new_side_data
```
