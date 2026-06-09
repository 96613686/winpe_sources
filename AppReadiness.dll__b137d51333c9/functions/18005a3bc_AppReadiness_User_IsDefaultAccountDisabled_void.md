# AppReadiness::User::IsDefaultAccountDisabled(void)

- ea: `0x18005a3bc`
- end: `0x18005a60a`
- name: `?IsDefaultAccountDisabled@User@AppReadiness@@SA_NXZ`
- size: `590`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x1800269b4`
- `0x180027a4c`
- `0x18003e210`
- `0x18003eca8`
- `0x18003ecb4`
- `0x1800473d8`
- `0x18004bde0`
- `0x18004be00`
- `0x18005a3bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005a4ee`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18005a4ee`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18005a587`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18005a587`
- `samcli!NetUserGetInfo` at `0x18005a5ab`
- `samcli!NetUserGetInfo` at `0x18005a5ab`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18005a408`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x18005a408`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18005a471`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x18005a471`
- `netutils!NetApiBufferFree` at `0x18005a5cc`
- `netutils!NetApiBufferFree` at `0x18005a5cc`

## string_xrefs

- `0x18005a421`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a48a`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a509`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a434`: `LsaLookupOpenLocalPolicy(&lsaAttributes, LOOKUP_VIEW_LOCAL_INFORMATION, &lsa)`
- `0x18005a42d`: `AppReadiness::User::IsDefaultAccountDisabled`
- `0x18005a496`: `AppReadiness::User::IsDefaultAccountDisabled`
- `0x18005a515`: `AppReadiness::User::IsDefaultAccountDisabled`
- `0x18005a51c`: `CreateWellKnownSid(WinAccountDefaultSystemManagedSid, domainInfo.get()->DomainSid, reinterpret_cast<SID*>(sid), &sidLen)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool AppReadiness::User::IsDefaultAccountDisabled(void)
{
  NTSTATUS v0; // eax
  int v1; // eax
  NTSTATUS v2; // eax
  int v3; // eax
  int Error; // eax
  bool v5; // bl
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID DomainInfo; // [rsp+50h] [rbp-B0h] BYREF
  PVOID PolicyHandle; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE bufptr; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Name[264]; // [rsp+130h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v0 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  v1 = ResultFromWin32FromStatus(v0);
  if ( v1 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v1,
      "LsaLookupOpenLocalPolicy(&lsaAttributes, LOOKUP_VIEW_LOCAL_INFORMATION, &lsa)",
      "AppReadiness::User::IsDefaultAccountDisabled",
      "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      2553);
    throw (Windows::HResultException *)pExceptionObject;
  }
  DomainInfo = 0;
  v2 = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &DomainInfo);
  v3 = ResultFromWin32FromStatus(v2);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "LsaLookupGetDomainInfo(lsa.get(), AccountDomainInformation, (PVOID*)&domainInfo)",
      "AppReadiness::User::IsDefaultAccountDisabled",
      "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      2556);
    throw (Windows::HResultException *)pExceptionObject;
  }
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  if ( !CreateWellKnownSid(
          WinLocalAccountAndAdministratorSid|WinCreatorGroupSid,
          *((PSID *)DomainInfo + 2),
          pSid,
          &cbSid) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "CreateWellKnownSid(WinAccountDefaultSystemManagedSid, domainInfo.get()->DomainSid, reinterpret_cast<SID*>(sid), &sidLen)",
        "AppReadiness::User::IsDefaultAccountDisabled",
        "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        2560);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v5 = 0;
  cchName = 260;
  cchReferencedDomainName = 16;
  peUse = 0;
  if ( LookupAccountSidW(0, pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    bufptr = 0;
    if ( !NetUserGetInfo(0, Name, 1u, &bufptr) )
    {
      if ( !bufptr )
        goto LABEL_14;
      v5 = (bufptr[40] & 2) != 0;
    }
    if ( bufptr )
      NetApiBufferFree(bufptr);
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&DomainInfo);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x18005a3bc  mov     [rsp-8+arg_0], rbx
0x18005a3c1  push    rbp
0x18005a3c2  lea     rbp, [rsp-250h]
0x18005a3ca  sub     rsp, 350h
0x18005a3d1  mov     rax, cs:__security_cookie
0x18005a3d8  xor     rax, rsp
0x18005a3db  mov     [rbp+250h+var_10], rax
0x18005a3e2  xorps   xmm0, xmm0
0x18005a3e5  movups  xmmword ptr [rbp+250h+ObjectAttributes.Length], xmm0
0x18005a3e9  movups  xmmword ptr [rbp+250h+ObjectAttributes.ObjectName], xmm0
0x18005a3ed  movups  xmmword ptr [rbp+250h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a3f1  mov     [rsp+350h+PolicyHandle], 0
0x18005a3fa  lea     r8, [rsp+350h+PolicyHandle]; PolicyHandle
0x18005a3ff  mov     edx, 1; AccessMask
0x18005a404  lea     rcx, [rbp+250h+ObjectAttributes]; ObjectAttributes
0x18005a408  call    cs:__imp_LsaLookupOpenLocalPolicy
0x18005a40e  mov     ecx, eax; int
0x18005a410  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18005a415  test    eax, eax
0x18005a417  jns     short loc_18005A459
0x18005a419  mov     dword ptr [rsp+350h+cchReferencedDomainName], 9F9h; int
0x18005a421  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a428  mov     [rsp+350h+ReferencedDomainName], rcx; char *
0x18005a42d  lea     r9, aAppreadinessUs_12; "AppReadiness::User::IsDefaultAccountDis"...
0x18005a434  lea     r8, aLsalookupopenl_0; "LsaLookupOpenLocalPolicy(&lsaAttributes"...
0x18005a43b  mov     edx, eax; int
0x18005a43d  lea     rcx, [rsp+350h+pExceptionObject]; this
0x18005a442  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a447  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a44e  lea     rcx, [rsp+350h+pExceptionObject]; pExceptionObject
0x18005a453  call    _CxxThrowException_0
0x18005a459  mov     [rsp+350h+DomainInfo], 0
0x18005a462  lea     r8, [rsp+350h+DomainInfo]; DomainInfo
0x18005a467  mov     edx, 5; DomainInfoClass
0x18005a46c  mov     rcx, [rsp+350h+PolicyHandle]; PolicyHandle
0x18005a471  call    cs:__imp_LsaLookupGetDomainInfo
0x18005a477  mov     ecx, eax; int
0x18005a479  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18005a47e  test    eax, eax
0x18005a480  jns     short loc_18005A4C2
0x18005a482  mov     dword ptr [rsp+350h+cchReferencedDomainName], 9FCh; int
0x18005a48a  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a491  mov     [rsp+350h+ReferencedDomainName], rcx; char *
0x18005a496  lea     r9, aAppreadinessUs_12; "AppReadiness::User::IsDefaultAccountDis"...
0x18005a49d  lea     r8, aLsalookupgetdo_1; "LsaLookupGetDomainInfo(lsa.get(), Accou"...
0x18005a4a4  mov     edx, eax; int
0x18005a4a6  lea     rcx, [rsp+350h+pExceptionObject]; this
0x18005a4ab  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a4b0  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a4b7  lea     rcx, [rsp+350h+pExceptionObject]; pExceptionObject
0x18005a4bc  call    _CxxThrowException_0
0x18005a4c2  mov     ebx, 44h ; 'D'
0x18005a4c7  mov     r8d, ebx; Size
0x18005a4ca  xor     edx, edx; Val
0x18005a4cc  lea     rcx, [rbp+250h+pSid]; void *
0x18005a4d0  call    memset_0
0x18005a4d5  mov     [rsp+350h+cbSid], ebx
0x18005a4d9  lea     r9, [rsp+350h+cbSid]; cbSid
0x18005a4de  lea     r8, [rbp+250h+pSid]; pSid
0x18005a4e2  mov     rdx, [rsp+350h+DomainInfo]
0x18005a4e7  mov     rdx, [rdx+10h]; DomainSid
0x18005a4eb  lea     ecx, [rbx+2Ah]; WellKnownSidType
0x18005a4ee  call    cs:__imp_CreateWellKnownSid
0x18005a4f4  test    eax, eax
0x18005a4f6  jnz     short loc_18005A541
0x18005a4f8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005a4fd  test    eax, eax
0x18005a4ff  jns     short loc_18005A541
0x18005a501  mov     dword ptr [rsp+350h+cchReferencedDomainName], 0A00h; int
0x18005a509  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a510  mov     [rsp+350h+ReferencedDomainName], rcx; char *
0x18005a515  lea     r9, aAppreadinessUs_12; "AppReadiness::User::IsDefaultAccountDis"...
0x18005a51c  lea     r8, aCreatewellknow_0; "CreateWellKnownSid(WinAccountDefaultSys"...
0x18005a523  mov     edx, eax; int
0x18005a525  lea     rcx, [rsp+350h+pExceptionObject]; this
0x18005a52a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a52f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a536  lea     rcx, [rsp+350h+pExceptionObject]; pExceptionObject
0x18005a53b  call    _CxxThrowException_0
0x18005a541  xor     bl, bl
0x18005a543  mov     [rsp+350h+cchName], 104h
0x18005a54b  mov     [rsp+350h+var_308], 10h
0x18005a553  mov     [rsp+350h+var_30C], 0
0x18005a55b  lea     rax, [rsp+350h+var_30C]
0x18005a560  mov     [rsp+350h+peUse], rax; peUse
0x18005a565  lea     rax, [rsp+350h+var_308]
0x18005a56a  mov     [rsp+350h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18005a56f  lea     rax, [rbp+250h+var_240]
0x18005a573  mov     [rsp+350h+ReferencedDomainName], rax; ReferencedDomainName
0x18005a578  lea     r9, [rsp+350h+cchName]; cchName
0x18005a57d  lea     r8, [rbp+250h+Name]; Name
0x18005a581  lea     rdx, [rbp+250h+pSid]; Sid
0x18005a585  xor     ecx, ecx; lpSystemName
0x18005a587  call    cs:__imp_LookupAccountSidW
0x18005a58d  test    eax, eax
0x18005a58f  jz      short loc_18005A5D3
0x18005a591  mov     [rsp+350h+bufptr], 0
0x18005a59a  lea     r9, [rsp+350h+bufptr]; bufptr
0x18005a59f  mov     r8d, 1; level
0x18005a5a5  lea     rdx, [rbp+250h+Name]; username
0x18005a5a9  xor     ecx, ecx; servername
0x18005a5ab  call    cs:__imp_NetUserGetInfo
0x18005a5b1  mov     rcx, [rsp+350h+bufptr]; Buffer
0x18005a5b6  test    eax, eax
0x18005a5b8  jnz     short loc_18005A5C7
0x18005a5ba  test    rcx, rcx
0x18005a5bd  jz      short loc_18005A5D3
0x18005a5bf  mov     bl, [rcx+28h]
0x18005a5c2  shr     bl, 1
0x18005a5c4  and     bl, 1
0x18005a5c7  test    rcx, rcx
0x18005a5ca  jz      short loc_18005A5D3
0x18005a5cc  call    cs:__imp_NetApiBufferFree
0x18005a5d2  nop
0x18005a5d3  lea     rcx, [rsp+350h+DomainInfo]
0x18005a5d8  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x18005a5dd  nop
0x18005a5de  lea     rcx, [rsp+350h+PolicyHandle]
0x18005a5e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a5e8  mov     al, bl
0x18005a5ea  mov     rcx, [rbp+250h+var_10]
0x18005a5f1  xor     rcx, rsp; StackCookie
0x18005a5f4  call    __security_check_cookie
0x18005a5f9  mov     rbx, [rsp+350h+arg_0]
0x18005a601  add     rsp, 350h
0x18005a608  pop     rbp
0x18005a609  retn
```
