# operator new(unsigned __int64)

- ea: `0x1800025c4`
- end: `0x180002600`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800025a0`
- `0x180002a88`
- `0x18000d5f0`

## callees

- `0x1800025c4`
- `0x180002b44`
- `0x180002b6c`
- `0x180002bf6`
- `0x180002c90`

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
0x1800025c4  push    rbx
0x1800025c6  sub     rsp, 20h
0x1800025ca  mov     rbx, rcx
0x1800025cd  jmp     short loc_1800025DE
0x1800025cf  mov     rcx, rbx
0x1800025d2  call    _o__callnewh_0
0x1800025d7  test    eax, eax
0x1800025d9  jz      short loc_1800025EE
0x1800025db  mov     rcx, rbx; Size
0x1800025de  call    _o_malloc_0
0x1800025e3  test    rax, rax
0x1800025e6  jz      short loc_1800025CF
0x1800025e8  add     rsp, 20h
0x1800025ec  pop     rbx
0x1800025ed  retn
0x1800025ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800025f2  jz      short loc_1800025FA
0x1800025f4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800025fa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
