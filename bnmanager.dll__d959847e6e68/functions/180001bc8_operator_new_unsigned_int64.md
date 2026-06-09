# operator new(unsigned __int64)

- ea: `0x180001bc8`
- end: `0x180001c04`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180001c0c`
- `0x1800025d0`
- `0x1800030a0`
- `0x18000322c`
- `0x180003be4`

## callees

- `0x180001bc8`
- `0x180002140`
- `0x1800021c6`
- `0x180002260`
- `0x18000bbd0`

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
0x180001bc8  push    rbx
0x180001bca  sub     rsp, 20h
0x180001bce  mov     rbx, rcx
0x180001bd1  jmp     short loc_180001BE2
0x180001bd3  mov     rcx, rbx
0x180001bd6  call    _o__callnewh_0
0x180001bdb  test    eax, eax
0x180001bdd  jz      short loc_180001BF2
0x180001bdf  mov     rcx, rbx; Size
0x180001be2  call    _o_malloc_0
0x180001be7  test    rax, rax
0x180001bea  jz      short loc_180001BD3
0x180001bec  add     rsp, 20h
0x180001bf0  pop     rbx
0x180001bf1  retn
0x180001bf2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001bf6  jz      short loc_180001BFE
0x180001bf8  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001bfe  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
