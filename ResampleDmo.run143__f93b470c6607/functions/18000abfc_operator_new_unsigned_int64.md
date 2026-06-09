# operator new(unsigned __int64)

- ea: `0x18000abfc`
- end: `0x18000ac38`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `18`
- callee_count: `5`
- tags: ``

## callers

- `0x180006590`
- `0x180007850`
- `0x180007cb0`
- `0x180007e70`
- `0x1800085e0`
- `0x1800092c4`
- `0x18000abb4`
- `0x180011040`
- `0x18006cc10`
- `0x18006d8b0`
- `0x18007ff40`
- `0x180080700`
- `0x1800807f0`
- `0x180081478`
- `0x180081574`
- `0x180081620`
- `0x180081f70`
- `0x180083cd0`

## callees

- `0x18000abfc`
- `0x18000b2f4`
- `0x18000b31c`
- `0x18000b67a`
- `0x18000b724`

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
0x18000abfc  push    rbx
0x18000abfe  sub     rsp, 20h
0x18000ac02  mov     rbx, rcx
0x18000ac05  jmp     short loc_18000AC16
0x18000ac07  mov     rcx, rbx
0x18000ac0a  call    _o__callnewh_0
0x18000ac0f  test    eax, eax
0x18000ac11  jz      short loc_18000AC26
0x18000ac13  mov     rcx, rbx; Size
0x18000ac16  call    _o_malloc_0
0x18000ac1b  test    rax, rax
0x18000ac1e  jz      short loc_18000AC07
0x18000ac20  add     rsp, 20h
0x18000ac24  pop     rbx
0x18000ac25  retn
0x18000ac26  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ac2a  jz      short loc_18000AC32
0x18000ac2c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000ac32  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
