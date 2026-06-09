# operator new(unsigned __int64)

- ea: `0x180001cf8`
- end: `0x180001d34`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001cec`

## callees

- `0x180001c42`
- `0x180001ca2`
- `0x180001cf8`
- `0x180001eb4`
- `0x180001edc`

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
0x180001cf8  push    rbx
0x180001cfa  sub     rsp, 20h
0x180001cfe  mov     rbx, rcx
0x180001d01  jmp     short loc_180001D12
0x180001d03  mov     rcx, rbx
0x180001d06  call    _o__callnewh_0
0x180001d0b  test    eax, eax
0x180001d0d  jz      short loc_180001D22
0x180001d0f  mov     rcx, rbx; Size
0x180001d12  call    _o_malloc_0
0x180001d17  test    rax, rax
0x180001d1a  jz      short loc_180001D03
0x180001d1c  add     rsp, 20h
0x180001d20  pop     rbx
0x180001d21  retn
0x180001d22  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001d26  jz      short loc_180001D2E
0x180001d28  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001d2e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
