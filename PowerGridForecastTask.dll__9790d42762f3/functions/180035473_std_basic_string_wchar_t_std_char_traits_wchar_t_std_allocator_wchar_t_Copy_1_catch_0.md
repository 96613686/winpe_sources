# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0

- ea: `0x180035473`
- end: `0x180035498`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180015898`
- `0x180026778`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 96), a2, 0);
  throw;
}

```

## disassembly

```asm
0x180035473  mov     [rsp+arg_8], rdx
0x180035478  push    rbp
0x180035479  sub     rsp, 20h
0x18003547d  mov     rbp, rdx
0x180035480  xor     r8d, r8d
0x180035483  mov     dl, 1
0x180035485  mov     rcx, [rbp+60h]
0x180035489  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003548e  xor     edx, edx; pThrowInfo
0x180035490  xor     ecx, ecx; pExceptionObject
0x180035492  call    _CxxThrowException_0
```
