# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140009c32`
- end: `0x140009c66`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002d4c`

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
0x140009c32  mov     [rsp+arg_8], rdx
0x140009c37  push    rbp
0x140009c38  sub     rsp, 20h
0x140009c3c  mov     rbp, rdx
0x140009c3f  mov     rcx, [rbp+58h]
0x140009c43  mov     [rbp+58h], rcx
0x140009c47  inc     rcx
0x140009c4a  xor     edx, edx
0x140009c4c  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x140009c51  mov     [rbp+68h], rax
0x140009c55  mov     rax, 0
0x140009c5f  add     rsp, 20h
0x140009c63  pop     rbp
0x140009c64  retn
```
