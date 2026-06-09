# operator new(unsigned __int64)

- ea: `0x180001aac`
- end: `0x180001ae8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180001af0`
- `0x180009494`
- `0x18000b660`
- `0x18000bd08`
- `0x18000c238`

## callees

- `0x180001aac`
- `0x180001f98`
- `0x180002026`
- `0x1800020c0`
- `0x18000b0cc`

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
0x180001aac  push    rbx
0x180001aae  sub     rsp, 20h
0x180001ab2  mov     rbx, rcx
0x180001ab5  jmp     short loc_180001AC6
0x180001ab7  mov     rcx, rbx
0x180001aba  call    _o__callnewh_0
0x180001abf  test    eax, eax
0x180001ac1  jz      short loc_180001AD6
0x180001ac3  mov     rcx, rbx; Size
0x180001ac6  call    _o_malloc_0
0x180001acb  test    rax, rax
0x180001ace  jz      short loc_180001AB7
0x180001ad0  add     rsp, 20h
0x180001ad4  pop     rbx
0x180001ad5  retn
0x180001ad6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001ada  jz      short loc_180001AE2
0x180001adc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001ae2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
