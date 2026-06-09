# OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute(void)

- ea: `0x18019bf50`
- end: `0x18019c5a2`
- name: `?Execute@RepairAclsOnRegistryTree@Internal@DEH@OSIntegration@@QEAAJXZ`
- size: `1618`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801373b0`

## callees

- `0x18005ded4`
- `0x180080cec`
- `0x180081254`
- `0x1800853cc`
- `0x18009aff4`
- `0x1800a9078`
- `0x1800bc4a0`
- `0x1800c5988`
- `0x1800c9ec8`
- `0x1800cfaac`
- `0x1800cfaf4`
- `0x18019bf50`
- `0x18019cf08`
- `0x1801e98a4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019bf7e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019bfcd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019bf7e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019bfcd`

## string_xrefs

- `0x18019c036`: `impersonateSelf.Impersonate()`
- `0x18019bf96`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c049`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c0b5`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c10d`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c181`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c1e6`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c264`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c2d3`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c35b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c3d4`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c461`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c4ed`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\repairaclsonregistrytree.cpp`
- `0x18019c2c0`: `restorePrivilege.Enable()`
- `0x18019c348`: `securityPrivilege.Initialize(SE_SECURITY_PRIVILEGE)`
- `0x18019c1d3`: `backupPrivilege.Enable()`
- `0x18019c251`: `restorePrivilege.Initialize(SE_RESTORE_PRIVILEGE)`
- `0x18019c0fa`: `ownershipNamePrivilege.Enable()`
- `0x18019c16e`: `backupPrivilege.Initialize(SE_BACKUP_PRIVILEGE)`
- `0x18019bfd7`: `ConvertStringSidToSid(TrustedInstallerSidString, &m_trustedInstallerSid)`
- `0x18019c0a2`: `ownershipNamePrivilege.Initialize(SE_TAKE_OWNERSHIP_PRIVILEGE)`
- `0x18019c4da`: `RepairAclsOnSubkeyTree(&rootKey, RootKeyPath, true)`
- `0x18019c3c1`: `securityPrivilege.Enable()`
- `0x18019c44e`: `rootKey.Open(HKEY_LOCAL_MACHINE, RootKeyPath, KEY_READ)`
- `0x18019bf8a`: `ConvertStringSidToSid(SystemSidString, &m_systemSid)`
- `0x18019bf9d`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c042`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c0ae`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c106`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c17a`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c1df`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c25d`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c2cc`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c354`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c3cd`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c45a`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019c4e6`: `OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute`
- `0x18019bfec`: `SOFTWARE\Classes\Extensions\ContractId`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute(PSID *Sid)
{
  const char *v2; // rax
  __int64 v3; // rdx
  const struct _tlgProvider_t *v5; // rax
  int v6; // r9d
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  char *v19; // [rsp+28h] [rbp-71h]
  int v20; // [rsp+30h] [rbp-69h] BYREF
  __int64 v21; // [rsp+38h] [rbp-61h]
  void *TokenHandle[2]; // [rsp+40h] [rbp-59h] BYREF
  char v23; // [rsp+50h] [rbp-49h]
  char v24; // [rsp+58h] [rbp-41h]
  __int64 v25; // [rsp+60h] [rbp-39h]
  void *v26[2]; // [rsp+68h] [rbp-31h] BYREF
  char v27; // [rsp+78h] [rbp-21h]
  char v28; // [rsp+80h] [rbp-19h]
  __int64 v29; // [rsp+88h] [rbp-11h]
  void *v30[2]; // [rsp+90h] [rbp-9h] BYREF
  char v31; // [rsp+A0h] [rbp+7h]
  char v32; // [rsp+A8h] [rbp+Fh]
  __int64 v33; // [rsp+B0h] [rbp+17h]
  void *v34[2]; // [rsp+B8h] [rbp+1Fh] BYREF
  char v35; // [rsp+C8h] [rbp+2Fh]
  char v36; // [rsp+D0h] [rbp+37h]
  __int64 v37; // [rsp+D8h] [rbp+3Fh]
  wil::details::in1diag5 *retaddr; // [rsp+F8h] [rbp+5Fh]
  HKEY phkResult; // [rsp+100h] [rbp+67h] BYREF
  const WCHAR *v40; // [rsp+108h] [rbp+6Fh] BYREF

  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    Sid,
    0);
  if ( !ConvertStringSidToSidW(L"S-1-5-18", Sid) )
  {
    v2 = "ConvertStringSidToSid(SystemSidString, &m_systemSid)";
    v3 = 215;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
             "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
             v2,
             v19);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    Sid + 1,
    0);
  if ( !ConvertStringSidToSidW(L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464", Sid + 1) )
  {
    v2 = "ConvertStringSidToSid(TrustedInstallerSidString, &m_trustedInstallerSid)";
    v3 = 216;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
             "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
             v2,
             v19);
  }
  v5 = AppXDEHTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u )
  {
    v40 = L"SOFTWARE\\Classes\\Extensions\\ContractId";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v5,
      (unsigned int)&word_1802B5F7E,
      0,
      v6,
      (__int64)&v40);
  }
  LOBYTE(v20) = 0;
  v21 = 0;
  v7 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)&v20);
  v8 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v19) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "impersonateSelf.Impersonate()",
      v19,
      v20);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  *(_OWORD *)TokenHandle = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v9 = Common::Deployment::Privilege::Initialize(TokenHandle, 9);
  v8 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v19) = v9;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "ownershipNamePrivilege.Initialize(SE_TAKE_OWNERSHIP_PRIVILEGE)",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  v10 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)TokenHandle);
  v8 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v19) = v10;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "ownershipNamePrivilege.Enable()",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v11 = Common::Deployment::Privilege::Initialize(v26, 17);
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v19) = v11;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "backupPrivilege.Initialize(SE_BACKUP_PRIVILEGE)",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  v12 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)v26);
  v8 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v19) = v12;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "backupPrivilege.Enable()",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v13 = Common::Deployment::Privilege::Initialize(v30, 18);
  v8 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v19) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "restorePrivilege.Initialize(SE_RESTORE_PRIVILEGE)",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  v14 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)v30);
  v8 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v19) = v14;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "restorePrivilege.Enable()",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v15 = Common::Deployment::Privilege::Initialize(v34, 8);
  v8 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v19) = v15;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "securityPrivilege.Initialize(SE_SECURITY_PRIVILEGE)",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v34);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  v16 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)v34);
  v8 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v19) = v16;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "securityPrivilege.Enable()",
      v19,
      v20);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v34);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  phkResult = 0;
  v17 = Common::RegistryKey::Open(
          &phkResult,
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Classes\\Extensions\\ContractId",
          0x20019u);
  v8 = v17;
  if ( v17 < 0 )
  {
    LODWORD(v19) = v17;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "rootKey.Open(HKEY_LOCAL_MACHINE, RootKeyPath, KEY_READ)",
      v19,
      v20);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v34);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  v18 = OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::RepairAclsOnSubkeyTree(
          (OSIntegration::DEH::Internal::RepairAclsOnRegistryTree *)Sid,
          (struct Common::RegistryKey *)&phkResult,
          L"SOFTWARE\\Classes\\Extensions\\ContractId",
          1);
  v8 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v19) = v18;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\repairaclsonregistrytree.cpp",
      "OSIntegration::DEH::Internal::RepairAclsOnRegistryTree::Execute",
      "RepairAclsOnSubkeyTree(&rootKey, RootKeyPath, true)",
      v19,
      v20);
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v34);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v20 )
      Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
    return v8;
  }
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v34);
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v30);
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v26);
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
  if ( (_BYTE)v20 )
    Common::ImpersonateSelf::Revert((Common::ImpersonateSelf *)&v20);
  return 0;
}

```

## disassembly

```asm
0x18019bf50  mov     [rsp-8+arg_10], rbx
0x18019bf55  mov     [rsp-8+arg_18], rsi
0x18019bf5a  push    rbp
0x18019bf5b  push    rdi
0x18019bf5c  push    r14
0x18019bf5e  lea     rbp, [rsp-47h]
0x18019bf63  sub     rsp, 0E0h
0x18019bf6a  mov     rdi, rcx
0x18019bf6d  xor     edx, edx
0x18019bf6f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18019bf74  mov     rdx, rdi; Sid
0x18019bf77  lea     rcx, aS1518; "S-1-5-18"
0x18019bf7e  call    cs:__imp_ConvertStringSidToSidW
0x18019bf84  xor     esi, esi
0x18019bf86  test    eax, eax
0x18019bf88  jnz     short loc_18019BFB7
0x18019bf8a  lea     rax, aConvertstrings_4; "ConvertStringSidToSid(SystemSidString, "...
0x18019bf91  mov     edx, 0D7h; void *
0x18019bf96  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019bf9d  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019bfa4  mov     [rsp+0F0h+var_D0], rax; char *
0x18019bfa9  mov     rcx, [rbp+5Fh]; this
0x18019bfad  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x18019bfb2  jmp     loc_18019C58A
0x18019bfb7  xor     edx, edx
0x18019bfb9  lea     rcx, [rdi+8]
0x18019bfbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18019bfc2  lea     rdx, [rdi+8]; Sid
0x18019bfc6  lea     rcx, aS1580956008885; "S-1-5-80-956008885-3418522649-183103804"...
0x18019bfcd  call    cs:__imp_ConvertStringSidToSidW
0x18019bfd3  test    eax, eax
0x18019bfd5  jnz     short loc_18019BFE5
0x18019bfd7  lea     rax, aConvertstrings_0; "ConvertStringSidToSid(TrustedInstallerS"...
0x18019bfde  mov     edx, 0D8h
0x18019bfe3  jmp     short loc_18019BF96
0x18019bfe5  call    ?Provider@AppXDEHTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDEHTelemetry::Provider(void)
0x18019bfea  mov     ecx, [rax]
0x18019bfec  lea     r14, aSoftwareClasse_2; "SOFTWARE\\Classes\\Extensions\\Contract"...
0x18019bff3  cmp     ecx, 5
0x18019bff6  jbe     short loc_18019C017
0x18019bff8  mov     [rbp+57h+arg_8], r14
0x18019bffc  lea     rcx, [rbp+57h+arg_8]
0x18019c000  mov     [rsp+0F0h+var_D0], rcx
0x18019c005  xor     r8d, r8d
0x18019c008  lea     rdx, word_1802B5F7E
0x18019c00f  mov     rcx, rax
0x18019c012  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18019c017  mov     byte ptr [rbp+57h+var_C0], sil
0x18019c01b  mov     [rbp+57h+var_B8], rsi
0x18019c01f  lea     rcx, [rbp+57h+var_C0]; this
0x18019c023  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x18019c028  mov     ebx, eax
0x18019c02a  test    eax, eax
0x18019c02c  jns     short loc_18019C072
0x18019c02e  mov     rcx, [rbp+5Fh]; this
0x18019c032  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c036  lea     rax, aImpersonatesel; "impersonateSelf.Impersonate()"
0x18019c03d  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c042  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c049  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c050  mov     edx, 0E0h; void *
0x18019c055  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c05a  nop
0x18019c05b  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c05f  jz      short loc_18019C06B
0x18019c061  lea     rcx, [rbp+57h+var_C0]; this
0x18019c065  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c06a  nop
0x18019c06b  mov     eax, ebx
0x18019c06d  jmp     loc_18019C58A
0x18019c072  xorps   xmm0, xmm0
0x18019c075  movdqu  xmmword ptr [rbp+57h+TokenHandle], xmm0
0x18019c07a  mov     [rbp+57h+var_A0], sil
0x18019c07e  mov     [rbp+57h+var_98], sil
0x18019c082  mov     [rbp+57h+var_90], rsi
0x18019c086  mov     edx, 9; int
0x18019c08b  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18019c08f  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18019c094  mov     ebx, eax
0x18019c096  test    eax, eax
0x18019c098  jns     short loc_18019C0E3
0x18019c09a  mov     rcx, [rbp+5Fh]; this
0x18019c09e  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c0a2  lea     rax, aOwnershipnamep; "ownershipNamePrivilege.Initialize(SE_TA"...
0x18019c0a9  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c0ae  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c0b5  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c0bc  mov     edx, 0E3h; void *
0x18019c0c1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c0c6  nop
0x18019c0c7  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c0cb  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c0d0  nop
0x18019c0d1  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c0d5  jz      short loc_18019C0E1
0x18019c0d7  lea     rcx, [rbp+57h+var_C0]; this
0x18019c0db  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c0e0  nop
0x18019c0e1  jmp     short loc_18019C06B
0x18019c0e3  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c0e7  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18019c0ec  mov     ebx, eax
0x18019c0ee  test    eax, eax
0x18019c0f0  jns     short loc_18019C13E
0x18019c0f2  mov     rcx, [rbp+5Fh]; this
0x18019c0f6  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c0fa  lea     rax, aOwnershipnamep_0; "ownershipNamePrivilege.Enable()"
0x18019c101  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c106  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c10d  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c114  mov     edx, 0E4h; void *
0x18019c119  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c11e  nop
0x18019c11f  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c123  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c128  nop
0x18019c129  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c12d  jz      short loc_18019C139
0x18019c12f  lea     rcx, [rbp+57h+var_C0]; this
0x18019c133  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c138  nop
0x18019c139  jmp     loc_18019C06B
0x18019c13e  xorps   xmm0, xmm0
0x18019c141  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18019c146  mov     [rbp+57h+var_78], sil
0x18019c14a  mov     [rbp+57h+var_70], sil
0x18019c14e  mov     [rbp+57h+var_68], rsi
0x18019c152  mov     edx, 11h; int
0x18019c157  lea     rcx, [rbp+57h+var_88]; TokenHandle
0x18019c15b  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18019c160  mov     ebx, eax
0x18019c162  test    eax, eax
0x18019c164  jns     short loc_18019C1BC
0x18019c166  mov     rcx, [rbp+5Fh]; this
0x18019c16a  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c16e  lea     rax, aBackupprivileg_0; "backupPrivilege.Initialize(SE_BACKUP_PR"...
0x18019c175  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c17a  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c181  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c188  mov     edx, 0E7h; void *
0x18019c18d  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c192  nop
0x18019c193  lea     rcx, [rbp+57h+var_88]; this
0x18019c197  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c19c  nop
0x18019c19d  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c1a1  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c1a6  nop
0x18019c1a7  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c1ab  jz      short loc_18019C1B7
0x18019c1ad  lea     rcx, [rbp+57h+var_C0]; this
0x18019c1b1  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c1b6  nop
0x18019c1b7  jmp     loc_18019C06B
0x18019c1bc  lea     rcx, [rbp+57h+var_88]; this
0x18019c1c0  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18019c1c5  mov     ebx, eax
0x18019c1c7  test    eax, eax
0x18019c1c9  jns     short loc_18019C221
0x18019c1cb  mov     rcx, [rbp+5Fh]; this
0x18019c1cf  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c1d3  lea     rax, aBackupprivileg; "backupPrivilege.Enable()"
0x18019c1da  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c1df  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c1e6  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c1ed  mov     edx, 0E8h; void *
0x18019c1f2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c1f7  nop
0x18019c1f8  lea     rcx, [rbp+57h+var_88]; this
0x18019c1fc  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c201  nop
0x18019c202  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c206  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c20b  nop
0x18019c20c  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c210  jz      short loc_18019C21C
0x18019c212  lea     rcx, [rbp+57h+var_C0]; this
0x18019c216  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c21b  nop
0x18019c21c  jmp     loc_18019C06B
0x18019c221  xorps   xmm0, xmm0
0x18019c224  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18019c229  mov     [rbp+57h+var_50], sil
0x18019c22d  mov     [rbp+57h+var_48], sil
0x18019c231  mov     [rbp+57h+var_40], rsi
0x18019c235  mov     edx, 12h; int
0x18019c23a  lea     rcx, [rbp+57h+var_60]; TokenHandle
0x18019c23e  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18019c243  mov     ebx, eax
0x18019c245  test    eax, eax
0x18019c247  jns     short loc_18019C2A9
0x18019c249  mov     rcx, [rbp+5Fh]; this
0x18019c24d  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c251  lea     rax, aRestoreprivile_0; "restorePrivilege.Initialize(SE_RESTORE_"...
0x18019c258  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c25d  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c264  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c26b  mov     edx, 0EBh; void *
0x18019c270  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c275  nop
0x18019c276  lea     rcx, [rbp+57h+var_60]; this
0x18019c27a  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c27f  nop
0x18019c280  lea     rcx, [rbp+57h+var_88]; this
0x18019c284  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c289  nop
0x18019c28a  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c28e  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c293  nop
0x18019c294  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c298  jz      short loc_18019C2A4
0x18019c29a  lea     rcx, [rbp+57h+var_C0]; this
0x18019c29e  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c2a3  nop
0x18019c2a4  jmp     loc_18019C06B
0x18019c2a9  lea     rcx, [rbp+57h+var_60]; this
0x18019c2ad  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18019c2b2  mov     ebx, eax
0x18019c2b4  test    eax, eax
0x18019c2b6  jns     short loc_18019C318
0x18019c2b8  mov     rcx, [rbp+5Fh]; this
0x18019c2bc  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c2c0  lea     rax, aRestoreprivile; "restorePrivilege.Enable()"
0x18019c2c7  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c2cc  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c2d3  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c2da  mov     edx, 0ECh; void *
0x18019c2df  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c2e4  nop
0x18019c2e5  lea     rcx, [rbp+57h+var_60]; this
0x18019c2e9  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c2ee  nop
0x18019c2ef  lea     rcx, [rbp+57h+var_88]; this
0x18019c2f3  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c2f8  nop
0x18019c2f9  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c2fd  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c302  nop
0x18019c303  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c307  jz      short loc_18019C313
0x18019c309  lea     rcx, [rbp+57h+var_C0]; this
0x18019c30d  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c312  nop
0x18019c313  jmp     loc_18019C06B
0x18019c318  xorps   xmm0, xmm0
0x18019c31b  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18019c320  mov     [rbp+57h+var_28], sil
0x18019c324  mov     [rbp+57h+var_20], sil
0x18019c328  mov     [rbp+57h+var_18], rsi
0x18019c32c  mov     edx, 8; int
0x18019c331  lea     rcx, [rbp+57h+var_38]; TokenHandle
0x18019c335  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18019c33a  mov     ebx, eax
0x18019c33c  test    eax, eax
0x18019c33e  jns     short loc_18019C3AA
0x18019c340  mov     rcx, [rbp+5Fh]; this
0x18019c344  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c348  lea     rax, aSecurityprivil; "securityPrivilege.Initialize(SE_SECURIT"...
0x18019c34f  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c354  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c35b  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c362  mov     edx, 0EFh; void *
0x18019c367  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c36c  nop
0x18019c36d  lea     rcx, [rbp+57h+var_38]; this
0x18019c371  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c376  nop
0x18019c377  lea     rcx, [rbp+57h+var_60]; this
0x18019c37b  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c380  nop
0x18019c381  lea     rcx, [rbp+57h+var_88]; this
0x18019c385  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c38a  nop
0x18019c38b  lea     rcx, [rbp+57h+TokenHandle]; this
0x18019c38f  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c394  nop
0x18019c395  cmp     byte ptr [rbp+57h+var_C0], sil
0x18019c399  jz      short loc_18019C3A5
0x18019c39b  lea     rcx, [rbp+57h+var_C0]; this
0x18019c39f  call    ?Revert@ImpersonateSelf@Common@@QEAAXXZ; Common::ImpersonateSelf::Revert(void)
0x18019c3a4  nop
0x18019c3a5  jmp     loc_18019C06B
0x18019c3aa  lea     rcx, [rbp+57h+var_38]; this
0x18019c3ae  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18019c3b3  mov     ebx, eax
0x18019c3b5  test    eax, eax
0x18019c3b7  jns     short loc_18019C423
0x18019c3b9  mov     rcx, [rbp+5Fh]; this
0x18019c3bd  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18019c3c1  lea     rax, aSecurityprivil_0; "securityPrivilege.Enable()"
0x18019c3c8  mov     [rsp+0F0h+var_D0], rax; char *
0x18019c3cd  lea     r9, aOsintegrationD_219; "OSIntegration::DEH::Internal::RepairAcl"...
0x18019c3d4  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18019c3db  mov     edx, 0F0h; void *
0x18019c3e0  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18019c3e5  nop
0x18019c3e6  lea     rcx, [rbp+57h+var_38]; this
0x18019c3ea  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18019c3ef  nop
0x18019c3f0  lea     rcx, [rbp+57h+var_60]; this
  ... truncated ...
```
