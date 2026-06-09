# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18001fb00`
- end: `0x18001fb6c`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `108`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180010574`
- `0x180010630`
- `0x18001074c`
- `0x18001ebc8`
- `0x1800201d4`
- `0x180020218`
- `0x18002169c`
- `0x1800217dc`

## callees

- `0x18000b99c`
- `0x18001fb00`
- `0x18001ff1c`

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
0x18001fb00  mov     [rsp+arg_0], rbx
0x18001fb05  mov     [rsp+arg_8], rsi
0x18001fb0a  push    rdi
0x18001fb0b  sub     rsp, 20h
0x18001fb0f  mov     rax, [rcx+820h]
0x18001fb16  mov     rdi, r8
0x18001fb19  sub     rax, [rcx+818h]
0x18001fb20  mov     rsi, rdx
0x18001fb23  mov     rbx, rcx
0x18001fb26  cmp     rax, r8
0x18001fb29  jnb     short loc_18001FB37
0x18001fb2b  mov     rdx, r8; unsigned __int64
0x18001fb2e  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001fb33  test    al, al
0x18001fb35  jz      short loc_18001FB5C
0x18001fb37  mov     rcx, [rbx+818h]; Destination
0x18001fb3e  mov     r9, rdi; SourceSize
0x18001fb41  mov     rdx, [rbx+820h]
0x18001fb48  mov     r8, rsi; Source
0x18001fb4b  sub     rdx, rcx; DestinationSize
0x18001fb4e  call    memcpy_s
0x18001fb53  add     [rbx+818h], rdi
0x18001fb5a  mov     al, 1
0x18001fb5c  mov     rbx, [rsp+28h+arg_0]
0x18001fb61  mov     rsi, [rsp+28h+arg_8]
0x18001fb66  add     rsp, 20h
0x18001fb6a  pop     rdi
0x18001fb6b  retn
```
