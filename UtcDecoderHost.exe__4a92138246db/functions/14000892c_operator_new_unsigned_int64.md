# operator new(unsigned __int64)

- ea: `0x14000892c`
- end: `0x140008968`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x140002110`
- `0x140007f20`
- `0x140009510`
- `0x14000d698`
- `0x14000eb3c`
- `0x14000f2d4`
- `0x14000f43c`
- `0x14000fccc`
- `0x140010fd4`
- `0x1400110a4`
- `0x140011740`
- `0x140012c4c`

## callees

- `0x14000892c`
- `0x140008efc`
- `0x140008fce`
- `0x1400090b0`
- `0x14000d918`

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
0x14000892c  push    rbx
0x14000892e  sub     rsp, 20h
0x140008932  mov     rbx, rcx
0x140008935  jmp     short loc_140008946
0x140008937  mov     rcx, rbx
0x14000893a  call    _o__callnewh_0
0x14000893f  test    eax, eax
0x140008941  jz      short loc_140008956
0x140008943  mov     rcx, rbx; Size
0x140008946  call    _o_malloc_0
0x14000894b  test    rax, rax
0x14000894e  jz      short loc_140008937
0x140008950  add     rsp, 20h
0x140008954  pop     rbx
0x140008955  retn
0x140008956  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000895a  jz      short loc_140008962
0x14000895c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140008962  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
