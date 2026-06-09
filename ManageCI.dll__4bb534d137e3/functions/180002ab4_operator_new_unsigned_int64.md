# operator new(unsigned __int64)

- ea: `0x180002ab4`
- end: `0x180002af0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `32`
- callee_count: `5`
- tags: ``

## callers

- `0x180002edc`
- `0x180004920`
- `0x180009490`
- `0x18000ad4c`
- `0x180012110`
- `0x180012da0`
- `0x180013660`
- `0x180014c20`
- `0x180015564`
- `0x180015598`
- `0x180016754`
- `0x180018e88`
- `0x18001bb6c`
- `0x18001c714`
- `0x18001cb90`
- `0x18001cc40`
- `0x18001cc90`
- `0x18001cd3c`
- `0x18001cddc`
- `0x18001ceb4`
- `0x18001d138`
- `0x18001d3b4`
- `0x18001d404`
- `0x18001d438`
- `0x18001d808`
- `0x18001d8d0`
- `0x18001d924`
- `0x18001dd48`
- `0x18001f0b0`
- `0x18001f14c`
- `0x18001f438`
- `0x18001ffd8`

## callees

- `0x180002ab4`
- `0x1800036c8`
- `0x1800036f0`
- `0x1800037a6`
- `0x18000384c`

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
0x180002ab4  push    rbx
0x180002ab6  sub     rsp, 20h
0x180002aba  mov     rbx, rcx
0x180002abd  jmp     short loc_180002ACE
0x180002abf  mov     rcx, rbx
0x180002ac2  call    _o__callnewh_0
0x180002ac7  test    eax, eax
0x180002ac9  jz      short loc_180002ADE
0x180002acb  mov     rcx, rbx; Size
0x180002ace  call    _o_malloc_0
0x180002ad3  test    rax, rax
0x180002ad6  jz      short loc_180002ABF
0x180002ad8  add     rsp, 20h
0x180002adc  pop     rbx
0x180002add  retn
0x180002ade  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002ae2  jz      short loc_180002AEA
0x180002ae4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002aea  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
