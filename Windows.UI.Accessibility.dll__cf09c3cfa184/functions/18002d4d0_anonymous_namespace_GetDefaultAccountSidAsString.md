# _anonymous_namespace_::GetDefaultAccountSidAsString

- ea: `0x18002d4d0`
- end: `0x18002d61f`
- name: `_anonymous_namespace_::GetDefaultAccountSidAsString`
- size: `335`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d6d8`

## callees

- `0x180003980`
- `0x180004344`
- `0x18000ea34`
- `0x18002cf10`
- `0x18002cf30`
- `0x18002d4d0`
- `0x18002dcf4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d59a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d59a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002d553`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002d553`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002d522`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002d522`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d5cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002d5cd`

## string_xrefs

- `0x18002d5a8`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`
- `0x18002d5db`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPWSTR *__fastcall anonymous_namespace_::GetDefaultAccountSidAsString(LPWSTR *StringSid)
{
  NTSTATUS v2; // eax
  unsigned int v3; // r8d
  NTSTATUS v4; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  const char *v7; // r9
  DWORD cbSid; // [rsp+20h] [rbp-59h] BYREF
  int v10; // [rsp+24h] [rbp-55h]
  PVOID DomainInfo; // [rsp+28h] [rbp-51h] BYREF
  PVOID PolicyHandle[2]; // [rsp+30h] [rbp-49h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  _BYTE pSid[80]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  PolicyHandle[1] = StringSid;
  v10 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle[0] = 0;
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, PolicyHandle);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x1F, v3, (const char *)(unsigned int)v2, cbSid);
  DomainInfo = 0;
  v4 = LsaLookupGetDomainInfo(PolicyHandle[0], AccountDomainInformation, &DomainInfo);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x22, v5, (const char *)(unsigned int)v4, cbSid);
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          pSid,
          &cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      v6);
  v10 = 1;
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(pSid, StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      v7);
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(PolicyHandle);
  return StringSid;
}

```

## disassembly

```asm
0x18002d4d0  mov     [rsp-8+arg_8], rbx
0x18002d4d5  push    rbp
0x18002d4d6  lea     rbp, [rsp-57h]
0x18002d4db  sub     rsp, 0D0h
0x18002d4e2  mov     rax, cs:__security_cookie
0x18002d4e9  xor     rax, rsp
0x18002d4ec  mov     [rbp+57h+var_10], rax
0x18002d4f0  mov     rbx, rcx
0x18002d4f3  mov     [rbp+57h+var_98], rcx
0x18002d4f7  mov     [rbp+57h+var_AC], 0
0x18002d4fe  xorps   xmm0, xmm0
0x18002d501  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002d505  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002d509  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d50d  mov     [rbp+57h+PolicyHandle], 0
0x18002d515  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002d519  mov     edx, 1; AccessMask
0x18002d51e  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002d522  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18002d528  mov     rcx, [rbp+5Fh]; this
0x18002d52c  test    eax, eax
0x18002d52e  jns     short loc_18002D53E
0x18002d530  mov     r9d, eax; char *
0x18002d533  mov     edx, 1Fh; void *
0x18002d538  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002d53e  mov     [rbp+57h+DomainInfo], 0
0x18002d546  lea     r8, [rbp+57h+DomainInfo]; DomainInfo
0x18002d54a  mov     edx, 5; DomainInfoClass
0x18002d54f  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002d553  call    cs:__imp_LsaLookupGetDomainInfo
0x18002d559  mov     rcx, [rbp+5Fh]; this
0x18002d55d  test    eax, eax
0x18002d55f  jns     short loc_18002D56F
0x18002d561  mov     r9d, eax; char *
0x18002d564  mov     edx, 22h ; '"'; void *
0x18002d569  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002d56f  xor     edx, edx; Val
0x18002d571  lea     r8d, [rdx+44h]; Size
0x18002d575  lea     rcx, [rbp+57h+pSid]; void *
0x18002d579  call    memset_0
0x18002d57e  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18002d585  lea     r9, [rbp+57h+cbSid]; cbSid
0x18002d589  lea     r8, [rbp+57h+pSid]; pSid
0x18002d58d  mov     rdx, [rbp+57h+DomainInfo]
0x18002d591  mov     rdx, [rdx+10h]; DomainSid
0x18002d595  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18002d59a  call    cs:__imp_CreateWellKnownSid
0x18002d5a0  mov     rcx, [rbp+5Fh]; this
0x18002d5a4  test    eax, eax
0x18002d5a6  jnz     short loc_18002D5B8
0x18002d5a8  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d5af  lea     edx, [rax+2Ah]; void *
0x18002d5b2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d5b8  mov     [rbp+57h+var_AC], 1
0x18002d5bf  mov     qword ptr [rbx], 0
0x18002d5c6  mov     rdx, rbx; StringSid
0x18002d5c9  lea     rcx, [rbp+57h+pSid]; Sid
0x18002d5cd  call    cs:__imp_ConvertSidToStringSidW
0x18002d5d3  mov     rcx, [rbp+5Fh]; this
0x18002d5d7  test    eax, eax
0x18002d5d9  jnz     short loc_18002D5EB
0x18002d5db  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d5e2  lea     edx, [rax+2Dh]; void *
0x18002d5e5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d5eb  lea     rcx, [rbp+57h+DomainInfo]
0x18002d5ef  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x18002d5f4  nop
0x18002d5f5  lea     rcx, [rbp+57h+PolicyHandle]
0x18002d5f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d5fe  mov     rax, rbx
0x18002d601  mov     rcx, [rbp+57h+var_10]
0x18002d605  xor     rcx, rsp; StackCookie
0x18002d608  call    __security_check_cookie
0x18002d60d  mov     rbx, [rsp+0D0h+arg_8]
0x18002d615  add     rsp, 0D0h
0x18002d61c  pop     rbp
0x18002d61d  retn
```
