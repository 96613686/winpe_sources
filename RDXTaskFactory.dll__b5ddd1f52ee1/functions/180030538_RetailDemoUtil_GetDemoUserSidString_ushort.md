# RetailDemoUtil::GetDemoUserSidString(ushort * *)

- ea: `0x180030538`
- end: `0x1800305b1`
- name: `?GetDemoUserSidString@RetailDemoUtil@@YAXPEAPEAG@Z`
- size: `121`
- prototype: `void __fastcall(LPWSTR *StringSid, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033334`
- `0x18003a290`
- `0x1800464a0`

## callees

- `0x180003cc4`
- `0x180014d04`
- `0x180022ad8`
- `0x18002ee20`
- `0x180030538`
- `0x1800305b8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030567`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030567`

## string_xrefs

- `0x180030576`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RetailDemoUtil::GetDemoUserSidString(LPWSTR *StringSid, unsigned __int16 **a2)
{
  const char *v3; // r9
  void *v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *Block; // [rsp+38h] [rbp+10h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  RetailDemoUtil::GetDemoUserToken(&v7, (unsigned __int64 *)a2);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v7);
  if ( !ConvertSidToStringSidW(*(PSID *)Block, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
      v3);
  v4 = Block;
  Block = 0;
  if ( v4 )
    operator delete(v4);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v7);
}

```

## disassembly

```asm
0x180030538  push    rbx
0x18003053a  sub     rsp, 20h
0x18003053e  mov     rbx, rcx
0x180030541  lea     rcx, [rsp+28h+arg_10]
0x180030546  call    ?GetDemoUserToken@RetailDemoUtil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; RetailDemoUtil::GetDemoUserToken(void)
0x18003054b  nop
0x18003054c  mov     rdx, [rsp+28h+arg_10]
0x180030551  lea     rcx, [rsp+28h+Block]
0x180030556  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18003055b  nop
0x18003055c  mov     rdx, rbx; StringSid
0x18003055f  mov     rcx, [rsp+28h+Block]
0x180030564  mov     rcx, [rcx]; Sid
0x180030567  call    cs:__imp_ConvertSidToStringSidW
0x18003056d  mov     rcx, [rsp+28h]; this
0x180030572  test    eax, eax
0x180030574  jnz     short loc_180030588
0x180030576  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003057d  mov     edx, 1B9h; void *
0x180030582  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180030588  mov     rcx, [rsp+28h+Block]; Block
0x18003058d  mov     [rsp+28h+Block], 0
0x180030596  test    rcx, rcx
0x180030599  jz      short loc_1800305A1
0x18003059b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800305a0  nop
0x1800305a1  lea     rcx, [rsp+28h+arg_10]
0x1800305a6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800305ab  add     rsp, 20h
0x1800305af  pop     rbx
0x1800305b0  retn
```
