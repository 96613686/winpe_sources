# UserHelpers::GetUserSidString(Windows::System::IUser *)

- ea: `0x1800437d8`
- end: `0x18004387e`
- name: `?GetUserSidString@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180043568`
- `0x180099698`

## callees

- `0x1800437d8`
- `0x180043884`
- `0x1800438a8`
- `0x180055f90`
- `0x180061304`
- `0x1800829f0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004383a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004383a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPWSTR *__fastcall UserHelpers::GetUserSidString(LPWSTR *StringSid, UserHelpers *a2)
{
  __int64 *UserTokenHandle; // rax
  const char *v4; // r9
  void *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *Block; // [rsp+50h] [rbp+18h] BYREF
  void *v9; // [rsp+58h] [rbp+20h] BYREF

  *StringSid = 0;
  UserTokenHandle = (__int64 *)UserHelpers::GetUserTokenHandle(&v9, a2);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, *UserTokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  if ( !ConvertSidToStringSidW(*(PSID *)Block, StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
      v4);
  v5 = Block;
  Block = 0;
  if ( v5 )
    operator delete(v5);
  return StringSid;
}

```

## disassembly

```asm
0x1800437d8  mov     rax, rsp
0x1800437db  mov     [rax+10h], rbx
0x1800437df  mov     [rax+8], rcx
0x1800437e3  push    rdi
0x1800437e4  sub     rsp, 30h
0x1800437e8  mov     rbx, rcx
0x1800437eb  mov     dword ptr [rax-18h], 0
0x1800437f2  mov     dword ptr [rax-18h], 1
0x1800437f9  mov     qword ptr [rcx], 0
0x180043800  lea     rcx, [rax+20h]
0x180043804  call    ?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetUserTokenHandle(Windows::System::IUser *)
0x180043809  nop
0x18004380a  mov     rdx, [rax]
0x18004380d  lea     rcx, [rsp+38h+Block]
0x180043812  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180043817  mov     [rsp+38h+var_18], 7
0x18004381f  lea     rcx, [rsp+38h+arg_18]
0x180043824  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043829  nop
0x18004382a  mov     rdi, [rsp+38h]
0x18004382f  mov     rdx, rbx; StringSid
0x180043832  mov     rcx, [rsp+38h+Block]
0x180043837  mov     rcx, [rcx]; Sid
0x18004383a  call    cs:__imp_ConvertSidToStringSidW
0x180043840  test    eax, eax
0x180043842  jnz     short loc_180043857
0x180043844  lea     r8, aOnecoreInterna_8; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18004384b  lea     edx, [rax+6Dh]; void *
0x18004384e  mov     rcx, rdi; this
0x180043851  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180043857  mov     rcx, [rsp+38h+Block]; Block
0x18004385c  mov     [rsp+38h+Block], 0
0x180043865  test    rcx, rcx
0x180043868  jz      short loc_18004386F
0x18004386a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004386f  mov     rax, rbx
0x180043872  mov     rbx, [rsp+38h+arg_8]
0x180043877  add     rsp, 30h
0x18004387b  pop     rdi
0x18004387c  retn
```
