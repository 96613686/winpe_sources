# CodeIntegrity::Management::detail::SbcpTokenView::operator<(CodeIntegrity::Management::detail::SbcpTokenView const &)

- ea: `0x1800168d8`
- end: `0x18001694f`
- name: `??MSbcpTokenView@detail@Management@CodeIntegrity@@QEBA_NAEBV0123@@Z`
- size: `119`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f09c`
- `0x18000f1ec`
- `0x18001a1a4`

## callees

- `0x180002a90`
- `0x180008474`
- `0x1800159b8`
- `0x180015a6c`

## pseudocode

```c
char __fastcall CodeIntegrity::Management::detail::SbcpTokenView::operator<(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  _BYTE v6[32]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-38h] BYREF

  v3 = CodeIntegrity::Management::detail::SbcpTokenView::name(a1, v7);
  v4 = CodeIntegrity::Management::detail::SbcpTokenView::name(a2, v6);
  LODWORD(v3) = (unsigned int)std::wstring::compare(v3, v4) >> 31;
  std::wstring::_Tidy_deallocate(v6);
  std::wstring::_Tidy_deallocate(v7);
  return v3;
}

```

## disassembly

```asm
0x1800168d8  mov     [rsp+arg_10], rbx
0x1800168dd  push    rdi
0x1800168de  sub     rsp, 70h
0x1800168e2  mov     rax, cs:__security_cookie
0x1800168e9  xor     rax, rsp
0x1800168ec  mov     [rsp+78h+var_18], rax
0x1800168f1  mov     rdi, rdx
0x1800168f4  lea     rdx, [rsp+78h+var_38]
0x1800168f9  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x1800168fe  lea     rdx, [rsp+78h+var_58]
0x180016903  mov     rcx, rdi
0x180016906  mov     rbx, rax
0x180016909  call    ?name@SbcpTokenView@detail@Management@CodeIntegrity@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CodeIntegrity::Management::detail::SbcpTokenView::name(void)
0x18001690e  mov     rdx, rax
0x180016911  mov     rcx, rbx
0x180016914  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180016919  mov     ebx, eax
0x18001691b  lea     rcx, [rsp+78h+var_58]
0x180016920  shr     ebx, 1Fh
0x180016923  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016928  lea     rcx, [rsp+78h+var_38]
0x18001692d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016932  mov     al, bl
0x180016934  mov     rcx, [rsp+78h+var_18]
0x180016939  xor     rcx, rsp; StackCookie
0x18001693c  call    __security_check_cookie
0x180016941  mov     rbx, [rsp+78h+arg_10]
0x180016949  add     rsp, 70h
0x18001694d  pop     rdi
0x18001694e  retn
```
