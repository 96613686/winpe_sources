# Windows::Internal::CapabilityAccess::Private::GetDsmaSid(void)

- ea: `0x18004157c`
- end: `0x18004169a`
- name: `?GetDsmaSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800416a0`

## callees

- `0x180039e9c`
- `0x18003ae98`
- `0x18003f504`
- `0x18003f544`
- `0x18004157c`
- `0x18004624c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004159b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004159b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004165c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18004165c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18004161e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18004161e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800415e6`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800415e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PSID *__fastcall Windows::Internal::CapabilityAccess::Private::GetDsmaSid(PSID *a1)
{
  HLOCAL v2; // rax
  const char *v3; // r9
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  const char *v6; // r9
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+10h]
  DWORD cbSid; // [rsp+88h] [rbp+20h] BYREF
  PVOID DomainInfo; // [rsp+90h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+30h] BYREF

  v2 = LocalAlloc(0, 0x44u);
  *a1 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v3);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v4 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v4,
      1);
  DomainInfo = 0;
  v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v5,
      1);
  cbSid = 68;
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          *a1,
          &cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v6);
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return a1;
}

```

## disassembly

```asm
0x18004157c  mov     [rsp-10h+arg_0], rcx
0x180041581  push    rbp
0x180041582  push    rbx
0x180041583  mov     rbp, rsp
0x180041586  sub     rsp, 68h
0x18004158a  mov     rbx, rcx
0x18004158d  mov     [rbp+var_48], 0
0x180041594  mov     edx, 44h ; 'D'; uBytes
0x180041599  xor     ecx, ecx; uFlags
0x18004159b  call    cs:__imp_LocalAlloc
0x1800415a1  mov     [rbx], rax
0x1800415a4  mov     edx, 1; AccessMask
0x1800415a9  mov     [rbp+var_48], edx
0x1800415ac  mov     rcx, [rbp+10h]; this
0x1800415b0  test    rax, rax
0x1800415b3  jnz     short loc_1800415C7
0x1800415b5  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800415bc  mov     edx, 0C3h; void *
0x1800415c1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800415c7  xorps   xmm0, xmm0
0x1800415ca  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800415ce  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800415d2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800415d6  mov     [rbp+PolicyHandle], 0
0x1800415de  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x1800415e2  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800415e6  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800415ec  mov     rcx, [rbp+10h]; this
0x1800415f0  test    eax, eax
0x1800415f2  jns     short loc_180041609
0x1800415f4  mov     r9d, eax; char *
0x1800415f7  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800415fe  mov     edx, 0C8h; void *
0x180041603  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180041609  mov     [rbp+DomainInfo], 0
0x180041611  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180041615  mov     edx, 5; DomainInfoClass
0x18004161a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18004161e  call    cs:__imp_LsaLookupGetDomainInfo
0x180041624  mov     rcx, [rbp+10h]; this
0x180041628  test    eax, eax
0x18004162a  jns     short loc_180041641
0x18004162c  mov     r9d, eax; char *
0x18004162f  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041636  mov     edx, 0CCh; void *
0x18004163b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180041641  mov     [rbp+cbSid], 44h ; 'D'
0x180041648  lea     r9, [rbp+cbSid]; cbSid
0x18004164c  mov     r8, [rbx]; pSid
0x18004164f  mov     rdx, [rbp+DomainInfo]
0x180041653  mov     rdx, [rdx+10h]; DomainSid
0x180041657  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18004165c  call    cs:__imp_CreateWellKnownSid
0x180041662  mov     rcx, [rbp+10h]; this
0x180041666  test    eax, eax
0x180041668  jnz     short loc_18004167C
0x18004166a  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041671  mov     edx, 0D3h; void *
0x180041676  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004167c  lea     rcx, [rbp+DomainInfo]
0x180041680  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x180041685  nop
0x180041686  lea     rcx, [rbp+PolicyHandle]
0x18004168a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004168f  mov     rax, rbx
0x180041692  add     rsp, 68h
0x180041696  pop     rbx
0x180041697  pop     rbp
0x180041698  retn
```
