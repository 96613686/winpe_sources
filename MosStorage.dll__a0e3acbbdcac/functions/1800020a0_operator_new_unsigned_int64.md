# operator new(unsigned __int64)

- ea: `0x1800020a0`
- end: `0x1800020dc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002cc4`
- `0x18000694c`
- `0x180009790`
- `0x18000aa8c`
- `0x18000ac28`
- `0x18000c860`
- `0x18000d4e4`

## callees

- `0x1800020a0`
- `0x1800026ac`
- `0x18000274e`
- `0x1800027d2`
- `0x18000abd0`

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
0x1800020a0  push    rbx
0x1800020a2  sub     rsp, 20h
0x1800020a6  mov     rbx, rcx
0x1800020a9  jmp     short loc_1800020BA
0x1800020ab  mov     rcx, rbx
0x1800020ae  call    _o__callnewh_0
0x1800020b3  test    eax, eax
0x1800020b5  jz      short loc_1800020CA
0x1800020b7  mov     rcx, rbx; Size
0x1800020ba  call    _o_malloc_0
0x1800020bf  test    rax, rax
0x1800020c2  jz      short loc_1800020AB
0x1800020c4  add     rsp, 20h
0x1800020c8  pop     rbx
0x1800020c9  retn
0x1800020ca  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800020ce  jz      short loc_1800020D6
0x1800020d0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800020d6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
