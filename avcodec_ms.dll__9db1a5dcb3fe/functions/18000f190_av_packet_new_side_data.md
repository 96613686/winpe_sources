# av_packet_new_side_data

- ea: `0x18000f190`
- end: `0x18000f1ff`
- name: `av_packet_new_side_data`
- size: `111`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000edf0`

## callees

- `0x18000ecb0`
- `0x18000f190`
- `0x180022716`
- `0x18002271c`

## pseudocode

```c
__int64 __fastcall av_packet_new_side_data(__int64 a1, int a2, unsigned __int64 a3)
{
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 > 0xFFFFFFFFFFFFFFBFuLL )
    return 0;
  _mm_lfence();
  v7 = av_mallocz(a3 + 64);
  if ( !v7 )
    return 0;
  _mm_lfence();
  if ( (int)av_packet_add_side_data(a1, a2, v7, a3) < 0 )
  {
    av_freep(&v7);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000f190  mov     [rsp+arg_0], rbx
0x18000f195  mov     [rsp+arg_8], rsi
0x18000f19a  push    rdi
0x18000f19b  sub     rsp, 20h
0x18000f19f  mov     rbx, r8
0x18000f1a2  mov     edi, edx
0x18000f1a4  mov     rsi, rcx
0x18000f1a7  cmp     r8, 0FFFFFFFFFFFFFFBFh
0x18000f1ab  ja      short loc_18000F1E6
0x18000f1ad  lfence
0x18000f1b0  lea     rcx, [r8+40h]
0x18000f1b4  call    av_mallocz
0x18000f1b9  mov     [rsp+28h+arg_10], rax
0x18000f1be  test    rax, rax
0x18000f1c1  jz      short loc_18000F1E6
0x18000f1c3  lfence
0x18000f1c6  mov     r8, [rsp+28h+arg_10]
0x18000f1cb  mov     r9, rbx
0x18000f1ce  mov     edx, edi
0x18000f1d0  mov     rcx, rsi
0x18000f1d3  call    av_packet_add_side_data
0x18000f1d8  test    eax, eax
0x18000f1da  jns     short loc_18000F1F8
0x18000f1dc  lea     rcx, [rsp+28h+arg_10]
0x18000f1e1  call    av_freep
0x18000f1e6  xor     eax, eax
0x18000f1e8  mov     rbx, [rsp+28h+arg_0]
0x18000f1ed  mov     rsi, [rsp+28h+arg_8]
0x18000f1f2  add     rsp, 20h
0x18000f1f6  pop     rdi
0x18000f1f7  retn
0x18000f1f8  mov     rax, [rsp+28h+arg_10]
0x18000f1fd  jmp     short loc_18000F1E8
```
