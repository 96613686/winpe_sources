# av_packet_side_data_add

- ea: `0x18000f480`
- end: `0x18000f485`
- name: `av_packet_side_data_add`
- size: `5`
- prototype: `__int64 __fastcall(int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000fcd4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_packet_side_data_add(int a1, int a2, int a3, int a4, __int64 a5)
{
  return av_packet_side_data_add_0(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000f480  jmp     av_packet_side_data_add_0
```
