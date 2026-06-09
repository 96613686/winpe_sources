# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000dc18`
- end: `0x18000dc84`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `108`
- prototype: `bool __fastcall(void **this, const void *, rsize_t)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a940`
- `0x18000a998`
- `0x18000a9f0`
- `0x18000da94`
- `0x18000dd70`
- `0x18000e734`
- `0x18000e874`

## callees

- `0x18000a0b8`
- `0x18000dc18`
- `0x18000dca8`

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
0x18000dc18  mov     [rsp+arg_0], rbx
0x18000dc1d  mov     [rsp+arg_8], rsi
0x18000dc22  push    rdi
0x18000dc23  sub     rsp, 20h
0x18000dc27  mov     rax, [rcx+820h]
0x18000dc2e  mov     rdi, r8
0x18000dc31  sub     rax, [rcx+818h]
0x18000dc38  mov     rsi, rdx
0x18000dc3b  mov     rbx, rcx
0x18000dc3e  cmp     rax, r8
0x18000dc41  jnb     short loc_18000DC4F
0x18000dc43  mov     rdx, r8; unsigned __int64
0x18000dc46  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dc4b  test    al, al
0x18000dc4d  jz      short loc_18000DC74
0x18000dc4f  mov     rcx, [rbx+818h]; Destination
0x18000dc56  mov     r9, rdi; SourceSize
0x18000dc59  mov     rdx, [rbx+820h]
0x18000dc60  mov     r8, rsi; Source
0x18000dc63  sub     rdx, rcx; DestinationSize
0x18000dc66  call    memcpy_s
0x18000dc6b  add     [rbx+818h], rdi
0x18000dc72  mov     al, 1
0x18000dc74  mov     rbx, [rsp+28h+arg_0]
0x18000dc79  mov     rsi, [rsp+28h+arg_8]
0x18000dc7e  add     rsp, 20h
0x18000dc82  pop     rdi
0x18000dc83  retn
```
