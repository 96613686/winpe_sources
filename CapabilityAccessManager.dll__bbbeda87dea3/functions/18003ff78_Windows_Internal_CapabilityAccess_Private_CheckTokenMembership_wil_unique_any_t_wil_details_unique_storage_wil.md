# Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,WELL_KNOWN_SID_TYPE)

- ea: `0x18003ff78`
- end: `0x1800400ed`
- name: `?CheckTokenMembership@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `373`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044614`
- `0x180044ad4`
- `0x18006ae88`
- `0x180090970`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x180039e9c`
- `0x18003f4a0`
- `0x18003ff78`
- `0x1800464d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004003e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004003e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ffc5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003ffc5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180040011`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180040011`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180040072`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800400cf`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180040072`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800400cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Internal::CapabilityAccess::Private::CheckTokenMembership(HANDLE *a1, WELL_KNOWN_SID_TYPE a2)
{
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  const char *v8; // r9
  int v9; // [rsp+30h] [rbp-39h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-31h] BYREF
  DWORD cbSid; // [rsp+40h] [rbp-29h] BYREF
  DWORD ReturnLength; // [rsp+44h] [rbp-25h] BYREF
  int TokenInformation; // [rsp+48h] [rbp-21h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(a2, 0, pSid, &cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  v9 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(*a1, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( !(unsigned int)CheckTokenMembershipEx(*a1, pSid, 1, &v9) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v8);
  }
  else
  {
    DuplicateTokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &DuplicateTokenHandle,
      0);
    if ( !DuplicateToken(*a1, SecurityIdentification, &DuplicateTokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v5);
    if ( !(unsigned int)CheckTokenMembershipEx(DuplicateTokenHandle, pSid, 1, &v9) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v6);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
  }
  return v9 != 0;
}

```

## disassembly

```asm
0x18003ff78  mov     [rsp-8+arg_10], rbx
0x18003ff7d  push    rbp
0x18003ff7e  push    rsi
0x18003ff7f  push    rdi
0x18003ff80  lea     rbp, [rsp-47h]
0x18003ff85  sub     rsp, 0B0h
0x18003ff8c  mov     rax, cs:__security_cookie
0x18003ff93  xor     rax, rsp
0x18003ff96  mov     [rbp+57h+var_20], rax
0x18003ff9a  mov     ebx, edx
0x18003ff9c  mov     rdi, rcx
0x18003ff9f  mov     esi, 44h ; 'D'
0x18003ffa4  mov     r8d, esi; Size
0x18003ffa7  xor     edx, edx; Val
0x18003ffa9  lea     rcx, [rbp+57h+pSid]; void *
0x18003ffad  call    memset_0
0x18003ffb2  mov     [rbp+57h+cbSid], esi
0x18003ffb5  mov     rsi, [rbp+5Fh]
0x18003ffb9  lea     r9, [rbp+57h+cbSid]; cbSid
0x18003ffbd  lea     r8, [rbp+57h+pSid]; pSid
0x18003ffc1  xor     edx, edx; DomainSid
0x18003ffc3  mov     ecx, ebx; WellKnownSidType
0x18003ffc5  call    cs:__imp_CreateWellKnownSid
0x18003ffcb  test    eax, eax
0x18003ffcd  jnz     short loc_18003FFE2
0x18003ffcf  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003ffd6  lea     edx, [rax+54h]; void *
0x18003ffd9  mov     rcx, rsi; this
0x18003ffdc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003ffe2  mov     [rbp+57h+var_90], 0
0x18003ffe9  mov     [rbp+57h+TokenInformation], 0
0x18003fff0  mov     [rbp+57h+var_7C], 0
0x18003fff7  lea     rax, [rbp+57h+var_7C]
0x18003fffb  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180040000  mov     r9d, 4; TokenInformationLength
0x180040006  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18004000a  lea     edx, [r9+5]; TokenInformationClass
0x18004000e  mov     rcx, [rdi]; TokenHandle
0x180040011  call    cs:__imp_GetTokenInformation
0x180040017  test    eax, eax
0x180040019  jnz     loc_1800400BE
0x18004001f  mov     [rbp+57h+DuplicateTokenHandle], 0
0x180040027  xor     edx, edx
0x180040029  lea     rcx, [rbp+57h+DuplicateTokenHandle]
0x18004002d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180040032  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x180040036  mov     edx, 1; ImpersonationLevel
0x18004003b  mov     rcx, [rdi]; ExistingTokenHandle
0x18004003e  call    cs:__imp_DuplicateToken
0x180040044  mov     rcx, [rbp+5Fh]; this
0x180040048  test    eax, eax
0x18004004a  jnz     short loc_18004005C
0x18004004c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040053  lea     edx, [rax+66h]; void *
0x180040056  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004005c  mov     rbx, [rbp+5Fh]
0x180040060  lea     r9, [rbp+57h+var_90]
0x180040064  mov     r8d, 1
0x18004006a  lea     rdx, [rbp+57h+pSid]
0x18004006e  mov     rcx, [rbp+57h+DuplicateTokenHandle]
0x180040072  call    cs:__imp_CheckTokenMembershipEx
0x180040078  test    eax, eax
0x18004007a  jnz     short loc_18004008F
0x18004007c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040083  lea     edx, [rax+67h]; void *
0x180040086  mov     rcx, rbx; this
0x180040089  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004008f  lea     rcx, [rbp+57h+DuplicateTokenHandle]
0x180040093  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040098  cmp     [rbp+57h+var_90], 0
0x18004009c  setnz   al
0x18004009f  mov     rcx, [rbp+57h+var_20]
0x1800400a3  xor     rcx, rsp; StackCookie
0x1800400a6  call    __security_check_cookie
0x1800400ab  mov     rbx, [rsp+0C0h+arg_10]
0x1800400b3  add     rsp, 0B0h
0x1800400ba  pop     rdi
0x1800400bb  pop     rsi
0x1800400bc  pop     rbp
0x1800400bd  retn
0x1800400be  lea     r9, [rbp+57h+var_90]
0x1800400c2  mov     r8d, 1
0x1800400c8  lea     rdx, [rbp+57h+pSid]
0x1800400cc  mov     rcx, [rdi]
0x1800400cf  call    cs:__imp_CheckTokenMembershipEx
0x1800400d5  test    eax, eax
0x1800400d7  jnz     short loc_180040098
0x1800400d9  mov     rcx, [rbp+5Fh]; this
0x1800400dd  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800400e4  lea     edx, [rax+6Bh]; void *
0x1800400e7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
