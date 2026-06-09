# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180012d36`
- end: `0x180012d67`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `49`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800092b0`
- `0x18000b2dc`

## pseudocode

```c
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v2;
  *(_QWORD *)(a2 + 120) = std::_Allocate<char>(v2 + 1, 0);
  return &loc_18000B359;
}

```

## disassembly

```asm
0x180012d36  mov     [rsp+arg_8], rdx
0x180012d3b  push    rbp
0x180012d3c  sub     rsp, 20h
0x180012d40  mov     rbp, rdx
0x180012d43  mov     rcx, [rbp+68h]
0x180012d47  mov     [rbp+68h], rcx
0x180012d4b  inc     rcx
0x180012d4e  xor     edx, edx
0x180012d50  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x180012d55  mov     [rbp+78h], rax
0x180012d59  lea     rax, loc_18000B359
0x180012d60  add     rsp, 20h
0x180012d64  pop     rbp
0x180012d65  retn
```
