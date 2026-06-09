# operator new(unsigned __int64)

- ea: `0x180001c24`
- end: `0x180001c60`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003f10`
- `0x180007080`
- `0x180007398`
- `0x1800074d8`
- `0x18000a5f0`
- `0x180010634`
- `0x180011028`

## callees

- `0x180001c24`
- `0x180002240`
- `0x180002596`
- `0x180002630`
- `0x1800078d8`

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
0x180001c24  push    rbx
0x180001c26  sub     rsp, 20h
0x180001c2a  mov     rbx, rcx
0x180001c2d  jmp     short loc_180001C3E
0x180001c2f  mov     rcx, rbx
0x180001c32  call    _o__callnewh_0
0x180001c37  test    eax, eax
0x180001c39  jz      short loc_180001C4E
0x180001c3b  mov     rcx, rbx; Size
0x180001c3e  call    _o_malloc_0
0x180001c43  test    rax, rax
0x180001c46  jz      short loc_180001C2F
0x180001c48  add     rsp, 20h
0x180001c4c  pop     rbx
0x180001c4d  retn
0x180001c4e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001c52  jz      short loc_180001C5A
0x180001c54  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001c5a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
