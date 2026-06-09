# operator new(unsigned __int64)

- ea: `0x1400029f0`
- end: `0x140002a2c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000360c`
- `0x1400043f0`
- `0x1400044e8`
- `0x140004d24`
- `0x140009170`

## callees

- `0x1400029f0`
- `0x1400030c0`
- `0x140003422`
- `0x140003500`
- `0x140007cd8`

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
0x1400029f0  push    rbx
0x1400029f2  sub     rsp, 20h
0x1400029f6  mov     rbx, rcx
0x1400029f9  jmp     short loc_140002A0A
0x1400029fb  mov     rcx, rbx
0x1400029fe  call    _o__callnewh_0
0x140002a03  test    eax, eax
0x140002a05  jz      short loc_140002A1A
0x140002a07  mov     rcx, rbx; Size
0x140002a0a  call    _o_malloc_0
0x140002a0f  test    rax, rax
0x140002a12  jz      short loc_1400029FB
0x140002a14  add     rsp, 20h
0x140002a18  pop     rbx
0x140002a19  retn
0x140002a1a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140002a1e  jz      short loc_140002A26
0x140002a20  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002a26  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
