# operator new(unsigned __int64)

- ea: `0x180001f7c`
- end: `0x180001fb8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001fc0`
- `0x180005bc4`

## callees

- `0x180001e56`
- `0x180001eda`
- `0x180001f7c`
- `0x180002134`
- `0x18000215c`

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
0x180001f7c  push    rbx
0x180001f7e  sub     rsp, 20h
0x180001f82  mov     rbx, rcx
0x180001f85  jmp     short loc_180001F96
0x180001f87  mov     rcx, rbx
0x180001f8a  call    _o__callnewh_0
0x180001f8f  test    eax, eax
0x180001f91  jz      short loc_180001FA6
0x180001f93  mov     rcx, rbx; Size
0x180001f96  call    _o_malloc_0
0x180001f9b  test    rax, rax
0x180001f9e  jz      short loc_180001F87
0x180001fa0  add     rsp, 20h
0x180001fa4  pop     rbx
0x180001fa5  retn
0x180001fa6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001faa  jz      short loc_180001FB2
0x180001fac  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001fb2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
