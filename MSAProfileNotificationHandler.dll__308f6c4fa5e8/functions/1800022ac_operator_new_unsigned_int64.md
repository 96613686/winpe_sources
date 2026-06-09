# operator new(unsigned __int64)

- ea: `0x1800022ac`
- end: `0x1800022e8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ce0`
- `0x1800022f0`

## callees

- `0x1800022ac`
- `0x180002724`
- `0x18000274c`
- `0x18000283c`
- `0x1800028c0`

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
0x1800022ac  push    rbx
0x1800022ae  sub     rsp, 20h
0x1800022b2  mov     rbx, rcx
0x1800022b5  jmp     short loc_1800022C6
0x1800022b7  mov     rcx, rbx
0x1800022ba  call    _o__callnewh_0
0x1800022bf  test    eax, eax
0x1800022c1  jz      short loc_1800022D6
0x1800022c3  mov     rcx, rbx; Size
0x1800022c6  call    _o_malloc_0
0x1800022cb  test    rax, rax
0x1800022ce  jz      short loc_1800022B7
0x1800022d0  add     rsp, 20h
0x1800022d4  pop     rbx
0x1800022d5  retn
0x1800022d6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800022da  jz      short loc_1800022E2
0x1800022dc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800022e2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
