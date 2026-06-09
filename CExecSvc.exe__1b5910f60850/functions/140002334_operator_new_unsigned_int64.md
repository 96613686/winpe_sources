# operator new(unsigned __int64)

- ea: `0x140002334`
- end: `0x140002370`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `23`
- callee_count: `5`
- tags: ``

## callers

- `0x140001f40`
- `0x1400026fc`
- `0x140004484`
- `0x140006190`
- `0x140006718`
- `0x140006db4`
- `0x140007010`
- `0x140007624`
- `0x1400077b8`
- `0x140007af4`
- `0x140008670`
- `0x14000ddf4`
- `0x140010240`
- `0x1400130d8`
- `0x140013504`
- `0x140013f90`
- `0x140015180`
- `0x140015e84`
- `0x1400168e0`
- `0x140016cc0`
- `0x14001a43c`
- `0x14001b24c`
- `0x14001b3c8`

## callees

- `0x140002334`
- `0x140002a18`
- `0x140002db6`
- `0x140002e90`
- `0x14000e844`

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
0x140002334  push    rbx
0x140002336  sub     rsp, 20h
0x14000233a  mov     rbx, rcx
0x14000233d  jmp     short loc_14000234E
0x14000233f  mov     rcx, rbx
0x140002342  call    _o__callnewh_0
0x140002347  test    eax, eax
0x140002349  jz      short loc_14000235E
0x14000234b  mov     rcx, rbx; Size
0x14000234e  call    _o_malloc_0
0x140002353  test    rax, rax
0x140002356  jz      short loc_14000233F
0x140002358  add     rsp, 20h
0x14000235c  pop     rbx
0x14000235d  retn
0x14000235e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140002362  jz      short loc_14000236A
0x140002364  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x14000236a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
