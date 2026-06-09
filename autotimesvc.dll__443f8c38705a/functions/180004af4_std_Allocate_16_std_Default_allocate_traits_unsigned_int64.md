# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180004af4`
- end: `0x180004b4b`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180004b54`
- `0x18000d990`
- `0x18000d9cc`
- `0x18000da94`
- `0x18000db50`
- `0x18000dc74`
- `0x18000f430`

## callees

- `0x180002a94`
- `0x180004af4`
- `0x18000a694`

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
    std::_Throw_bad_array_new_length();
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
0x180004af4  sub     rsp, 28h
0x180004af8  test    rcx, rcx
0x180004afb  jnz     short loc_180004B04
0x180004afd  xor     eax, eax
0x180004aff  add     rsp, 28h
0x180004b03  retn
0x180004b04  cmp     rcx, 1000h
0x180004b0b  jb      short loc_180004B3C
0x180004b0d  lea     rax, [rcx+27h]
0x180004b11  cmp     rax, rcx
0x180004b14  jbe     short loc_180004B45
0x180004b16  mov     rcx, rax; Size
0x180004b19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b1e  mov     rcx, rax
0x180004b21  test    rax, rax
0x180004b24  jnz     short loc_180004B2B
0x180004b26  lea     ecx, [rax+5]; Size
0x180004b29  int     29h; Win8: RtlFailFast(ecx)
0x180004b2b  add     rax, 27h ; '''
0x180004b2f  and     rax, 0FFFFFFFFFFFFFFE0h
0x180004b33  mov     [rax-8], rcx
0x180004b37  add     rsp, 28h
0x180004b3b  retn
0x180004b3c  add     rsp, 28h
0x180004b40  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b45  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
