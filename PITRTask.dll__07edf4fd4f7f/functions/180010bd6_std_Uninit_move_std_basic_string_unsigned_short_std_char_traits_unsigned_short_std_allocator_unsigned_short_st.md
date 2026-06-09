# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x180010bd6`
- end: `0x180010c06`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001dcc`
- `0x180003078`
- `0x180010bd6`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 88); i != *(_QWORD *)(a2 + 80); i += 32 )
    std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(a1, i);
  throw;
}

```

## disassembly

```asm
0x180010bd6  mov     [rsp+arg_8], rdx
0x180010bdb  push    rbx
0x180010bdc  push    rbp
0x180010bdd  sub     rsp, 28h
0x180010be1  mov     rbp, rdx
0x180010be4  mov     rbx, [rbp+58h]
0x180010be8  jmp     short loc_180010BF6
0x180010bea  mov     rdx, rbx
0x180010bed  call    ??$destroy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(std::wstring *)
0x180010bf2  add     rbx, 20h ; ' '
0x180010bf6  cmp     rbx, [rbp+50h]
0x180010bfa  jnz     short loc_180010BEA
0x180010bfc  xor     edx, edx; pThrowInfo
0x180010bfe  xor     ecx, ecx; pExceptionObject
0x180010c00  call    _CxxThrowException_0
```
