# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(int)

- ea: `0x180049a44`
- end: `0x180049f8e`
- name: `?RemovePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z`
- size: `1354`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180040f60`
- `0x18004d950`
- `0x18004e678`
- `0x18004e864`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180044a3c`
- `0x180044ecc`
- `0x180049a44`
- `0x18004d360`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049df7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049df7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f57`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180049d60`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180049d60`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049c65`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049ebc`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049f1e`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049c65`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049ebc`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180049f1e`

## string_xrefs

- `0x180049aee`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049b3d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049dc7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049e69`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049ab7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049b36`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049b9c`: `Failed to remove related packages`
- `0x180049c2b`: `Failed to remove related packages`
- `0x180049ae7`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage`
- `0x180049aa3`: `Ignoring attempt to offline deprovision framework %s provisioned by itself`
- `0x180049b6d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

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
  unsigned __int16 **v14; // rbx
  unsigned __int16 *v15; // rdx
  __int64 v17; // r8
  int v18; // r15d
  int v19; // eax
  void *v20; // rbx
  int v21; // eax
  struct AppxAllUserStore::_PackageInfo *v22; // rdx
  unsigned __int16 *v23; // r12
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
           (char *)&pv,
           L"Ignoring attempt to offline deprovision framework %s provisioned by itself");
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x59C,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v5);
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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v7);
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
      v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              L"Failed to remove related packages",
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              0,
              1454);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5AE,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v12);
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
  v13 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
          L"Failed to deregister main package and get its dependent packages",
          L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          0,
          1461);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5B5,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v13);
LABEL_18:
  v14 = (unsigned __int16 **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) < 8u )
    v15 = (unsigned __int16 *)((char *)this + 48);
  else
    v15 = *v14;
  v18 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(this, v15);
  if ( v18 < 0 )
  {
    pv = 0;
    if ( *((_QWORD *)this + 9) >= 8u )
      v14 = (unsigned __int16 **)*v14;
    v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&pv,
            L"Failed to destage package'%s'",
            v14);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v19);
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
    v21 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1467);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v21);
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
    v23 = (unsigned __int16 *)*((_QWORD *)v22 + 3 * v4);
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
            (char *)&pv,
            L"Failed to deregister staged package'%s'",
            v23);
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CB,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v24);
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
    v26 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1483);
    if ( v26 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CB,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v26);
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
          (char *)&pv,
          L"Failed to destage package'%s'",
          v23);
  if ( v27 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5D1,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v27);
  v25 = pv;
  if ( v2 )
  {
    v28 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1489);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D1,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v28);
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
0x180049a44  mov     [rsp-38h+arg_8], rbx
0x180049a49  push    rbp
0x180049a4a  push    rsi
0x180049a4b  push    rdi
0x180049a4c  push    r12
0x180049a4e  push    r13
0x180049a50  push    r14
0x180049a52  push    r15
0x180049a54  mov     rbp, rsp
0x180049a57  sub     rsp, 60h
0x180049a5b  mov     r14d, edx
0x180049a5e  mov     rsi, rcx
0x180049a61  xor     r13d, r13d
0x180049a64  mov     [rbp+arg_0], r13d
0x180049a68  mov     [rbp+arg_10], r13
0x180049a6c  lea     rax, [rbp+arg_10]
0x180049a70  mov     [rbp+var_20], rax
0x180049a74  lea     rax, [rbp+arg_0]
0x180049a78  mov     [rbp+var_18], rax
0x180049a7c  lea     r15d, [r13+1]
0x180049a80  mov     [rbp+var_10], r15b
0x180049a84  cmp     [rcx+10Ch], r13d
0x180049a8b  jz      loc_180049B2F
0x180049a91  mov     [rbp+pv], r13
0x180049a95  lea     r8, [rcx+30h]
0x180049a99  cmp     qword ptr [r8+18h], 8
0x180049a9e  jb      short loc_180049AA3
0x180049aa0  mov     r8, [r8]
0x180049aa3  lea     rdx, aIgnoringAttemp; "Ignoring attempt to offline deprovision"...
0x180049aaa  lea     rcx, [rbp+pv]
0x180049aae  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049ab3  mov     rcx, [rbp+38h]; this
0x180049ab7  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049abe  test    eax, eax
0x180049ac0  jns     short loc_180049AD2
0x180049ac2  mov     r9d, eax; char *
0x180049ac5  mov     r8, rdi; unsigned int
0x180049ac8  mov     edx, 59Ch; void *
0x180049acd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049ad2  mov     dword ptr [rsp+60h+var_38], r13d
0x180049ad7  mov     [rsp+60h+var_40], 2; int
0x180049adf  mov     esi, 5A4h
0x180049ae4  mov     r9d, esi
0x180049ae7  lea     r8, aMsixpackagePro_1; "MsixPackage::Provisioning::Library::Msi"...
0x180049aee  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049af5  mov     rbx, [rbp+pv]
0x180049af9  mov     rcx, rbx
0x180049afc  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049b01  mov     rcx, [rbp+38h]; this
0x180049b05  test    eax, eax
0x180049b07  jns     short loc_180049B17
0x180049b09  mov     r9d, eax; char *
0x180049b0c  mov     r8, rdi; unsigned int
0x180049b0f  mov     edx, esi; void *
0x180049b11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049b16  nop
0x180049b17  test    rbx, rbx
0x180049b1a  jz      short loc_180049B26
0x180049b1c  mov     rcx, rbx; pv
0x180049b1f  call    cs:__imp_CoTaskMemFree
0x180049b25  nop
0x180049b26  cmp     [rbp+arg_10], r13
0x180049b2a  jmp     loc_180049EB3
0x180049b2f  mov     rcx, [rcx+0D8h]
0x180049b36  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049b3d  lea     r12, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049b44  test    rcx, rcx
0x180049b47  jz      short loc_180049BC0
0x180049b49  mov     [rbp+var_30], rcx
0x180049b4d  mov     [rbp+var_28], r14d
0x180049b51  mov     eax, [rbp+var_24]
0x180049b54  mov     [rbp+var_24], eax
0x180049b57  lea     r8, [rbp+var_30]
0x180049b5b  call    MsixPackage__Provisioning__Library__MsixProvisioningRequest__ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___
0x180049b60  mov     ebx, eax
0x180049b62  test    eax, eax
0x180049b64  jns     short loc_180049BC0
0x180049b66  mov     rcx, [rbp+38h]; this
0x180049b6a  mov     r9d, eax; char *
0x180049b6d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049b74  mov     edx, 309h; void *
0x180049b79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049b7e  test    r14d, r14d
0x180049b81  jz      loc_180049C2B
0x180049b87  mov     dword ptr [rsp+60h+var_38], ebx
0x180049b8b  mov     [rsp+60h+var_40], r15d; int
0x180049b90  mov     r9d, 5AEh
0x180049b96  xor     r8d, r8d
0x180049b99  mov     rdx, r12
0x180049b9c  lea     rcx, aFailedToRemove_4; "Failed to remove related packages"
0x180049ba3  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049ba8  mov     rcx, [rbp+38h]; this
0x180049bac  test    eax, eax
0x180049bae  jns     short loc_180049BC0
0x180049bb0  mov     r9d, eax; char *
0x180049bb3  mov     r8, rdi; unsigned int
0x180049bb6  mov     edx, 5AEh; void *
0x180049bbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049bc0  lea     r9, [rbp+arg_0]; unsigned int *
0x180049bc4  lea     r8, [rbp+arg_10]; struct AppxAllUserStore::_PackageInfo **
0x180049bc8  mov     edx, r14d; int
0x180049bcb  mov     rcx, rsi; this
0x180049bce  call    ?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)
0x180049bd3  mov     ebx, eax
0x180049bd5  test    eax, eax
0x180049bd7  jns     short loc_180049C1B
0x180049bd9  test    r14d, r14d
0x180049bdc  jz      loc_180049C72
0x180049be2  mov     dword ptr [rsp+60h+var_38], eax
0x180049be6  mov     [rsp+60h+var_40], r15d; int
0x180049beb  mov     r9d, 5B5h
0x180049bf1  xor     r8d, r8d
0x180049bf4  mov     rdx, r12
0x180049bf7  lea     rcx, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x180049bfe  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049c03  mov     rcx, [rbp+38h]; this
0x180049c07  test    eax, eax
0x180049c09  jns     short loc_180049C1B
0x180049c0b  mov     r9d, eax; char *
0x180049c0e  mov     r8, rdi; unsigned int
0x180049c11  mov     edx, 5B5h; void *
0x180049c16  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049c1b  lea     rbx, [rsi+30h]
0x180049c1f  cmp     qword ptr [rbx+18h], 8
0x180049c24  jb      short loc_180049C80
0x180049c26  mov     rdx, [rbx]
0x180049c29  jmp     short loc_180049C83
0x180049c2b  lea     rax, aFailedToRemove_4; "Failed to remove related packages"
0x180049c32  mov     edx, 5AEh; void *
0x180049c37  mov     [rsp+60h+var_38], rax; char *
0x180049c3c  lea     rax, aWs; "%ws"
0x180049c43  mov     r8, rdi; unsigned int
0x180049c46  mov     r9d, ebx; char *
0x180049c49  mov     qword ptr [rsp+60h+var_40], rax; int
0x180049c4e  mov     rcx, [rbp+38h]; this
0x180049c52  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049c57  nop
0x180049c58  cmp     [rbp+arg_10], r13
0x180049c5c  jz      short loc_180049C6B
0x180049c5e  lea     rdx, [rbp+arg_10]
0x180049c62  mov     ecx, [rbp+arg_0]
0x180049c65  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180049c6b  mov     eax, ebx
0x180049c6d  jmp     loc_180049EC4
0x180049c72  lea     rax, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x180049c79  mov     edx, 5B5h
0x180049c7e  jmp     short loc_180049C37
0x180049c80  mov     rdx, rbx; unsigned __int16 *
0x180049c83  mov     rcx, rsi; this
0x180049c86  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x180049c8b  mov     r15d, eax
0x180049c8e  test    eax, eax
0x180049c90  jns     loc_180049D24
0x180049c96  mov     [rbp+pv], r13
0x180049c9a  cmp     qword ptr [rbx+18h], 8
0x180049c9f  jb      short loc_180049CA4
0x180049ca1  mov     rbx, [rbx]
0x180049ca4  mov     r8, rbx
0x180049ca7  lea     rdx, aFailedToDestag; "Failed to destage package'%s'"
0x180049cae  lea     rcx, [rbp+pv]
0x180049cb2  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049cb7  mov     rcx, [rbp+38h]; this
0x180049cbb  test    eax, eax
0x180049cbd  jns     short loc_180049CCF
0x180049cbf  mov     r9d, eax; char *
0x180049cc2  mov     r8, rdi; unsigned int
0x180049cc5  mov     edx, 5BBh; void *
0x180049cca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049ccf  mov     rbx, [rbp+pv]
0x180049cd3  test    r14d, r14d
0x180049cd6  jz      loc_180049EDC
0x180049cdc  mov     dword ptr [rsp+60h+var_38], r15d
0x180049ce1  mov     [rsp+60h+var_40], 1; int
0x180049ce9  mov     r9d, 5BBh
0x180049cef  xor     r8d, r8d
0x180049cf2  mov     rdx, r12
0x180049cf5  mov     rcx, rbx
0x180049cf8  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049cfd  mov     rcx, [rbp+38h]; this
0x180049d01  test    eax, eax
0x180049d03  jns     short loc_180049D16
0x180049d05  mov     r9d, eax; char *
0x180049d08  mov     r8, rdi; unsigned int
0x180049d0b  mov     edx, 5BBh; void *
0x180049d10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049d15  nop
0x180049d16  test    rbx, rbx
0x180049d19  jz      short loc_180049D24
0x180049d1b  mov     rcx, rbx; pv
0x180049d1e  call    cs:__imp_CoTaskMemFree
0x180049d24  mov     rdx, [rbp+arg_10]
0x180049d28  test    rdx, rdx
0x180049d2b  jz      loc_180049EB0
0x180049d31  cmp     [rbp+arg_0], 0
0x180049d35  jbe     loc_180049EB0
0x180049d3b  mov     eax, r13d
0x180049d3e  lea     rcx, [rax+rax*2]
0x180049d42  mov     r12, [rdx+rcx*8]
0x180049d46  test    r12, r12
0x180049d49  jz      loc_180049EA3
0x180049d4f  mov     rcx, [rsi+10h]
0x180049d53  mov     r8b, 1
0x180049d56  mov     rdx, r12
0x180049d59  mov     rcx, [rcx+248h]
0x180049d60  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180049d66  mov     r15d, eax
0x180049d69  test    eax, eax
0x180049d6b  jns     loc_180049DFD
0x180049d71  mov     [rbp+pv], 0
0x180049d79  mov     r8, r12
0x180049d7c  lea     rdx, aFailedToDeregi_2; "Failed to deregister staged package'%s'"
0x180049d83  lea     rcx, [rbp+pv]
0x180049d87  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049d8c  mov     rcx, [rbp+38h]; this
0x180049d90  test    eax, eax
0x180049d92  jns     short loc_180049DA4
0x180049d94  mov     r9d, eax; char *
0x180049d97  mov     r8, rdi; unsigned int
0x180049d9a  mov     edx, 5CBh; void *
0x180049d9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049da4  mov     rbx, [rbp+pv]
0x180049da8  test    r14d, r14d
0x180049dab  jz      loc_180049F29
0x180049db1  mov     dword ptr [rsp+60h+var_38], r15d
0x180049db6  mov     [rsp+60h+var_40], 1; int
0x180049dbe  mov     r9d, 5CBh
0x180049dc4  xor     r8d, r8d
0x180049dc7  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049dce  mov     rcx, rbx
0x180049dd1  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049dd6  mov     rcx, [rbp+38h]; this
0x180049dda  test    eax, eax
0x180049ddc  jns     short loc_180049DEF
0x180049dde  mov     r9d, eax; char *
0x180049de1  mov     r8, rdi; unsigned int
0x180049de4  mov     edx, 5CBh; void *
0x180049de9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049dee  nop
0x180049def  test    rbx, rbx
0x180049df2  jz      short loc_180049DFD
0x180049df4  mov     rcx, rbx; pv
0x180049df7  call    cs:__imp_CoTaskMemFree
0x180049dfd  mov     rdx, r12; unsigned __int16 *
0x180049e00  mov     rcx, rsi; this
0x180049e03  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x180049e08  mov     r15d, eax
0x180049e0b  test    eax, eax
0x180049e0d  jns     loc_180049E9F
0x180049e13  mov     [rbp+pv], 0
0x180049e1b  mov     r8, r12
0x180049e1e  lea     rdx, aFailedToDestag; "Failed to destage package'%s'"
0x180049e25  lea     rcx, [rbp+pv]
0x180049e29  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049e2e  mov     rcx, [rbp+38h]; this
0x180049e32  test    eax, eax
0x180049e34  jns     short loc_180049E46
0x180049e36  mov     r9d, eax; char *
0x180049e39  mov     r8, rdi; unsigned int
0x180049e3c  mov     edx, 5D1h; void *
0x180049e41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e46  mov     rbx, [rbp+pv]
0x180049e4a  test    r14d, r14d
0x180049e4d  jz      loc_180049F65
0x180049e53  mov     dword ptr [rsp+60h+var_38], r15d
0x180049e58  mov     [rsp+60h+var_40], 1; int
0x180049e60  mov     r9d, 5D1h
0x180049e66  xor     r8d, r8d
0x180049e69  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049e70  mov     rcx, rbx
0x180049e73  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049e78  mov     rcx, [rbp+38h]; this
0x180049e7c  test    eax, eax
0x180049e7e  jns     short loc_180049E91
0x180049e80  mov     r9d, eax; char *
0x180049e83  mov     r8, rdi; unsigned int
0x180049e86  mov     edx, 5D1h; void *
0x180049e8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049e90  nop
0x180049e91  test    rbx, rbx
0x180049e94  jz      short loc_180049E9F
0x180049e96  mov     rcx, rbx; pv
0x180049e99  call    cs:__imp_CoTaskMemFree
0x180049e9f  mov     rdx, [rbp+arg_10]
0x180049ea3  inc     r13d
0x180049ea6  cmp     r13d, [rbp+arg_0]
0x180049eaa  jb      loc_180049D3B
0x180049eb0  test    rdx, rdx
0x180049eb3  jz      short loc_180049EC2
0x180049eb5  lea     rdx, [rbp+arg_10]
0x180049eb9  mov     ecx, [rbp+arg_0]
0x180049ebc  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180049ec2  xor     eax, eax
0x180049ec4  mov     rbx, [rsp+60h+arg_8]
0x180049ecc  add     rsp, 60h
0x180049ed0  pop     r15
0x180049ed2  pop     r14
0x180049ed4  pop     r13
0x180049ed6  pop     r12
0x180049ed8  pop     rdi
0x180049ed9  pop     rsi
  ... truncated ...
```
