# operator new(unsigned __int64)

- ea: `0x180001ed8`
- end: `0x180001f14`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e9c`
- `0x180001ea8`
- `0x180012620`
- `0x180012710`
- `0x180012af4`
- `0x180014e14`
- `0x1800166e8`

## callees

- `0x180001ed8`
- `0x180002504`
- `0x18000252c`
- `0x1800025fe`
- `0x180002690`

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
0x180001ed8  push    rbx
0x180001eda  sub     rsp, 20h
0x180001ede  mov     rbx, rcx
0x180001ee1  jmp     short loc_180001EF2
0x180001ee3  mov     rcx, rbx
0x180001ee6  call    _o__callnewh_0
0x180001eeb  test    eax, eax
0x180001eed  jz      short loc_180001F02
0x180001eef  mov     rcx, rbx; Size
0x180001ef2  call    _o_malloc_0
0x180001ef7  test    rax, rax
0x180001efa  jz      short loc_180001EE3
0x180001efc  add     rsp, 20h
0x180001f00  pop     rbx
0x180001f01  retn
0x180001f02  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001f06  jz      short loc_180001F0E
0x180001f08  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001f0e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
