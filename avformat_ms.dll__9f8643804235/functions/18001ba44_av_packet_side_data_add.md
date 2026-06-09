# av_packet_side_data_add

- ea: `0x18001ba44`
- end: `0x18001ba4a`
- name: `av_packet_side_data_add`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180006390`

## import_xrefs

- `avcodec_ms!av_packet_side_data_add` at `0x18001ba44`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_packet_side_data_add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  return __imp_av_packet_side_data_add(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18001ba44  jmp     cs:__imp_av_packet_side_data_add
```
