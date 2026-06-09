# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000fd43`
- end: `0x18000fd87`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000123c`
- `0x180001418`
- `0x180001578`
- `0x18000fd43`

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
  return &loc_1800014A1;
}

```

## disassembly

```asm
0x18000fd43  mov     [rsp+arg_8], rdx
0x18000fd48  push    rbp
0x18000fd49  sub     rsp, 20h
0x18000fd4d  mov     rbp, rdx
0x18000fd50  mov     rcx, [rbp+68h]
0x18000fd54  mov     [rbp+68h], rcx
0x18000fd58  xor     eax, eax
0x18000fd5a  add     rcx, 1; Size
0x18000fd5e  jz      short loc_18000FD75
0x18000fd60  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fd64  ja      short loc_18000FD70
0x18000fd66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd6b  test    rax, rax
0x18000fd6e  jnz     short loc_18000FD75
0x18000fd70  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000fd75  mov     [rbp+78h], rax
0x18000fd79  lea     rax, loc_1800014A1
0x18000fd80  add     rsp, 20h
0x18000fd84  pop     rbp
0x18000fd85  retn
```
