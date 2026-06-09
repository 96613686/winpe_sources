# ProviderSubSystem_Common_Globals::AdjustSecurityDescriptorWithSid(_SID *,_SID *,ulong,_SECURITY_DESCRIPTOR * &,_SECURITY_DESCRIPTOR * &)

- ea: `0x140040e78`
- end: `0x14004146f`
- name: `?AdjustSecurityDescriptorWithSid@ProviderSubSystem_Common_Globals@@SAJPEAU_SID@@0KAEAPEAU_SECURITY_DESCRIPTOR@@1@Z`
- size: `1527`
- prototype: `__int64 __fastcall(PSID pSid, PSID pGroup, __int64, PSECURITY_DESCRIPTOR *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140041c60`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x14002b716`
- `0x140040e78`
- `0x140046430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140040f66`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140041080`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004120d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140040f66`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140041080`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004120d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140041397`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140041397`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140040ff2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400411ba`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140040ff2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1400411ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400410b8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400410b8`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140040f46`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140041048`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140040f46`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140041048`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14004126a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14004126a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400412ae`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400412e5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140041317`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14004134b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14004137f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400412ae`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400412e5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140041317`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14004134b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14004137f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400413b3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400413e2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400413b3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400413e2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140041184`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1400411e2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140041184`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1400411e2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400410f9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140041282`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400410f9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140041282`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140041067`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400411ce`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140041067`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1400411ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400413bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400413bd`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Common_Globals::AdjustSecurityDescriptorWithSid(
        PSID pSid,
        PSID pGroup,
        __int64 a3,
        PSECURITY_DESCRIPTOR *a4,
        struct _SECURITY_DESCRIPTOR **a5)
{
  PSECURITY_DESCRIPTOR v6; // rcx
  int v9; // ebx
  _OWORD *v10; // r13
  __int16 LengthSid; // ax
  struct _ACL *v12; // r12
  void *v13; // r15
  DWORD v14; // eax
  DWORD v15; // esi
  DWORD v16; // r12d
  char *v17; // rax
  _DWORD *v18; // rdi
  struct _ACL *v19; // rax
  WORD v20; // r15
  struct _ACL *v21; // rax
  struct _ACL *v22; // rsi
  DWORD v23; // r15d
  struct _ACL *v24; // rax
  PSECURITY_DESCRIPTOR *v25; // r14
  void *v26; // rax
  DWORD dwOwnerSize; // [rsp+60h] [rbp-71h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+64h] [rbp-6Dh] BYREF
  DWORD dwSaclSize; // [rsp+68h] [rbp-69h] BYREF
  DWORD dwDaclSize; // [rsp+6Ch] [rbp-65h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp-61h] BYREF
  DWORD dwBufferLength; // [rsp+74h] [rbp-5Dh] BYREF
  PACL pAcl; // [rsp+78h] [rbp-59h]
  PACL pSacl; // [rsp+80h] [rbp-51h]
  PSID lpMem; // [rsp+88h] [rbp-49h]
  PSID pPrimaryGroup; // [rsp+90h] [rbp-41h]
  void *v38; // [rsp+98h] [rbp-39h]
  PSECURITY_DESCRIPTOR *v39; // [rsp+A0h] [rbp-31h]
  _OWORD pSecurityDescriptor[2]; // [rsp+A8h] [rbp-29h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-9h]
  __int64 pAclInformation; // [rsp+D0h] [rbp-1h] BYREF
  int v43; // [rsp+D8h] [rbp+7h]

  v39 = (PSECURITY_DESCRIPTOR *)a5;
  pAcl = 0;
  v41 = 0;
  v6 = *a4;
  pSacl = 0;
  lpMem = 0;
  v9 = 0;
  pPrimaryGroup = 0;
  v38 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( v6 )
  {
    dwAbsoluteSecurityDescriptorSize = 40;
    v10 = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( MakeAbsoluteSD(
           v6,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize)
      || GetLastError() != 122 )
    {
      v9 = -2147217398;
    }
    else
    {
      LengthSid = GetLengthSid(pSid);
      v12 = (struct _ACL *)operator new(dwDaclSize + 12 + (unsigned __int16)(LengthSid - 4));
      pAcl = v12;
      pSacl = (PACL)operator new(dwSaclSize);
      lpMem = operator new(dwOwnerSize);
      pPrimaryGroup = operator new(dwPrimaryGroupSize);
      v13 = operator new(dwAbsoluteSecurityDescriptorSize);
      v38 = v13;
      if ( v13 && v12 && pSacl && lpMem && pPrimaryGroup )
      {
        if ( InitializeSecurityDescriptor(v13, 1u)
          && MakeAbsoluteSD(
               *a4,
               v13,
               &dwAbsoluteSecurityDescriptorSize,
               v12,
               &dwDaclSize,
               pSacl,
               &dwSaclSize,
               lpMem,
               &dwOwnerSize,
               pPrimaryGroup,
               &dwPrimaryGroupSize)
          && ((v10 = v13, dwOwnerSize) || SetSecurityDescriptorOwner(v13, pSid, 0)) )
        {
          if ( !dwPrimaryGroupSize && !SetSecurityDescriptorGroup(v13, pGroup, 0) )
            v9 = -2147217398;
        }
        else
        {
          v9 = -2147217398;
        }
      }
      else
      {
        v9 = -2147217402;
      }
    }
  }
  else
  {
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || !SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, 0)
      || !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0) )
    {
      v9 = -2147217398;
    }
    v10 = pSecurityDescriptor;
  }
  v14 = GetLengthSid(pSid);
  v15 = v14;
  if ( v9 >= 0 )
  {
    v16 = (unsigned __int16)(v14 - 4) + 12;
    v17 = (char *)operator new(v16);
    v18 = v17;
    if ( !v17 )
    {
      v9 = -2147217402;
      goto LABEL_56;
    }
    CopySid(v15, v17 + 8, pSid);
    v18[1] = 1;
    pAclInformation = 0;
    v43 = 0;
    v19 = pAcl;
    *(_WORD *)v18 = 768;
    *((_WORD *)v18 + 1) = v16;
    if ( v19 )
    {
      if ( GetAclInformation(v19, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v20 = ProviderSubSystem_Common_Globals::s_System_ACESize
            + ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
            + v15
            - 4
            + v43
            + ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
            + ProviderSubSystem_Common_Globals::s_LocalService_ACESize
            + WORD2(pAclInformation)
            + 12;
        v21 = (struct _ACL *)operator new(
                               ProviderSubSystem_Common_Globals::s_System_ACESize
                             + ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
                             + (unsigned __int16)(v15 - 4)
                             + v43
                             + ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
                             + (unsigned int)ProviderSubSystem_Common_Globals::s_LocalService_ACESize
                             + HIDWORD(pAclInformation)
                             + 12);
        v22 = v21;
        if ( v21 )
        {
          memcpy_0(v21, pAcl, (unsigned int)(v43 + HIDWORD(pAclInformation)));
          v22->AclSize = v20;
          goto LABEL_37;
        }
        v9 = -2147217402;
LABEL_36:
        if ( v9 < 0 )
          goto LABEL_54;
LABEL_37:
        if ( !AddAce(v22, 2u, pAclInformation, v18, v16) )
          goto LABEL_51;
        if ( !ProviderSubSystem_Common_Globals::s_System_ACESize
          || !AddAce(
                v22,
                2u,
                1u,
                ProviderSubSystem_Common_Globals::s_Provider_System_ACE,
                ProviderSubSystem_Common_Globals::s_System_ACESize) )
        {
          v9 = -2147217398;
          goto LABEL_54;
        }
        if ( !ProviderSubSystem_Common_Globals::s_LocalService_ACESize
          || !AddAce(
                v22,
                2u,
                2u,
                ProviderSubSystem_Common_Globals::s_Provider_LocalService_ACE,
                ProviderSubSystem_Common_Globals::s_LocalService_ACESize)
          || !ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
          || !AddAce(
                v22,
                2u,
                3u,
                ProviderSubSystem_Common_Globals::s_Provider_NetworkService_ACE,
                ProviderSubSystem_Common_Globals::s_NetworkService_ACESize)
          || !ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
          || !AddAce(
                v22,
                2u,
                4u,
                ProviderSubSystem_Common_Globals::s_Provider_LocalAdmins_ACE,
                ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize)
          || !SetSecurityDescriptorDacl(v10, 1, v22, 0) )
        {
          goto LABEL_51;
        }
        v25 = v39;
        dwBufferLength = 0;
        if ( MakeSelfRelativeSD(v10, *v39, &dwBufferLength) || GetLastError() != 122 )
          goto LABEL_54;
        v26 = operator new(dwBufferLength);
        *v25 = v26;
        if ( v26 )
        {
          if ( !MakeSelfRelativeSD(v10, v26, &dwBufferLength) )
LABEL_51:
            v9 = -2147217398;
LABEL_54:
          operator delete(v18);
          operator delete(v22);
          goto LABEL_56;
        }
LABEL_53:
        v9 = -2147217402;
        goto LABEL_54;
      }
      v22 = 0;
    }
    else
    {
      v23 = ProviderSubSystem_Common_Globals::s_LocalService_ACESize
          + 20
          + ProviderSubSystem_Common_Globals::s_System_ACESize
          + ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
          + (unsigned __int16)(GetLengthSid(pSid) - 4)
          + ProviderSubSystem_Common_Globals::s_NetworkService_ACESize;
      v24 = (struct _ACL *)operator new(v23);
      v22 = v24;
      if ( !v24 )
        goto LABEL_53;
      if ( InitializeAcl(v24, v23, 2u) && GetAclInformation(v22, &pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_36;
    }
    v9 = -2147217398;
    goto LABEL_36;
  }
LABEL_56:
  operator delete(pAcl);
  operator delete(pSacl);
  operator delete(lpMem);
  operator delete(pPrimaryGroup);
  operator delete(v38);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140040e78  mov     [rsp-8+arg_10], rbx
0x140040e7d  push    rbp
0x140040e7e  push    rsi
0x140040e7f  push    rdi
0x140040e80  push    r12
0x140040e82  push    r13
0x140040e84  push    r14
0x140040e86  push    r15
0x140040e88  lea     rbp, [rsp-1Fh]
0x140040e8d  sub     rsp, 0F0h
0x140040e94  mov     rax, cs:__security_cookie
0x140040e9b  xor     rax, rsp
0x140040e9e  mov     [rbp+4Fh+var_40], rax
0x140040ea2  mov     rax, [rbp+4Fh+arg_20]
0x140040ea6  xor     r15d, r15d
0x140040ea9  xorps   xmm0, xmm0
0x140040eac  mov     [rbp+4Fh+var_80], rax
0x140040eb0  xor     eax, eax
0x140040eb2  mov     [rbp+4Fh+pAcl], r15
0x140040eb6  mov     r14, rcx
0x140040eb9  mov     [rbp+4Fh+var_58], rax
0x140040ebd  mov     rcx, [r9]; pSelfRelativeSecurityDescriptor
0x140040ec0  mov     rdi, r9
0x140040ec3  mov     [rbp+4Fh+var_A0], r15
0x140040ec7  mov     rsi, rdx
0x140040eca  mov     [rbp+4Fh+lpMem], r15
0x140040ece  mov     ebx, r15d
0x140040ed1  mov     [rbp+4Fh+var_90], r15
0x140040ed5  mov     r12d, 8004100Ah
0x140040edb  mov     [rbp+4Fh+var_88], r15
0x140040edf  movups  [rbp+4Fh+pSecurityDescriptor], xmm0
0x140040ee3  movups  [rbp+4Fh+var_68], xmm0
0x140040ee7  test    rcx, rcx
0x140040eea  jz      loc_1400411B1
0x140040ef0  lea     rax, [rbp+4Fh+dwPrimaryGroupSize]
0x140040ef4  mov     [rbp+4Fh+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x140040efb  mov     [rsp+120h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140040f00  lea     r8, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140040f04  mov     [rsp+120h+pPrimaryGroup], r15; pPrimaryGroup
0x140040f09  lea     rax, [rbp+4Fh+dwOwnerSize]
0x140040f0d  mov     [rsp+120h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140040f12  xor     r9d, r9d; pDacl
0x140040f15  mov     [rsp+120h+pOwner], r15; pOwner
0x140040f1a  lea     rax, [rbp+4Fh+dwSaclSize]
0x140040f1e  mov     [rsp+120h+lpdwSaclSize], rax; lpdwSaclSize
0x140040f23  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140040f25  lea     rax, [rbp+4Fh+dwDaclSize]
0x140040f29  mov     [rsp+120h+pSacl], r15; pSacl
0x140040f2e  mov     [rsp+120h+lpdwDaclSize], rax; lpdwDaclSize
0x140040f33  mov     r13d, r15d
0x140040f36  mov     [rbp+4Fh+dwDaclSize], r15d
0x140040f3a  mov     [rbp+4Fh+dwSaclSize], r15d
0x140040f3e  mov     [rbp+4Fh+dwOwnerSize], r15d
0x140040f42  mov     [rbp+4Fh+dwPrimaryGroupSize], r15d
0x140040f46  call    cs:__imp_MakeAbsoluteSD
0x140040f4c  test    eax, eax
0x140040f4e  jnz     loc_1400411A9
0x140040f54  call    cs:__imp_GetLastError
0x140040f5a  cmp     eax, 7Ah ; 'z'
0x140040f5d  jnz     loc_1400411A9
0x140040f63  mov     rcx, r14; pSid
0x140040f66  call    cs:__imp_GetLengthSid
0x140040f6c  sub     ax, 4
0x140040f70  movzx   ecx, ax
0x140040f73  mov     eax, [rbp+4Fh+dwDaclSize]
0x140040f76  add     eax, 0Ch
0x140040f79  add     ecx, eax; dwBytes
0x140040f7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040f80  mov     ecx, [rbp+4Fh+dwSaclSize]; dwBytes
0x140040f83  mov     r12, rax
0x140040f86  mov     [rbp+4Fh+pAcl], rax
0x140040f8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040f8f  mov     ecx, [rbp+4Fh+dwOwnerSize]; dwBytes
0x140040f92  mov     [rbp+4Fh+var_A0], rax
0x140040f96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040f9b  mov     ecx, [rbp+4Fh+dwPrimaryGroupSize]; dwBytes
0x140040f9e  mov     [rbp+4Fh+lpMem], rax
0x140040fa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040fa7  mov     ecx, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]; dwBytes
0x140040faa  mov     [rbp+4Fh+var_90], rax
0x140040fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040fb3  mov     r15, rax
0x140040fb6  mov     [rbp+4Fh+var_88], rax
0x140040fba  xor     eax, eax
0x140040fbc  test    r15, r15
0x140040fbf  jz      loc_14004119F
0x140040fc5  test    r12, r12
0x140040fc8  jz      loc_14004119F
0x140040fce  cmp     [rbp+4Fh+var_A0], rax
0x140040fd2  jz      loc_14004119F
0x140040fd8  cmp     [rbp+4Fh+lpMem], rax
0x140040fdc  jz      loc_14004119F
0x140040fe2  cmp     [rbp+4Fh+var_90], rax
0x140040fe6  jz      loc_14004119F
0x140040fec  lea     edx, [rax+1]; dwRevision
0x140040fef  mov     rcx, r15; pSecurityDescriptor
0x140040ff2  call    cs:__imp_InitializeSecurityDescriptor
0x140040ff8  test    eax, eax
0x140040ffa  jz      short loc_140041075
0x140040ffc  mov     rcx, [rdi]; pSelfRelativeSecurityDescriptor
0x140040fff  lea     rax, [rbp+4Fh+dwPrimaryGroupSize]
0x140041003  mov     [rsp+120h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140041008  lea     r8, [rbp+4Fh+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x14004100c  mov     rax, [rbp+4Fh+var_90]
0x140041010  mov     r9, r12; pDacl
0x140041013  mov     [rsp+120h+pPrimaryGroup], rax; pPrimaryGroup
0x140041018  mov     rdx, r15; pAbsoluteSecurityDescriptor
0x14004101b  lea     rax, [rbp+4Fh+dwOwnerSize]
0x14004101f  mov     [rsp+120h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140041024  mov     rax, [rbp+4Fh+lpMem]
0x140041028  mov     [rsp+120h+pOwner], rax; pOwner
0x14004102d  lea     rax, [rbp+4Fh+dwSaclSize]
0x140041031  mov     [rsp+120h+lpdwSaclSize], rax; lpdwSaclSize
0x140041036  mov     rax, [rbp+4Fh+var_A0]
0x14004103a  mov     [rsp+120h+pSacl], rax; pSacl
0x14004103f  lea     rax, [rbp+4Fh+dwDaclSize]
0x140041043  mov     [rsp+120h+lpdwDaclSize], rax; lpdwDaclSize
0x140041048  call    cs:__imp_MakeAbsoluteSD
0x14004104e  test    eax, eax
0x140041050  jz      short loc_140041075
0x140041052  mov     r13, r15
0x140041055  cmp     [rbp+4Fh+dwOwnerSize], ebx
0x140041058  jnz     loc_140041172
0x14004105e  xor     r8d, r8d; bOwnerDefaulted
0x140041061  mov     rdx, r14; pOwner
0x140041064  mov     rcx, r15; pSecurityDescriptor
0x140041067  call    cs:__imp_SetSecurityDescriptorOwner
0x14004106d  test    eax, eax
0x14004106f  jnz     loc_140041172
0x140041075  mov     ebx, 8004100Ah
0x14004107a  xor     r15d, r15d
0x14004107d  mov     rcx, r14; pSid
0x140041080  call    cs:__imp_GetLengthSid
0x140041086  mov     esi, eax
0x140041088  test    ebx, ebx
0x14004108a  js      loc_140041419
0x140041090  add     eax, 0FFFFFFFCh
0x140041093  movzx   r12d, ax
0x140041097  add     r12d, 0Ch
0x14004109b  mov     ecx, r12d; dwBytes
0x14004109e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400410a3  mov     rdi, rax
0x1400410a6  test    rax, rax
0x1400410a9  jz      loc_140041414
0x1400410af  lea     rdx, [rax+8]; pDestinationSid
0x1400410b3  mov     r8, r14; pSourceSid
0x1400410b6  mov     ecx, esi; nDestinationSidLength
0x1400410b8  call    cs:__imp_CopySid
0x1400410be  xor     eax, eax
0x1400410c0  mov     dword ptr [rdi+4], 1
0x1400410c7  mov     [rbp+4Fh+pAclInformation], rax
0x1400410cb  mov     [rbp+4Fh+var_48], eax
0x1400410ce  mov     rax, [rbp+4Fh+pAcl]
0x1400410d2  mov     word ptr [rdi], 300h
0x1400410d7  mov     [rdi+2], r12w
0x1400410dc  test    rax, rax
0x1400410df  jz      loc_14004120A
0x1400410e5  mov     r14d, 2
0x1400410eb  lea     rdx, [rbp+4Fh+pAclInformation]; pAclInformation
0x1400410ef  mov     r9d, r14d; dwAclInformationClass
0x1400410f2  mov     rcx, rax; pAcl
0x1400410f5  lea     r8d, [r14+0Ah]; nAclInformationLength
0x1400410f9  call    cs:__imp_GetAclInformation
0x1400410ff  test    eax, eax
0x140041101  jz      loc_140041202
0x140041107  movzx   eax, cs:?s_LocalAdmins_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
0x14004110e  sub     si, 4
0x140041112  movzx   ecx, cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x140041119  mov     r15d, dword ptr [rbp+4Fh+pAclInformation+4]
0x14004111d  movzx   edx, si
0x140041120  add     r15d, 0Ch
0x140041124  add     edx, eax
0x140041126  movzx   eax, cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x14004112d  add     edx, eax
0x14004112f  movzx   eax, cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x140041136  add     eax, [rbp+4Fh+var_48]
0x140041139  add     eax, edx
0x14004113b  add     ecx, eax
0x14004113d  add     r15d, ecx
0x140041140  mov     ecx, r15d; dwBytes
0x140041143  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041148  mov     rsi, rax
0x14004114b  test    rax, rax
0x14004114e  jz      loc_1400411F8
0x140041154  mov     r8d, dword ptr [rbp+4Fh+pAclInformation+4]
0x140041158  mov     rcx, rax; void *
0x14004115b  add     r8d, [rbp+4Fh+var_48]; Size
0x14004115f  mov     rdx, [rbp+4Fh+pAcl]; Src
0x140041163  call    memcpy_0
0x140041168  mov     [rsi+2], r15w
0x14004116d  jmp     loc_140041299
0x140041172  cmp     [rbp+4Fh+dwPrimaryGroupSize], ebx
0x140041175  jnz     loc_14004107A
0x14004117b  xor     r8d, r8d; bGroupDefaulted
0x14004117e  mov     rdx, rsi; pGroup
0x140041181  mov     rcx, r15; pSecurityDescriptor
0x140041184  call    cs:__imp_SetSecurityDescriptorGroup
0x14004118a  xor     r15d, r15d
0x14004118d  test    eax, eax
0x14004118f  jnz     loc_14004107D
0x140041195  mov     ebx, 8004100Ah
0x14004119a  jmp     loc_14004107D
0x14004119f  mov     ebx, 80041006h
0x1400411a4  jmp     loc_14004107A
0x1400411a9  mov     ebx, r12d
0x1400411ac  jmp     loc_14004107D
0x1400411b1  mov     edx, 1; dwRevision
0x1400411b6  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400411ba  call    cs:__imp_InitializeSecurityDescriptor
0x1400411c0  test    eax, eax
0x1400411c2  jz      short loc_1400411EC
0x1400411c4  xor     r8d, r8d; bOwnerDefaulted
0x1400411c7  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400411cb  mov     rdx, r14; pOwner
0x1400411ce  call    cs:__imp_SetSecurityDescriptorOwner
0x1400411d4  test    eax, eax
0x1400411d6  jz      short loc_1400411EC
0x1400411d8  xor     r8d, r8d; bGroupDefaulted
0x1400411db  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1400411df  mov     rdx, rsi; pGroup
0x1400411e2  call    cs:__imp_SetSecurityDescriptorGroup
0x1400411e8  test    eax, eax
0x1400411ea  jnz     short loc_1400411EF
0x1400411ec  mov     ebx, r12d
0x1400411ef  lea     r13, [rbp+4Fh+pSecurityDescriptor]
0x1400411f3  jmp     loc_14004107D
0x1400411f8  mov     ebx, 80041006h
0x1400411fd  jmp     loc_140041291
0x140041202  mov     rsi, r15
0x140041205  jmp     loc_14004128C
0x14004120a  mov     rcx, r14; pSid
0x14004120d  call    cs:__imp_GetLengthSid
0x140041213  movzx   r8d, cs:?s_LocalAdmins_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalAdmins_ACESize
0x14004121b  sub     ax, 4
0x14004121f  movzx   r15d, cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x140041227  movzx   ecx, ax
0x14004122a  movzx   eax, cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x140041231  add     r15d, ecx
0x140041234  add     r8d, eax
0x140041237  movzx   eax, cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x14004123e  add     eax, 14h
0x140041241  add     r15d, r8d
0x140041244  add     r15d, eax
0x140041247  mov     ecx, r15d; dwBytes
0x14004124a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004124f  mov     rsi, rax
0x140041252  test    rax, rax
0x140041255  jz      loc_1400413FD
0x14004125b  mov     r14d, 2
0x140041261  mov     edx, r15d; nAclLength
0x140041264  mov     r8d, r14d; dwAclRevision
0x140041267  mov     rcx, rax; pAcl
0x14004126a  call    cs:__imp_InitializeAcl
0x140041270  test    eax, eax
0x140041272  jz      short loc_14004128C
0x140041274  mov     r9d, r14d; dwAclInformationClass
0x140041277  lea     r8d, [r14+0Ah]; nAclInformationLength
0x14004127b  lea     rdx, [rbp+4Fh+pAclInformation]; pAclInformation
0x14004127f  mov     rcx, rsi; pAcl
0x140041282  call    cs:__imp_GetAclInformation
0x140041288  test    eax, eax
0x14004128a  jnz     short loc_140041291
0x14004128c  mov     ebx, 8004100Ah
0x140041291  test    ebx, ebx
0x140041293  js      loc_140041402
0x140041299  mov     r8d, dword ptr [rbp+4Fh+pAclInformation]; dwStartingAceIndex
0x14004129d  mov     r9, rdi; pAceList
0x1400412a0  mov     edx, r14d; dwAceRevision
0x1400412a3  mov     dword ptr [rsp+120h+lpdwDaclSize], r12d; nAceListLength
0x1400412a8  mov     rcx, rsi; pAcl
0x1400412ab  mov     r15, rsi
0x1400412ae  call    cs:__imp_AddAce
0x1400412b4  xor     r12d, r12d
0x1400412b7  test    eax, eax
0x1400412b9  jz      loc_1400413EC
0x1400412bf  movzx   eax, cs:?s_System_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_System_ACESize
0x1400412c6  test    ax, ax
0x1400412c9  jz      loc_1400413F3
0x1400412cf  mov     r9, cs:?s_Provider_System_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; pAceList
0x1400412d6  lea     r8d, [r12+1]; dwStartingAceIndex
0x1400412db  mov     edx, r14d; dwAceRevision
0x1400412de  mov     dword ptr [rsp+120h+lpdwDaclSize], eax; nAceListLength
0x1400412e2  mov     rcx, rsi; pAcl
0x1400412e5  call    cs:__imp_AddAce
0x1400412eb  test    eax, eax
0x1400412ed  jz      loc_1400413F3
0x1400412f3  movzx   eax, cs:?s_LocalService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_LocalService_ACESize
0x1400412fa  test    ax, ax
0x1400412fd  jz      loc_1400413EC
0x140041303  mov     r9, cs:?s_Provider_LocalService_ACE@ProviderSubSystem_Common_Globals@@2PEAU_ACCESS_ALLOWED_ACE@@EA; pAceList
0x14004130a  mov     r8d, r14d; dwStartingAceIndex
0x14004130d  mov     edx, r14d; dwAceRevision
0x140041310  mov     dword ptr [rsp+120h+lpdwDaclSize], eax; nAceListLength
0x140041314  mov     rcx, rsi; pAcl
0x140041317  call    cs:__imp_AddAce
0x14004131d  test    eax, eax
0x14004131f  jz      loc_1400413EC
0x140041325  movzx   eax, cs:?s_NetworkService_ACESize@ProviderSubSystem_Common_Globals@@2GA; ushort ProviderSubSystem_Common_Globals::s_NetworkService_ACESize
0x14004132c  test    ax, ax
0x14004132f  jz      loc_1400413EC
  ... truncated ...
```
