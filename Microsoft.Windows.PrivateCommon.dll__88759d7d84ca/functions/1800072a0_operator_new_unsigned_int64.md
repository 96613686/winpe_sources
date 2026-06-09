# operator new(unsigned __int64)

- ea: `0x1800072a0`
- end: `0x1800072db`
- name: `??2@YAPEAX_K@Z`
- size: `59`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800060b0`
- `0x180006190`
- `0x180006370`
- `0x180007070`
- `0x1800072dc`

## callees

- `0x1800072a0`
- `0x180007be8`
- `0x180007c08`
- `0x18000b5b6`
- `0x18000b5bc`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
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
0x1800072a0  push    rbx
0x1800072a2  sub     rsp, 20h
0x1800072a6  mov     rbx, rcx
0x1800072a9  jmp     short loc_1800072BA
0x1800072ab  mov     rcx, rbx; Size
0x1800072ae  call    _callnewh_0
0x1800072b3  test    eax, eax
0x1800072b5  jz      short loc_1800072CA
0x1800072b7  mov     rcx, rbx; Size
0x1800072ba  call    malloc_0
0x1800072bf  test    rax, rax
0x1800072c2  jz      short loc_1800072AB
0x1800072c4  add     rsp, 20h
0x1800072c8  pop     rbx
0x1800072c9  retn
0x1800072ca  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800072ce  jz      short loc_1800072D6
0x1800072d0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800072d6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
