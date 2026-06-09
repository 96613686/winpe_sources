# CodeIntegrity::Management::detail::SbcpTokenView::name(void)

- ea: `0x180015a6c`
- end: `0x180015ae4`
- name: `?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fb60`
- `0x180010534`
- `0x180011d00`
- `0x1800168d8`
- `0x1800188c0`

## callees

- `0x180002a90`
- `0x18000828c`
- `0x180008474`
- `0x18000eab0`
- `0x18000ef38`
- `0x18001097c`

## pseudocode

```c
__int64 __fastcall CodeIntegrity::Management::detail::SbcpTokenView::name(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // r9
  __int64 v6; // rax
  _BYTE v8[32]; // [rsp+20h] [rbp-38h] BYREF

  v3 = a1 + 56;
  std::operator+<unsigned short>(v8, a1 + 24);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v6 = std::wstring::_Append<unsigned short>(v5, v4, *(_QWORD *)(v3 + 16));
  std::wstring::wstring(a2, v6);
  std::wstring::_Tidy_deallocate((__int64)v8);
  return a2;
}

```

## disassembly

```asm
0x180015a6c  mov     [rsp+arg_10], rbx
0x180015a71  push    rdi
0x180015a72  sub     rsp, 50h
0x180015a76  mov     rax, cs:__security_cookie
0x180015a7d  xor     rax, rsp
0x180015a80  mov     [rsp+58h+var_18], rax
0x180015a85  mov     rdi, rdx
0x180015a88  lea     rbx, [rcx+38h]
0x180015a8c  lea     rdx, [rcx+18h]
0x180015a90  lea     rcx, [rsp+58h+var_38]
0x180015a95  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180015a9a  mov     r9, rax
0x180015a9d  mov     rcx, rbx
0x180015aa0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015aa5  mov     r8, [rbx+10h]
0x180015aa9  mov     rdx, rax
0x180015aac  mov     rcx, r9
0x180015aaf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180015ab4  mov     rdx, rax
0x180015ab7  mov     rcx, rdi
0x180015aba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180015abf  lea     rcx, [rsp+58h+var_38]
0x180015ac4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ac9  mov     rax, rdi
0x180015acc  mov     rcx, [rsp+58h+var_18]
0x180015ad1  xor     rcx, rsp; StackCookie
0x180015ad4  call    __security_check_cookie
0x180015ad9  mov     rbx, [rsp+58h+arg_10]
0x180015ade  add     rsp, 50h
0x180015ae2  pop     rdi
0x180015ae3  retn
```
