# av_packet_side_data_new

- ea: `0x18000f760`
- end: `0x18000f7f4`
- name: `av_packet_side_data_new`
- size: `148`
- prototype: `_QWORD *__fastcall(__int64 *, int *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000a670`

## callees

- `0x18000f760`
- `0x18000fcd4`
- `0x18002271c`
- `0x1800228dc`
- `0x180024280`

## pseudocode

```c
_QWORD *__fastcall av_packet_side_data_new(__int64 *a1, int *a2, int a3, unsigned __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // r9
  _QWORD *v10; // rbx
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  if ( a4 > 0xFFFFFFFFFFFFFFBFuLL )
    return 0;
  _mm_lfence();
  v8 = av_malloc(a4 + 64);
  v12 = v8;
  if ( !v8 )
    return 0;
  _mm_lfence();
  sub_180024280(v8 + a4, 0, 64, v9);
  v10 = av_packet_side_data_add_0(a1, a2, a3, v12, a4);
  if ( !v10 )
    av_freep(&v12);
  return v10;
}

```

## disassembly

```asm
0x18000f760  mov     [rsp+arg_0], rbx
0x18000f765  mov     [rsp+arg_8], rbp
0x18000f76a  mov     [rsp+arg_10], rsi
0x18000f76f  push    rdi
0x18000f770  sub     rsp, 30h
0x18000f774  mov     rbx, r9
0x18000f777  mov     edi, r8d
0x18000f77a  mov     rsi, rdx
0x18000f77d  mov     rbp, rcx
0x18000f780  cmp     r9, 0FFFFFFFFFFFFFFBFh
0x18000f784  ja      short loc_18000F7DD
0x18000f786  lfence
0x18000f789  lea     rcx, [r9+40h]
0x18000f78d  call    av_malloc
0x18000f792  mov     [rsp+38h+arg_18], rax
0x18000f797  test    rax, rax
0x18000f79a  jz      short loc_18000F7DD
0x18000f79c  lfence
0x18000f79f  xor     edx, edx
0x18000f7a1  lea     rcx, [rax+rbx]
0x18000f7a5  lea     r8d, [rdx+40h]
0x18000f7a9  call    sub_180024280
0x18000f7ae  mov     r9, [rsp+38h+arg_18]
0x18000f7b3  mov     r8d, edi
0x18000f7b6  mov     rdx, rsi
0x18000f7b9  mov     [rsp+38h+var_18], rbx
0x18000f7be  mov     rcx, rbp
0x18000f7c1  call    av_packet_side_data_add_0
0x18000f7c6  mov     rbx, rax
0x18000f7c9  test    rax, rax
0x18000f7cc  jnz     short loc_18000F7D8
0x18000f7ce  lea     rcx, [rsp+38h+arg_18]
0x18000f7d3  call    av_freep
0x18000f7d8  mov     rax, rbx
0x18000f7db  jmp     short loc_18000F7DF
0x18000f7dd  xor     eax, eax
0x18000f7df  mov     rbx, [rsp+38h+arg_0]
0x18000f7e4  mov     rbp, [rsp+38h+arg_8]
0x18000f7e9  mov     rsi, [rsp+38h+arg_10]
0x18000f7ee  add     rsp, 30h
0x18000f7f2  pop     rdi
0x18000f7f3  retn
```
