# av_mastering_display_metadata_create_side_data

- ea: `0x180043a50`
- end: `0x180043a8e`
- name: `av_mastering_display_metadata_create_side_data`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18003b750`
- `0x180043a50`
- `0x180043a90`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_mastering_display_metadata_create_side_data(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rbx

  result = av_frame_new_side_data(a1, 0xBu, 88);
  v2 = result;
  if ( result )
  {
    sub_18007B020(*(__m128i **)(result + 8), 0, 0x58u);
    sub_180043A90(*(_QWORD *)(v2 + 8));
    return *(_QWORD *)(v2 + 8);
  }
  return result;
}

```

## disassembly

```asm
0x180043a50  push    rbx
0x180043a52  sub     rsp, 20h
0x180043a56  mov     edx, 0Bh
0x180043a5b  lea     r8d, [rdx+4Dh]
0x180043a5f  call    av_frame_new_side_data
0x180043a64  mov     rbx, rax
0x180043a67  test    rax, rax
0x180043a6a  jz      short loc_180043A88
0x180043a6c  mov     rcx, [rax+8]
0x180043a70  xor     edx, edx
0x180043a72  lea     r8d, [rdx+58h]
0x180043a76  call    sub_18007B020
0x180043a7b  mov     rcx, [rbx+8]
0x180043a7f  call    sub_180043A90
0x180043a84  mov     rax, [rbx+8]
0x180043a88  add     rsp, 20h
0x180043a8c  pop     rbx
0x180043a8d  retn
```
