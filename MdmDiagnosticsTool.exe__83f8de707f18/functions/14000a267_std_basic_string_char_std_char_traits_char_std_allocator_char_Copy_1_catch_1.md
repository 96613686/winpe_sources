# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14000a267`
- end: `0x14000a29b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002dd0`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v2;
  *(_QWORD *)(a2 + 104) = std::_Allocate<char>(v2 + 1, 0);
  return 0;
}

```

## disassembly

```asm
0x14000a267  mov     [rsp+arg_8], rdx
0x14000a26c  push    rbp
0x14000a26d  sub     rsp, 20h
0x14000a271  mov     rbp, rdx
0x14000a274  mov     rcx, [rbp+58h]
0x14000a278  mov     [rbp+58h], rcx
0x14000a27c  inc     rcx
0x14000a27f  xor     edx, edx
0x14000a281  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14000a286  mov     [rbp+68h], rax
0x14000a28a  mov     rax, 0
0x14000a294  add     rsp, 20h
0x14000a298  pop     rbp
0x14000a299  retn
```
