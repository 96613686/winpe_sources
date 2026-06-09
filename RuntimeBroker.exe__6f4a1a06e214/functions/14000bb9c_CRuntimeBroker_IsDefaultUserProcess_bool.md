# CRuntimeBroker::IsDefaultUserProcess(bool *)

- ea: `0x14000bb9c`
- end: `0x14000bcdd`
- name: `?IsDefaultUserProcess@CRuntimeBroker@@SAJPEA_N@Z`
- size: `321`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140006580`

## callees

- `0x140004f50`
- `0x140007f38`
- `0x140008c80`
- `0x14000ab14`
- `0x14000acf0`
- `0x14000ad10`
- `0x14000ad60`
- `0x14000bb9c`
- `0x14000c5fc`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x14000bca2`
- `ntdll!RtlEqualSid` at `0x14000bca2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14000bc7a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14000bc7a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x14000bbfc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x14000bbfc`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x14000bc46`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x14000bc46`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14000bc22`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x14000bc22`

## string_xrefs

- `0x14000bc88`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::IsDefaultUserProcess(bool *a1)
{
  void *SelfSid; // rsi
  NTSTATUS DomainInfo; // eax
  unsigned int v4; // r8d
  __int64 v5; // rdx
  int LastError; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  PVOID Buffer; // [rsp+20h] [rbp-79h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-71h] BYREF
  PVOID PolicyHandle; // [rsp+30h] [rbp-69h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-59h] BYREF
  _BYTE pSid[80]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a1 = 0;
  cbSid = 68;
  Buffer = 0;
  PolicyHandle = 0;
  SelfSid = CRuntimeBroker::GetSelfSid();
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DomainInfo = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( DomainInfo < 0 )
  {
    v5 = 1324;
LABEL_5:
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)v5,
                  v4,
                  (const char *)(unsigned int)DomainInfo,
                  (int)Buffer);
LABEL_6:
    v7 = LastError;
    goto LABEL_12;
  }
  Buffer = 0;
  DomainInfo = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &Buffer);
  if ( DomainInfo < 0 )
  {
    v5 = 1325;
    goto LABEL_5;
  }
  if ( !CreateWellKnownSid(WinLocalAccountAndAdministratorSid|WinCreatorGroupSid, *((PSID *)Buffer + 2), pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x52E,
                  (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
                  v8);
    goto LABEL_6;
  }
  if ( RtlEqualSid(SelfSid, pSid) )
    *a1 = 1;
  v7 = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v7;
}

```

## disassembly

```asm
0x14000bb9c  push    rbp
0x14000bb9e  push    rbx
0x14000bb9f  push    rsi
0x14000bba0  push    rdi
0x14000bba1  lea     rbp, [rsp-3Fh]
0x14000bba6  sub     rsp, 0D8h
0x14000bbad  mov     rax, cs:__security_cookie
0x14000bbb4  xor     rax, rsp
0x14000bbb7  mov     [rbp+57h+var_30], rax
0x14000bbbb  mov     rdi, rcx
0x14000bbbe  mov     byte ptr [rcx], 0
0x14000bbc1  call    ?GetSelfSid@CRuntimeBroker@@SAPEAXXZ; CRuntimeBroker::GetSelfSid(void)
0x14000bbc6  xorps   xmm0, xmm0
0x14000bbc9  mov     [rbp+57h+cbSid], 44h ; 'D'
0x14000bbd0  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x14000bbd4  mov     [rbp+57h+Buffer], 0
0x14000bbdc  mov     edx, 1; AccessMask
0x14000bbe1  mov     [rbp+57h+PolicyHandle], 0
0x14000bbe9  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000bbed  mov     rsi, rax
0x14000bbf0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000bbf4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000bbf8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bbfc  call    cs:__imp_LsaLookupOpenLocalPolicy
0x14000bc02  test    eax, eax
0x14000bc04  jns     short loc_14000BC0D
0x14000bc06  mov     edx, 52Ch
0x14000bc0b  jmp     short loc_14000BC55
0x14000bc0d  mov     rbx, [rbp+57h+Buffer]
0x14000bc11  test    rbx, rbx
0x14000bc14  jz      short loc_14000BC31
0x14000bc16  lea     rcx, [rbp+57h+var_B8]; this
0x14000bc1a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000bc1f  mov     rcx, rbx; Buffer
0x14000bc22  call    cs:__imp_LsaLookupFreeMemory
0x14000bc28  lea     rcx, [rbp+57h+var_B8]; this
0x14000bc2c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000bc31  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x14000bc35  lea     r8, [rbp+57h+Buffer]; DomainInfo
0x14000bc39  mov     edx, 5; DomainInfoClass
0x14000bc3e  mov     [rbp+57h+Buffer], 0
0x14000bc46  call    cs:__imp_LsaLookupGetDomainInfo
0x14000bc4c  test    eax, eax
0x14000bc4e  jns     short loc_14000BC65
0x14000bc50  mov     edx, 52Dh; void *
0x14000bc55  mov     rcx, [rbp+5Fh]; this
0x14000bc59  mov     r9d, eax; char *
0x14000bc5c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x14000bc61  mov     ebx, eax
0x14000bc63  jmp     short loc_14000BCB1
0x14000bc65  mov     rdx, [rbp+57h+Buffer]
0x14000bc69  lea     r9, [rbp+57h+cbSid]; cbSid
0x14000bc6d  lea     r8, [rbp+57h+pSid]; pSid
0x14000bc71  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x14000bc76  mov     rdx, [rdx+10h]; DomainSid
0x14000bc7a  call    cs:__imp_CreateWellKnownSid
0x14000bc80  test    eax, eax
0x14000bc82  jnz     short loc_14000BC9B
0x14000bc84  mov     rcx, [rbp+5Fh]; this
0x14000bc88  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x14000bc8f  mov     edx, 52Eh; void *
0x14000bc94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bc99  jmp     short loc_14000BC61
0x14000bc9b  lea     rdx, [rbp+57h+pSid]; Sid2
0x14000bc9f  mov     rcx, rsi; Sid1
0x14000bca2  call    cs:__imp_RtlEqualSid
0x14000bca8  test    al, al
0x14000bcaa  jz      short loc_14000BCAF
0x14000bcac  mov     byte ptr [rdi], 1
0x14000bcaf  xor     ebx, ebx
0x14000bcb1  lea     rcx, [rbp+57h+Buffer]
0x14000bcb5  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x14000bcba  lea     rcx, [rbp+57h+PolicyHandle]
0x14000bcbe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000bcc3  mov     eax, ebx
0x14000bcc5  mov     rcx, [rbp+57h+var_30]
0x14000bcc9  xor     rcx, rsp; StackCookie
0x14000bccc  call    __security_check_cookie
0x14000bcd1  add     rsp, 0D8h
0x14000bcd8  pop     rdi
0x14000bcd9  pop     rsi
0x14000bcda  pop     rbx
0x14000bcdb  pop     rbp
0x14000bcdc  retn
```
