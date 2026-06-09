# operator new(unsigned __int64)

- ea: `0x1800026fc`
- end: `0x180002738`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `16`
- callee_count: `5`
- tags: ``

## callers

- `0x180002740`
- `0x180006170`
- `0x180006190`
- `0x180008428`
- `0x180008a94`
- `0x180008c1c`
- `0x180009610`
- `0x18000a4d0`
- `0x18000ac1c`
- `0x18000ad94`
- `0x18000afd0`
- `0x18000b990`
- `0x18000d4dc`
- `0x18000d508`
- `0x18000e0e4`
- `0x18000eda0`

## callees

- `0x180001f06`
- `0x180001fac`
- `0x1800026fc`
- `0x180002804`
- `0x18000282c`

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
0x1800026fc  push    rbx
0x1800026fe  sub     rsp, 20h
0x180002702  mov     rbx, rcx
0x180002705  jmp     short loc_180002716
0x180002707  mov     rcx, rbx
0x18000270a  call    _o__callnewh_0
0x18000270f  test    eax, eax
0x180002711  jz      short loc_180002726
0x180002713  mov     rcx, rbx; Size
0x180002716  call    _o_malloc_0
0x18000271b  test    rax, rax
0x18000271e  jz      short loc_180002707
0x180002720  add     rsp, 20h
0x180002724  pop     rbx
0x180002725  retn
0x180002726  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000272a  jz      short loc_180002732
0x18000272c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002732  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
