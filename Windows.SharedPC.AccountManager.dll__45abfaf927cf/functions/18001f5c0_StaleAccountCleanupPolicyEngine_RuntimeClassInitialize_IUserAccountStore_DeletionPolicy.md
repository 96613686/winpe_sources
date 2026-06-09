# StaleAccountCleanupPolicyEngine::RuntimeClassInitialize(IUserAccountStore *,DeletionPolicy)

- ea: `0x18001f5c0`
- end: `0x18001f6d8`
- name: `?RuntimeClassInitialize@StaleAccountCleanupPolicyEngine@@UEAAJPEAUIUserAccountStore@@W4DeletionPolicy@@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b63c`

## callees

- `0x180003530`
- `0x180008a38`
- `0x18000a1bc`
- `0x18000cd50`
- `0x18001c4c0`
- `0x18001f5c0`
- `0x18002297c`

## string_xrefs

- `0x18001f6aa`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\staleaccountcleanuppolicyengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StaleAccountCleanupPolicyEngine::RuntimeClassInitialize(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 SharedPCRegistryValue; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v10[8]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  std::wstring::wstring((__int64)v11, (__int64)L"InactiveAccountThresholdInDays");
  std::wstring::wstring((__int64)v10, (__int64)L"AccountManagement");
  SharedPCRegistryValue = (unsigned int)GetSharedPCRegistryValue((__int64)v10, (__int64)v11, 0x1Eu);
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v11);
  *(_QWORD *)(a1 + 72) = 864000000000LL * SharedPCRegistryValue;
  std::wstring::wstring((__int64)v10, (__int64)L"DisableProfileInactivityEvaluationOnLogoff");
  std::wstring::wstring((__int64)v11, (__int64)L"AccountManagement");
  *(_BYTE *)(a1 + 80) = (unsigned int)GetSharedPCRegistryValue((__int64)v11, (__int64)v10, 0) == 1;
  std::wstring::_Tidy_deallocate((__int64)v11);
  std::wstring::_Tidy_deallocate((__int64)v10);
  v7 = BasePolicyEngine::RuntimeClassInitialize(a1, a2, a3);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14,
    (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\staleaccountcleanuppolicyengine.cpp",
    (const char *)(unsigned int)v7,
    v10[0]);
  return v8;
}

```

## disassembly

```asm
0x18001f5c0  push    rbp
0x18001f5c2  push    rbx
0x18001f5c3  push    rsi
0x18001f5c4  push    rdi
0x18001f5c5  push    r14
0x18001f5c7  mov     rbp, rsp
0x18001f5ca  sub     rsp, 70h
0x18001f5ce  mov     rax, cs:__security_cookie
0x18001f5d5  xor     rax, rsp
0x18001f5d8  mov     [rbp+var_10], rax
0x18001f5dc  mov     r14d, r8d
0x18001f5df  mov     rsi, rdx
0x18001f5e2  mov     rdi, rcx
0x18001f5e5  lea     rdx, aInactiveaccoun; "InactiveAccountThresholdInDays"
0x18001f5ec  lea     rcx, [rbp+var_30]
0x18001f5f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f5f5  nop
0x18001f5f6  lea     rdx, aAccountmanagem; "AccountManagement"
0x18001f5fd  lea     rcx, [rbp+var_50]
0x18001f601  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f606  nop
0x18001f607  mov     r8d, 1Eh
0x18001f60d  lea     rdx, [rbp+var_30]
0x18001f611  lea     rcx, [rbp+var_50]
0x18001f615  call    ?GetSharedPCRegistryValue@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z; GetSharedPCRegistryValue(std::wstring const &,std::wstring const &,ulong)
0x18001f61a  mov     ebx, eax
0x18001f61c  lea     rcx, [rbp+var_50]
0x18001f620  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f625  nop
0x18001f626  lea     rcx, [rbp+var_30]
0x18001f62a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f62f  mov     rcx, 0C92A69C000h
0x18001f639  imul    rbx, rcx
0x18001f63d  mov     [rdi+48h], rbx
0x18001f641  lea     rdx, aDisableprofile; "DisableProfileInactivityEvaluationOnLog"...
0x18001f648  lea     rcx, [rbp+var_50]
0x18001f64c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f651  nop
0x18001f652  lea     rdx, aAccountmanagem; "AccountManagement"
0x18001f659  lea     rcx, [rbp+var_30]
0x18001f65d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f662  nop
0x18001f663  xor     r8d, r8d
0x18001f666  lea     rdx, [rbp+var_50]
0x18001f66a  lea     rcx, [rbp+var_30]
0x18001f66e  call    ?GetSharedPCRegistryValue@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z; GetSharedPCRegistryValue(std::wstring const &,std::wstring const &,ulong)
0x18001f673  cmp     eax, 1
0x18001f676  setz    al
0x18001f679  mov     [rdi+50h], al
0x18001f67c  lea     rcx, [rbp+var_30]
0x18001f680  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f685  nop
0x18001f686  lea     rcx, [rbp+var_50]
0x18001f68a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f68f  mov     r8d, r14d
0x18001f692  mov     rdx, rsi
0x18001f695  mov     rcx, rdi
0x18001f698  call    ?RuntimeClassInitialize@BasePolicyEngine@@UEAAJPEAUIUserAccountStore@@W4DeletionPolicy@@@Z; BasePolicyEngine::RuntimeClassInitialize(IUserAccountStore *,DeletionPolicy)
0x18001f69d  mov     ebx, eax
0x18001f69f  test    eax, eax
0x18001f6a1  jns     short loc_18001F6BF
0x18001f6a3  mov     rcx, [rbp+28h]; this
0x18001f6a7  mov     r9d, eax; char *
0x18001f6aa  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001f6b1  mov     edx, 14h; void *
0x18001f6b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6bb  mov     eax, ebx
0x18001f6bd  jmp     short loc_18001F6C1
0x18001f6bf  xor     eax, eax
0x18001f6c1  mov     rcx, [rbp+var_10]
0x18001f6c5  xor     rcx, rsp; StackCookie
0x18001f6c8  call    __security_check_cookie
0x18001f6cd  add     rsp, 70h
0x18001f6d1  pop     r14
0x18001f6d3  pop     rdi
0x18001f6d4  pop     rsi
0x18001f6d5  pop     rbx
0x18001f6d6  pop     rbp
0x18001f6d7  retn
```
