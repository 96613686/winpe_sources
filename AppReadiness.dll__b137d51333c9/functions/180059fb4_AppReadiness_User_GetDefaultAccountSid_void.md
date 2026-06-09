# AppReadiness::User::GetDefaultAccountSid(void)

- ea: `0x180059fb4`
- end: `0x18005a0dd`
- name: `?GetDefaultAccountSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010afc`
- `0x180026c10`
- `0x180032450`

## callees

- `0x180021bd4`
- `0x1800269b4`
- `0x180027a4c`
- `0x18003ecb4`
- `0x18004bde0`
- `0x18004be00`
- `0x180059fb4`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180059fed`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180059fed`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18005a051`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18005a051`

## string_xrefs

- `0x18005a006`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a06a`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a019`: `LsaLookupOpenLocalPolicy(&lsaAttributes, LOOKUP_VIEW_LOCAL_INFORMATION, &lsa)`
- `0x18005a012`: `AppReadiness::User::GetDefaultAccountSid`
- `0x18005a076`: `AppReadiness::User::GetDefaultAccountSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppReadiness::User::GetDefaultAccountSid(__int64 a1)
{
  NTSTATUS v2; // eax
  int v3; // eax
  NTSTATUS v4; // eax
  int v5; // eax
  _BYTE pExceptionObject[40]; // [rsp+38h] [rbp-1h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  PVOID DomainInfo; // [rsp+A8h] [rbp+6Fh] BYREF
  PVOID PolicyHandle; // [rsp+B0h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  v3 = ResultFromWin32FromStatus(v2);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "LsaLookupOpenLocalPolicy(&lsaAttributes, LOOKUP_VIEW_LOCAL_INFORMATION, &lsa)",
      "AppReadiness::User::GetDefaultAccountSid",
      "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      2539);
    throw (Windows::HResultException *)pExceptionObject;
  }
  DomainInfo = 0;
  v4 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  v5 = ResultFromWin32FromStatus(v4);
  if ( v5 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v5,
      "LsaLookupGetDomainInfo(lsa.get(), AccountDomainInformation, (PVOID *)&domainInfo)",
      "AppReadiness::User::GetDefaultAccountSid",
      "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      2542);
    throw (Windows::HResultException *)pExceptionObject;
  }
  AppReadiness::User::GetWellKnownSid(
    a1,
    WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
    *((void **)DomainInfo + 2));
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return a1;
}

```

## disassembly

```asm
0x180059fb4  mov     [rsp-8+arg_0], rbx
0x180059fb9  push    rbp
0x180059fba  lea     rbp, [rsp-57h]
0x180059fbf  sub     rsp, 90h
0x180059fc6  mov     rbx, rcx
0x180059fc9  xorps   xmm0, xmm0
0x180059fcc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180059fd0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180059fd4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059fd8  mov     [rbp+57h+PolicyHandle], 0
0x180059fe0  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x180059fe4  mov     edx, 1; AccessMask
0x180059fe9  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180059fed  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180059ff3  mov     ecx, eax; int
0x180059ff5  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180059ffa  test    eax, eax
0x180059ffc  jns     short loc_18005A03C
0x180059ffe  mov     [rsp+90h+var_68], 9EBh; int
0x18005a006  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a00d  mov     [rsp+90h+var_70], rcx; char *
0x18005a012  lea     r9, aAppreadinessUs_13; "AppReadiness::User::GetDefaultAccountSi"...
0x18005a019  lea     r8, aLsalookupopenl_0; "LsaLookupOpenLocalPolicy(&lsaAttributes"...
0x18005a020  mov     edx, eax; int
0x18005a022  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18005a026  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a02b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a032  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005a036  call    _CxxThrowException_0
0x18005a03c  mov     [rbp+57h+DomainInfo], 0
0x18005a044  lea     r8, [rbp+57h+DomainInfo]; DomainInfo
0x18005a048  mov     edx, 5; DomainInfoClass
0x18005a04d  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18005a051  call    cs:__imp_LsaLookupGetDomainInfo
0x18005a057  mov     ecx, eax; int
0x18005a059  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18005a05e  test    eax, eax
0x18005a060  jns     short loc_18005A0A0
0x18005a062  mov     [rsp+90h+var_68], 9EEh; int
0x18005a06a  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a071  mov     [rsp+90h+var_70], rcx; char *
0x18005a076  lea     r9, aAppreadinessUs_13; "AppReadiness::User::GetDefaultAccountSi"...
0x18005a07d  lea     r8, aLsalookupgetdo_0; "LsaLookupGetDomainInfo(lsa.get(), Accou"...
0x18005a084  mov     edx, eax; int
0x18005a086  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18005a08a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a08f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a096  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005a09a  call    _CxxThrowException_0
0x18005a0a0  mov     r8, [rbp+57h+DomainInfo]
0x18005a0a4  mov     r8, [r8+10h]
0x18005a0a8  mov     edx, 6Eh ; 'n'
0x18005a0ad  mov     rcx, rbx
0x18005a0b0  call    ?GetWellKnownSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; AppReadiness::User::GetWellKnownSid(WELL_KNOWN_SID_TYPE,void *)
0x18005a0b5  nop
0x18005a0b6  lea     rcx, [rbp+57h+DomainInfo]
0x18005a0ba  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x18005a0bf  nop
0x18005a0c0  lea     rcx, [rbp+57h+PolicyHandle]
0x18005a0c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a0c9  mov     rax, rbx
0x18005a0cc  mov     rbx, [rsp+90h+arg_0]
0x18005a0d4  add     rsp, 90h
0x18005a0db  pop     rbp
0x18005a0dc  retn
```
