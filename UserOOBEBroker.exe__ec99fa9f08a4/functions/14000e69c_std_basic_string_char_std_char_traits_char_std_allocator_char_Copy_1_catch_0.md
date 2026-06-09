# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x14000e69c`
- end: `0x14000e6c1`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000263c`
- `0x140006260`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x14000e69c  mov     [rsp+arg_8], rdx
0x14000e6a1  push    rbp
0x14000e6a2  sub     rsp, 20h
0x14000e6a6  mov     rbp, rdx
0x14000e6a9  xor     r8d, r8d
0x14000e6ac  mov     dl, 1
0x14000e6ae  mov     rcx, [rbp+50h]
0x14000e6b2  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000e6b7  xor     edx, edx; pThrowInfo
0x14000e6b9  xor     ecx, ecx; pExceptionObject
0x14000e6bb  call    _CxxThrowException_0
```
