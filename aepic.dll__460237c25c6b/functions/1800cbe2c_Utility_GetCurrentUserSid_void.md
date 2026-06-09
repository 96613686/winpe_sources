# Utility::GetCurrentUserSid(void)

- ea: `0x1800cbe2c`
- end: `0x1800cbecd`
- name: `?GetCurrentUserSid@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x1800060e8`
- `0x18000faf0`
- `0x18001036c`
- `0x1800c9b28`
- `0x1800cbe2c`
- `0x1800cfc24`
- `0x1800cff88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbe9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cbe9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cbe66`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cbe66`

## string_xrefs

- `0x1800cbe75`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Utility::GetCurrentUserSid(__int64 a1)
{
  const char *v2; // r9
  void *v3; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPWSTR StringSid; // [rsp+48h] [rbp+10h] BYREF
  void *Block; // [rsp+50h] [rbp+18h] BYREF
  void *v8; // [rsp+58h] [rbp+20h] BYREF

  wil::open_current_access_token(&v8);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v8);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
      v2);
  std::wstring::wstring(a1, StringSid);
  CoTaskMemFree(StringSid);
  v3 = Block;
  Block = 0;
  if ( v3 )
    operator delete(v3);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x1800cbe2c  push    rbx
0x1800cbe2e  sub     rsp, 30h
0x1800cbe32  mov     rbx, rcx
0x1800cbe35  lea     rcx, [rsp+38h+arg_18]
0x1800cbe3a  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x1800cbe3f  nop
0x1800cbe40  mov     rdx, [rsp+38h+arg_18]
0x1800cbe45  lea     rcx, [rsp+38h+Block]
0x1800cbe4a  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1800cbe4f  nop
0x1800cbe50  mov     [rsp+38h+StringSid], 0
0x1800cbe59  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800cbe5e  mov     rcx, [rsp+38h+Block]
0x1800cbe63  mov     rcx, [rcx]; Sid
0x1800cbe66  call    cs:__imp_ConvertSidToStringSidW
0x1800cbe6c  test    eax, eax
0x1800cbe6e  jnz     short loc_1800CBE87
0x1800cbe70  mov     rcx, [rsp+38h]; this
0x1800cbe75  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800cbe7c  mov     edx, 307h; void *
0x1800cbe81  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800cbe87  mov     rdx, [rsp+38h+StringSid]
0x1800cbe8c  mov     rcx, rbx
0x1800cbe8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cbe94  nop
0x1800cbe95  mov     rcx, [rsp+38h+StringSid]; pv
0x1800cbe9a  call    cs:__imp_CoTaskMemFree
0x1800cbea0  nop
0x1800cbea1  mov     rcx, [rsp+38h+Block]; Block
0x1800cbea6  mov     [rsp+38h+Block], 0
0x1800cbeaf  test    rcx, rcx
0x1800cbeb2  jz      short loc_1800CBEBA
0x1800cbeb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cbeb9  nop
0x1800cbeba  lea     rcx, [rsp+38h+arg_18]
0x1800cbebf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cbec4  mov     rax, rbx
0x1800cbec7  add     rsp, 30h
0x1800cbecb  pop     rbx
0x1800cbecc  retn
```
