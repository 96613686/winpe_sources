# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000f4f1`
- end: `0x18000f525`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008770`

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
0x18000f4f1  mov     [rsp+arg_8], rdx
0x18000f4f6  push    rbp
0x18000f4f7  sub     rsp, 20h
0x18000f4fb  mov     rbp, rdx
0x18000f4fe  mov     rcx, [rbp+58h]
0x18000f502  mov     [rbp+58h], rcx
0x18000f506  inc     rcx
0x18000f509  xor     edx, edx
0x18000f50b  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000f510  mov     [rbp+68h], rax
0x18000f514  mov     rax, 0
0x18000f51e  add     rsp, 20h
0x18000f522  pop     rbp
0x18000f523  retn
```
