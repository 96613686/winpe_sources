# operator new(unsigned __int64)

- ea: `0x180001650`
- end: `0x18000168c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x180001f8c`
- `0x18000213c`
- `0x180006890`
- `0x18000852c`
- `0x180008658`
- `0x1800099d8`
- `0x18000a65c`
- `0x18000a9e0`
- `0x18000ab90`
- `0x18000b1f4`
- `0x18000b2cc`
- `0x18000b348`

## callees

- `0x180001650`
- `0x180001cc4`
- `0x180002006`
- `0x1800020a0`
- `0x180007d74`

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
0x180001650  push    rbx
0x180001652  sub     rsp, 20h
0x180001656  mov     rbx, rcx
0x180001659  jmp     short loc_18000166A
0x18000165b  mov     rcx, rbx
0x18000165e  call    _o__callnewh_0
0x180001663  test    eax, eax
0x180001665  jz      short loc_18000167A
0x180001667  mov     rcx, rbx; Size
0x18000166a  call    _o_malloc_0
0x18000166f  test    rax, rax
0x180001672  jz      short loc_18000165B
0x180001674  add     rsp, 20h
0x180001678  pop     rbx
0x180001679  retn
0x18000167a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000167e  jz      short loc_180001686
0x180001680  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001686  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
