# av_video_enc_params_create_side_data

- ea: `0x1800778d0`
- end: `0x180077959`
- name: `av_video_enc_params_create_side_data`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18002ec70`
- `0x18002f210`
- `0x18003b7b0`
- `0x1800449d0`
- `0x180077860`
- `0x1800778d0`

## pseudocode

```c
__int64 __fastcall av_video_enc_params_create_side_data(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+38h] [rbp-10h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v4 = av_video_enc_params_alloc(a2, a3, &v7);
  v9 = v4;
  if ( !v4 )
    return 0;
  v6 = av_buffer_create(v4, v7, 0, 0, 0);
  v8 = v6;
  if ( !v6 )
  {
    av_freep(&v9);
    return 0;
  }
  if ( !av_frame_new_side_data_from_buf(a1, 19, v6) )
  {
    av_buffer_unref(&v8);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800778d0  push    rbx
0x1800778d2  sub     rsp, 40h
0x1800778d6  mov     eax, r8d
0x1800778d9  mov     r9d, edx
0x1800778dc  mov     rbx, rcx
0x1800778df  lea     r8, [rsp+48h+var_18]
0x1800778e4  mov     edx, eax
0x1800778e6  mov     ecx, r9d
0x1800778e9  call    av_video_enc_params_alloc
0x1800778ee  mov     [rsp+48h+arg_18], rax
0x1800778f3  test    rax, rax
0x1800778f6  jnz     short loc_1800778FC
0x1800778f8  xor     eax, eax
0x1800778fa  jmp     short loc_180077953
0x1800778fc  mov     rdx, [rsp+48h+var_18]
0x180077901  xor     r9d, r9d
0x180077904  xor     r8d, r8d
0x180077907  mov     [rsp+48h+var_28], 0
0x18007790f  mov     rcx, rax
0x180077912  call    av_buffer_create
0x180077917  mov     [rsp+48h+var_10], rax
0x18007791c  test    rax, rax
0x18007791f  jnz     short loc_18007792D
0x180077921  lea     rcx, [rsp+48h+arg_18]
0x180077926  call    av_freep
0x18007792b  jmp     short loc_1800778F8
0x18007792d  mov     r8, rax
0x180077930  mov     edx, 13h
0x180077935  mov     rcx, rbx
0x180077938  call    av_frame_new_side_data_from_buf
0x18007793d  test    rax, rax
0x180077940  jnz     short loc_18007794E
0x180077942  lea     rcx, [rsp+48h+var_10]
0x180077947  call    av_buffer_unref
0x18007794c  jmp     short loc_1800778F8
0x18007794e  mov     rax, [rsp+48h+arg_18]
0x180077953  add     rsp, 40h
0x180077957  pop     rbx
0x180077958  retn
```
