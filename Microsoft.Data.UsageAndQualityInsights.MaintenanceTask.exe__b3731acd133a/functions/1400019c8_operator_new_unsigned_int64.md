# operator new(unsigned __int64)

- ea: `0x1400019c8`
- end: `0x140001a04`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400094c0`
- `0x1400095cc`
- `0x140009760`

## callees

- `0x1400019c8`
- `0x140002054`
- `0x1400020fe`
- `0x1400021e0`
- `0x14000af2c`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400019c8  push    rbx
0x1400019ca  sub     rsp, 20h
0x1400019ce  mov     rbx, rcx
0x1400019d1  jmp     short loc_1400019E2
0x1400019d3  mov     rcx, rbx
0x1400019d6  call    _o__callnewh_0
0x1400019db  test    eax, eax
0x1400019dd  jz      short loc_1400019F2
0x1400019df  mov     rcx, rbx; Size
0x1400019e2  call    _o_malloc_0
0x1400019e7  test    rax, rax
0x1400019ea  jz      short loc_1400019D3
0x1400019ec  add     rsp, 20h
0x1400019f0  pop     rbx
0x1400019f1  retn
0x1400019f2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400019f6  jz      short loc_1400019FE
0x1400019f8  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400019fe  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
