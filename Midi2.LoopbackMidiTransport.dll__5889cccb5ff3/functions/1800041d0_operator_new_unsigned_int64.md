# operator new(unsigned __int64)

- ea: `0x1800041d0`
- end: `0x18000420c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `38`
- callee_count: `5`
- tags: ``

## callers

- `0x180004690`
- `0x18000499c`
- `0x1800073e4`
- `0x180007504`
- `0x180007650`
- `0x18000b4e0`
- `0x18000df04`
- `0x18000e22c`
- `0x18000ed4c`
- `0x18000efa8`
- `0x18000ff50`
- `0x1800105c0`
- `0x180013574`
- `0x180015464`
- `0x180015660`
- `0x180015790`
- `0x1800158e8`
- `0x180015a48`
- `0x180015ba0`
- `0x180015cf8`
- `0x1800176ec`
- `0x180017c54`
- `0x180018710`
- `0x18001b450`
- `0x18001bd50`
- `0x18001bfc8`
- `0x18001c188`
- `0x18001c400`
- `0x18001c6b0`
- `0x180021c1c`
- `0x180022a6c`
- `0x180026bf0`
- `0x180026d90`
- `0x18002a608`
- `0x18002a7b4`
- `0x18002a8cc`
- `0x18002af1c`
- `0x18002da24`

## callees

- `0x1800041d0`
- `0x180004e88`
- `0x180004f32`
- `0x180004fd0`
- `0x18000c290`

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
0x1800041d0  push    rbx
0x1800041d2  sub     rsp, 20h
0x1800041d6  mov     rbx, rcx
0x1800041d9  jmp     short loc_1800041EA
0x1800041db  mov     rcx, rbx
0x1800041de  call    _o__callnewh_0
0x1800041e3  test    eax, eax
0x1800041e5  jz      short loc_1800041FA
0x1800041e7  mov     rcx, rbx; Size
0x1800041ea  call    _o_malloc_0
0x1800041ef  test    rax, rax
0x1800041f2  jz      short loc_1800041DB
0x1800041f4  add     rsp, 20h
0x1800041f8  pop     rbx
0x1800041f9  retn
0x1800041fa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800041fe  jz      short loc_180004206
0x180004200  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180004206  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
