# StateRepository::Security::CreateDefaultAccountSid(void *,ulong)

- ea: `0x18000db3c`
- end: `0x18000dc52`
- name: `?CreateDefaultAccountSid@Security@StateRepository@@YAJPEAXK@Z`
- size: `278`
- prototype: `__int64 __fastcall(StateRepository::Security *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000de90`

## callees

- `0x1800093ec`
- `0x18000db1c`
- `0x18000db3c`
- `0x18000dc58`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000dc02`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000dc02`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000dbb4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18000dbb4`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000dbe2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000dc34`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000dbe2`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x18000dc34`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000db7d`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18000db7d`

## string_xrefs

- `0x18000dc10`: `onecore\base\appmodel\StateRepository\Common\Inc\Security.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Security::CreateDefaultAccountSid(StateRepository::Security *this, void *a2)
{
  NTSTATUS v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  unsigned int v6; // r8d
  int LastError; // eax
  PVOID v8; // rcx
  const char *v9; // r9
  PVOID v10; // rcx
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
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x7E,
           v3,
           (const char *)(unsigned int)v2,
           ObjectAttributes.Length);
    goto LABEL_12;
  }
  DomainInfo = 0;
  v5 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  if ( v5 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x81,
                  v6,
                  (const char *)(unsigned int)v5,
                  ObjectAttributes.Length);
    goto LABEL_5;
  }
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          qword_1800186B0,
          &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x83,
                  (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Common\\Inc\\Security.hpp",
                  v9);
LABEL_5:
    v8 = DomainInfo;
    v4 = LastError;
    DomainInfo = 0;
    if ( v8 )
      LsaLookupFreeMemory(v8);
    goto LABEL_12;
  }
  v10 = DomainInfo;
  DomainInfo = 0;
  if ( v10 )
    LsaLookupFreeMemory(v10);
  v4 = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v4;
}

```

## disassembly

```asm
0x18000db3c  mov     [rsp-8+arg_18], rbx
0x18000db41  mov     [rsp-8+cbSid], edx
0x18000db45  mov     [rsp-8+DomainInfo], rcx
0x18000db4a  push    rbp
0x18000db4b  mov     rbp, rsp
0x18000db4e  sub     rsp, 50h
0x18000db52  xorps   xmm0, xmm0
0x18000db55  mov     [rbp+cbSid], 44h ; 'D'
0x18000db5c  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x18000db60  mov     [rbp+PolicyHandle], 0
0x18000db68  mov     edx, 1; AccessMask
0x18000db6d  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000db71  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000db75  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000db79  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000db7d  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18000db83  test    eax, eax
0x18000db85  jns     short loc_18000DB9F
0x18000db87  mov     rcx, [rbp+8]; this
0x18000db8b  mov     r9d, eax; char *
0x18000db8e  mov     edx, 7Eh ; '~'; void *
0x18000db93  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000db98  mov     ebx, eax
0x18000db9a  jmp     loc_18000DC3C
0x18000db9f  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000dba3  lea     r8, [rbp+DomainInfo]; DomainInfo
0x18000dba7  mov     edx, 5; DomainInfoClass
0x18000dbac  mov     [rbp+DomainInfo], 0
0x18000dbb4  call    cs:__imp_LsaLookupGetDomainInfo
0x18000dbba  test    eax, eax
0x18000dbbc  jns     short loc_18000DBEA
0x18000dbbe  mov     rcx, [rbp+8]; this
0x18000dbc2  mov     r9d, eax; char *
0x18000dbc5  mov     edx, 81h; void *
0x18000dbca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000dbcf  mov     rcx, [rbp+DomainInfo]; Buffer
0x18000dbd3  mov     ebx, eax
0x18000dbd5  mov     [rbp+DomainInfo], 0
0x18000dbdd  test    rcx, rcx
0x18000dbe0  jz      short loc_18000DC3C
0x18000dbe2  call    cs:__imp_LsaLookupFreeMemory
0x18000dbe8  jmp     short loc_18000DC3C
0x18000dbea  mov     rdx, [rbp+DomainInfo]
0x18000dbee  lea     r9, [rbp+cbSid]; cbSid
0x18000dbf2  lea     r8, qword_1800186B0; pSid
0x18000dbf9  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x18000dbfe  mov     rdx, [rdx+10h]; DomainSid
0x18000dc02  call    cs:__imp_CreateWellKnownSid
0x18000dc08  test    eax, eax
0x18000dc0a  jnz     short loc_18000DC23
0x18000dc0c  mov     rcx, [rbp+8]; this
0x18000dc10  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\StateRepositor"...
0x18000dc17  mov     edx, 83h; void *
0x18000dc1c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000dc21  jmp     short loc_18000DBCF
0x18000dc23  mov     rcx, [rbp+DomainInfo]; Buffer
0x18000dc27  mov     [rbp+DomainInfo], 0
0x18000dc2f  test    rcx, rcx
0x18000dc32  jz      short loc_18000DC3A
0x18000dc34  call    cs:__imp_LsaLookupFreeMemory
0x18000dc3a  xor     ebx, ebx
0x18000dc3c  lea     rcx, [rbp+PolicyHandle]
0x18000dc40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000dc45  mov     eax, ebx
0x18000dc47  mov     rbx, [rsp+50h+arg_18]
0x18000dc4c  add     rsp, 50h
0x18000dc50  pop     rbp
0x18000dc51  retn
```
