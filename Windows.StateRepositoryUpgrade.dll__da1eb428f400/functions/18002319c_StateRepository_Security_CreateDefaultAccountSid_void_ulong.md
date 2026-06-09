# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x18002319c`
- end: `0x1800232c0`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `292`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023ba8`

## callees

- `0x18000a3a0`
- `0x180013728`
- `0x1800230b0`
- `0x18002319c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180023270`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180023270`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800231dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800231dd`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180023250`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800232a2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180023250`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800232a2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002321b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18002321b`

## string_xrefs

- `0x1800231eb`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x180023229`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`
- `0x18002327e`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Security::CreateDefaultAccountSid(StateRepository::Security *this, void *a2)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  int LastError; // eax
  PVOID v6; // rcx
  const char *v7; // r9
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
  if ( v2 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x7E,
           (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
           (const char *)(unsigned int)v2,
           ObjectAttributes.Length);
    goto LABEL_12;
  }
  DomainInfo = 0;
  v4 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( v4 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x81,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  (const char *)(unsigned int)v4,
                  ObjectAttributes.Length);
    goto LABEL_5;
  }
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          qword_18004BF60,
          &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x83,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  v7);
LABEL_5:
    v6 = DomainInfo;
    v3 = LastError;
    DomainInfo = 0;
    if ( v6 )
      LsaLookupFreeMemory(v6);
    goto LABEL_12;
  }
  v8 = DomainInfo;
  DomainInfo = 0;
  if ( v8 )
    LsaLookupFreeMemory(v8);
  v3 = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v3;
}

```

## disassembly

```asm
0x18002319c  mov     [rsp-8+arg_18], rbx
0x1800231a1  mov     [rsp-8+cbSid], edx
0x1800231a5  mov     [rsp-8+DomainInfo], rcx
0x1800231aa  push    rbp
0x1800231ab  mov     rbp, rsp
0x1800231ae  sub     rsp, 50h
0x1800231b2  xorps   xmm0, xmm0
0x1800231b5  mov     [rbp+cbSid], 44h ; 'D'
0x1800231bc  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x1800231c0  mov     [rbp+PolicyHandle], 0
0x1800231c8  mov     edx, 1; AccessMask
0x1800231cd  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800231d1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800231d5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800231d9  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800231dd  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800231e3  test    eax, eax
0x1800231e5  jns     short loc_180023206
0x1800231e7  mov     rcx, [rbp+8]; this
0x1800231eb  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\StateRepositor"...
0x1800231f2  mov     r9d, eax; char *
0x1800231f5  mov     edx, 7Eh ; '~'; void *
0x1800231fa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800231ff  mov     ebx, eax
0x180023201  jmp     loc_1800232AA
0x180023206  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002320a  lea     r8, [rbp+DomainInfo]; DomainInfo
0x18002320e  mov     edx, 5; DomainInfoClass
0x180023213  mov     [rbp+DomainInfo], 0
0x18002321b  call    cs:__imp_LsaLookupGetDomainInfo
0x180023221  test    eax, eax
0x180023223  jns     short loc_180023258
0x180023225  mov     rcx, [rbp+8]; this
0x180023229  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\StateRepositor"...
0x180023230  mov     r9d, eax; char *
0x180023233  mov     edx, 81h; void *
0x180023238  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002323d  mov     rcx, [rbp+DomainInfo]; Buffer
0x180023241  mov     ebx, eax
0x180023243  mov     [rbp+DomainInfo], 0
0x18002324b  test    rcx, rcx
0x18002324e  jz      short loc_1800232AA
0x180023250  call    cs:__imp_LsaLookupFreeMemory
0x180023256  jmp     short loc_1800232AA
0x180023258  mov     rdx, [rbp+DomainInfo]
0x18002325c  lea     r9, [rbp+cbSid]; cbSid
0x180023260  lea     r8, qword_18004BF60; pSid
0x180023267  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18002326c  mov     rdx, [rdx+10h]; DomainSid
0x180023270  call    cs:__imp_CreateWellKnownSid
0x180023276  test    eax, eax
0x180023278  jnz     short loc_180023291
0x18002327a  mov     rcx, [rbp+8]; this
0x18002327e  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\StateRepositor"...
0x180023285  mov     edx, 83h; void *
0x18002328a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002328f  jmp     short loc_18002323D
0x180023291  mov     rcx, [rbp+DomainInfo]; Buffer
0x180023295  mov     [rbp+DomainInfo], 0
0x18002329d  test    rcx, rcx
0x1800232a0  jz      short loc_1800232A8
0x1800232a2  call    cs:__imp_LsaLookupFreeMemory
0x1800232a8  xor     ebx, ebx
0x1800232aa  lea     rcx, [rbp+PolicyHandle]
0x1800232ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800232b3  mov     eax, ebx
0x1800232b5  mov     rbx, [rsp+50h+arg_18]
0x1800232ba  add     rsp, 50h
0x1800232be  pop     rbp
0x1800232bf  retn
```
