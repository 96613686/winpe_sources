# Utility::GetCurrentUserSid(void)

- ea: `0x18003f1c8`
- end: `0x18003f288`
- name: `?GetCurrentUserSid@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008e58`

## callees

- `0x18003f1c8`
- `0x18003f290`
- `0x1800404c4`
- `0x1800405a8`
- `0x18005a56c`
- `0x1801003d8`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x18003f213`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18003f213`
- `KERNEL32!CloseHandle` at `0x18003f274`
- `KERNEL32!CloseHandle` at `0x18003f274`
- `ole32!CoTaskMemFree` at `0x18003f247`
- `ole32!CoTaskMemFree` at `0x18003f247`

## string_xrefs

- `0x18003f222`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Utility::GetCurrentUserSid(__int64 a1)
{
  char *v2; // rbx
  const char *v3; // r9
  void *v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPWSTR StringSid; // [rsp+48h] [rbp+10h] BYREF
  void *Block; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+20h] BYREF

  wil::open_current_access_token(&hObject);
  v2 = (char *)hObject;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, hObject);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x307,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
      v3);
  std::wstring::wstring(a1, StringSid);
  CoTaskMemFree(StringSid);
  v4 = Block;
  Block = 0;
  if ( v4 )
    operator delete(v4);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  return a1;
}

```

## disassembly

```asm
0x18003f1c8  push    rdi
0x18003f1ca  sub     rsp, 30h
0x18003f1ce  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x18003f1d7  mov     [rsp+38h+arg_0], rbx
0x18003f1dc  mov     rdi, rcx
0x18003f1df  lea     rcx, [rsp+38h+hObject]
0x18003f1e4  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18003f1e9  nop
0x18003f1ea  mov     rbx, [rsp+38h+hObject]
0x18003f1ef  mov     rdx, rbx
0x18003f1f2  lea     rcx, [rsp+38h+Block]
0x18003f1f7  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18003f1fc  nop
0x18003f1fd  mov     [rsp+38h+StringSid], 0
0x18003f206  lea     rdx, [rsp+38h+StringSid]; StringSid
0x18003f20b  mov     rcx, [rsp+38h+Block]
0x18003f210  mov     rcx, [rcx]; Sid
0x18003f213  call    cs:__imp_ConvertSidToStringSidW
0x18003f219  test    eax, eax
0x18003f21b  jnz     short loc_18003F234
0x18003f21d  mov     rcx, [rsp+38h]; this
0x18003f222  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18003f229  mov     edx, 307h; void *
0x18003f22e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003f234  mov     rdx, [rsp+38h+StringSid]
0x18003f239  mov     rcx, rdi
0x18003f23c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003f241  nop
0x18003f242  mov     rcx, [rsp+38h+StringSid]; pv
0x18003f247  call    cs:__imp_CoTaskMemFree
0x18003f24d  nop
0x18003f24e  mov     rcx, [rsp+38h+Block]; Block
0x18003f253  mov     [rsp+38h+Block], 0
0x18003f25c  test    rcx, rcx
0x18003f25f  jz      short loc_18003F267
0x18003f261  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003f266  nop
0x18003f267  lea     rax, [rbx-1]
0x18003f26b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f26f  ja      short loc_18003F27A
0x18003f271  mov     rcx, rbx; hObject
0x18003f274  call    cs:__imp_CloseHandle
0x18003f27a  mov     rax, rdi
0x18003f27d  mov     rbx, [rsp+38h+arg_0]
0x18003f282  add     rsp, 30h
0x18003f286  pop     rdi
0x18003f287  retn
```
