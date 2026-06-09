# operator new(unsigned __int64)

- ea: `0x18000197c`
- end: `0x1800019b8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800019c0`
- `0x180005b70`
- `0x180005be0`
- `0x180005db8`
- `0x1800088c0`
- `0x18000a5f0`
- `0x18000a65c`
- `0x18000b2fc`

## callees

- `0x18000197c`
- `0x180001e98`
- `0x180001f36`
- `0x180001fba`
- `0x180009104`

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
0x18000197c  push    rbx
0x18000197e  sub     rsp, 20h
0x180001982  mov     rbx, rcx
0x180001985  jmp     short loc_180001996
0x180001987  mov     rcx, rbx
0x18000198a  call    _o__callnewh_0
0x18000198f  test    eax, eax
0x180001991  jz      short loc_1800019A6
0x180001993  mov     rcx, rbx; Size
0x180001996  call    _o_malloc_0
0x18000199b  test    rax, rax
0x18000199e  jz      short loc_180001987
0x1800019a0  add     rsp, 20h
0x1800019a4  pop     rbx
0x1800019a5  retn
0x1800019a6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800019aa  jz      short loc_1800019B2
0x1800019ac  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800019b2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
