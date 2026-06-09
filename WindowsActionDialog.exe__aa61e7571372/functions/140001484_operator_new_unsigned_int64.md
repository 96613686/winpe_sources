# operator new(unsigned __int64)

- ea: `0x140001484`
- end: `0x1400014c0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1400014c8`
- `0x140002d98`
- `0x14000759c`
- `0x140007a78`

## callees

- `0x140001484`
- `0x140001ae8`
- `0x140001e3a`
- `0x140001f20`
- `0x140007780`

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
0x140001484  push    rbx
0x140001486  sub     rsp, 20h
0x14000148a  mov     rbx, rcx
0x14000148d  jmp     short loc_14000149E
0x14000148f  mov     rcx, rbx
0x140001492  call    _o__callnewh_0
0x140001497  test    eax, eax
0x140001499  jz      short loc_1400014AE
0x14000149b  mov     rcx, rbx; Size
0x14000149e  call    _o_malloc_0
0x1400014a3  test    rax, rax
0x1400014a6  jz      short loc_14000148F
0x1400014a8  add     rsp, 20h
0x1400014ac  pop     rbx
0x1400014ad  retn
0x1400014ae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400014b2  jz      short loc_1400014BA
0x1400014b4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1400014ba  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
