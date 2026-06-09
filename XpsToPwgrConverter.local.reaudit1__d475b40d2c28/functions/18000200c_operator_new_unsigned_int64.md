# operator new(unsigned __int64)

- ea: `0x18000200c`
- end: `0x180002048`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180001b6c`
- `0x180009c90`
- `0x180009e3c`
- `0x18000a550`
- `0x18000acc0`
- `0x18000c33c`
- `0x18000ca20`
- `0x18000cb50`
- `0x18000cc68`
- `0x18000cddc`
- `0x18000e2b4`

## callees

- `0x18000200c`
- `0x180002050`
- `0x1800020d6`
- `0x180002170`
- `0x18000c968`

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
0x18000200c  push    rbx
0x18000200e  sub     rsp, 20h
0x180002012  mov     rbx, rcx
0x180002015  jmp     short loc_180002026
0x180002017  mov     rcx, rbx
0x18000201a  call    _o__callnewh_0
0x18000201f  test    eax, eax
0x180002021  jz      short loc_180002036
0x180002023  mov     rcx, rbx; Size
0x180002026  call    _o_malloc_0
0x18000202b  test    rax, rax
0x18000202e  jz      short loc_180002017
0x180002030  add     rsp, 20h
0x180002034  pop     rbx
0x180002035  retn
0x180002036  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000203a  jz      short loc_180002042
0x18000203c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002042  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
