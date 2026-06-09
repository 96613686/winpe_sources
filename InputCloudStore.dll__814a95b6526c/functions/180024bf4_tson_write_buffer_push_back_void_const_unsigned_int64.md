# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180024bf4`
- end: `0x180024c60`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `108`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000986c`
- `0x180009928`
- `0x1800099e8`
- `0x180016934`
- `0x1800169f0`
- `0x180016b0c`
- `0x180023e20`
- `0x18002522c`
- `0x180026204`
- `0x180026338`

## callees

- `0x180007ac8`
- `0x180024bf4`
- `0x180025068`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back(void **this, const void *a2, rsize_t a3)
{
  bool result; // al

  if ( (_BYTE *)this[260] - (_BYTE *)this[259] >= a3
    || (result = tson::write_buffer::reserve((tson::write_buffer *)this, a3)) )
  {
    memcpy_s(this[259], (_BYTE *)this[260] - (_BYTE *)this[259], a2, a3);
    this[259] = (char *)this[259] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180024bf4  mov     [rsp+arg_0], rbx
0x180024bf9  mov     [rsp+arg_8], rsi
0x180024bfe  push    rdi
0x180024bff  sub     rsp, 20h
0x180024c03  mov     rax, [rcx+820h]
0x180024c0a  mov     rdi, r8
0x180024c0d  sub     rax, [rcx+818h]
0x180024c14  mov     rsi, rdx
0x180024c17  mov     rbx, rcx
0x180024c1a  cmp     rax, r8
0x180024c1d  jnb     short loc_180024C2B
0x180024c1f  mov     rdx, r8; unsigned __int64
0x180024c22  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x180024c27  test    al, al
0x180024c29  jz      short loc_180024C50
0x180024c2b  mov     rcx, [rbx+818h]; Destination
0x180024c32  mov     r9, rdi; SourceSize
0x180024c35  mov     rdx, [rbx+820h]
0x180024c3c  mov     r8, rsi; Source
0x180024c3f  sub     rdx, rcx; DestinationSize
0x180024c42  call    memcpy_s
0x180024c47  add     [rbx+818h], rdi
0x180024c4e  mov     al, 1
0x180024c50  mov     rbx, [rsp+28h+arg_0]
0x180024c55  mov     rsi, [rsp+28h+arg_8]
0x180024c5a  add     rsp, 20h
0x180024c5e  pop     rdi
0x180024c5f  retn
```
