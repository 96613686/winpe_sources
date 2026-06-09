# OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey(ushort const *,bool)

- ea: `0x18019c668`
- end: `0x18019c8c8`
- name: `?RepairAclsOnKey@RepairAclsOnRegistryTree@Internal@DEH@OSIntegration@@AEAAJPEBG_N@Z`
- size: `608`
- prototype: `__int64 __fastcall(PSID *this, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18019c8d0`

## callees

- `0x18000e6e0`
- `0x180091cac`
- `0x18009aff4`
- `0x1800c9ec8`
- `0x18019bc80`
- `0x18019c668`
- `0x18019cfe8`
- `0x18019d020`

## import_xrefs

- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18019c6ee`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18019c6ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18019c69f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18019c69f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c7a4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c813`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c868`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c7a4`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c813`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18019c868`

## string_xrefs

- `0x18019c750`: `Common::PathHelpers::CombinePaths(L"MACHINE", keyPath, &keyPathBuffer)`
- `0x18019c700`: `RtlGetDaclSecurityDescriptor(securityDescriptor.get(), &daclPresent, &dacl, &daclDefaulted)`
- `0x18019c6b9`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey`
- `0x18019c70c`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey`
- `0x18019c75c`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey`
- `0x18019c7da`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey`
- `0x18019c6c0`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c763`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c7e1`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c6ad`: `ConvertStringSecurityDescriptorToSecurityDescriptor(sddl, SDDL_REVISION_1, &securityDescriptor, nullptr)`
- `0x18019c836`: `SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, DACL_SECURITY_INFORMATION | PROTECTED_DACL_SECURITY_INFORMATION, nullptr, nullptr, dacl, nullptr)`
- `0x18019c88b`: `SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, OWNER_SECURITY_INFORMATION, m_trustedInstallerSid.get(), nullptr, nullptr, nullptr)`
- `0x18019c7c7`: `SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, OWNER_SECURITY_INFORMATION, m_systemSid.get(), nullptr, nullptr, nullptr)`
- `0x18019c826`: `Failed to set dacl on key %ls`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey(
        PSID *this,
        const unsigned __int16 *a2,
        char a3)
{
  unsigned int LastError; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  int v10; // eax
  DWORD v11; // eax
  unsigned int v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  PACL pDacl; // [rsp+28h] [rbp-48h]
  wil::details *pDacla; // [rsp+28h] [rbp-48h]
  wil::details *pDaclb; // [rsp+28h] [rbp-48h]
  wil::details *pDaclc; // [rsp+28h] [rbp-48h]
  int pSacl; // [rsp+30h] [rbp-40h]
  unsigned __int8 DaclPresent[8]; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-28h] BYREF
  PACL Dacl; // [rsp+50h] [rbp-20h] BYREF
  LPWSTR pObjectName[2]; // [rsp+58h] [rbp-18h] BYREF
  int v25; // [rsp+68h] [rbp-8h]
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned __int8 DaclDefaulted; // [rsp+A8h] [rbp+38h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:P(A;CI;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;CI;GA;;;SY)(A;CI;GR;;;"
           "BA)(A;CI;GR;;;BU)(A;CI;GR;;;S-1-15-2-1)(A;CI;GR;;;S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-4"
           "32734479-3232135806-4053264122-3456934681)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0x1C,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
                  "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
                  "ConvertStringSecurityDescriptorToSecurityDescriptor(sddl, SDDL_REVISION_1, &securityDescriptor, nullptr)",
                  (const char *)pDacl);
LABEL_5:
    v9 = LastError;
    goto LABEL_18;
  }
  Dacl = 0;
  DaclPresent[0] = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    LODWORD(pDacl) = DaclSecurityDescriptor;
    LastError = wil::details::in1diag5::Return_NtStatus(
                  retaddr,
                  (void *)0x21,
                  v8,
                  "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
                  "RtlGetDaclSecurityDescriptor(securityDescriptor.get(), &daclPresent, &dacl, &daclDefaulted)",
                  (wil::details *)pDacl,
                  pSacl);
    goto LABEL_5;
  }
  *(_OWORD *)pObjectName = 0;
  v25 = 0;
  v10 = Common::PathHelpers::CombinePaths(L"MACHINE", a2, (struct Common::StringBuffer *)pObjectName);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v11 = SetNamedSecurityInfoW(pObjectName[1], SE_REGISTRY_KEY, 1u, *this, 0, 0, 0);
    if ( v11 )
    {
      LODWORD(pDacla) = v11;
      v12 = wil::details::in1diag5::Return_Win32Msg(
              retaddr,
              (void *)0x29,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
              "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
              "SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, OWNER_SECURITY_INFORMATION, m_systemSid.ge"
              "t(), nullptr, nullptr, nullptr)",
              pDacla,
              (unsigned int)"Failed to set owner on key %ls",
              (const char *)pObjectName[1]);
    }
    else
    {
      v13 = SetNamedSecurityInfoW(pObjectName[1], SE_REGISTRY_KEY, 0x80000004, 0, 0, Dacl, 0);
      if ( v13 )
      {
        LODWORD(pDaclb) = v13;
        v12 = wil::details::in1diag5::Return_Win32Msg(
                retaddr,
                (void *)0x2D,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
                "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
                "SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, DACL_SECURITY_INFORMATION | PROTECTED_DA"
                "CL_SECURITY_INFORMATION, nullptr, nullptr, dacl, nullptr)",
                pDaclb,
                (unsigned int)"Failed to set dacl on key %ls",
                (const char *)pObjectName[1]);
      }
      else
      {
        if ( !a3 || (v14 = SetNamedSecurityInfoW(pObjectName[1], SE_REGISTRY_KEY, 1u, this[1], 0, 0, 0)) == 0 )
        {
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pObjectName);
          v9 = 0;
          goto LABEL_18;
        }
        LODWORD(pDaclc) = v14;
        v12 = wil::details::in1diag5::Return_Win32Msg(
                retaddr,
                (void *)0x33,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
                "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
                "SetNamedSecurityInfo(keyPathBuffer.GetChars(), SE_REGISTRY_KEY, OWNER_SECURITY_INFORMATION, m_trustedIns"
                "tallerSid.get(), nullptr, nullptr, nullptr)",
                pDaclc,
                (unsigned int)"Failed to set owner on key %ls",
                (const char *)pObjectName[1]);
      }
    }
    v9 = v12;
  }
  else
  {
    LODWORD(pDacl) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnKey",
      "Common::PathHelpers::CombinePaths(L\"MACHINE\", keyPath, &keyPathBuffer)",
      (const char *)pDacl,
      pSacl);
  }
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pObjectName);
LABEL_18:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  return v9;
}

```

## disassembly

```asm
0x18019c668  mov     [rsp-18h+arg_0], rbx
0x18019c66d  mov     [rsp-18h+arg_8], rsi
0x18019c672  push    rbp
0x18019c673  push    rdi
0x18019c674  push    r14
0x18019c676  mov     rbp, rsp
0x18019c679  sub     rsp, 70h
0x18019c67d  mov     sil, r8b
0x18019c680  mov     rbx, rdx
0x18019c683  mov     rdi, rcx
0x18019c686  xor     r14d, r14d
0x18019c689  mov     [rbp+SecurityDescriptor], r14
0x18019c68d  xor     r9d, r9d; SecurityDescriptorSize
0x18019c690  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18019c694  lea     edx, [r14+1]; StringSDRevision
0x18019c698  lea     rcx, aOSygSydPACiGaS; "O:SYG:SYD:P(A;CI;GA;;;S-1-5-80-95600888"...
0x18019c69f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18019c6a5  test    eax, eax
0x18019c6a7  jnz     short loc_18019C6D2
0x18019c6a9  mov     rcx, [rbp+18h]; this
0x18019c6ad  lea     rax, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x18019c6b4  mov     [rsp+70h+psidGroup], rax; char *
0x18019c6b9  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c6c0  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c6c7  lea     edx, [r14+1Ch]; void *
0x18019c6cb  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x18019c6d0  jmp     short loc_18019C71D
0x18019c6d2  mov     [rbp+Dacl], r14
0x18019c6d6  mov     [rbp+DaclPresent], r14b
0x18019c6da  mov     [rbp+DaclDefaulted], r14b
0x18019c6de  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x18019c6e2  lea     r8, [rbp+Dacl]; Dacl
0x18019c6e6  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18019c6ea  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18019c6ee  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18019c6f4  test    eax, eax
0x18019c6f6  jns     short loc_18019C724
0x18019c6f8  mov     rcx, [rbp+18h]; this
0x18019c6fc  mov     dword ptr [rsp+70h+pDacl], eax; wil::details *
0x18019c700  lea     rax, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor(securityDe"...
0x18019c707  mov     [rsp+70h+psidGroup], rax; char *
0x18019c70c  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c713  mov     edx, 21h ; '!'; void *
0x18019c718  call    ?Return_NtStatus@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Return_NtStatus(void *,uint,char const *,char const *,char const *,long)
0x18019c71d  mov     ebx, eax
0x18019c71f  jmp     loc_18019C8A8
0x18019c724  xorps   xmm0, xmm0
0x18019c727  movups  xmmword ptr [rbp+pObjectName], xmm0
0x18019c72b  mov     [rbp+var_8], r14d
0x18019c72f  lea     r8, [rbp+pObjectName]; struct Common::StringBuffer *
0x18019c733  mov     rdx, rbx; unsigned __int16 *
0x18019c736  lea     rcx, aMachine_0; "MACHINE"
0x18019c73d  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18019c742  mov     ebx, eax
0x18019c744  test    eax, eax
0x18019c746  jns     short loc_18019C783
0x18019c748  mov     rcx, [rbp+18h]; this
0x18019c74c  mov     dword ptr [rsp+70h+pDacl], eax; char *
0x18019c750  lea     rax, aCommonPathhelp_0; "Common::PathHelpers::CombinePaths(L\"MA"...
0x18019c757  mov     [rsp+70h+psidGroup], rax; char *
0x18019c75c  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c763  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c76a  mov     edx, 25h ; '%'; void *
0x18019c76f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c774  nop
0x18019c775  lea     rcx, [rbp+pObjectName]; this
0x18019c779  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18019c77e  jmp     loc_18019C8A8
0x18019c783  mov     [rsp+70h+pSacl], r14; pSacl
0x18019c788  mov     [rsp+70h+pDacl], r14; pDacl
0x18019c78d  mov     [rsp+70h+psidGroup], r14; psidGroup
0x18019c792  mov     r9, [rdi]; psidOwner
0x18019c795  mov     ebx, 4
0x18019c79a  lea     r8d, [rbx-3]; SecurityInfo
0x18019c79e  mov     edx, ebx; ObjectType
0x18019c7a0  mov     rcx, [rbp+pObjectName+8]; pObjectName
0x18019c7a4  call    cs:__imp_SetNamedSecurityInfoW
0x18019c7aa  test    eax, eax
0x18019c7ac  jz      short loc_18019C7F1
0x18019c7ae  mov     rdx, [rbp+pObjectName+8]
0x18019c7b2  mov     [rsp+70h+var_38], rdx; char *
0x18019c7b7  lea     rdx, aFailedToSetOwn; "Failed to set owner on key %ls"
0x18019c7be  mov     [rsp+70h+pSacl], rdx; unsigned int
0x18019c7c3  mov     dword ptr [rsp+70h+pDacl], eax; wil::details *
0x18019c7c7  lea     rax, aSetnamedsecuri_1; "SetNamedSecurityInfo(keyPathBuffer.GetC"...
0x18019c7ce  lea     edx, [rbx+25h]; void *
0x18019c7d1  mov     rcx, [rbp+18h]; this
0x18019c7d5  mov     [rsp+70h+psidGroup], rax; char *
0x18019c7da  lea     r9, aOsintegrationD_194; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c7e1  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c7e8  call    ?Return_Win32Msg@in1diag5@details@wil@@YAJPEAXIPEBD11K1ZZ; wil::details::in1diag5::Return_Win32Msg(void *,uint,char const *,char const *,char const *,ulong,char const *,...)
0x18019c7ed  mov     ebx, eax
0x18019c7ef  jmp     short loc_18019C775
0x18019c7f1  mov     rax, [rbp+Dacl]
0x18019c7f5  mov     [rsp+70h+pSacl], r14; pSacl
0x18019c7fa  mov     [rsp+70h+pDacl], rax; pDacl
0x18019c7ff  mov     [rsp+70h+psidGroup], r14; psidGroup
0x18019c804  xor     r9d, r9d; psidOwner
0x18019c807  mov     r8d, 80000004h; SecurityInfo
0x18019c80d  mov     edx, ebx; ObjectType
0x18019c80f  mov     rcx, [rbp+pObjectName+8]; pObjectName
0x18019c813  call    cs:__imp_SetNamedSecurityInfoW
0x18019c819  test    eax, eax
0x18019c81b  jz      short loc_18019C844
0x18019c81d  mov     rdx, [rbp+pObjectName+8]
0x18019c821  mov     [rsp+70h+var_38], rdx
0x18019c826  lea     rdx, aFailedToSetDac; "Failed to set dacl on key %ls"
0x18019c82d  mov     [rsp+70h+pSacl], rdx
0x18019c832  mov     dword ptr [rsp+70h+pDacl], eax
0x18019c836  lea     rax, aSetnamedsecuri_2; "SetNamedSecurityInfo(keyPathBuffer.GetC"...
0x18019c83d  mov     edx, 2Dh ; '-'
0x18019c842  jmp     short loc_18019C7D1
0x18019c844  test    sil, sil
0x18019c847  jz      short loc_18019C89C
0x18019c849  mov     [rsp+70h+pSacl], r14; pSacl
0x18019c84e  mov     [rsp+70h+pDacl], r14; pDacl
0x18019c853  mov     [rsp+70h+psidGroup], r14; psidGroup
0x18019c858  mov     r9, [rdi+8]; psidOwner
0x18019c85c  mov     r8d, 1; SecurityInfo
0x18019c862  mov     edx, ebx; ObjectType
0x18019c864  mov     rcx, [rbp+pObjectName+8]; pObjectName
0x18019c868  call    cs:__imp_SetNamedSecurityInfoW
0x18019c86e  test    eax, eax
0x18019c870  jz      short loc_18019C89C
0x18019c872  mov     rdx, [rbp+pObjectName+8]
0x18019c876  mov     [rsp+70h+var_38], rdx
0x18019c87b  lea     rdx, aFailedToSetOwn; "Failed to set owner on key %ls"
0x18019c882  mov     [rsp+70h+pSacl], rdx
0x18019c887  mov     dword ptr [rsp+70h+pDacl], eax
0x18019c88b  lea     rax, aSetnamedsecuri; "SetNamedSecurityInfo(keyPathBuffer.GetC"...
0x18019c892  mov     edx, 33h ; '3'
0x18019c897  jmp     loc_18019C7D1
0x18019c89c  lea     rcx, [rbp+pObjectName]; this
0x18019c8a0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18019c8a5  mov     ebx, r14d
0x18019c8a8  lea     rcx, [rbp+SecurityDescriptor]
0x18019c8ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18019c8b1  mov     eax, ebx
0x18019c8b3  lea     r11, [rsp+70h+var_s0]
0x18019c8b8  mov     rbx, [r11+20h]
0x18019c8bc  mov     rsi, [r11+28h]
0x18019c8c0  mov     rsp, r11
0x18019c8c3  pop     r14
0x18019c8c5  pop     rdi
0x18019c8c6  pop     rbp
0x18019c8c7  retn
```
