# operator new(unsigned __int64)

- ea: `0x14000192c`
- end: `0x140001968`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001360`

## callees

- `0x14000192c`
- `0x140001d84`
- `0x140001dac`
- `0x140001ea8`
- `0x140001f68`

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
0x14000192c  push    rbx
0x14000192e  sub     rsp, 20h
0x140001932  mov     rbx, rcx
0x140001935  jmp     short loc_140001946
0x140001937  mov     rcx, rbx
0x14000193a  call    _o__callnewh_0
0x14000193f  test    eax, eax
0x140001941  jz      short loc_140001956
0x140001943  mov     rcx, rbx; Size
0x140001946  call    _o_malloc_0
0x14000194b  test    rax, rax
0x14000194e  jz      short loc_140001937
0x140001950  add     rsp, 20h
0x140001954  pop     rbx
0x140001955  retn
0x140001956  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000195a  jz      short loc_140001962
0x14000195c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001962  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
