# operator new(unsigned __int64)

- ea: `0x180001754`
- end: `0x180001790`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000258c`

## callees

- `0x180001754`
- `0x180001e84`
- `0x180001eac`
- `0x18000223a`
- `0x1800022b2`

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
0x180001754  push    rbx
0x180001756  sub     rsp, 20h
0x18000175a  mov     rbx, rcx
0x18000175d  jmp     short loc_18000176E
0x18000175f  mov     rcx, rbx
0x180001762  call    _o__callnewh_0
0x180001767  test    eax, eax
0x180001769  jz      short loc_18000177E
0x18000176b  mov     rcx, rbx; Size
0x18000176e  call    _o_malloc_0
0x180001773  test    rax, rax
0x180001776  jz      short loc_18000175F
0x180001778  add     rsp, 20h
0x18000177c  pop     rbx
0x18000177d  retn
0x18000177e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001782  jz      short loc_18000178A
0x180001784  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000178a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
