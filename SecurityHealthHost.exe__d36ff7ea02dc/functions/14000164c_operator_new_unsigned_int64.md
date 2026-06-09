# operator new(unsigned __int64)

- ea: `0x14000164c`
- end: `0x140001688`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000190c`
- `0x140002304`
- `0x140002390`
- `0x140003f18`
- `0x140005fdc`
- `0x14000c688`

## callees

- `0x14000164c`
- `0x140002120`
- `0x14000223e`
- `0x14000224a`
- `0x140002e80`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
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
0x14000164c  push    rbx
0x14000164e  sub     rsp, 20h
0x140001652  mov     rbx, rcx
0x140001655  jmp     short loc_140001666
0x140001657  mov     rcx, rbx; Size
0x14000165a  call    _callnewh_0
0x14000165f  test    eax, eax
0x140001661  jz      short loc_140001676
0x140001663  mov     rcx, rbx; Size
0x140001666  call    malloc_0
0x14000166b  test    rax, rax
0x14000166e  jz      short loc_140001657
0x140001670  add     rsp, 20h
0x140001674  pop     rbx
0x140001675  retn
0x140001676  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000167a  jz      short loc_140001682
0x14000167c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140001682  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
