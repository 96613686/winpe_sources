# operator new(unsigned __int64)

- ea: `0x180002a94`
- end: `0x180002ad0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180002ad8`
- `0x180002fe0`
- `0x180004af4`
- `0x180004dc0`
- `0x180007534`
- `0x18000f540`

## callees

- `0x180002a94`
- `0x180003210`
- `0x180003238`
- `0x180003582`
- `0x180003620`

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
0x180002a94  push    rbx
0x180002a96  sub     rsp, 20h
0x180002a9a  mov     rbx, rcx
0x180002a9d  jmp     short loc_180002AAE
0x180002a9f  mov     rcx, rbx
0x180002aa2  call    _o__callnewh_0
0x180002aa7  test    eax, eax
0x180002aa9  jz      short loc_180002ABE
0x180002aab  mov     rcx, rbx; Size
0x180002aae  call    _o_malloc_0
0x180002ab3  test    rax, rax
0x180002ab6  jz      short loc_180002A9F
0x180002ab8  add     rsp, 20h
0x180002abc  pop     rbx
0x180002abd  retn
0x180002abe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002ac2  jz      short loc_180002ACA
0x180002ac4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002aca  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
