# _anonymous_namespace_::GetCurrentUserSid

- ea: `0x18002d454`
- end: `0x18002d4c8`
- name: `_anonymous_namespace_::GetCurrentUserSid`
- size: `116`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d2b0`

## callees

- `0x18000ea34`
- `0x18002c8cc`
- `0x18002cec8`
- `0x18002d454`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d495`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d495`

## string_xrefs

- `0x18002d4a4`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall anonymous_namespace_::GetCurrentUserSid(LPWSTR *StringSid)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PSID *v5; // [rsp+48h] [rbp+10h] BYREF

  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&v5, -4);
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(*v5, StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      v2);
  wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(&v5);
  return StringSid;
}

```

## disassembly

```asm
0x18002d454  mov     [rsp+arg_0], rcx
0x18002d459  push    rbx
0x18002d45a  sub     rsp, 30h
0x18002d45e  mov     rbx, rcx
0x18002d461  mov     [rsp+38h+var_18], 0
0x18002d469  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x18002d470  lea     rcx, [rsp+38h+arg_8]
0x18002d475  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18002d47a  nop
0x18002d47b  mov     [rsp+38h+var_18], 7
0x18002d483  mov     qword ptr [rbx], 0
0x18002d48a  mov     rdx, rbx; StringSid
0x18002d48d  mov     rcx, [rsp+38h+arg_8]
0x18002d492  mov     rcx, [rcx]; Sid
0x18002d495  call    cs:__imp_ConvertSidToStringSidW
0x18002d49b  mov     rcx, [rsp+38h]; this
0x18002d4a0  test    eax, eax
0x18002d4a2  jnz     short loc_18002D4B4
0x18002d4a4  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d4ab  lea     edx, [rax+51h]; void *
0x18002d4ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d4b4  lea     rcx, [rsp+38h+arg_8]
0x18002d4b9  call    ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x18002d4be  mov     rax, rbx
0x18002d4c1  add     rsp, 30h
0x18002d4c5  pop     rbx
0x18002d4c6  retn
```
