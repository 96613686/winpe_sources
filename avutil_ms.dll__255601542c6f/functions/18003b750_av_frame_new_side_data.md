# av_frame_new_side_data

- ea: `0x18003b750`
- end: `0x18003b7a5`
- name: `av_frame_new_side_data`
- size: `85`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002a730`
- `0x180036840`
- `0x18003a620`
- `0x18003bfe0`
- `0x18003cdd0`
- `0x18003eb60`
- `0x1800439c0`
- `0x180043a50`
- `0x1800515a0`

## callees

- `0x18002ebe0`
- `0x18002f210`
- `0x18003b750`
- `0x180050d2c`

## pseudocode

```c
__int64 __fastcall av_frame_new_side_data(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = av_buffer_alloc(a3);
  v5 = sub_180050D2C(a1 + 264, a1 + 272, a2, v7);
  if ( !v5 )
    av_buffer_unref(&v7);
  return v5;
}

```

## disassembly

```asm
0x18003b750  mov     [rsp+arg_8], rbx
0x18003b755  push    rdi
0x18003b756  sub     rsp, 20h
0x18003b75a  mov     rbx, rcx
0x18003b75d  mov     edi, edx
0x18003b75f  mov     rcx, r8
0x18003b762  call    av_buffer_alloc
0x18003b767  lea     rdx, [rbx+110h]
0x18003b76e  mov     [rsp+28h+arg_0], rax
0x18003b773  lea     rcx, [rbx+108h]
0x18003b77a  mov     r9, rax
0x18003b77d  mov     r8d, edi
0x18003b780  call    sub_180050D2C
0x18003b785  mov     rbx, rax
0x18003b788  test    rax, rax
0x18003b78b  jnz     short loc_18003B797
0x18003b78d  lea     rcx, [rsp+28h+arg_0]
0x18003b792  call    av_buffer_unref
0x18003b797  mov     rax, rbx
0x18003b79a  mov     rbx, [rsp+28h+arg_8]
0x18003b79f  add     rsp, 20h
0x18003b7a3  pop     rdi
0x18003b7a4  retn
```
