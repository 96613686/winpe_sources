# operator new(unsigned __int64)

- ea: `0x180001430`
- end: `0x18000146c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002590`
- `0x18000c4c0`

## callees

- `0x180001430`
- `0x180001b14`
- `0x180001b3c`
- `0x180001ee6`
- `0x180001f46`

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
0x180001430  push    rbx
0x180001432  sub     rsp, 20h
0x180001436  mov     rbx, rcx
0x180001439  jmp     short loc_18000144A
0x18000143b  mov     rcx, rbx
0x18000143e  call    _o__callnewh_0
0x180001443  test    eax, eax
0x180001445  jz      short loc_18000145A
0x180001447  mov     rcx, rbx; Size
0x18000144a  call    _o_malloc_0
0x18000144f  test    rax, rax
0x180001452  jz      short loc_18000143B
0x180001454  add     rsp, 20h
0x180001458  pop     rbx
0x180001459  retn
0x18000145a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000145e  jz      short loc_180001466
0x180001460  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001466  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
