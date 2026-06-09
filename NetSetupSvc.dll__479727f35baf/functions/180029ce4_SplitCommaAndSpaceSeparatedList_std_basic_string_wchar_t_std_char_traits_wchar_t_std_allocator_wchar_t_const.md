# SplitCommaAndSpaceSeparatedList(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180029ce4`
- end: `0x180029dd9`
- name: `?SplitCommaAndSpaceSeparatedList@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x180007048`
- `0x18000d954`
- `0x18000d9b4`
- `0x18001793c`
- `0x180018490`
- `0x180019c24`
- `0x180029c8c`
- `0x180029ce4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall SplitCommaAndSpaceSeparatedList(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // r8
  _WORD *v4; // rsi
  _WORD *i; // rbx
  _BYTE v7[16]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+40h] [rbp-28h]

  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(a1);
  std::wstring::wstring((__int64)v7);
  v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v4 = (_WORD *)(v2 + 2LL * *(_QWORD *)(v3 + 16));
  for ( i = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(); i != v4; ++i )
  {
    if ( *i == 32 || *i == 44 )
    {
      if ( (unsigned __int8)IsValidRangeToken(v7) )
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v7);
      v8 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr() = 0;
    }
    else
    {
      std::wstring::push_back(v7, (unsigned __int16)*i);
    }
  }
  if ( (unsigned __int8)IsValidRangeToken(v7) )
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v7);
  std::wstring::_Tidy_deallocate((__int64)v7);
  return a1;
}

```

## disassembly

```asm
0x180029ce4  push    rbp
0x180029ce6  push    rbx
0x180029ce7  push    rsi
0x180029ce8  push    rdi
0x180029ce9  mov     rbp, rsp
0x180029cec  sub     rsp, 68h
0x180029cf0  mov     rax, cs:__security_cookie
0x180029cf7  xor     rax, rsp
0x180029cfa  mov     [rbp+var_18], rax
0x180029cfe  mov     r8, rdx
0x180029d01  mov     rdi, rcx
0x180029d04  mov     [rbp+var_40], rcx
0x180029d08  mov     [rbp+var_48], 0
0x180029d0f  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180029d14  mov     [rbp+var_48], 1
0x180029d1b  lea     rcx, [rbp+var_38]
0x180029d1f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180029d24  nop
0x180029d25  mov     rcx, rdx
0x180029d28  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029d2d  mov     rdx, rax
0x180029d30  mov     rax, [r8+10h]
0x180029d34  lea     rsi, [rdx+rax*2]
0x180029d38  mov     rcx, r8
0x180029d3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029d40  mov     rbx, rax
0x180029d43  cmp     rax, rsi
0x180029d46  jz      short loc_180029D9D
0x180029d48  cmp     word ptr [rbx], 20h ; ' '
0x180029d4c  jz      short loc_180029D62
0x180029d4e  cmp     word ptr [rbx], 2Ch ; ','
0x180029d52  jz      short loc_180029D62
0x180029d54  movzx   edx, word ptr [rbx]
0x180029d57  lea     rcx, [rbp+var_38]
0x180029d5b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x180029d60  jmp     short loc_180029D94
0x180029d62  lea     rcx, [rbp+var_38]
0x180029d66  call    IsValidRangeToken
0x180029d6b  test    al, al
0x180029d6d  jz      short loc_180029D7B
0x180029d6f  lea     rdx, [rbp+var_38]
0x180029d73  mov     rcx, rdi
0x180029d76  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180029d7b  mov     [rbp+var_28], 0
0x180029d83  lea     rcx, [rbp+var_38]
0x180029d87  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180029d8c  mov     rdx, rax
0x180029d8f  xor     eax, eax
0x180029d91  mov     [rdx], ax
0x180029d94  add     rbx, 2
0x180029d98  cmp     rbx, rsi
0x180029d9b  jnz     short loc_180029D48
0x180029d9d  lea     rcx, [rbp+var_38]
0x180029da1  call    IsValidRangeToken
0x180029da6  test    al, al
0x180029da8  jz      short loc_180029DB7
0x180029daa  lea     rdx, [rbp+var_38]
0x180029dae  mov     rcx, rdi
0x180029db1  call    ??$_Emplace_one_at_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180029db6  nop
0x180029db7  lea     rcx, [rbp+var_38]
0x180029dbb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029dc0  mov     rax, rdi
0x180029dc3  mov     rcx, [rbp+var_18]
0x180029dc7  xor     rcx, rsp; StackCookie
0x180029dca  call    __security_check_cookie
0x180029dcf  add     rsp, 68h
0x180029dd3  pop     rdi
0x180029dd4  pop     rsi
0x180029dd5  pop     rbx
0x180029dd6  pop     rbp
0x180029dd7  retn
```
