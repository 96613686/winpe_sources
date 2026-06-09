# Common::Deployment::AccessHelpers::ReplacePackageSidWithPackageCapabilitySid(ushort const *,void *)

- ea: `0x180054b3c`
- end: `0x180055028`
- name: `?ReplacePackageSidWithPackageCapabilitySid@AccessHelpers@Deployment@Common@@SAJPEBGPEAX@Z`
- size: `1260`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, PSID pSid)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005341c`

## callees

- `0x18004d8b0`
- `0x180054b3c`
- `0x18005deb8`
- `0x1800a8f80`
- `0x1800a8fc8`
- `0x1800aa988`
- `0x1800c9060`
- `0x1800f0260`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180054c7e`
- `ntdll!RtlValidSid` at `0x180054c7e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180054d44`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180054d44`
- `ntdll!RtlFreeSid` at `0x18005501c`
- `ntdll!RtlFreeSid` at `0x18005501c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054deb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054e00`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054deb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180054e00`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180054e71`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180054e71`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180054dcd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180054dcd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054ca6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cb7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cc8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cd9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054ce9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cfa`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054d0b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054ca6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cb7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cc8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cd9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054ce9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054cfa`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180054d0b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180054c8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180054c8f`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180054f34`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180054f34`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180054bfd`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180054bfd`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180054ea0`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180054ea0`

## string_xrefs

- `0x180054c1f`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180054db6`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180054e34`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180054ef0`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180054f7d`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180055006`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x180054c10`: `GetNamedSecurityInfo %ls`
- `0x180054ff7`: `SetNamedSecurityInfo %ls %u`
- `0x180054fd1`: `AddAccessAllowedAceEx %ls %u %p`
- `0x180054d94`: `DACL of %ls has duplicated package*SIDs ? %u`
- `0x180054faa`: `DACL of %ls missing package*SIDs ? %u`
- `0x180054f76`: `DeleteAce %ls %u %u %u 0x%0x`
- `0x180054f1d`: `PackageSidToPackageCapabilitySid %ls %p`
- `0x180054edc`: `GetNamedSecurityInfo %ls returned null dacl.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Common::Deployment::AccessHelpers::ReplacePackageSidWithPackageCapabilitySid(
        WCHAR *pObjectName,
        PSID pSid)
{
  PSID v2; // rdi
  const WCHAR *i; // r13
  WCHAR *v5; // rax
  DWORD NamedSecurityInfoW; // eax
  int v7; // ebx
  ULONG SubAuthority7; // r12d
  ULONG v10; // r15d
  ULONG v11; // r14d
  ULONG v12; // esi
  ULONG v13; // edi
  ULONG v14; // ebx
  ULONG *SidSubAuthority; // rax
  void *v16; // rdx
  NTSTATUS v17; // ebx
  char v18; // di
  char v19; // si
  DWORD v20; // ebx
  const char *v21; // rax
  __int64 v22; // rdx
  void *v23; // rdx
  char *v24; // r14
  int LastErrorMsg; // eax
  DWORD v26; // eax
  PACL *ppDacl; // [rsp+28h] [rbp-51h]
  PACL *ppSacl; // [rsp+30h] [rbp-49h]
  PACL *ppSacla; // [rsp+30h] [rbp-49h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // [rsp+38h] [rbp-41h]
  __int64 SubAuthority6; // [rsp+40h] [rbp-39h]
  PSID pSid2; // [rsp+60h] [rbp-19h] BYREF
  PACL pAcl; // [rsp+68h] [rbp-11h] BYREF
  PSID pSida; // [rsp+70h] [rbp-9h]
  LPVOID pAce; // [rsp+78h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR P; // [rsp+80h] [rbp+7h] BYREF
  LPWSTR pObjectNamea; // [rsp+88h] [rbp+Fh]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = pSid;
  pSida = pSid;
  pObjectNamea = pObjectName;
  if ( Common::Deployment::Platform::g_platform == 5 )
    return 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogEventAv>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LogEventAv>::GetImpl'::`2'::impl)
    || pObjectName )
  {
    v5 = pObjectName;
    for ( i = pObjectName; v5; ++v5 )
    {
      if ( !*v5 )
        break;
      if ( *v5 == 47 || *v5 == 92 )
        i = v5 + 1;
    }
  }
  else
  {
    i = &LocaleName;
  }
  P = 0;
  pAcl = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &P);
  if ( NamedSecurityInfoW )
  {
    v7 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x345,
           (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
           (const char *)NamedSecurityInfoW,
           (unsigned int)"GetNamedSecurityInfo %ls",
           (const char *)i);
    goto LABEL_12;
  }
  if ( !pAcl )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x348,
      (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (const char *)0x80004003LL,
      (int)"GetNamedSecurityInfo %ls returned null dacl.",
      (const char *)i);
    goto LABEL_12;
  }
  pSid2 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  if ( !RtlValidSid(v2) )
  {
    v7 = -2147024809;
LABEL_44:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x34D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (const char *)(unsigned int)v7,
      (int)"PackageSidToPackageCapabilitySid %ls %p",
      (const char *)i,
      v2);
    goto LABEL_32;
  }
  if ( *GetSidSubAuthorityCount(v2) != 8 )
  {
    v7 = -2147418113;
    goto LABEL_44;
  }
  SubAuthority7 = *GetSidSubAuthority(v2, 7u);
  v10 = *GetSidSubAuthority(v2, 6u);
  v11 = *GetSidSubAuthority(v2, 5u);
  v12 = *GetSidSubAuthority(v2, 4u);
  v13 = *GetSidSubAuthority(v2, 3u);
  v14 = *GetSidSubAuthority(pSida, 2u);
  SidSubAuthority = GetSidSubAuthority(pSida, 1u);
  v17 = RtlAllocateAndInitializeSid(
          &IdentifierAuthority,
          8u,
          3u,
          *SidSubAuthority,
          v14,
          v13,
          v12,
          v11,
          v10,
          SubAuthority7,
          &pSid2);
  if ( v17 < 0 )
  {
    v7 = v17 | 0x10000000;
    if ( v7 < 0 )
    {
      v2 = pSida;
      goto LABEL_44;
    }
  }
  v18 = 0;
  v19 = 0;
  pAce = 0;
  v20 = 0;
  while ( v20 < pAcl->AceCount )
  {
    if ( !GetAce(pAcl, v20, &pAce) )
    {
      LODWORD(ppSacl) = pAcl->AceCount;
      LODWORD(ppDacl) = v20;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x356,
                       (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                       "GetAce %ls %u %u",
                       (const char *)i,
                       ppDacl,
                       ppSacl);
      goto LABEL_31;
    }
    if ( *(_BYTE *)pAce )
    {
LABEL_29:
      ++v20;
    }
    else
    {
      v24 = (char *)pAce + 8;
      if ( !EqualSid((char *)pAce + 8, pSida) )
      {
        if ( EqualSid(v24, pSid2) )
          v18 = 1;
        goto LABEL_29;
      }
      if ( !DeleteAce(pAcl, v20) )
      {
        LODWORD(SubAuthority6) = *((unsigned __int8 *)pAce + 1);
        LODWORD(ppSecurityDescriptor) = *(unsigned __int8 *)pAce;
        LODWORD(ppSacl) = pAcl->AceCount;
        LODWORD(ppDacl) = v20;
        LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                         retaddr,
                         (void *)0x361,
                         (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                         "DeleteAce %ls %u %u %u 0x%0x",
                         (const char *)i,
                         ppDacl,
                         ppSacl,
                         ppSecurityDescriptor,
                         SubAuthority6);
        goto LABEL_31;
      }
      v19 = 1;
    }
  }
  if ( v19 )
  {
    if ( v18 )
    {
      LODWORD(ppSacl) = pAcl->AceCount;
      v21 = "DACL of %ls has duplicated package*SIDs ? %u";
      v7 = -2147418113;
      v22 = 886;
LABEL_23:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
        (const char *)0x8000FFFFLL,
        (int)v21,
        (const char *)i,
        ppSacl);
      goto LABEL_32;
    }
    if ( AddAccessAllowedAceEx(pAcl, 2u, 3u, 0x10000000u, pSid2) )
    {
      v26 = SetNamedSecurityInfoW(pObjectNamea, SE_FILE_OBJECT, 4u, 0, 0, pAcl, 0);
      if ( !v26 )
      {
        if ( pSid2 )
          RtlFreeSid(pSid2);
        goto LABEL_37;
      }
      LODWORD(ppSacla) = pAcl->AceCount;
      LastErrorMsg = wil::details::in1diag3::Return_Win32Msg(
                       retaddr,
                       (void *)0x38C,
                       (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                       (const char *)v26,
                       (unsigned int)"SetNamedSecurityInfo %ls %u",
                       (const char *)i,
                       ppSacla);
    }
    else
    {
      LODWORD(ppDacl) = pAcl->AceCount;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x381,
                       (unsigned int)"onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                       "AddAccessAllowedAceEx %ls %u %p",
                       (const char *)i,
                       ppDacl,
                       pSid2);
    }
LABEL_31:
    v7 = LastErrorMsg;
LABEL_32:
    Common::AutoPtrSidRtlFreeSid((Common *)pSid2, v23);
  }
  else
  {
    if ( !v18 )
    {
      LODWORD(ppSacl) = pAcl->AceCount;
      v21 = "DACL of %ls missing package*SIDs ? %u";
      v7 = -2147418113;
      v22 = 884;
      goto LABEL_23;
    }
    Common::AutoPtrSidRtlFreeSid((Common *)pSid2, v16);
LABEL_37:
    v7 = 0;
  }
LABEL_12:
  AutoPtrRtlHeapDeallocate<unsigned short>(P);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180054b3c  mov     [rsp-8+arg_10], rbx
0x180054b41  push    rbp
0x180054b42  push    rsi
0x180054b43  push    rdi
0x180054b44  push    r12
0x180054b46  push    r13
0x180054b48  push    r14
0x180054b4a  push    r15
0x180054b4c  lea     rbp, [rsp-27h]
0x180054b51  sub     rsp, 0A0h
0x180054b58  mov     rax, cs:__security_cookie
0x180054b5f  xor     rax, rsp
0x180054b62  mov     [rbp+57h+var_38], rax
0x180054b66  mov     rdi, rdx
0x180054b69  mov     [rbp+57h+pSid], rdx
0x180054b6d  mov     rbx, rcx
0x180054b70  mov     [rbp+57h+pObjectName], rcx
0x180054b74  cmp     cs:?g_platform@Platform@Deployment@Common@@3KA, 5; ulong Common::Deployment::Platform::g_platform
0x180054b7b  jz      loc_180054EC3
0x180054b81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LogEventAv@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LogEventAv@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogEventAv> `wil::Feature<__WilFeatureTraits_Feature_LogEventAv>::GetImpl(void)'::`2'::impl
0x180054b88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LogEventAv@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LogEventAv>::__private_IsEnabled(void)
0x180054b8d  xor     esi, esi
0x180054b8f  test    al, al
0x180054b91  jz      short loc_180054BA1
0x180054b93  test    rbx, rbx
0x180054b96  jnz     short loc_180054BA1
0x180054b98  lea     r13, LocaleName
0x180054b9f  jmp     short loc_180054BCB
0x180054ba1  mov     rax, rbx
0x180054ba4  mov     r13, rbx
0x180054ba7  test    rbx, rbx
0x180054baa  jz      short loc_180054BCB
0x180054bac  cmp     [rax], si
0x180054baf  jz      short loc_180054BCB
0x180054bb1  cmp     word ptr [rax], 2Fh ; '/'
0x180054bb5  jz      loc_180054ECA
0x180054bbb  cmp     word ptr [rax], 5Ch ; '\'
0x180054bbf  jz      loc_180054ECA
0x180054bc5  add     rax, 2
0x180054bc9  jnz     short loc_180054BAC
0x180054bcb  mov     [rbp+57h+P], rsi
0x180054bcf  mov     [rbp+57h+pAcl], rsi
0x180054bd3  lea     rax, [rbp+57h+P]
0x180054bd7  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180054bdc  mov     [rsp+0D0h+ppSacl], rsi; ppSacl
0x180054be1  lea     rax, [rbp+57h+pAcl]
0x180054be5  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x180054bea  mov     [rsp+0D0h+ppsidGroup], rsi; ppsidGroup
0x180054bef  xor     r9d, r9d; ppsidOwner
0x180054bf2  lea     edx, [r9+1]; ObjectType
0x180054bf6  lea     r8d, [r9+4]; SecurityInfo
0x180054bfa  mov     rcx, rbx; pObjectName
0x180054bfd  call    cs:__imp_GetNamedSecurityInfoW
0x180054c03  test    eax, eax
0x180054c05  jz      short loc_180054C64
0x180054c07  mov     rcx, [rbp+5Fh]; this
0x180054c0b  mov     [rsp+0D0h+ppDacl], r13; char *
0x180054c10  lea     rdx, aGetnamedsecuri; "GetNamedSecurityInfo %ls"
0x180054c17  mov     [rsp+0D0h+ppsidGroup], rdx; unsigned int
0x180054c1c  mov     r9d, eax; char *
0x180054c1f  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x180054c26  mov     edx, 345h; void *
0x180054c2b  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180054c30  mov     ebx, eax
0x180054c32  mov     rcx, [rbp+57h+P]; P
0x180054c36  call    ??$AutoPtrRtlHeapDeallocate@G@@YAXPEAG@Z; AutoPtrRtlHeapDeallocate<ushort>(ushort *)
0x180054c3b  mov     eax, ebx
0x180054c3d  mov     rcx, [rbp+57h+var_38]
0x180054c41  xor     rcx, rsp; StackCookie
0x180054c44  call    __security_check_cookie
0x180054c49  mov     rbx, [rsp+0D0h+arg_10]
0x180054c51  add     rsp, 0A0h
0x180054c58  pop     r15
0x180054c5a  pop     r14
0x180054c5c  pop     r13
0x180054c5e  pop     r12
0x180054c60  pop     rdi
0x180054c61  pop     rsi
0x180054c62  pop     rbp
0x180054c63  retn
0x180054c64  cmp     [rbp+57h+pAcl], rsi
0x180054c68  jz      loc_180054ED3
0x180054c6e  mov     [rbp+57h+pSid2], rsi
0x180054c72  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x180054c75  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x180054c7b  mov     rcx, rdi; Sid
0x180054c7e  call    cs:__imp_RtlValidSid
0x180054c84  test    al, al
0x180054c86  jz      loc_180054F06
0x180054c8c  mov     rcx, rdi; pSid
0x180054c8f  call    cs:__imp_GetSidSubAuthorityCount
0x180054c95  cmp     byte ptr [rax], 8
0x180054c98  jnz     loc_180054F0D
0x180054c9e  mov     edx, 7; nSubAuthority
0x180054ca3  mov     rcx, rdi; pSid
0x180054ca6  call    cs:__imp_GetSidSubAuthority
0x180054cac  mov     r12d, [rax]
0x180054caf  mov     edx, 6; nSubAuthority
0x180054cb4  mov     rcx, rdi; pSid
0x180054cb7  call    cs:__imp_GetSidSubAuthority
0x180054cbd  mov     r15d, [rax]
0x180054cc0  mov     edx, 5; nSubAuthority
0x180054cc5  mov     rcx, rdi; pSid
0x180054cc8  call    cs:__imp_GetSidSubAuthority
0x180054cce  mov     r14d, [rax]
0x180054cd1  mov     edx, 4; nSubAuthority
0x180054cd6  mov     rcx, rdi; pSid
0x180054cd9  call    cs:__imp_GetSidSubAuthority
0x180054cdf  mov     esi, [rax]
0x180054ce1  mov     edx, 3; nSubAuthority
0x180054ce6  mov     rcx, rdi; pSid
0x180054ce9  call    cs:__imp_GetSidSubAuthority
0x180054cef  mov     edi, [rax]
0x180054cf1  mov     edx, 2; nSubAuthority
0x180054cf6  mov     rcx, [rbp+57h+pSid]; pSid
0x180054cfa  call    cs:__imp_GetSidSubAuthority
0x180054d00  mov     ebx, [rax]
0x180054d02  mov     edx, 1; nSubAuthority
0x180054d07  mov     rcx, [rbp+57h+pSid]; pSid
0x180054d0b  call    cs:__imp_GetSidSubAuthority
0x180054d11  lea     rcx, [rbp+57h+pSid2]
0x180054d15  mov     [rsp+0D0h+Sid], rcx; Sid
0x180054d1a  mov     [rsp+0D0h+SubAuthority7], r12d; SubAuthority7
0x180054d1f  mov     dword ptr [rsp+0D0h+SubAuthority6], r15d; SubAuthority6
0x180054d24  mov     dword ptr [rsp+0D0h+ppSecurityDescriptor], r14d; SubAuthority5
0x180054d29  mov     dword ptr [rsp+0D0h+ppSacl], esi; SubAuthority4
0x180054d2d  mov     dword ptr [rsp+0D0h+ppDacl], edi; SubAuthority3
0x180054d31  mov     dword ptr [rsp+0D0h+ppsidGroup], ebx; SubAuthority2
0x180054d35  mov     r9d, [rax]; SubAuthority1
0x180054d38  mov     r8d, 3; SubAuthority0
0x180054d3e  mov     dl, 8; SubAuthorityCount
0x180054d40  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180054d44  call    cs:__imp_RtlAllocateAndInitializeSid
0x180054d4a  mov     ebx, eax
0x180054d4c  xor     r15d, r15d
0x180054d4f  test    eax, eax
0x180054d51  jns     short loc_180054D5F
0x180054d53  or      ebx, 10000000h
0x180054d59  jl      loc_180054F14
0x180054d5f  mov     dil, r15b
0x180054d62  mov     sil, r15b
0x180054d65  mov     [rbp+57h+pAce], r15
0x180054d69  mov     ebx, r15d
0x180054d6c  mov     r12d, 1
0x180054d72  mov     rcx, [rbp+57h+pAcl]; pAcl
0x180054d76  movzx   eax, word ptr [rcx+4]
0x180054d7a  cmp     ebx, eax
0x180054d7c  jb      short loc_180054DC7
0x180054d7e  test    sil, sil
0x180054d81  jz      loc_180054F93
0x180054d87  test    dil, dil
0x180054d8a  jz      loc_180054E59
0x180054d90  mov     dword ptr [rsp+0D0h+ppSacl], eax
0x180054d94  lea     rax, aDaclOfLsHasDup; "DACL of %ls has duplicated package*SIDs"...
0x180054d9b  mov     ebx, 8000FFFFh
0x180054da0  mov     edx, 376h; void *
0x180054da5  mov     [rsp+0D0h+ppDacl], r13; char *
0x180054daa  mov     rcx, [rbp+5Fh]; this
0x180054dae  mov     [rsp+0D0h+ppsidGroup], rax; int
0x180054db3  mov     r9d, ebx; char *
0x180054db6  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x180054dbd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054dc2  jmp     loc_180054E4B
0x180054dc7  lea     r8, [rbp+57h+pAce]; pAce
0x180054dcb  mov     edx, ebx; dwAceIndex
0x180054dcd  call    cs:__imp_GetAce
0x180054dd3  test    eax, eax
0x180054dd5  jz      short loc_180054E18
0x180054dd7  mov     rax, [rbp+57h+pAce]
0x180054ddb  cmp     [rax], r15b
0x180054dde  jnz     short loc_180054E10
0x180054de0  lea     r14, [rax+8]
0x180054de4  mov     rdx, [rbp+57h+pSid]; pSid2
0x180054de8  mov     rcx, r14; pSid1
0x180054deb  call    cs:__imp_EqualSid
0x180054df1  test    eax, eax
0x180054df3  jnz     loc_180054F2E
0x180054df9  mov     rdx, [rbp+57h+pSid2]; pSid2
0x180054dfd  mov     rcx, r14; pSid1
0x180054e00  call    cs:__imp_EqualSid
0x180054e06  movzx   edi, dil
0x180054e0a  test    eax, eax
0x180054e0c  cmovnz  edi, r12d
0x180054e10  add     ebx, r12d
0x180054e13  jmp     loc_180054D72
0x180054e18  mov     rax, [rbp+57h+pAcl]
0x180054e1c  movzx   edx, word ptr [rax+4]
0x180054e20  mov     dword ptr [rsp+0D0h+ppSacl], edx
0x180054e24  mov     dword ptr [rsp+0D0h+ppDacl], ebx
0x180054e28  lea     r9, aGetaceLsUU; "GetAce %ls %u %u"
0x180054e2f  mov     edx, 356h; void *
0x180054e34  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x180054e3b  mov     [rsp+0D0h+ppsidGroup], r13; char *
0x180054e40  mov     rcx, [rbp+5Fh]; this
0x180054e44  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180054e49  mov     ebx, eax
0x180054e4b  mov     rcx, [rbp+57h+pSid2]; this
0x180054e4f  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x180054e54  jmp     loc_180054C32
0x180054e59  mov     rax, [rbp+57h+pSid2]
0x180054e5d  mov     [rsp+0D0h+ppsidGroup], rax; pSid
0x180054e62  mov     edx, 2; dwAceRevision
0x180054e67  mov     r9d, 10000000h; AccessMask
0x180054e6d  lea     r8d, [rdx+1]; AceFlags
0x180054e71  call    cs:__imp_AddAccessAllowedAceEx
0x180054e77  test    eax, eax
0x180054e79  mov     rax, [rbp+57h+pAcl]
0x180054e7d  jz      loc_180054FC0
0x180054e83  mov     [rsp+0D0h+ppSacl], r15; pSacl
0x180054e88  mov     [rsp+0D0h+ppDacl], rax; pDacl
0x180054e8d  mov     [rsp+0D0h+ppsidGroup], r15; psidGroup
0x180054e92  xor     r9d, r9d; psidOwner
0x180054e95  lea     r8d, [r9+4]; SecurityInfo
0x180054e99  mov     edx, r12d; ObjectType
0x180054e9c  mov     rcx, [rbp+57h+pObjectName]; pObjectName
0x180054ea0  call    cs:__imp_SetNamedSecurityInfoW
0x180054ea6  test    eax, eax
0x180054ea8  jnz     loc_180054FE2
0x180054eae  mov     rcx, [rbp+57h+pSid2]; Sid
0x180054eb2  test    rcx, rcx
0x180054eb5  jnz     loc_18005501C
0x180054ebb  mov     ebx, r15d
0x180054ebe  jmp     loc_180054C32
0x180054ec3  xor     eax, eax
0x180054ec5  jmp     loc_180054C3D
0x180054eca  lea     r13, [rax+2]
0x180054ece  jmp     loc_180054BC5
0x180054ed3  mov     rcx, [rbp+5Fh]; this
0x180054ed7  mov     [rsp+0D0h+ppDacl], r13; char *
0x180054edc  lea     rax, aGetnamedsecuri_0; "GetNamedSecurityInfo %ls returned null "...
0x180054ee3  mov     [rsp+0D0h+ppsidGroup], rax; int
0x180054ee8  mov     ebx, 80004003h
0x180054eed  mov     r9d, ebx; char *
0x180054ef0  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x180054ef7  mov     edx, 348h; void *
0x180054efc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054f01  jmp     loc_180054C32
0x180054f06  mov     ebx, 80070057h
0x180054f0b  jmp     short loc_180054F18
0x180054f0d  mov     ebx, 8000FFFFh
0x180054f12  jmp     short loc_180054F18
0x180054f14  mov     rdi, [rbp+57h+pSid]
0x180054f18  mov     [rsp+0D0h+ppSacl], rdi
0x180054f1d  lea     rax, aPackagesidtopa; "PackageSidToPackageCapabilitySid %ls %p"
0x180054f24  mov     edx, 34Dh
0x180054f29  jmp     loc_180054DA5
0x180054f2e  mov     edx, ebx; dwAceIndex
0x180054f30  mov     rcx, [rbp+57h+pAcl]; pAcl
0x180054f34  call    cs:__imp_DeleteAce
0x180054f3a  test    eax, eax
0x180054f3c  jz      short loc_180054F46
0x180054f3e  mov     sil, r12b
0x180054f41  jmp     loc_180054D72
0x180054f46  mov     rax, [rbp+57h+pAce]
0x180054f4a  movzx   r8d, byte ptr [rax+1]
0x180054f4f  movzx   r9d, byte ptr [rax]
0x180054f53  mov     rax, [rbp+57h+pAcl]
0x180054f57  movzx   edx, word ptr [rax+4]
0x180054f5b  mov     rcx, [rbp+5Fh]; this
0x180054f5f  mov     dword ptr [rsp+0D0h+SubAuthority6], r8d
0x180054f64  mov     dword ptr [rsp+0D0h+ppSecurityDescriptor], r9d
0x180054f69  mov     dword ptr [rsp+0D0h+ppSacl], edx
0x180054f6d  mov     dword ptr [rsp+0D0h+ppDacl], ebx
0x180054f71  mov     [rsp+0D0h+ppsidGroup], r13; char *
0x180054f76  lea     r9, aDeleteaceLsUUU; "DeleteAce %ls %u %u %u 0x%0x"
0x180054f7d  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x180054f84  mov     edx, 361h; void *
0x180054f89  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180054f8e  jmp     loc_180054E49
0x180054f93  test    dil, dil
0x180054f96  jz      short loc_180054FA6
0x180054f98  mov     rcx, [rbp+57h+pSid2]; this
0x180054f9c  call    ?AutoPtrSidRtlFreeSid@Common@@YAXPEAX@Z; Common::AutoPtrSidRtlFreeSid(void *)
0x180054fa1  jmp     loc_180054EBB
0x180054fa6  mov     dword ptr [rsp+0D0h+ppSacl], eax
0x180054faa  lea     rax, aDaclOfLsMissin; "DACL of %ls missing package*SIDs ? %u"
0x180054fb1  mov     ebx, 8000FFFFh
0x180054fb6  mov     edx, 374h
0x180054fbb  jmp     loc_180054DA5
0x180054fc0  mov     r8, [rbp+57h+pSid2]
0x180054fc4  movzx   edx, word ptr [rax+4]
0x180054fc8  mov     [rsp+0D0h+ppSacl], r8
0x180054fcd  mov     dword ptr [rsp+0D0h+ppDacl], edx
0x180054fd1  lea     r9, aAddaccessallow; "AddAccessAllowedAceEx %ls %u %p"
0x180054fd8  mov     edx, 381h
0x180054fdd  jmp     loc_180054E34
0x180054fe2  mov     rcx, [rbp+57h+pAcl]
0x180054fe6  movzx   edx, word ptr [rcx+4]
0x180054fea  mov     rcx, [rbp+5Fh]; this
0x180054fee  mov     dword ptr [rsp+0D0h+ppSacl], edx
0x180054ff2  mov     [rsp+0D0h+ppDacl], r13; char *
0x180054ff7  lea     rdx, aSetnamedsecuri_0; "SetNamedSecurityInfo %ls %u"
0x180054ffe  mov     [rsp+0D0h+ppsidGroup], rdx; unsigned int
0x180055003  mov     r9d, eax; char *
0x180055006  lea     r8, aOnecoreAdminAp_135; "onecore\\admin\\appmodel\\common\\acces"...
0x18005500d  mov     edx, 38Ch; void *
0x180055012  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180055017  jmp     loc_180054E49
0x18005501c  call    cs:__imp_RtlFreeSid
0x180055022  jmp     loc_180054EBB
  ... truncated ...
```
