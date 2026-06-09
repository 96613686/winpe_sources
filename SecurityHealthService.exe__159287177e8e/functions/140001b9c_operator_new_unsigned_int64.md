# operator new(unsigned __int64)

- ea: `0x140001b9c`
- end: `0x140001bd8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x14000162c`
- `0x140002474`
- `0x140007538`
- `0x14000cc78`
- `0x14000ce04`
- `0x14000cf98`
- `0x14000d15c`
- `0x14000de3c`

## callees

- `0x140001b9c`
- `0x140001e80`
- `0x140001fba`
- `0x140001fc6`
- `0x14000d9c8`

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
0x140001b9c  push    rbx
0x140001b9e  sub     rsp, 20h
0x140001ba2  mov     rbx, rcx
0x140001ba5  jmp     short loc_140001BB6
0x140001ba7  mov     rcx, rbx; Size
0x140001baa  call    _callnewh_0
0x140001baf  test    eax, eax
0x140001bb1  jz      short loc_140001BC6
0x140001bb3  mov     rcx, rbx; Size
0x140001bb6  call    malloc_0
0x140001bbb  test    rax, rax
0x140001bbe  jz      short loc_140001BA7
0x140001bc0  add     rsp, 20h
0x140001bc4  pop     rbx
0x140001bc5  retn
0x140001bc6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140001bca  jz      short loc_140001BD2
0x140001bcc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001bd2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
