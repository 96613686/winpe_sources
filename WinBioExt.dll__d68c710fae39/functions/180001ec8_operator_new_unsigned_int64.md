# operator new(unsigned __int64)

- ea: `0x180001ec8`
- end: `0x180001f04`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001a1c`
- `0x180006700`
- `0x180006b40`
- `0x180006edc`

## callees

- `0x180001ec8`
- `0x180001f0c`
- `0x180001f34`
- `0x180001fc6`
- `0x180002060`

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
0x180001ec8  push    rbx
0x180001eca  sub     rsp, 20h
0x180001ece  mov     rbx, rcx
0x180001ed1  jmp     short loc_180001EE2
0x180001ed3  mov     rcx, rbx
0x180001ed6  call    _o__callnewh_0
0x180001edb  test    eax, eax
0x180001edd  jz      short loc_180001EF2
0x180001edf  mov     rcx, rbx; Size
0x180001ee2  call    _o_malloc_0
0x180001ee7  test    rax, rax
0x180001eea  jz      short loc_180001ED3
0x180001eec  add     rsp, 20h
0x180001ef0  pop     rbx
0x180001ef1  retn
0x180001ef2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001ef6  jz      short loc_180001EFE
0x180001ef8  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001efe  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
