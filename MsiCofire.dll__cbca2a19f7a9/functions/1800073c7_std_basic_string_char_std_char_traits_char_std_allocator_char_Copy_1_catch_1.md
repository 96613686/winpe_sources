# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1800073c7`
- end: `0x18000740b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001b48`
- `0x180001d28`
- `0x180001e88`
- `0x1800073c7`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_180001DB1;
}

```

## disassembly

```asm
0x1800073c7  mov     [rsp+arg_8], rdx
0x1800073cc  push    rbp
0x1800073cd  sub     rsp, 20h
0x1800073d1  mov     rbp, rdx
0x1800073d4  mov     rcx, [rbp+68h]
0x1800073d8  mov     [rbp+68h], rcx
0x1800073dc  xor     eax, eax
0x1800073de  add     rcx, 1; Size
0x1800073e2  jz      short loc_1800073F9
0x1800073e4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800073e8  ja      short loc_1800073F4
0x1800073ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073ef  test    rax, rax
0x1800073f2  jnz     short loc_1800073F9
0x1800073f4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800073f9  mov     [rbp+78h], rax
0x1800073fd  lea     rax, loc_180001DB1
0x180007404  add     rsp, 20h
0x180007408  pop     rbp
0x180007409  retn
```
