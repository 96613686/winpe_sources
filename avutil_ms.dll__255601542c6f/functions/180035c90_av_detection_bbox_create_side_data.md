# av_detection_bbox_create_side_data

- ea: `0x180035c90`
- end: `0x180035d12`
- name: `av_detection_bbox_create_side_data`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18002ec70`
- `0x18002f210`
- `0x180035c20`
- `0x180035c90`
- `0x18003b7b0`
- `0x1800449d0`

## pseudocode

```c
__int64 __fastcall av_detection_bbox_create_side_data(__int64 a1, unsigned int a2)
{
  __int64 v3; // rax
  __int64 v5; // rax
  __int64 v6[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  v3 = av_detection_bbox_alloc(a2, &v8);
  v7 = v3;
  if ( !v3 )
    return 0;
  v5 = av_buffer_create(v3, v8, 0, 0, 0);
  v6[0] = v5;
  if ( !v5 )
  {
    av_freep(&v7);
    return 0;
  }
  if ( !av_frame_new_side_data_from_buf(a1, 22, v5) )
  {
    av_buffer_unref(v6);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180035c90  push    rbx
0x180035c92  sub     rsp, 40h
0x180035c96  mov     eax, edx
0x180035c98  mov     rbx, rcx
0x180035c9b  mov     ecx, eax
0x180035c9d  lea     rdx, [rsp+48h+arg_18]
0x180035ca2  call    av_detection_bbox_alloc
0x180035ca7  mov     [rsp+48h+arg_10], rax
0x180035cac  test    rax, rax
0x180035caf  jnz     short loc_180035CB5
0x180035cb1  xor     eax, eax
0x180035cb3  jmp     short loc_180035D0C
0x180035cb5  mov     rdx, [rsp+48h+arg_18]
0x180035cba  xor     r9d, r9d
0x180035cbd  xor     r8d, r8d
0x180035cc0  mov     [rsp+48h+var_28], 0
0x180035cc8  mov     rcx, rax
0x180035ccb  call    av_buffer_create
0x180035cd0  mov     [rsp+48h+var_18], rax
0x180035cd5  test    rax, rax
0x180035cd8  jnz     short loc_180035CE6
0x180035cda  lea     rcx, [rsp+48h+arg_10]
0x180035cdf  call    av_freep
0x180035ce4  jmp     short loc_180035CB1
0x180035ce6  mov     r8, rax
0x180035ce9  mov     edx, 16h
0x180035cee  mov     rcx, rbx
0x180035cf1  call    av_frame_new_side_data_from_buf
0x180035cf6  test    rax, rax
0x180035cf9  jnz     short loc_180035D07
0x180035cfb  lea     rcx, [rsp+48h+var_18]
0x180035d00  call    av_buffer_unref
0x180035d05  jmp     short loc_180035CB1
0x180035d07  mov     rax, [rsp+48h+arg_10]
0x180035d0c  add     rsp, 40h
0x180035d10  pop     rbx
0x180035d11  retn
```
