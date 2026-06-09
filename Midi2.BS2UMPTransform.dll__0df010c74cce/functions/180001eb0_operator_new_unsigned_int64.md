# operator new(unsigned __int64)

- ea: `0x180001eb0`
- end: `0x180001eec`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022a0`
- `0x1800022dc`
- `0x180004a94`
- `0x180004ba4`
- `0x180004ce0`
- `0x18000a328`
- `0x18000a4b8`
- `0x18000a5c0`

## callees

- `0x180001eb0`
- `0x1800024e0`
- `0x180002812`
- `0x1800028b0`
- `0x18000acb8`

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
0x180001eb0  push    rbx
0x180001eb2  sub     rsp, 20h
0x180001eb6  mov     rbx, rcx
0x180001eb9  jmp     short loc_180001ECA
0x180001ebb  mov     rcx, rbx
0x180001ebe  call    _o__callnewh_0
0x180001ec3  test    eax, eax
0x180001ec5  jz      short loc_180001EDA
0x180001ec7  mov     rcx, rbx; Size
0x180001eca  call    _o_malloc_0
0x180001ecf  test    rax, rax
0x180001ed2  jz      short loc_180001EBB
0x180001ed4  add     rsp, 20h
0x180001ed8  pop     rbx
0x180001ed9  retn
0x180001eda  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001ede  jz      short loc_180001EE6
0x180001ee0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001ee6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
