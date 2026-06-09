# operator new(unsigned __int64)

- ea: `0x180001424`
- end: `0x180001460`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001474`
- `0x180002090`

## callees

- `0x180001424`
- `0x180001b34`
- `0x180001b5c`
- `0x180001ee2`
- `0x180001f42`

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
0x180001424  push    rbx
0x180001426  sub     rsp, 20h
0x18000142a  mov     rbx, rcx
0x18000142d  jmp     short loc_18000143E
0x18000142f  mov     rcx, rbx
0x180001432  call    _o__callnewh_0
0x180001437  test    eax, eax
0x180001439  jz      short loc_18000144E
0x18000143b  mov     rcx, rbx; Size
0x18000143e  call    _o_malloc_0
0x180001443  test    rax, rax
0x180001446  jz      short loc_18000142F
0x180001448  add     rsp, 20h
0x18000144c  pop     rbx
0x18000144d  retn
0x18000144e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001452  jz      short loc_18000145A
0x180001454  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000145a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
