# av_packet_side_data_free

- ea: `0x18000f490`
- end: `0x18000f4ec`
- name: `av_packet_side_data_free`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180006660`
- `0x180006908`

## callees

- `0x18000f490`
- `0x18002271c`
- `0x18002277c`

## pseudocode

```c
__int64 __fastcall av_packet_side_data_free(_QWORD *a1, int *a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rbx
  __int64 result; // rax

  v2 = *a2;
  v4 = (_QWORD *)*a1;
  if ( v2 > 0 )
  {
    do
    {
      av_free(*v4);
      v4 += 3;
      --v2;
    }
    while ( v2 );
  }
  result = av_freep(a1);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x18000f490  mov     [rsp+arg_0], rbx
0x18000f495  mov     [rsp+arg_8], rsi
0x18000f49a  mov     [rsp+arg_10], rdi
0x18000f49f  push    r14
0x18000f4a1  sub     rsp, 20h
0x18000f4a5  movsxd  rdi, dword ptr [rdx]
0x18000f4a8  mov     rsi, rdx
0x18000f4ab  mov     rbx, [rcx]
0x18000f4ae  mov     r14, rcx
0x18000f4b1  test    rdi, rdi
0x18000f4b4  jle     short loc_18000F4C8
0x18000f4b6  mov     rcx, [rbx]
0x18000f4b9  call    av_free
0x18000f4be  lea     rbx, [rbx+18h]
0x18000f4c2  sub     rdi, 1
0x18000f4c6  jnz     short loc_18000F4B6
0x18000f4c8  mov     rcx, r14
0x18000f4cb  call    av_freep
0x18000f4d0  mov     rbx, [rsp+28h+arg_0]
0x18000f4d5  mov     rdi, [rsp+28h+arg_10]
0x18000f4da  mov     dword ptr [rsi], 0
0x18000f4e0  mov     rsi, [rsp+28h+arg_8]
0x18000f4e5  add     rsp, 20h
0x18000f4e9  pop     r14
0x18000f4eb  retn
```
