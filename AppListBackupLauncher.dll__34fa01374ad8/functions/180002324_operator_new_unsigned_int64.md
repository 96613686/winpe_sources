# operator new(unsigned __int64)

- ea: `0x180002324`
- end: `0x180002360`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002368`
- `0x1800032ac`
- `0x180004428`
- `0x1800045b4`
- `0x180004d78`
- `0x1800072a0`
- `0x18000f970`

## callees

- `0x180002324`
- `0x180002c60`
- `0x180002d16`
- `0x180002db0`
- `0x18000e89c`

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
0x180002324  push    rbx
0x180002326  sub     rsp, 20h
0x18000232a  mov     rbx, rcx
0x18000232d  jmp     short loc_18000233E
0x18000232f  mov     rcx, rbx
0x180002332  call    _o__callnewh_0
0x180002337  test    eax, eax
0x180002339  jz      short loc_18000234E
0x18000233b  mov     rcx, rbx; Size
0x18000233e  call    _o_malloc_0
0x180002343  test    rax, rax
0x180002346  jz      short loc_18000232F
0x180002348  add     rsp, 20h
0x18000234c  pop     rbx
0x18000234d  retn
0x18000234e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002352  jz      short loc_18000235A
0x180002354  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000235a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
