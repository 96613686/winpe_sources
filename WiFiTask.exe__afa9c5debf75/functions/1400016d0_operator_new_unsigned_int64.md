# operator new(unsigned __int64)

- ea: `0x1400016d0`
- end: `0x14000170c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x140001714`
- `0x1400019a8`
- `0x140002d70`
- `0x140002f18`
- `0x14000728c`
- `0x140009994`
- `0x14000cf98`
- `0x14000dd04`
- `0x14000dfc4`
- `0x14000e4cc`
- `0x14000e694`
- `0x14000e908`

## callees

- `0x1400016d0`
- `0x140001ce8`
- `0x140002046`
- `0x140002120`
- `0x14000b570`

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
0x1400016d0  push    rbx
0x1400016d2  sub     rsp, 20h
0x1400016d6  mov     rbx, rcx
0x1400016d9  jmp     short loc_1400016EA
0x1400016db  mov     rcx, rbx
0x1400016de  call    _o__callnewh_0
0x1400016e3  test    eax, eax
0x1400016e5  jz      short loc_1400016FA
0x1400016e7  mov     rcx, rbx; Size
0x1400016ea  call    _o_malloc_0
0x1400016ef  test    rax, rax
0x1400016f2  jz      short loc_1400016DB
0x1400016f4  add     rsp, 20h
0x1400016f8  pop     rbx
0x1400016f9  retn
0x1400016fa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400016fe  jz      short loc_140001706
0x140001700  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001706  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
