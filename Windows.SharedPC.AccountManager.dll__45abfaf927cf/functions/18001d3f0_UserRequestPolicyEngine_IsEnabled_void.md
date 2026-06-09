# UserRequestPolicyEngine::IsEnabled(void)

- ea: `0x18001d3f0`
- end: `0x18001d47a`
- name: `?IsEnabled@UserRequestPolicyEngine@@UEAA_NXZ`
- size: `138`
- prototype: `bool __fastcall(UserRequestPolicyEngine *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003530`
- `0x18000a1bc`
- `0x18000cd50`
- `0x18001d3f0`
- `0x18002297c`

## string_xrefs

- `0x18001d40a`: `EnableUserRequestedDeletes`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UserRequestPolicyEngine::IsEnabled(UserRequestPolicyEngine *this)
{
  const char *v1; // r9
  bool v2; // bl
  bool v4; // [rsp+20h] [rbp-58h]
  _BYTE v6[32]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v7[32]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    std::wstring::wstring((__int64)v7, (__int64)L"EnableUserRequestedDeletes");
    std::wstring::wstring((__int64)v6, (__int64)L"AccountManagement");
    v2 = (unsigned int)GetSharedPCRegistryValue((__int64)v6, (__int64)v7, 0) != 0;
    v4 = v2;
    std::wstring::_Tidy_deallocate((__int64)v6);
    std::wstring::_Tidy_deallocate((__int64)v7);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6E,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\userrequestpolicyengine.cpp",
      v1);
    return v4;
  }
  return v2;
}

```

## disassembly

```asm
0x18001d3f0  push    rbx
0x18001d3f2  sub     rsp, 70h
0x18001d3f6  mov     rax, cs:__security_cookie
0x18001d3fd  xor     rax, rsp
0x18001d400  mov     [rsp+78h+var_10], rax
0x18001d405  mov     [rsp+78h+var_58], 0
0x18001d40a  lea     rdx, aEnableuserrequ; "EnableUserRequestedDeletes"
0x18001d411  lea     rcx, [rsp+78h+var_30]
0x18001d416  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d41b  nop
0x18001d41c  lea     rdx, aAccountmanagem; "AccountManagement"
0x18001d423  lea     rcx, [rsp+78h+var_50]
0x18001d428  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d42d  nop
0x18001d42e  xor     r8d, r8d
0x18001d431  lea     rdx, [rsp+78h+var_30]
0x18001d436  lea     rcx, [rsp+78h+var_50]
0x18001d43b  call    ?GetSharedPCRegistryValue@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z; GetSharedPCRegistryValue(std::wstring const &,std::wstring const &,ulong)
0x18001d440  test    eax, eax
0x18001d442  setnz   bl
0x18001d445  mov     [rsp+78h+var_58], bl
0x18001d449  lea     rcx, [rsp+78h+var_50]
0x18001d44e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d453  nop
0x18001d454  lea     rcx, [rsp+78h+var_30]
0x18001d459  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d45e  nop
0x18001d45f  jmp     short loc_18001D465
0x18001d461  mov     bl, [rsp+78h+var_58]
0x18001d465  mov     al, bl
0x18001d467  mov     rcx, [rsp+78h+var_10]
0x18001d46c  xor     rcx, rsp; StackCookie
0x18001d46f  call    __security_check_cookie
0x18001d474  add     rsp, 70h
0x18001d478  pop     rbx
0x18001d479  retn
```
