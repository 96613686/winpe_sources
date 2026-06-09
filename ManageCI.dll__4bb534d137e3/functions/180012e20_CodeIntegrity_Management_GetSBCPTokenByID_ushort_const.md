# CodeIntegrity::Management::GetSBCPTokenByID(ushort const *)

- ea: `0x180012e20`
- end: `0x180012f43`
- name: `?GetSBCPTokenByID@Management@CodeIntegrity@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEBG@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800090d0`

## callees

- `0x180002a90`
- `0x180008474`
- `0x18000eab0`
- `0x180010534`
- `0x1800109d8`
- `0x180010a1c`
- `0x180010ca4`
- `0x180012e20`
- `0x180015518`
- `0x1800159fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CodeIntegrity::Management::GetSBCPTokenByID(__int64 a1, __int64 a2)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 result; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17[2]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v18[32]; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v20[32]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *(_QWORD *)v17 = a1;
  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
    (__int64 *)qword_180039710,
    (__int64 *)v17,
    (__int64)qword_180039720);
  try
  {
    if ( *(_QWORD *)v17 == *(_QWORD *)qword_180039710 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0xAD, v4, v5, v17[0]);
    v6 = (__int64 *)(*(_QWORD *)v17 + 64LL);
    v7 = std::wstring::wstring((__int64)v20, a2);
    v8 = std::operator+<unsigned short>(v19, qword_180039720);
    std::wstring::wstring(v18, v9, v8, v7);
    std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(
      v6,
      v17,
      (__int64)v18);
    std::wstring::_Tidy_deallocate((__int64)v18);
    std::wstring::_Tidy_deallocate((__int64)v19);
    std::wstring::_Tidy_deallocate((__int64)v20);
    if ( *(_QWORD *)v17 == *v6 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0xB3, v10, v11, v17[0]);
    std::vector<unsigned char>::vector<unsigned char>(a1, *(_QWORD *)v17 + 120LL);
    result = a1;
  }
  catch ( std::exception )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0xBA, v12, v13);
    wil::details::in1diag3::Throw_CaughtException(retaddr, (void *)0xBB, v15, v16);
  }
  if ( *(_QWORD *)v17 == *(_QWORD *)qword_180039710 )
    wil::details::in1diag3::Throw_Win32(retaddr, (void *)0xAD, v4, v5, v17[0]);
}

```

## disassembly

```asm
0x180012e20  mov     [rsp+arg_10], rbx
0x180012e25  mov     [rsp+arg_18], rsi
0x180012e2a  push    rdi
0x180012e2b  sub     rsp, 0A0h
0x180012e32  mov     rax, cs:__security_cookie
0x180012e39  xor     rax, rsp
0x180012e3c  mov     [rsp+0A8h+var_18], rax
0x180012e44  mov     rsi, rdx
0x180012e47  mov     rbx, rcx
0x180012e4a  mov     qword ptr [rsp+0A8h+var_88], rcx; unsigned int
0x180012e4f  lea     r8, qword_180039720
0x180012e56  lea     rdx, [rsp+0A8h+var_88]
0x180012e5b  mov     rcx, cs:qword_180039710
0x180012e62  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x180012e67  mov     rax, qword ptr [rsp+0A8h+var_88]
0x180012e6c  mov     rcx, cs:qword_180039710
0x180012e73  cmp     rax, [rcx]
0x180012e76  jnz     short loc_180012E8A
0x180012e78  mov     rcx, [rsp+0A8h]; this
0x180012e80  mov     edx, 0ADh; void *
0x180012e85  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012e8a  lea     rdi, [rax+40h]
0x180012e8e  mov     rdx, rsi
0x180012e91  lea     rcx, [rsp+0A8h+var_38]
0x180012e96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012e9b  mov     rsi, rax
0x180012e9e  lea     rdx, qword_180039720
0x180012ea5  lea     rcx, [rsp+0A8h+var_58]
0x180012eaa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180012eaf  nop
0x180012eb0  mov     r9, rsi
0x180012eb3  mov     r8, rax
0x180012eb6  lea     rcx, [rsp+0A8h+var_78]
0x180012ebb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180012ec0  lea     r8, [rsp+0A8h+var_78]
0x180012ec5  lea     rdx, [rsp+0A8h+var_88]
0x180012eca  mov     rcx, rdi
0x180012ecd  call    ??$find@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@$0A@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VAuthorizationToken@Management@CodeIntegrity@@@std@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::find<std::wstring,std::less<void>,0>(std::wstring const &)
0x180012ed2  lea     rcx, [rsp+0A8h+var_78]
0x180012ed7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012edc  nop
0x180012edd  lea     rcx, [rsp+0A8h+var_58]
0x180012ee2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ee7  nop
0x180012ee8  lea     rcx, [rsp+0A8h+var_38]
0x180012eed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012ef2  mov     rdx, qword ptr [rsp+0A8h+var_88]
0x180012ef7  cmp     rdx, [rdi]
0x180012efa  jnz     short loc_180012F0E
0x180012efc  mov     rcx, [rsp+0A8h]; this
0x180012f04  mov     edx, 0B3h; void *
0x180012f09  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012f0e  add     rdx, 78h ; 'x'
0x180012f12  mov     rcx, rbx
0x180012f15  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180012f1a  mov     rax, rbx
0x180012f1d  mov     rcx, [rsp+0A8h+var_18]
0x180012f25  xor     rcx, rsp; StackCookie
0x180012f28  call    __security_check_cookie
0x180012f2d  lea     r11, [rsp+0A8h+var_8]
0x180012f35  mov     rbx, [r11+20h]
0x180012f39  mov     rsi, [r11+28h]
0x180012f3d  mov     rsp, r11
0x180012f40  pop     rdi
0x180012f41  retn
```
