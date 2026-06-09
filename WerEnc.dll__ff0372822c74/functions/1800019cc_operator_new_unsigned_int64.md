# operator new(unsigned __int64)

- ea: `0x1800019cc`
- end: `0x180001a08`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001430`
- `0x180001a10`

## callees

- `0x1800019cc`
- `0x180001e54`
- `0x180001e7c`
- `0x180001f60`
- `0x180001fc0`

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
0x1800019cc  push    rbx
0x1800019ce  sub     rsp, 20h
0x1800019d2  mov     rbx, rcx
0x1800019d5  jmp     short loc_1800019E6
0x1800019d7  mov     rcx, rbx
0x1800019da  call    _o__callnewh_0
0x1800019df  test    eax, eax
0x1800019e1  jz      short loc_1800019F6
0x1800019e3  mov     rcx, rbx; Size
0x1800019e6  call    _o_malloc_0
0x1800019eb  test    rax, rax
0x1800019ee  jz      short loc_1800019D7
0x1800019f0  add     rsp, 20h
0x1800019f4  pop     rbx
0x1800019f5  retn
0x1800019f6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800019fa  jz      short loc_180001A02
0x1800019fc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001a02  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
