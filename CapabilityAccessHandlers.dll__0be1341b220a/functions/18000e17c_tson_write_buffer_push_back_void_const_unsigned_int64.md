# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000e17c`
- end: `0x18000e1e8`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `108`
- prototype: `bool __fastcall(void **this, const void *, rsize_t)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a810`
- `0x18000a868`
- `0x18000a8c0`
- `0x18000aad0`
- `0x18000df0c`
- `0x18000e324`
- `0x18000e368`
- `0x18000f168`
- `0x18000f2a8`

## callees

- `0x1800034d8`
- `0x18000e17c`
- `0x18000e20c`

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
0x18000e17c  mov     [rsp+arg_0], rbx
0x18000e181  mov     [rsp+arg_8], rsi
0x18000e186  push    rdi
0x18000e187  sub     rsp, 20h
0x18000e18b  mov     rax, [rcx+820h]
0x18000e192  mov     rdi, r8
0x18000e195  sub     rax, [rcx+818h]
0x18000e19c  mov     rsi, rdx
0x18000e19f  mov     rbx, rcx
0x18000e1a2  cmp     rax, r8
0x18000e1a5  jnb     short loc_18000E1B3
0x18000e1a7  mov     rdx, r8; unsigned __int64
0x18000e1aa  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000e1af  test    al, al
0x18000e1b1  jz      short loc_18000E1D8
0x18000e1b3  mov     rcx, [rbx+818h]; Destination
0x18000e1ba  mov     r9, rdi; SourceSize
0x18000e1bd  mov     rdx, [rbx+820h]
0x18000e1c4  mov     r8, rsi; Source
0x18000e1c7  sub     rdx, rcx; DestinationSize
0x18000e1ca  call    memcpy_s
0x18000e1cf  add     [rbx+818h], rdi
0x18000e1d6  mov     al, 1
0x18000e1d8  mov     rbx, [rsp+28h+arg_0]
0x18000e1dd  mov     rsi, [rsp+28h+arg_8]
0x18000e1e2  add     rsp, 20h
0x18000e1e6  pop     rdi
0x18000e1e7  retn
```
