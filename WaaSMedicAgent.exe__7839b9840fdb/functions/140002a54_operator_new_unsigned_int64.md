# operator new(unsigned __int64)

- ea: `0x140002a54`
- end: `0x140002a90`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140002490`
- `0x140002e1c`
- `0x140004218`
- `0x14000b984`
- `0x140010c94`

## callees

- `0x140002a54`
- `0x140003180`
- `0x14000357e`
- `0x140003660`
- `0x1400073e4`

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
0x140002a54  push    rbx
0x140002a56  sub     rsp, 20h
0x140002a5a  mov     rbx, rcx
0x140002a5d  jmp     short loc_140002A6E
0x140002a5f  mov     rcx, rbx
0x140002a62  call    _o__callnewh_0
0x140002a67  test    eax, eax
0x140002a69  jz      short loc_140002A7E
0x140002a6b  mov     rcx, rbx; Size
0x140002a6e  call    _o_malloc_0
0x140002a73  test    rax, rax
0x140002a76  jz      short loc_140002A5F
0x140002a78  add     rsp, 20h
0x140002a7c  pop     rbx
0x140002a7d  retn
0x140002a7e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140002a82  jz      short loc_140002A8A
0x140002a84  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002a8a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
