# BasicUtils::GetUserSidString(void)

- ea: `0x180024710`
- end: `0x18002478b`
- name: `?GetUserSidString@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `123`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024080`
- `0x180024370`
- `0x1800244b0`

## callees

- `0x180024710`
- `0x180024a94`
- `0x18002a514`
- `0x180043af4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002474a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002474a`

## string_xrefs

- `0x180024759`: `onecore\windows\accessibletech\common\basicutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall BasicUtils::GetUserSidString(LPWSTR *StringSid)
{
  const char *v2; // r9
  void *v3; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block);
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\basicutils.cpp",
      v2);
  v3 = Block;
  Block = 0;
  if ( v3 )
    operator delete(v3);
  return StringSid;
}

```

## disassembly

```asm
0x180024710  mov     [rsp+arg_0], rcx
0x180024715  push    rbx
0x180024716  sub     rsp, 30h
0x18002471a  mov     rbx, rcx
0x18002471d  mov     [rsp+38h+var_18], 0
0x180024725  lea     rcx, [rsp+38h+Block]
0x18002472a  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18002472f  nop
0x180024730  mov     [rsp+38h+var_18], 3
0x180024738  mov     qword ptr [rbx], 0
0x18002473f  mov     rdx, rbx; StringSid
0x180024742  mov     rcx, [rsp+38h+Block]
0x180024747  mov     rcx, [rcx]; Sid
0x18002474a  call    cs:__imp_ConvertSidToStringSidW
0x180024750  mov     rcx, [rsp+38h]; this
0x180024755  test    eax, eax
0x180024757  jnz     short loc_180024769
0x180024759  lea     r8, aOnecoreWindows_3; "onecore\\windows\\accessibletech\\commo"...
0x180024760  lea     edx, [rax+76h]; void *
0x180024763  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024769  mov     rcx, [rsp+38h+Block]; Block
0x18002476e  mov     [rsp+38h+Block], 0
0x180024777  test    rcx, rcx
0x18002477a  jz      short loc_180024781
0x18002477c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024781  mov     rax, rbx
0x180024784  add     rsp, 30h
0x180024788  pop     rbx
0x180024789  retn
```
