# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$81

- ea: `0x180004b40`
- end: `0x180004b72`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$81`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800017c0`
- `0x180001a60`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_81(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rdx

  v3 = *(_QWORD *)(a2 + 120);
  *(_QWORD *)(a2 + 120) = v3;
  *(_QWORD *)(a2 + 136) = std::_Wrap_alloc<std::allocator<wchar_t>>::allocate(a1, v3 + 1);
  return &loc_1800018B4;
}

```

## disassembly

```asm
0x180004b40  mov     [rsp+arg_8], rdx
0x180004b45  push    rbp
0x180004b46  sub     rsp, 20h
0x180004b4a  mov     rbp, rdx
0x180004b4d  mov     rdx, [rbp+78h]
0x180004b51  mov     [rbp+78h], rdx
0x180004b55  inc     rdx
0x180004b58  call    ?allocate@?$_Wrap_alloc@V?$allocator@_W@std@@@std@@QEAAPEA_W_K@Z; std::_Wrap_alloc<std::allocator<wchar_t>>::allocate(unsigned __int64)
0x180004b5d  mov     [rbp+88h], rax
0x180004b64  lea     rax, loc_1800018B4
0x180004b6b  add     rsp, 20h
0x180004b6f  pop     rbp
0x180004b70  retn
```
