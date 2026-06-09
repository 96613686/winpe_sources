# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$80

- ea: `0x180004b72`
- end: `0x180004b97`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$80`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001440`
- `0x180004ac0`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_80(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 112), a2, 0);
  throw;
}

```

## disassembly

```asm
0x180004b72  mov     [rsp+arg_8], rdx
0x180004b77  push    rbp
0x180004b78  sub     rsp, 20h
0x180004b7c  mov     rbp, rdx
0x180004b7f  xor     r8d, r8d
0x180004b82  mov     dl, 1
0x180004b84  mov     rcx, [rbp+70h]
0x180004b88  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004b8d  xor     edx, edx; pThrowInfo
0x180004b8f  xor     ecx, ecx; pExceptionObject
0x180004b91  call    _CxxThrowException_0
```
