# Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)

- ea: `0x18000ac14`
- end: `0x18000ac96`
- name: `?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z`
- size: `130`
- prototype: `LPWSTR *__fastcall(LPWSTR *StringSid, void *)`
- caller_count: `12`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000aebc`
- `0x18000b528`
- `0x18000ba1c`
- `0x18000bca8`
- `0x18000c5f0`
- `0x180011b94`
- `0x1800121b0`
- `0x180015b9c`
- `0x180016478`
- `0x180027514`
- `0x18003cc40`
- `0x18003d4d8`

## callees

- `0x18000ac14`
- `0x18000ac9c`
- `0x18002a43c`
- `0x180032254`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ac52`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ac52`

## string_xrefs

- `0x18000ac84`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPWSTR *__fastcall Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(LPWSTR *StringSid, void *a2)
{
  const char *v3; // r9
  void *v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  Block = a2;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block);
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      v3);
  v4 = Block;
  Block = 0;
  if ( v4 )
    operator delete(v4);
  return StringSid;
}

```

## disassembly

```asm
0x18000ac14  mov     rax, rsp
0x18000ac17  mov     [rax+10h], rdx
0x18000ac1b  mov     [rax+8], rcx
0x18000ac1f  push    rbx
0x18000ac20  sub     rsp, 30h
0x18000ac24  mov     rbx, rcx
0x18000ac27  mov     dword ptr [rax-18h], 0
0x18000ac2e  lea     rcx, [rax+10h]
0x18000ac32  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18000ac37  nop
0x18000ac38  mov     [rsp+38h+var_18], 7
0x18000ac40  mov     qword ptr [rbx], 0
0x18000ac47  mov     rdx, rbx; StringSid
0x18000ac4a  mov     rcx, [rsp+38h+Block]
0x18000ac4f  mov     rcx, [rcx]; Sid
0x18000ac52  call    cs:__imp_ConvertSidToStringSidW
0x18000ac58  mov     rcx, [rsp+38h]; this
0x18000ac5d  test    eax, eax
0x18000ac5f  jz      short loc_18000AC84
0x18000ac61  mov     rcx, [rsp+38h+Block]; Block
0x18000ac66  mov     [rsp+38h+Block], 0
0x18000ac6f  test    rcx, rcx
0x18000ac72  jnz     short loc_18000AC7D
0x18000ac74  mov     rax, rbx
0x18000ac77  add     rsp, 30h
0x18000ac7b  pop     rbx
0x18000ac7c  retn
0x18000ac7d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ac82  jmp     short loc_18000AC74
0x18000ac84  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18000ac8b  mov     edx, 75h ; 'u'; void *
0x18000ac90  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
