# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0

- ea: `0x18000f1cc`
- end: `0x18000f1f1`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ebc`
- `0x1800074c4`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18000f1cc  mov     [rsp+arg_8], rdx
0x18000f1d1  push    rbp
0x18000f1d2  sub     rsp, 20h
0x18000f1d6  mov     rbp, rdx
0x18000f1d9  xor     r8d, r8d
0x18000f1dc  mov     dl, 1
0x18000f1de  mov     rcx, [rbp+50h]
0x18000f1e2  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f1e7  xor     edx, edx; pThrowInfo
0x18000f1e9  xor     ecx, ecx; pExceptionObject
0x18000f1eb  call    _CxxThrowException_0
```
