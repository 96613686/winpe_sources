# operator new(unsigned __int64)

- ea: `0x140002960`
- end: `0x14000299c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000356c`
- `0x14000432c`
- `0x140004424`
- `0x140004c80`
- `0x140008d58`

## callees

- `0x140002960`
- `0x140003020`
- `0x140003382`
- `0x140003460`
- `0x1400079f0`

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
0x140002960  push    rbx
0x140002962  sub     rsp, 20h
0x140002966  mov     rbx, rcx
0x140002969  jmp     short loc_14000297A
0x14000296b  mov     rcx, rbx
0x14000296e  call    _o__callnewh_0
0x140002973  test    eax, eax
0x140002975  jz      short loc_14000298A
0x140002977  mov     rcx, rbx; Size
0x14000297a  call    _o_malloc_0
0x14000297f  test    rax, rax
0x140002982  jz      short loc_14000296B
0x140002984  add     rsp, 20h
0x140002988  pop     rbx
0x140002989  retn
0x14000298a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000298e  jz      short loc_140002996
0x140002990  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002996  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
