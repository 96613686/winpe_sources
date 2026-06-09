# operator new(unsigned __int64)

- ea: `0x18000214c`
- end: `0x180002188`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ba4c`
- `0x18000dc28`
- `0x18000e4b4`
- `0x18000e5a4`
- `0x18000e7a8`
- `0x18000e91c`
- `0x18000ea3c`
- `0x18000ed18`
- `0x18000f9f0`

## callees

- `0x18000214c`
- `0x1800028f0`
- `0x180002976`
- `0x180002a10`
- `0x180011d50`

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
0x18000214c  push    rbx
0x18000214e  sub     rsp, 20h
0x180002152  mov     rbx, rcx
0x180002155  jmp     short loc_180002166
0x180002157  mov     rcx, rbx
0x18000215a  call    _o__callnewh_0
0x18000215f  test    eax, eax
0x180002161  jz      short loc_180002176
0x180002163  mov     rcx, rbx; Size
0x180002166  call    _o_malloc_0
0x18000216b  test    rax, rax
0x18000216e  jz      short loc_180002157
0x180002170  add     rsp, 20h
0x180002174  pop     rbx
0x180002175  retn
0x180002176  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000217a  jz      short loc_180002182
0x18000217c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002182  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
