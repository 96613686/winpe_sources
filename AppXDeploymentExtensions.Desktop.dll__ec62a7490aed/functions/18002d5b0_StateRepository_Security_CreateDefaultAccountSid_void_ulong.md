# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x18002d5b0`
- end: `0x18002d70c`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `348`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002d30c`

## callees

- `0x18000669c`
- `0x18002d5b0`
- `0x180058a04`
- `0x180068f18`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d690`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d690`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002d628`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x18002d628`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002d6c8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002d6e7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002d6c8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18002d6e7`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002d5f1`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18002d5f1`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002d64e`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002d64e`

## string_xrefs

- `0x18002d605`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x18002d662`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x18002d6a4`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Security::CreateDefaultAccountSid(StateRepository::Security *this, void *a2)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  unsigned int LastError; // eax
  const char *v6; // r9
  PVOID v7; // rcx
  PVOID v8; // rcx
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  PVOID DomainInfo; // [rsp+60h] [rbp+10h] BYREF
  DWORD cbSid; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  DomainInfo = this;
  cbSid = 68;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v2 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 >= 0 )
  {
    DomainInfo = 0;
    v4 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
    if ( v4 >= 0 )
    {
      if ( CreateWellKnownSid(
             WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
             *((PSID *)DomainInfo + 2),
             &unk_180245AF0,
             &cbSid) )
      {
        v8 = DomainInfo;
        DomainInfo = 0;
        if ( v8 )
          LsaLookupFreeMemory(v8);
        v3 = 0;
        goto LABEL_13;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x83,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                    v6);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x81,
                    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                    (const char *)(unsigned int)v4,
                    ObjectAttributes.Length);
    }
    v7 = DomainInfo;
    v3 = LastError;
    DomainInfo = 0;
    if ( v7 )
      LsaLookupFreeMemory(v7);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    return v3;
  }
  v3 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x7E,
         (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
         (const char *)(unsigned int)v2,
         ObjectAttributes.Length);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x18002d5b0  mov     [rsp-8+arg_18], rbx
0x18002d5b5  mov     [rsp-8+cbSid], edx
0x18002d5b9  mov     [rsp-8+DomainInfo], rcx
0x18002d5be  push    rbp
0x18002d5bf  mov     rbp, rsp
0x18002d5c2  sub     rsp, 50h
0x18002d5c6  xorps   xmm0, xmm0
0x18002d5c9  mov     [rbp+cbSid], 44h ; 'D'
0x18002d5d0  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x18002d5d4  mov     [rbp+PolicyHandle], 0
0x18002d5dc  mov     edx, 1; AccessMask
0x18002d5e1  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002d5e5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002d5e9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002d5ed  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d5f1  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18002d5f8  nop     dword ptr [rax+rax+00h]
0x18002d5fd  test    eax, eax
0x18002d5ff  jns     short loc_18002D639
0x18002d601  mov     rcx, [rbp+8]; this
0x18002d605  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18002d60c  mov     r9d, eax; char *
0x18002d60f  mov     edx, 7Eh ; '~'; void *
0x18002d614  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002d619  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002d61d  mov     ebx, eax
0x18002d61f  test    rcx, rcx
0x18002d622  jz      loc_18002D6FE
0x18002d628  call    cs:__imp_LsaLookupClose
0x18002d62f  nop     dword ptr [rax+rax+00h]
0x18002d634  jmp     loc_18002D6FE
0x18002d639  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002d63d  lea     r8, [rbp+DomainInfo]; DomainInfo
0x18002d641  mov     edx, 5; DomainInfoClass
0x18002d646  mov     [rbp+DomainInfo], 0
0x18002d64e  call    cs:__imp_LsaLookupGetDomainInfo
0x18002d655  nop     dword ptr [rax+rax+00h]
0x18002d65a  test    eax, eax
0x18002d65c  jns     short loc_18002D678
0x18002d65e  mov     rcx, [rbp+8]; this
0x18002d662  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18002d669  mov     r9d, eax; char *
0x18002d66c  mov     edx, 81h; void *
0x18002d671  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002d676  jmp     short loc_18002D6B5
0x18002d678  mov     rdx, [rbp+DomainInfo]
0x18002d67c  lea     r9, [rbp+cbSid]; cbSid
0x18002d680  lea     r8, unk_180245AF0; pSid
0x18002d687  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18002d68c  mov     rdx, [rdx+10h]; DomainSid
0x18002d690  call    cs:__imp_CreateWellKnownSid
0x18002d697  nop     dword ptr [rax+rax+00h]
0x18002d69c  test    eax, eax
0x18002d69e  jnz     short loc_18002D6D6
0x18002d6a0  mov     rcx, [rbp+8]; this
0x18002d6a4  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x18002d6ab  mov     edx, 83h; void *
0x18002d6b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d6b5  mov     rcx, [rbp+DomainInfo]; Buffer
0x18002d6b9  mov     ebx, eax
0x18002d6bb  mov     [rbp+DomainInfo], 0
0x18002d6c3  test    rcx, rcx
0x18002d6c6  jz      short loc_18002D6F5
0x18002d6c8  call    cs:__imp_LsaLookupFreeMemory
0x18002d6cf  nop     dword ptr [rax+rax+00h]
0x18002d6d4  jmp     short loc_18002D6F5
0x18002d6d6  mov     rcx, [rbp+DomainInfo]; Buffer
0x18002d6da  mov     [rbp+DomainInfo], 0
0x18002d6e2  test    rcx, rcx
0x18002d6e5  jz      short loc_18002D6F3
0x18002d6e7  call    cs:__imp_LsaLookupFreeMemory
0x18002d6ee  nop     dword ptr [rax+rax+00h]
0x18002d6f3  xor     ebx, ebx
0x18002d6f5  lea     rcx, [rbp+PolicyHandle]
0x18002d6f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d6fe  mov     eax, ebx
0x18002d700  mov     rbx, [rsp+50h+arg_18]
0x18002d705  add     rsp, 50h
0x18002d709  pop     rbp
0x18002d70a  retn
```
