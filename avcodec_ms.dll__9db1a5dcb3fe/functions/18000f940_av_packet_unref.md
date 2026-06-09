# av_packet_unref

- ea: `0x18000f940`
- end: `0x18000f96c`
- name: `av_packet_unref`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `20`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004010`
- `0x180005810`
- `0x180005bc0`
- `0x180006020`
- `0x180006bd0`
- `0x180007460`
- `0x180007a84`
- `0x180007d18`
- `0x1800097f0`
- `0x180009fb0`
- `0x18000a3cc`
- `0x18000a950`
- `0x18000eda0`
- `0x18000ef00`
- `0x18000f2f0`
- `0x18000f9a0`
- `0x18000fb80`
- `0x18000fbb0`
- `0x180010c30`
- `0x180011534`

## callees

- `0x18000ef30`
- `0x18000fc2c`
- `0x180022758`

## pseudocode

```c
__int64 __fastcall av_packet_unref(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9

  av_packet_free_side_data((__int64)a1);
  av_buffer_unref(a1 + 11);
  av_buffer_unref(a1);
  return sub_18000FC2C(a1, v2, v3, v4);
}

```

## disassembly

```asm
0x18000f940  push    rbx
0x18000f942  sub     rsp, 20h
0x18000f946  mov     rbx, rcx
0x18000f949  call    av_packet_free_side_data
0x18000f94e  lea     rcx, [rbx+58h]
0x18000f952  call    av_buffer_unref
0x18000f957  mov     rcx, rbx
0x18000f95a  call    av_buffer_unref
0x18000f95f  mov     rcx, rbx
0x18000f962  add     rsp, 20h
0x18000f966  pop     rbx
0x18000f967  jmp     sub_18000FC2C
```
