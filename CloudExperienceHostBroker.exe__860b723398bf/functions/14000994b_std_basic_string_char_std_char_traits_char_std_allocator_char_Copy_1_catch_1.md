# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14000994b`
- end: `0x14000997f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002fd8`

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
0x14000994b  mov     [rsp+arg_8], rdx
0x140009950  push    rbp
0x140009951  sub     rsp, 20h
0x140009955  mov     rbp, rdx
0x140009958  mov     rcx, [rbp+58h]
0x14000995c  mov     [rbp+58h], rcx
0x140009960  inc     rcx
0x140009963  xor     edx, edx
0x140009965  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14000996a  mov     [rbp+68h], rax
0x14000996e  mov     rax, 0
0x140009978  add     rsp, 20h
0x14000997c  pop     rbp
0x14000997d  retn
```
