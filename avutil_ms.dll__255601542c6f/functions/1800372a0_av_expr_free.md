# av_expr_free

- ea: `0x1800372a0`
- end: `0x1800372fe`
- name: `av_expr_free`
- size: `94`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800372a0`
- `0x180037300`
- `0x180037600`
- `0x180038784`
- `0x180038850`
- `0x180038958`
- `0x18003927c`
- `0x18003932c`

## callees

- `0x1800372a0`
- `0x1800449d0`

## pseudocode

```c
void __fastcall av_expr_free(__int64 a1)
{
  __m128i v1; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v1.m128i_i64[0] = a1;
    av_expr_free(*(_QWORD *)(a1 + 32));
    av_expr_free(*(_QWORD *)(v1.m128i_i64[0] + 40));
    av_expr_free(*(_QWORD *)(v1.m128i_i64[0] + 48));
    av_freep((__m128i *)(v1.m128i_i64[0] + 56));
    av_freep((__m128i *)(v1.m128i_i64[0] + 64));
    av_freep(&v1);
  }
}

```

## disassembly

```asm
0x1800372a0  test    rcx, rcx
0x1800372a3  jz      short locret_1800372FD
0x1800372a5  mov     qword ptr [rsp+arg_0], rcx
0x1800372aa  sub     rsp, 28h
0x1800372ae  mov     rcx, [rcx+20h]
0x1800372b2  call    av_expr_free
0x1800372b7  mov     rcx, qword ptr [rsp+28h+arg_0]
0x1800372bc  mov     rcx, [rcx+28h]
0x1800372c0  call    av_expr_free
0x1800372c5  mov     rcx, qword ptr [rsp+28h+arg_0]
0x1800372ca  mov     rcx, [rcx+30h]
0x1800372ce  call    av_expr_free
0x1800372d3  mov     rcx, qword ptr [rsp+28h+arg_0]
0x1800372d8  add     rcx, 38h ; '8'
0x1800372dc  call    av_freep
0x1800372e1  mov     rcx, qword ptr [rsp+28h+arg_0]
0x1800372e6  add     rcx, 40h ; '@'
0x1800372ea  call    av_freep
0x1800372ef  lea     rcx, [rsp+28h+arg_0]
0x1800372f4  call    av_freep
0x1800372f9  add     rsp, 28h
0x1800372fd  retn
```
