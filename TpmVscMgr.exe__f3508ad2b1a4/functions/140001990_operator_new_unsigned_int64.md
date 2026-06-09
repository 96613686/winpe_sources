# operator new(unsigned __int64)

- ea: `0x140001990`
- end: `0x1400019cc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `23`
- callee_count: `5`
- tags: ``

## callers

- `0x14000224c`
- `0x1400067e8`
- `0x1400068f4`
- `0x1400069b0`
- `0x140006af4`
- `0x140006f18`
- `0x140007058`
- `0x140007394`
- `0x1400074fc`
- `0x140007778`
- `0x140007d04`
- `0x140007dc0`
- `0x140008784`
- `0x140009434`
- `0x14000b5b4`
- `0x14000b8e0`
- `0x14000cd00`
- `0x14000d5a8`
- `0x14000d858`
- `0x14000d974`
- `0x14000e870`
- `0x14000e9f8`
- `0x1400110b8`

## callees

- `0x140001990`
- `0x140002280`
- `0x14000234e`
- `0x14000241a`
- `0x14000b04c`

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
0x140001990  push    rbx
0x140001992  sub     rsp, 20h
0x140001996  mov     rbx, rcx
0x140001999  jmp     short loc_1400019AA
0x14000199b  mov     rcx, rbx
0x14000199e  call    _o__callnewh_0
0x1400019a3  test    eax, eax
0x1400019a5  jz      short loc_1400019BA
0x1400019a7  mov     rcx, rbx; Size
0x1400019aa  call    _o_malloc_0
0x1400019af  test    rax, rax
0x1400019b2  jz      short loc_14000199B
0x1400019b4  add     rsp, 20h
0x1400019b8  pop     rbx
0x1400019b9  retn
0x1400019ba  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400019be  jz      short loc_1400019C6
0x1400019c0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400019c6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
