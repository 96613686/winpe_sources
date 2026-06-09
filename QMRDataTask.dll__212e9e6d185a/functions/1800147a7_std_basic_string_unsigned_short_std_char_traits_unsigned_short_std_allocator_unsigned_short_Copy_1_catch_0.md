# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x1800147a7`
- end: `0x1800147cc`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001cec`
- `0x1800026c8`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
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
0x1800147a7  mov     [rsp+arg_8], rdx
0x1800147ac  push    rbp
0x1800147ad  sub     rsp, 20h
0x1800147b1  mov     rbp, rdx
0x1800147b4  xor     r8d, r8d
0x1800147b7  mov     dl, 1
0x1800147b9  mov     rcx, [rbp+50h]
0x1800147bd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800147c2  xor     edx, edx; pThrowInfo
0x1800147c4  xor     ecx, ecx; pExceptionObject
0x1800147c6  call    _CxxThrowException_0
```
