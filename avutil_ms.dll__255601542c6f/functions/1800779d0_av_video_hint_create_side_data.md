# av_video_hint_create_side_data

- ea: `0x1800779d0`
- end: `0x180077a5d`
- name: `av_video_hint_create_side_data`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18002ec70`
- `0x18002f210`
- `0x18003b7b0`
- `0x1800449d0`
- `0x180077960`
- `0x1800779d0`

## pseudocode

```c
__int64 __fastcall av_video_hint_create_side_data(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v5; // rax
  __int64 v6[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v3 = av_video_hint_alloc(a2, &v7);
  v8 = v3;
  if ( !v3 )
    return 0;
  v5 = av_buffer_create(v3, v7, 0, 0, 0);
  v6[0] = v5;
  if ( !v5 )
  {
    av_freep(&v8);
    return 0;
  }
  if ( !av_frame_new_side_data_from_buf(a1, 27, v5) )
  {
    av_buffer_unref(v6);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1800779d0  push    rbx
0x1800779d2  sub     rsp, 40h
0x1800779d6  mov     rax, rdx
0x1800779d9  mov     [rsp+48h+arg_10], 0
0x1800779e2  mov     rbx, rcx
0x1800779e5  lea     rdx, [rsp+48h+arg_10]
0x1800779ea  mov     rcx, rax
0x1800779ed  call    av_video_hint_alloc
0x1800779f2  mov     [rsp+48h+arg_18], rax
0x1800779f7  test    rax, rax
0x1800779fa  jnz     short loc_180077A00
0x1800779fc  xor     eax, eax
0x1800779fe  jmp     short loc_180077A57
0x180077a00  mov     rdx, [rsp+48h+arg_10]
0x180077a05  xor     r9d, r9d
0x180077a08  xor     r8d, r8d
0x180077a0b  mov     [rsp+48h+var_28], 0
0x180077a13  mov     rcx, rax
0x180077a16  call    av_buffer_create
0x180077a1b  mov     [rsp+48h+var_18], rax
0x180077a20  test    rax, rax
0x180077a23  jnz     short loc_180077A31
0x180077a25  lea     rcx, [rsp+48h+arg_18]
0x180077a2a  call    av_freep
0x180077a2f  jmp     short loc_1800779FC
0x180077a31  mov     r8, rax
0x180077a34  mov     edx, 1Bh
0x180077a39  mov     rcx, rbx
0x180077a3c  call    av_frame_new_side_data_from_buf
0x180077a41  test    rax, rax
0x180077a44  jnz     short loc_180077A52
0x180077a46  lea     rcx, [rsp+48h+var_18]
0x180077a4b  call    av_buffer_unref
0x180077a50  jmp     short loc_1800779FC
0x180077a52  mov     rax, [rsp+48h+arg_18]
0x180077a57  add     rsp, 40h
0x180077a5b  pop     rbx
0x180077a5c  retn
```
