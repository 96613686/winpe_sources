# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x18001c217`
- end: `0x18001c247`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008fce`
- `0x18000f3e0`
- `0x18001c217`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 40 )
    std::_Dest_val<std::allocator<std::wstring>,std::wstring>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18001c217  mov     [rsp+arg_8], rdx
0x18001c21c  push    rbx
0x18001c21d  push    rbp
0x18001c21e  sub     rsp, 28h
0x18001c222  mov     rbp, rdx
0x18001c225  mov     rbx, [rbp+48h]
0x18001c229  jmp     short loc_18001C237
0x18001c22b  mov     rdx, rbx
0x18001c22e  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x18001c233  add     rbx, 28h ; '('
0x18001c237  cmp     rbx, [rbp+40h]
0x18001c23b  jnz     short loc_18001C22B
0x18001c23d  xor     edx, edx; pThrowInfo
0x18001c23f  xor     ecx, ecx; pExceptionObject
0x18001c241  call    _CxxThrowException_0
```
