# operator new(unsigned __int64)

- ea: `0x180002b5c`
- end: `0x180002b98`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b38`
- `0x1800080c0`
- `0x1800081d0`
- `0x180008458`

## callees

- `0x180002b5c`
- `0x180003148`
- `0x1800031e6`
- `0x180003280`
- `0x18000ae0c`

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
0x180002b5c  push    rbx
0x180002b5e  sub     rsp, 20h
0x180002b62  mov     rbx, rcx
0x180002b65  jmp     short loc_180002B76
0x180002b67  mov     rcx, rbx
0x180002b6a  call    _o__callnewh_0
0x180002b6f  test    eax, eax
0x180002b71  jz      short loc_180002B86
0x180002b73  mov     rcx, rbx; Size
0x180002b76  call    _o_malloc_0
0x180002b7b  test    rax, rax
0x180002b7e  jz      short loc_180002B67
0x180002b80  add     rsp, 20h
0x180002b84  pop     rbx
0x180002b85  retn
0x180002b86  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002b8a  jz      short loc_180002B92
0x180002b8c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002b92  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
