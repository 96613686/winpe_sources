# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x1800aa1f4`
- end: `0x1800aa356`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `354`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800aabdc`

## callees

- `0x18001ab7c`
- `0x18003f544`
- `0x1800a07e4`
- `0x1800aa1f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aa2df`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aa2df`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800aa27f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800aa27f`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa2b4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa311`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa338`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa2b4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa311`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800aa338`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800aa235`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800aa235`

## string_xrefs

- `0x1800aa246`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x1800aa290`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x1800aa2ed`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::Security::CreateDefaultAccountSid(StateRepository::Security *this, void *a2)
{
  NTSTATUS v2; // eax
  unsigned int LastError; // ebx
  NTSTATUS v5; // eax
  PVOID v6; // rcx
  const char *v7; // r9
  PVOID v8; // rcx
  PVOID v9; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  PVOID DomainInfo; // [rsp+60h] [rbp+10h] BYREF
  DWORD cbSid; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  DomainInfo = this;
  cbSid = 68;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x7E,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  (const char *)(unsigned int)v2,
                  ObjectAttributes.Length);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    return LastError;
  }
  DomainInfo = 0;
  v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( v5 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  (const char *)(unsigned int)v5,
                  ObjectAttributes.Length);
    v6 = DomainInfo;
    DomainInfo = 0;
    if ( v6 )
      LsaLookupFreeMemory(v6);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    return LastError;
  }
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          qword_180168FE0,
          &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x83,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  v7);
    v8 = DomainInfo;
    DomainInfo = 0;
    if ( v8 )
      LsaLookupFreeMemory(v8);
    goto LABEL_7;
  }
  v9 = DomainInfo;
  DomainInfo = 0;
  if ( v9 )
    LsaLookupFreeMemory(v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return 0;
}

```

## disassembly

```asm
0x1800aa1f4  mov     [rsp-8+arg_18], rbx
0x1800aa1f9  mov     [rsp-8+cbSid], edx
0x1800aa1fd  mov     [rsp-8+DomainInfo], rcx
0x1800aa202  push    rbp
0x1800aa203  mov     rbp, rsp
0x1800aa206  sub     rsp, 50h
0x1800aa20a  mov     [rbp+cbSid], 44h ; 'D'
0x1800aa211  xorps   xmm0, xmm0
0x1800aa214  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800aa218  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800aa21c  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aa220  mov     [rbp+PolicyHandle], 0
0x1800aa228  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x1800aa22c  mov     edx, 1; AccessMask
0x1800aa231  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800aa235  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800aa23b  test    eax, eax
0x1800aa23d  jns     short loc_1800AA26A
0x1800aa23f  mov     rcx, [rbp+8]; this
0x1800aa243  mov     r9d, eax; char *
0x1800aa246  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x1800aa24d  mov     edx, 7Eh ; '~'; void *
0x1800aa252  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aa257  mov     ebx, eax
0x1800aa259  lea     rcx, [rbp+PolicyHandle]
0x1800aa25d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa262  nop
0x1800aa263  mov     eax, ebx
0x1800aa265  jmp     loc_1800AA34B
0x1800aa26a  mov     [rbp+DomainInfo], 0
0x1800aa272  lea     r8, [rbp+DomainInfo]; DomainInfo
0x1800aa276  mov     edx, 5; DomainInfoClass
0x1800aa27b  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800aa27f  call    cs:__imp_LsaLookupGetDomainInfo
0x1800aa285  test    eax, eax
0x1800aa287  jns     short loc_1800AA2C7
0x1800aa289  mov     rcx, [rbp+8]; this
0x1800aa28d  mov     r9d, eax; char *
0x1800aa290  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x1800aa297  mov     edx, 81h; void *
0x1800aa29c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800aa2a1  mov     ebx, eax
0x1800aa2a3  mov     rcx, [rbp+DomainInfo]; Buffer
0x1800aa2a7  mov     [rbp+DomainInfo], 0
0x1800aa2af  test    rcx, rcx
0x1800aa2b2  jz      short loc_1800AA2BB
0x1800aa2b4  call    cs:__imp_LsaLookupFreeMemory
0x1800aa2ba  nop
0x1800aa2bb  lea     rcx, [rbp+PolicyHandle]
0x1800aa2bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa2c4  nop
0x1800aa2c5  jmp     short loc_1800AA263
0x1800aa2c7  lea     r9, [rbp+cbSid]; cbSid
0x1800aa2cb  lea     r8, qword_180168FE0; pSid
0x1800aa2d2  mov     rdx, [rbp+DomainInfo]
0x1800aa2d6  mov     rdx, [rdx+10h]; DomainSid
0x1800aa2da  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800aa2df  call    cs:__imp_CreateWellKnownSid
0x1800aa2e5  test    eax, eax
0x1800aa2e7  jnz     short loc_1800AA327
0x1800aa2e9  mov     rcx, [rbp+8]; this
0x1800aa2ed  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\StateRepositor"...
0x1800aa2f4  mov     edx, 83h; void *
0x1800aa2f9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aa2fe  mov     ebx, eax
0x1800aa300  mov     rcx, [rbp+DomainInfo]; Buffer
0x1800aa304  mov     [rbp+DomainInfo], 0
0x1800aa30c  test    rcx, rcx
0x1800aa30f  jz      short loc_1800AA318
0x1800aa311  call    cs:__imp_LsaLookupFreeMemory
0x1800aa317  nop
0x1800aa318  lea     rcx, [rbp+PolicyHandle]
0x1800aa31c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa321  nop
0x1800aa322  jmp     loc_1800AA263
0x1800aa327  mov     rcx, [rbp+DomainInfo]; Buffer
0x1800aa32b  mov     [rbp+DomainInfo], 0
0x1800aa333  test    rcx, rcx
0x1800aa336  jz      short loc_1800AA33F
0x1800aa338  call    cs:__imp_LsaLookupFreeMemory
0x1800aa33e  nop
0x1800aa33f  lea     rcx, [rbp+PolicyHandle]
0x1800aa343  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa348  nop
0x1800aa349  xor     eax, eax
0x1800aa34b  mov     rbx, [rsp+50h+arg_18]
0x1800aa350  add     rsp, 50h
0x1800aa354  pop     rbp
0x1800aa355  retn
```
