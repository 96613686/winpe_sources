# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x140004d50`
- end: `0x140004da7`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140004db0`
- `0x140004de0`
- `0x140004e7c`
- `0x140004fc4`
- `0x14000f7dc`
- `0x14000f85c`
- `0x140011a8c`

## callees

- `0x140002f64`
- `0x140004d50`
- `0x14000de1c`

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
0x140004d50  sub     rsp, 28h
0x140004d54  test    rcx, rcx
0x140004d57  jnz     short loc_140004D60
0x140004d59  xor     eax, eax
0x140004d5b  add     rsp, 28h
0x140004d5f  retn
0x140004d60  cmp     rcx, 1000h
0x140004d67  jb      short loc_140004D98
0x140004d69  lea     rax, [rcx+27h]
0x140004d6d  cmp     rax, rcx
0x140004d70  jbe     short loc_140004DA1
0x140004d72  mov     rcx, rax; Size
0x140004d75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004d7a  mov     rcx, rax
0x140004d7d  test    rax, rax
0x140004d80  jnz     short loc_140004D87
0x140004d82  lea     ecx, [rax+5]; Size
0x140004d85  int     29h; Win8: RtlFailFast(ecx)
0x140004d87  add     rax, 27h ; '''
0x140004d8b  and     rax, 0FFFFFFFFFFFFFFE0h
0x140004d8f  mov     [rax-8], rcx
0x140004d93  add     rsp, 28h
0x140004d97  retn
0x140004d98  add     rsp, 28h
0x140004d9c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004da1  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
