# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(int)

- ea: `0x18004db50`
- end: `0x18004e0d7`
- name: `?RemovePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z`
- size: `1415`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044bb0`
- `0x180051c10`
- `0x18005294c`
- `0x180052b48`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x180048920`
- `0x180048dec`
- `0x18004db50`
- `0x1800515f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004de36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dfc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e09a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dc2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004de36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dfc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e09a`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004de7e`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004de7e`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004dd77`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004dfec`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004e05b`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004dd77`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004dfec`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004e05b`

## string_xrefs

- `0x18004dbc3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004dc48`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004dbfa`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004dc4f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004deeb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004df93`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004dbf3`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage`
- `0x18004dbaf`: `Ignoring attempt to offline deprovision framework %s provisioned by itself`
- `0x18004dcae`: `Failed to remove related packages`
- `0x18004dd3d`: `Failed to remove related packages`
- `0x18004dc7f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        __int64 a2)
{
  int v2; // r14d
  unsigned int v4; // r13d
  int v5; // eax
  void *v6; // rbx
  int v7; // eax
  bool v8; // zf
  __int64 v9; // rcx
  int v10; // eax
  unsigned int DependencyPackages; // ebx
  int v12; // eax
  int v13; // eax
  const unsigned __int16 **v14; // rbx
  const unsigned __int16 *v15; // rdx
  __int64 v17; // r8
  int v18; // r15d
  int v19; // eax
  void *v20; // rbx
  int v21; // eax
  struct AppxAllUserStore::_PackageInfo *v22; // rdx
  const unsigned __int16 *v23; // r12
  int v24; // eax
  void *v25; // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  bool v29; // zf
  int v30; // [rsp+20h] [rbp-40h]
  __int64 v31; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+38h] [rbp-28h]
  struct AppxAllUserStore::_PackageInfo **v33; // [rsp+40h] [rbp-20h]
  unsigned int *v34; // [rsp+48h] [rbp-18h]
  char v35; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v37; // [rsp+A0h] [rbp+40h] BYREF
  struct AppxAllUserStore::_PackageInfo *v38; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+58h] BYREF

  v2 = a2;
  v4 = 0;
  v37 = 0;
  v38 = 0;
  v33 = &v38;
  v34 = &v37;
  v35 = 1;
  if ( *((_DWORD *)this + 67) )
  {
    pv = 0;
    v5 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           &pv,
           L"Ignoring attempt to offline deprovision framework %s provisioned by itself");
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x59C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v5,
        v30);
    v6 = pv;
    v7 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
           L"MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage",
           1444);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5A4,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v7,
        2);
    if ( v6 )
      CoTaskMemFree(v6);
    v8 = v38 == 0;
    goto LABEL_58;
  }
  v9 = *((_QWORD *)this + 27);
  if ( v9 )
  {
    v31 = v9;
    v32 = a2;
    v10 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___(
            v9,
            a2,
            &v31);
    DependencyPackages = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v10,
        v30);
      if ( !v2 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5AE,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)DependencyPackages,
          (int)"%ws",
          L"Failed to remove related packages");
LABEL_21:
        if ( v38 )
          DeleteAllPackagesFromPackageArray(v37);
        return DependencyPackages;
      }
      v30 = 1;
      v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              L"Failed to remove related packages",
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              0,
              1454);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5AE,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v12,
          1);
    }
  }
  DependencyPackages = MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(
                         this,
                         v2,
                         &v38,
                         &v37);
  if ( (DependencyPackages & 0x80000000) == 0 )
    goto LABEL_18;
  if ( !v2 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5B5,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)DependencyPackages,
      (int)"%ws",
      (const char *)L"Failed to deregister main package and get its dependent packages");
    goto LABEL_21;
  }
  v30 = 1;
  v13 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
          L"Failed to deregister main package and get its dependent packages",
          L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          0,
          1461);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B5,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v13,
      1);
LABEL_18:
  v14 = (const unsigned __int16 **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) < 8u )
    v15 = (const unsigned __int16 *)((char *)this + 48);
  else
    v15 = *v14;
  v18 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(this, v15);
  if ( v18 < 0 )
  {
    pv = 0;
    if ( *((_QWORD *)this + 9) >= 8u )
      v14 = (const unsigned __int16 **)*v14;
    v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            L"Failed to destage package'%s'",
            v14);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v19,
        v30);
    v20 = pv;
    if ( !v2 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18,
        (int)"%ws",
        (const char *)pv);
      if ( v20 )
        CoTaskMemFree(v20);
      v29 = v38 == 0;
      goto LABEL_64;
    }
    v30 = 1;
    v21 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1467);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v21,
        1);
    if ( v20 )
      CoTaskMemFree(v20);
  }
  v22 = v38;
  if ( !v38 || !v37 )
  {
LABEL_57:
    v8 = v22 == 0;
LABEL_58:
    if ( !v8 )
      DeleteAllPackagesFromPackageArray(v37);
    return 0;
  }
  while ( 1 )
  {
    v23 = (const unsigned __int16 *)*((_QWORD *)v22 + 3 * v4);
    if ( v23 )
      break;
LABEL_56:
    if ( ++v4 >= v37 )
      goto LABEL_57;
  }
  LOBYTE(v17) = 1;
  v18 = RemoveStagedPackageFromRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), *((_QWORD *)v22 + 3 * v4), v17);
  if ( v18 < 0 )
  {
    pv = 0;
    v24 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            L"Failed to deregister staged package'%s'",
            v23);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v24,
        v30);
    v25 = pv;
    if ( !v2 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5CB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18,
        (int)"%ws",
        (const char *)pv);
      goto LABEL_68;
    }
    v30 = 1;
    v26 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1483);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v26,
        1);
    if ( v25 )
      CoTaskMemFree(v25);
  }
  v18 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(this, v23);
  if ( v18 >= 0 )
  {
LABEL_55:
    v22 = v38;
    goto LABEL_56;
  }
  pv = 0;
  v27 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          L"Failed to destage package'%s'",
          v23);
  if ( v27 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5D1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v27,
      v30);
  v25 = pv;
  if ( v2 )
  {
    v30 = 1;
    v28 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1489);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D1,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v28,
        1);
    if ( v25 )
      CoTaskMemFree(v25);
    goto LABEL_55;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x5D1,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v18,
    (int)"%ws",
    (const char *)pv);
LABEL_68:
  if ( v25 )
    CoTaskMemFree(v25);
  v29 = v38 == 0;
LABEL_64:
  if ( !v29 )
    DeleteAllPackagesFromPackageArray(v37);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18004db50  mov     [rsp-38h+arg_8], rbx
0x18004db55  push    rbp
0x18004db56  push    rsi
0x18004db57  push    rdi
0x18004db58  push    r12
0x18004db5a  push    r13
0x18004db5c  push    r14
0x18004db5e  push    r15
0x18004db60  mov     rbp, rsp
0x18004db63  sub     rsp, 60h
0x18004db67  mov     r14d, edx
0x18004db6a  mov     rsi, rcx
0x18004db6d  xor     r13d, r13d
0x18004db70  mov     [rbp+arg_0], r13d
0x18004db74  mov     [rbp+arg_10], r13
0x18004db78  lea     rax, [rbp+arg_10]
0x18004db7c  mov     [rbp+var_20], rax
0x18004db80  lea     rax, [rbp+arg_0]
0x18004db84  mov     [rbp+var_18], rax
0x18004db88  lea     r15d, [r13+1]
0x18004db8c  mov     [rbp+var_10], r15b
0x18004db90  cmp     [rcx+10Ch], r13d
0x18004db97  jz      loc_18004DC41
0x18004db9d  mov     [rbp+pv], r13
0x18004dba1  lea     r8, [rcx+30h]
0x18004dba5  cmp     qword ptr [r8+18h], 8
0x18004dbaa  jb      short loc_18004DBAF
0x18004dbac  mov     r8, [r8]
0x18004dbaf  lea     rdx, aIgnoringAttemp; "Ignoring attempt to offline deprovision"...
0x18004dbb6  lea     rcx, [rbp+pv]
0x18004dbba  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004dbbf  mov     rcx, [rbp+38h]; this
0x18004dbc3  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dbca  test    eax, eax
0x18004dbcc  jns     short loc_18004DBDE
0x18004dbce  mov     r9d, eax; char *
0x18004dbd1  mov     r8, rdi; unsigned int
0x18004dbd4  mov     edx, 59Ch; void *
0x18004dbd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dbde  mov     dword ptr [rsp+60h+var_38], r13d
0x18004dbe3  mov     [rsp+60h+var_40], 2; int
0x18004dbeb  mov     esi, 5A4h
0x18004dbf0  mov     r9d, esi
0x18004dbf3  lea     r8, aMsixpackagePro_1; "MsixPackage::Provisioning::Library::Msi"...
0x18004dbfa  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dc01  mov     rbx, [rbp+pv]
0x18004dc05  mov     rcx, rbx
0x18004dc08  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004dc0d  mov     rcx, [rbp+38h]; this
0x18004dc11  test    eax, eax
0x18004dc13  jns     short loc_18004DC23
0x18004dc15  mov     r9d, eax; char *
0x18004dc18  mov     r8, rdi; unsigned int
0x18004dc1b  mov     edx, esi; void *
0x18004dc1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dc22  nop
0x18004dc23  test    rbx, rbx
0x18004dc26  jz      short loc_18004DC38
0x18004dc28  mov     rcx, rbx; pv
0x18004dc2b  call    cs:__imp_CoTaskMemFree
0x18004dc32  nop     dword ptr [rax+rax+00h]
0x18004dc37  nop
0x18004dc38  cmp     [rbp+arg_10], r13
0x18004dc3c  jmp     loc_18004DFE3
0x18004dc41  mov     rcx, [rcx+0D8h]
0x18004dc48  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dc4f  lea     r12, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dc56  test    rcx, rcx
0x18004dc59  jz      short loc_18004DCD2
0x18004dc5b  mov     [rbp+var_30], rcx
0x18004dc5f  mov     [rbp+var_28], r14d
0x18004dc63  mov     eax, [rbp+var_24]
0x18004dc66  mov     [rbp+var_24], eax
0x18004dc69  lea     r8, [rbp+var_30]
0x18004dc6d  call    MsixPackage__Provisioning__Library__MsixProvisioningRequest__ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___
0x18004dc72  mov     ebx, eax
0x18004dc74  test    eax, eax
0x18004dc76  jns     short loc_18004DCD2
0x18004dc78  mov     rcx, [rbp+38h]; this
0x18004dc7c  mov     r9d, eax; char *
0x18004dc7f  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dc86  mov     edx, 309h; void *
0x18004dc8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dc90  test    r14d, r14d
0x18004dc93  jz      loc_18004DD3D
0x18004dc99  mov     dword ptr [rsp+60h+var_38], ebx
0x18004dc9d  mov     [rsp+60h+var_40], r15d; int
0x18004dca2  mov     r9d, 5AEh
0x18004dca8  xor     r8d, r8d
0x18004dcab  mov     rdx, r12
0x18004dcae  lea     rcx, aFailedToRemove_4; "Failed to remove related packages"
0x18004dcb5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004dcba  mov     rcx, [rbp+38h]; this
0x18004dcbe  test    eax, eax
0x18004dcc0  jns     short loc_18004DCD2
0x18004dcc2  mov     r9d, eax; char *
0x18004dcc5  mov     r8, rdi; unsigned int
0x18004dcc8  mov     edx, 5AEh; void *
0x18004dccd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dcd2  lea     r9, [rbp+arg_0]; unsigned int *
0x18004dcd6  lea     r8, [rbp+arg_10]; struct AppxAllUserStore::_PackageInfo **
0x18004dcda  mov     edx, r14d; int
0x18004dcdd  mov     rcx, rsi; this
0x18004dce0  call    ?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)
0x18004dce5  mov     ebx, eax
0x18004dce7  test    eax, eax
0x18004dce9  jns     short loc_18004DD2D
0x18004dceb  test    r14d, r14d
0x18004dcee  jz      loc_18004DD8A
0x18004dcf4  mov     dword ptr [rsp+60h+var_38], eax
0x18004dcf8  mov     [rsp+60h+var_40], r15d; int
0x18004dcfd  mov     r9d, 5B5h
0x18004dd03  xor     r8d, r8d
0x18004dd06  mov     rdx, r12
0x18004dd09  lea     rcx, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x18004dd10  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004dd15  mov     rcx, [rbp+38h]; this
0x18004dd19  test    eax, eax
0x18004dd1b  jns     short loc_18004DD2D
0x18004dd1d  mov     r9d, eax; char *
0x18004dd20  mov     r8, rdi; unsigned int
0x18004dd23  mov     edx, 5B5h; void *
0x18004dd28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dd2d  lea     rbx, [rsi+30h]
0x18004dd31  cmp     qword ptr [rbx+18h], 8
0x18004dd36  jb      short loc_18004DD98
0x18004dd38  mov     rdx, [rbx]
0x18004dd3b  jmp     short loc_18004DD9B
0x18004dd3d  lea     rax, aFailedToRemove_4; "Failed to remove related packages"
0x18004dd44  mov     edx, 5AEh; void *
0x18004dd49  mov     [rsp+60h+var_38], rax; char *
0x18004dd4e  lea     rax, aWs; "%ws"
0x18004dd55  mov     r8, rdi; unsigned int
0x18004dd58  mov     r9d, ebx; char *
0x18004dd5b  mov     qword ptr [rsp+60h+var_40], rax; int
0x18004dd60  mov     rcx, [rbp+38h]; this
0x18004dd64  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004dd69  nop
0x18004dd6a  cmp     [rbp+arg_10], r13
0x18004dd6e  jz      short loc_18004DD83
0x18004dd70  lea     rdx, [rbp+arg_10]
0x18004dd74  mov     ecx, [rbp+arg_0]
0x18004dd77  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x18004dd7e  nop     dword ptr [rax+rax+00h]
0x18004dd83  mov     eax, ebx
0x18004dd85  jmp     loc_18004DFFA
0x18004dd8a  lea     rax, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x18004dd91  mov     edx, 5B5h
0x18004dd96  jmp     short loc_18004DD49
0x18004dd98  mov     rdx, rbx; unsigned __int16 *
0x18004dd9b  mov     rcx, rsi; this
0x18004dd9e  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x18004dda3  mov     r15d, eax
0x18004dda6  test    eax, eax
0x18004dda8  jns     loc_18004DE42
0x18004ddae  mov     [rbp+pv], r13
0x18004ddb2  cmp     qword ptr [rbx+18h], 8
0x18004ddb7  jb      short loc_18004DDBC
0x18004ddb9  mov     rbx, [rbx]
0x18004ddbc  mov     r8, rbx
0x18004ddbf  lea     rdx, aFailedToDestag; "Failed to destage package'%s'"
0x18004ddc6  lea     rcx, [rbp+pv]
0x18004ddca  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004ddcf  mov     rcx, [rbp+38h]; this
0x18004ddd3  test    eax, eax
0x18004ddd5  jns     short loc_18004DDE7
0x18004ddd7  mov     r9d, eax; char *
0x18004ddda  mov     r8, rdi; unsigned int
0x18004dddd  mov     edx, 5BBh; void *
0x18004dde2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dde7  mov     rbx, [rbp+pv]
0x18004ddeb  test    r14d, r14d
0x18004ddee  jz      loc_18004E013
0x18004ddf4  mov     dword ptr [rsp+60h+var_38], r15d
0x18004ddf9  mov     [rsp+60h+var_40], 1; int
0x18004de01  mov     r9d, 5BBh
0x18004de07  xor     r8d, r8d
0x18004de0a  mov     rdx, r12
0x18004de0d  mov     rcx, rbx
0x18004de10  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004de15  mov     rcx, [rbp+38h]; this
0x18004de19  test    eax, eax
0x18004de1b  jns     short loc_18004DE2E
0x18004de1d  mov     r9d, eax; char *
0x18004de20  mov     r8, rdi; unsigned int
0x18004de23  mov     edx, 5BBh; void *
0x18004de28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004de2d  nop
0x18004de2e  test    rbx, rbx
0x18004de31  jz      short loc_18004DE42
0x18004de33  mov     rcx, rbx; pv
0x18004de36  call    cs:__imp_CoTaskMemFree
0x18004de3d  nop     dword ptr [rax+rax+00h]
0x18004de42  mov     rdx, [rbp+arg_10]
0x18004de46  test    rdx, rdx
0x18004de49  jz      loc_18004DFE0
0x18004de4f  cmp     [rbp+arg_0], 0
0x18004de53  jbe     loc_18004DFE0
0x18004de59  mov     eax, r13d
0x18004de5c  lea     rcx, [rax+rax*2]
0x18004de60  mov     r12, [rdx+rcx*8]
0x18004de64  test    r12, r12
0x18004de67  jz      loc_18004DFD3
0x18004de6d  mov     rcx, [rsi+10h]
0x18004de71  mov     r8b, 1
0x18004de74  mov     rdx, r12
0x18004de77  mov     rcx, [rcx+248h]
0x18004de7e  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x18004de85  nop     dword ptr [rax+rax+00h]
0x18004de8a  mov     r15d, eax
0x18004de8d  test    eax, eax
0x18004de8f  jns     loc_18004DF27
0x18004de95  mov     [rbp+pv], 0
0x18004de9d  mov     r8, r12
0x18004dea0  lea     rdx, aFailedToDeregi_2; "Failed to deregister staged package'%s'"
0x18004dea7  lea     rcx, [rbp+pv]
0x18004deab  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004deb0  mov     rcx, [rbp+38h]; this
0x18004deb4  test    eax, eax
0x18004deb6  jns     short loc_18004DEC8
0x18004deb8  mov     r9d, eax; char *
0x18004debb  mov     r8, rdi; unsigned int
0x18004debe  mov     edx, 5CBh; void *
0x18004dec3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dec8  mov     rbx, [rbp+pv]
0x18004decc  test    r14d, r14d
0x18004decf  jz      loc_18004E06C
0x18004ded5  mov     dword ptr [rsp+60h+var_38], r15d
0x18004deda  mov     [rsp+60h+var_40], 1; int
0x18004dee2  mov     r9d, 5CBh
0x18004dee8  xor     r8d, r8d
0x18004deeb  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004def2  mov     rcx, rbx
0x18004def5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004defa  mov     rcx, [rbp+38h]; this
0x18004defe  test    eax, eax
0x18004df00  jns     short loc_18004DF13
0x18004df02  mov     r9d, eax; char *
0x18004df05  mov     r8, rdi; unsigned int
0x18004df08  mov     edx, 5CBh; void *
0x18004df0d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004df12  nop
0x18004df13  test    rbx, rbx
0x18004df16  jz      short loc_18004DF27
0x18004df18  mov     rcx, rbx; pv
0x18004df1b  call    cs:__imp_CoTaskMemFree
0x18004df22  nop     dword ptr [rax+rax+00h]
0x18004df27  mov     rdx, r12; unsigned __int16 *
0x18004df2a  mov     rcx, rsi; this
0x18004df2d  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x18004df32  mov     r15d, eax
0x18004df35  test    eax, eax
0x18004df37  jns     loc_18004DFCF
0x18004df3d  mov     [rbp+pv], 0
0x18004df45  mov     r8, r12
0x18004df48  lea     rdx, aFailedToDestag; "Failed to destage package'%s'"
0x18004df4f  lea     rcx, [rbp+pv]
0x18004df53  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004df58  mov     rcx, [rbp+38h]; this
0x18004df5c  test    eax, eax
0x18004df5e  jns     short loc_18004DF70
0x18004df60  mov     r9d, eax; char *
0x18004df63  mov     r8, rdi; unsigned int
0x18004df66  mov     edx, 5D1h; void *
0x18004df6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004df70  mov     rbx, [rbp+pv]
0x18004df74  test    r14d, r14d
0x18004df77  jz      loc_18004E0AE
0x18004df7d  mov     dword ptr [rsp+60h+var_38], r15d
0x18004df82  mov     [rsp+60h+var_40], 1; int
0x18004df8a  mov     r9d, 5D1h
0x18004df90  xor     r8d, r8d
0x18004df93  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004df9a  mov     rcx, rbx
0x18004df9d  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004dfa2  mov     rcx, [rbp+38h]; this
0x18004dfa6  test    eax, eax
0x18004dfa8  jns     short loc_18004DFBB
0x18004dfaa  mov     r9d, eax; char *
0x18004dfad  mov     r8, rdi; unsigned int
0x18004dfb0  mov     edx, 5D1h; void *
0x18004dfb5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004dfba  nop
0x18004dfbb  test    rbx, rbx
0x18004dfbe  jz      short loc_18004DFCF
0x18004dfc0  mov     rcx, rbx; pv
0x18004dfc3  call    cs:__imp_CoTaskMemFree
0x18004dfca  nop     dword ptr [rax+rax+00h]
0x18004dfcf  mov     rdx, [rbp+arg_10]
0x18004dfd3  inc     r13d
0x18004dfd6  cmp     r13d, [rbp+arg_0]
0x18004dfda  jb      loc_18004DE59
0x18004dfe0  test    rdx, rdx
0x18004dfe3  jz      short loc_18004DFF8
0x18004dfe5  lea     rdx, [rbp+arg_10]
0x18004dfe9  mov     ecx, [rbp+arg_0]
0x18004dfec  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x18004dff3  nop     dword ptr [rax+rax+00h]
0x18004dff8  xor     eax, eax
0x18004dffa  mov     rbx, [rsp+60h+arg_8]
  ... truncated ...
```
