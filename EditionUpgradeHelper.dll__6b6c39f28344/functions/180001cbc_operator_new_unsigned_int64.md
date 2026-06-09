# operator new(unsigned __int64)

- ea: `0x180001cbc`
- end: `0x180001cf8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d00`
- `0x180001d0c`
- `0x180009cac`

## callees

- `0x180001cbc`
- `0x180002324`
- `0x18000234c`
- `0x18000241e`
- `0x1800024b0`

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
0x180001cbc  push    rbx
0x180001cbe  sub     rsp, 20h
0x180001cc2  mov     rbx, rcx
0x180001cc5  jmp     short loc_180001CD6
0x180001cc7  mov     rcx, rbx
0x180001cca  call    _o__callnewh_0
0x180001ccf  test    eax, eax
0x180001cd1  jz      short loc_180001CE6
0x180001cd3  mov     rcx, rbx; Size
0x180001cd6  call    _o_malloc_0
0x180001cdb  test    rax, rax
0x180001cde  jz      short loc_180001CC7
0x180001ce0  add     rsp, 20h
0x180001ce4  pop     rbx
0x180001ce5  retn
0x180001ce6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001cea  jz      short loc_180001CF2
0x180001cec  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001cf2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
