# operator new(unsigned __int64)

- ea: `0x1800032f0`
- end: `0x18000332c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003334`
- `0x180007c88`
- `0x1800090dc`
- `0x18000eb3c`
- `0x18000ff2c`

## callees

- `0x1800031ce`
- `0x18000326c`
- `0x1800032f0`
- `0x1800034b4`
- `0x1800034dc`

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
0x1800032f0  push    rbx
0x1800032f2  sub     rsp, 20h
0x1800032f6  mov     rbx, rcx
0x1800032f9  jmp     short loc_18000330A
0x1800032fb  mov     rcx, rbx
0x1800032fe  call    _o__callnewh_0
0x180003303  test    eax, eax
0x180003305  jz      short loc_18000331A
0x180003307  mov     rcx, rbx; Size
0x18000330a  call    _o_malloc_0
0x18000330f  test    rax, rax
0x180003312  jz      short loc_1800032FB
0x180003314  add     rsp, 20h
0x180003318  pop     rbx
0x180003319  retn
0x18000331a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000331e  jz      short loc_180003326
0x180003320  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180003326  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
