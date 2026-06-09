# operator new(unsigned __int64)

- ea: `0x140001ee0`
- end: `0x140001f1c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400064b8`
- `0x1400065a8`

## callees

- `0x140001d76`
- `0x140001e42`
- `0x140001ee0`
- `0x140001f4c`
- `0x140001f74`

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
0x140001ee0  push    rbx
0x140001ee2  sub     rsp, 20h
0x140001ee6  mov     rbx, rcx
0x140001ee9  jmp     short loc_140001EFA
0x140001eeb  mov     rcx, rbx
0x140001eee  call    _o__callnewh_0
0x140001ef3  test    eax, eax
0x140001ef5  jz      short loc_140001F0A
0x140001ef7  mov     rcx, rbx; Size
0x140001efa  call    _o_malloc_0
0x140001eff  test    rax, rax
0x140001f02  jz      short loc_140001EEB
0x140001f04  add     rsp, 20h
0x140001f08  pop     rbx
0x140001f09  retn
0x140001f0a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140001f0e  jz      short loc_140001F16
0x140001f10  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001f16  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
