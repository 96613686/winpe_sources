# operator new(unsigned __int64)

- ea: `0x14000367c`
- end: `0x1400036b8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1400036e4`
- `0x140003ddc`
- `0x140009cd8`
- `0x14000c13c`
- `0x14000c230`
- `0x14000c474`

## callees

- `0x14000367c`
- `0x140003d8c`
- `0x140003db4`
- `0x140003e6e`
- `0x140003f50`

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
0x14000367c  push    rbx
0x14000367e  sub     rsp, 20h
0x140003682  mov     rbx, rcx
0x140003685  jmp     short loc_140003696
0x140003687  mov     rcx, rbx
0x14000368a  call    _o__callnewh_0
0x14000368f  test    eax, eax
0x140003691  jz      short loc_1400036A6
0x140003693  mov     rcx, rbx; Size
0x140003696  call    _o_malloc_0
0x14000369b  test    rax, rax
0x14000369e  jz      short loc_140003687
0x1400036a0  add     rsp, 20h
0x1400036a4  pop     rbx
0x1400036a5  retn
0x1400036a6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400036aa  jz      short loc_1400036B2
0x1400036ac  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400036b2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
