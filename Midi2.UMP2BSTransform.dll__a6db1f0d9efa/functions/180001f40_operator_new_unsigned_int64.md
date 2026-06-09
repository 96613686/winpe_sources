# operator new(unsigned __int64)

- ea: `0x180001f40`
- end: `0x180001f7c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180002330`
- `0x18000236c`
- `0x180004b24`
- `0x180004c34`
- `0x180004d70`
- `0x18000a4f0`
- `0x18000a65c`
- `0x18000e1ec`

## callees

- `0x180001f40`
- `0x180002570`
- `0x1800028a2`
- `0x180002940`
- `0x18000dd20`

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
0x180001f40  push    rbx
0x180001f42  sub     rsp, 20h
0x180001f46  mov     rbx, rcx
0x180001f49  jmp     short loc_180001F5A
0x180001f4b  mov     rcx, rbx
0x180001f4e  call    _o__callnewh_0
0x180001f53  test    eax, eax
0x180001f55  jz      short loc_180001F6A
0x180001f57  mov     rcx, rbx; Size
0x180001f5a  call    _o_malloc_0
0x180001f5f  test    rax, rax
0x180001f62  jz      short loc_180001F4B
0x180001f64  add     rsp, 20h
0x180001f68  pop     rbx
0x180001f69  retn
0x180001f6a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001f6e  jz      short loc_180001F76
0x180001f70  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001f76  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
