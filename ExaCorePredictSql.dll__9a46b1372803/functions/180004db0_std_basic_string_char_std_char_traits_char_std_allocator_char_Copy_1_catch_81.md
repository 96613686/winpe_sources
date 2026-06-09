# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$81

- ea: `0x180004db0`
- end: `0x180004ddf`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$81`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800035d0`
- `0x180003640`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_81(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  *(_QWORD *)(a2 + 120) = std::_Wrap_alloc<std::allocator<char>>::allocate(a1, v3 + 1);
  return &loc_18000370B;
}

```

## disassembly

```asm
0x180004db0  mov     [rsp+arg_8], rdx
0x180004db5  push    rbp
0x180004db6  sub     rsp, 20h
0x180004dba  mov     rbp, rdx
0x180004dbd  mov     rdx, [rbp+68h]
0x180004dc1  mov     [rbp+68h], rdx
0x180004dc5  inc     rdx
0x180004dc8  call    ?allocate@?$_Wrap_alloc@V?$allocator@D@std@@@std@@QEAAPEAD_K@Z; std::_Wrap_alloc<std::allocator<char>>::allocate(unsigned __int64)
0x180004dcd  mov     [rbp+78h], rax
0x180004dd1  lea     rax, loc_18000370B
0x180004dd8  add     rsp, 20h
0x180004ddc  pop     rbp
0x180004ddd  retn
```
