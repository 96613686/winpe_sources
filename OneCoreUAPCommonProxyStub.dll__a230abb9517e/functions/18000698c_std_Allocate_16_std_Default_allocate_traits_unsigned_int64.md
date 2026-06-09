# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x18000698c`
- end: `0x1800069e3`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a90`
- `0x180006be8`
- `0x180006d28`

## callees

- `0x1800045c8`
- `0x18000698c`
- `0x180009c28`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return operator new(a1);
  if ( a1 + 39 < a1 )
    __scrt_throw_std_bad_array_new_length();
  v2 = operator new(a1 + 39);
  v3 = v2;
  if ( !v2 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v3;
  return result;
}

```

## disassembly

```asm
0x18000698c  sub     rsp, 28h
0x180006990  test    rcx, rcx
0x180006993  jnz     short loc_18000699C
0x180006995  xor     eax, eax
0x180006997  add     rsp, 28h
0x18000699b  retn
0x18000699c  cmp     rcx, 1000h
0x1800069a3  jb      short loc_1800069D4
0x1800069a5  lea     rax, [rcx+27h]
0x1800069a9  cmp     rax, rcx
0x1800069ac  jbe     short loc_1800069DD
0x1800069ae  mov     rcx, rax; Size
0x1800069b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069b6  mov     rcx, rax
0x1800069b9  test    rax, rax
0x1800069bc  jnz     short loc_1800069C3
0x1800069be  lea     ecx, [rax+5]; Size
0x1800069c1  int     29h; Win8: RtlFailFast(ecx)
0x1800069c3  add     rax, 27h ; '''
0x1800069c7  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800069cb  mov     [rax-8], rcx
0x1800069cf  add     rsp, 28h
0x1800069d3  retn
0x1800069d4  add     rsp, 28h
0x1800069d8  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069dd  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
