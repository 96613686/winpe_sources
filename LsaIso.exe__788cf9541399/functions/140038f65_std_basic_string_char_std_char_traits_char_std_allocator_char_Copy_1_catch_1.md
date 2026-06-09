# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140038f65`
- end: `0x140038f99`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000747c`

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
0x140038f65  mov     [rsp+arg_8], rdx
0x140038f6a  push    rbp
0x140038f6b  sub     rsp, 20h
0x140038f6f  mov     rbp, rdx
0x140038f72  mov     rcx, [rbp+58h]
0x140038f76  mov     [rbp+58h], rcx
0x140038f7a  inc     rcx
0x140038f7d  xor     edx, edx
0x140038f7f  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x140038f84  mov     [rbp+68h], rax
0x140038f88  mov     rax, 0
0x140038f92  add     rsp, 20h
0x140038f96  pop     rbp
0x140038f97  retn
```
