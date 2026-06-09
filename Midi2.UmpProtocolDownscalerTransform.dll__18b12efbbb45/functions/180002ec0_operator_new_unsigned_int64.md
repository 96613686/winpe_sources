# operator new(unsigned __int64)

- ea: `0x180002ec0`
- end: `0x180002efc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x180003380`
- `0x1800033bc`
- `0x180005d04`
- `0x180005e14`
- `0x180005f50`
- `0x18000b1d0`
- `0x18000b238`
- `0x18000b344`
- `0x18000b4d4`
- `0x18000b5dc`
- `0x18000b770`
- `0x18000c354`
- `0x18000c450`
- `0x18000c62c`
- `0x18000dee0`
- `0x18000df90`
- `0x18000e950`

## callees

- `0x180002ec0`
- `0x1800038a8`
- `0x180003952`
- `0x1800039f0`
- `0x180010e54`

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
0x180002ec0  push    rbx
0x180002ec2  sub     rsp, 20h
0x180002ec6  mov     rbx, rcx
0x180002ec9  jmp     short loc_180002EDA
0x180002ecb  mov     rcx, rbx
0x180002ece  call    _o__callnewh_0
0x180002ed3  test    eax, eax
0x180002ed5  jz      short loc_180002EEA
0x180002ed7  mov     rcx, rbx; Size
0x180002eda  call    _o_malloc_0
0x180002edf  test    rax, rax
0x180002ee2  jz      short loc_180002ECB
0x180002ee4  add     rsp, 20h
0x180002ee8  pop     rbx
0x180002ee9  retn
0x180002eea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002eee  jz      short loc_180002EF6
0x180002ef0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002ef6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
