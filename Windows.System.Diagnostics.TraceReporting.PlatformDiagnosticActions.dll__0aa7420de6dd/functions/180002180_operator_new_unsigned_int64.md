# operator new(unsigned __int64)

- ea: `0x180002180`
- end: `0x1800021bc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800021c4`
- `0x1800021e8`
- `0x180006ca0`
- `0x180008de0`

## callees

- `0x180001fa6`
- `0x180002040`
- `0x180002180`
- `0x18000221c`
- `0x18000976c`

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
0x180002180  push    rbx
0x180002182  sub     rsp, 20h
0x180002186  mov     rbx, rcx
0x180002189  jmp     short loc_18000219A
0x18000218b  mov     rcx, rbx
0x18000218e  call    _o__callnewh_0
0x180002193  test    eax, eax
0x180002195  jz      short loc_1800021AA
0x180002197  mov     rcx, rbx; Size
0x18000219a  call    _o_malloc_0
0x18000219f  test    rax, rax
0x1800021a2  jz      short loc_18000218B
0x1800021a4  add     rsp, 20h
0x1800021a8  pop     rbx
0x1800021a9  retn
0x1800021aa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800021ae  jz      short loc_1800021B6
0x1800021b0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800021b6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
