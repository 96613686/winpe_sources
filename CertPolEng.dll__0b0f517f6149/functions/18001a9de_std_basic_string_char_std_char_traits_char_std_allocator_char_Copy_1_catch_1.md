# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001a9de`
- end: `0x18001aa12`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f2ec`

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
0x18001a9de  mov     [rsp+arg_8], rdx
0x18001a9e3  push    rbp
0x18001a9e4  sub     rsp, 20h
0x18001a9e8  mov     rbp, rdx
0x18001a9eb  mov     rcx, [rbp+58h]
0x18001a9ef  mov     [rbp+58h], rcx
0x18001a9f3  inc     rcx
0x18001a9f6  xor     edx, edx
0x18001a9f8  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18001a9fd  mov     [rbp+68h], rax
0x18001aa01  mov     rax, 0
0x18001aa0b  add     rsp, 20h
0x18001aa0f  pop     rbp
0x18001aa10  retn
```
