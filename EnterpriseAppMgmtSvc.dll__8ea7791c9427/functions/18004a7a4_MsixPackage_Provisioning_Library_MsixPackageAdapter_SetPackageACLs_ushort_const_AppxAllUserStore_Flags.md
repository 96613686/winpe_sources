# MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs(ushort const *,AppxAllUserStore::Flags)

- ea: `0x18004a7a4`
- end: `0x18004ae5d`
- name: `?SetPackageACLs@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEBGW4Flags@AppxAllUserStore@@@Z`
- size: `1721`
- prototype: `int __high(const unsigned __int16 *, enum AppxAllUserStore::Flags)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ae64`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180046a40`
- `0x180046ba4`
- `0x18004a744`
- `0x18004a7a4`
- `0x180066db2`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004abb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ad0b`
- `AppXAllUserStore!ApplyPackageRootFolderACLs` at `0x18004adc8`
- `AppXAllUserStore!ApplyPackageRootFolderACLs` at `0x18004adc8`
- `AppXAllUserStore!PackageSidToPackageCapabilitySid` at `0x18004ad89`
- `AppXAllUserStore!PackageSidToPackageCapabilitySid` at `0x18004ad89`
- `AppXAllUserStore!HasCentennial` at `0x18004a983`
- `AppXAllUserStore!HasCentennial` at `0x18004a983`
- `AppXAllUserStore!FamilyMonikerStringToSid` at `0x18004ad58`
- `AppXAllUserStore!FamilyMonikerStringToSid` at `0x18004ad58`

## string_xrefs

- `0x18004a869`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a930`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ac44`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004acd1`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a840`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a88c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a906`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a953`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a9a6`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004aa29`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004aaa4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ab1c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ab92`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ac1a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ac67`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004aca7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004acf4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004adfb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ae1c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a862`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004a929`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004ac3d`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004acca`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004a820`: `Failed to get manifest reader from package. hr=0x%x`
- `0x18004aa95`: `Failed while setting ACLs for package with inprocMediaExtension capability on directory %ws`
- `0x18004aa1a`: `Failed to check package for inprocMediaExtension capability.`
- `0x18004a997`: `Failed to determine if the package in question contains any runFullTrust components.`
- `0x18004a8e6`: `Failed to get internal manifest reader interface.`
- `0x18004ad70`: `Failed to set package ACLs on %ws.`
- `0x18004add9`: `Failed to set package ACLs on %ws.`
- `0x18004ad9a`: `Failed to get the package capability SID for package %ws.`
- `0x18004ad69`: `Failed to get the package SID for package %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs(
        __int64 a1,
        const char *a2,
        __int64 a3)
{
  __int64 v5; // rsi
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  void *v10; // rbx
  int v11; // eax
  int v12; // eax
  LPVOID v13; // rbx
  int v14; // eax
  void *v15; // rcx
  __int64 v16; // rcx
  int v17; // ebx
  const char *v18; // r9
  __int64 result; // rax
  int HasInprocMediaExtensionCapability; // ebx
  int v21; // ebx
  int HasDependencyTargetCapability; // ebx
  int v23; // eax
  int v24; // eax
  void *v25; // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  const char *v29; // rbx
  int v30; // edi
  __int64 v31; // rdx
  const char *v32; // rax
  char *v33; // [rsp+28h] [rbp-110h]
  char v34; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v35[7]; // [rsp+31h] [rbp-107h] BYREF
  __int64 v36; // [rsp+38h] [rbp-100h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-F8h] BYREF
  LPVOID v38; // [rsp+48h] [rbp-F0h] BYREF
  _BYTE v39[80]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v40[80]; // [rsp+A0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v5 = a3 | 2;
    v35[0] = 0;
    v6 = *(__int64 **)(a1 + 240);
    if ( !v6 )
      goto LABEL_58;
    v36 = 0;
    v7 = *v6;
    v36 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 56))(v6, &v36);
    if ( v8 < 0 )
    {
      pv = 0;
      v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             (char *)&pv,
             L"Failed to get manifest reader from package. hr=0x%x",
             (unsigned int)v8);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x46D,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v9);
      v10 = pv;
      v11 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              pv,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
              1142);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x476,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v11);
      if ( v10 )
        CoTaskMemFree(v10);
      goto LABEL_50;
    }
    pv = 0;
    (**(void (__fastcall ***)(__int64, GUID *, LPVOID *))v36)(v36, &GUID_c43825ab_69b7_400a_9709_cc37f5a72d24, &pv);
    if ( v36 )
    {
      v17 = HasCentennial(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 584LL), v36, v35);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x496,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to determine if the package in question contains any runFullTrust components.",
          v33);
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        return (unsigned int)v17;
      }
      if ( !v35[0] )
      {
        v34 = 0;
        HasInprocMediaExtensionCapability = MsixPackage::Provisioning::Library::MsixPackageAdapter::HasInprocMediaExtensionCapability(
                                              v16,
                                              &pv,
                                              &v34);
        if ( HasInprocMediaExtensionCapability < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x49C,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)HasInprocMediaExtensionCapability,
            (int)"Failed to check package for inprocMediaExtension capability.",
            v33);
          if ( pv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          return (unsigned int)HasInprocMediaExtensionCapability;
        }
        if ( v34 )
        {
          v21 = MsixPackage::Provisioning::Library::MsixPackageAdapter::SetFrameworkACLs(v16, a2, v5);
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x4A5,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v21,
              (int)"Failed while setting ACLs for package with inprocMediaExtension capability on directory %ws",
              a2);
            if ( pv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            return (unsigned int)v21;
          }
        }
      }
      v34 = 0;
      HasDependencyTargetCapability = MsixPackage::Provisioning::Library::MsixPackageAdapter::HasDependencyTargetCapability(
                                        v16,
                                        &pv,
                                        &v34);
      if ( HasDependencyTargetCapability < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4AA,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)HasDependencyTargetCapability,
          (int)"Failed to check package for dependencyTarget capability.",
          v33);
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        return (unsigned int)HasDependencyTargetCapability;
      }
      if ( !v34 )
        goto LABEL_48;
      v38 = 0;
      v23 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&v38,
              L"%s provisioned as dependencyTarget package.",
              a2);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B4,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v23);
      v5 |= 0x4000uLL;
      v15 = v38;
      if ( !v38 )
        goto LABEL_48;
    }
    else
    {
      v38 = 0;
      v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&v38,
              L"Failed to get internal manifest reader interface.");
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x485,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v12);
      v13 = v38;
      v14 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              v38,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
              1165);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x48D,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v14);
      if ( !v13 )
        goto LABEL_48;
      v15 = v13;
    }
    CoTaskMemFree(v15);
LABEL_48:
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_50:
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v35[0] )
    {
      v38 = 0;
      v24 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&v38,
              L"%s provisioned as full trust package.",
              a2);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C7,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v24);
      v25 = v38;
      v26 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              v38,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
              1231);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CF,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v26);
      v5 |= 1uLL;
LABEL_62:
      if ( v25 )
        CoTaskMemFree(v25);
      v29 = (const char *)(*(_QWORD *)(a1 + 16) + 768LL);
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 16) + 792LL) >= 8u )
        v29 = *(const char **)v29;
      memset_0(v39, 0, 0x44u);
      memset_0(v40, 0, 0x44u);
      v30 = FamilyMonikerStringToSid(v29, 68, v39);
      if ( v30 < 0 )
      {
        v31 = 1394;
        v32 = "Failed to get the package SID for package %ws.";
LABEL_72:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v30,
          (int)v32,
          v29);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4E9,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v30,
          (int)"Failed to set package ACLs on %ws.",
          a2);
        return (unsigned int)v30;
      }
      v30 = PackageSidToPackageCapabilitySid(v39, 68, v40);
      if ( v30 < 0 )
      {
        v31 = 1400;
        v32 = "Failed to get the package capability SID for package %ws.";
        goto LABEL_72;
      }
      v30 = ApplyPackageRootFolderACLs(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 584LL), a2, v39, v40, v29, v5);
      if ( v30 < 0 )
      {
        v31 = 1411;
        v32 = "Failed to set package ACLs on %ws.";
        v29 = a2;
        goto LABEL_72;
      }
      return 0;
    }
LABEL_58:
    v38 = 0;
    v27 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&v38,
            L"%s provisioned as partial trust package.",
            a2);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DD,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v27);
    v25 = v38;
    v28 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            v38,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
            1253);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4E5,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v28);
    goto LABEL_62;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4ED,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18004a7a4  push    rbx
0x18004a7a6  push    rsi
0x18004a7a7  push    rdi
0x18004a7a8  push    r12
0x18004a7aa  push    r13
0x18004a7ac  push    r14
0x18004a7ae  push    r15
0x18004a7b0  sub     rsp, 100h
0x18004a7b7  mov     rax, cs:__security_cookie
0x18004a7be  xor     rax, rsp
0x18004a7c1  mov     [rsp+138h+var_48], rax
0x18004a7c9  mov     rsi, r8
0x18004a7cc  mov     r14, rdx
0x18004a7cf  mov     r15, rcx
0x18004a7d2  mov     r13d, 2
0x18004a7d8  or      rsi, r13
0x18004a7db  xor     r12d, r12d
0x18004a7de  mov     [rsp+138h+var_107], r12b
0x18004a7e3  mov     rcx, [rcx+0F0h]
0x18004a7ea  test    rcx, rcx
0x18004a7ed  jz      loc_18004AC7F
0x18004a7f3  mov     [rsp+138h+var_100], r12
0x18004a7f8  mov     rax, [rcx]
0x18004a7fb  mov     [rsp+138h+var_100], r12
0x18004a800  lea     rdx, [rsp+138h+var_100]
0x18004a805  mov     rax, [rax+38h]
0x18004a809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a80e  mov     ebx, eax
0x18004a810  test    eax, eax
0x18004a812  jns     loc_18004A8B2
0x18004a818  mov     [rsp+138h+pv], r12
0x18004a81d  mov     r8d, eax
0x18004a820  lea     rdx, aFailedToGetMan_3; "Failed to get manifest reader from pack"...
0x18004a827  lea     rcx, [rsp+138h+pv]
0x18004a82c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004a831  mov     rcx, [rsp+138h]; this
0x18004a839  test    eax, eax
0x18004a83b  jns     short loc_18004A851
0x18004a83d  mov     r9d, eax; char *
0x18004a840  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a847  mov     edx, 46Dh; void *
0x18004a84c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a851  mov     dword ptr [rsp+138h+var_110], ebx
0x18004a855  mov     [rsp+138h+var_118], r13d; int
0x18004a85a  mov     edi, 476h
0x18004a85f  mov     r9d, edi
0x18004a862  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004a869  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a870  mov     rbx, [rsp+138h+pv]
0x18004a875  mov     rcx, rbx
0x18004a878  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a87d  mov     rcx, [rsp+138h]; this
0x18004a885  test    eax, eax
0x18004a887  jns     short loc_18004A89B
0x18004a889  mov     r9d, eax; char *
0x18004a88c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a893  mov     edx, edi; void *
0x18004a895  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a89a  nop
0x18004a89b  test    rbx, rbx
0x18004a89e  jz      loc_18004ABD0
0x18004a8a4  mov     rcx, rbx; pv
0x18004a8a7  call    cs:__imp_CoTaskMemFree
0x18004a8ad  jmp     loc_18004ABD0
0x18004a8b2  mov     [rsp+138h+pv], r12
0x18004a8b7  mov     rcx, [rsp+138h+var_100]
0x18004a8bc  mov     rax, [rcx]
0x18004a8bf  lea     r8, [rsp+138h+pv]
0x18004a8c4  lea     rdx, _GUID_c43825ab_69b7_400a_9709_cc37f5a72d24
0x18004a8cb  mov     rax, [rax]
0x18004a8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8d3  mov     rdx, [rsp+138h+var_100]
0x18004a8d8  test    rdx, rdx
0x18004a8db  jnz     loc_18004A973
0x18004a8e1  mov     [rsp+138h+var_F0], r12
0x18004a8e6  lea     rdx, aFailedToGetInt_0; "Failed to get internal manifest reader "...
0x18004a8ed  lea     rcx, [rsp+138h+var_F0]
0x18004a8f2  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004a8f7  mov     rcx, [rsp+138h]; this
0x18004a8ff  test    eax, eax
0x18004a901  jns     short loc_18004A917
0x18004a903  mov     r9d, eax; char *
0x18004a906  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a90d  mov     edx, 485h; void *
0x18004a912  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a917  mov     dword ptr [rsp+138h+var_110], r12d
0x18004a91c  mov     [rsp+138h+var_118], r13d; int
0x18004a921  mov     edi, 48Dh
0x18004a926  mov     r9d, edi
0x18004a929  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004a930  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a937  mov     rbx, [rsp+138h+var_F0]
0x18004a93c  mov     rcx, rbx
0x18004a93f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a944  mov     rcx, [rsp+138h]; this
0x18004a94c  test    eax, eax
0x18004a94e  jns     short loc_18004A962
0x18004a950  mov     r9d, eax; char *
0x18004a953  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a95a  mov     edx, edi; void *
0x18004a95c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a961  nop
0x18004a962  test    rbx, rbx
0x18004a965  jz      loc_18004ABB9
0x18004a96b  mov     rcx, rbx
0x18004a96e  jmp     loc_18004ABB2
0x18004a973  mov     rcx, [r15+10h]
0x18004a977  lea     r8, [rsp+138h+var_107]
0x18004a97c  mov     rcx, [rcx+248h]
0x18004a983  call    cs:__imp_HasCentennial
0x18004a989  mov     ebx, eax
0x18004a98b  test    eax, eax
0x18004a98d  jns     short loc_18004A9ED
0x18004a98f  mov     rcx, [rsp+138h]; this
0x18004a997  lea     rax, aFailedToDeterm_9; "Failed to determine if the package in q"...
0x18004a99e  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004a9a3  mov     r9d, ebx; char *
0x18004a9a6  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a9ad  mov     edx, 496h; void *
0x18004a9b2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a9b7  nop
0x18004a9b8  mov     rcx, [rsp+138h+pv]
0x18004a9bd  test    rcx, rcx
0x18004a9c0  jz      short loc_18004A9CF
0x18004a9c2  mov     rax, [rcx]
0x18004a9c5  mov     rax, [rax+10h]
0x18004a9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9ce  nop
0x18004a9cf  mov     rcx, [rsp+138h+var_100]
0x18004a9d4  test    rcx, rcx
0x18004a9d7  jz      short loc_18004A9E6
0x18004a9d9  mov     rax, [rcx]
0x18004a9dc  mov     rax, [rax+10h]
0x18004a9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9e5  nop
0x18004a9e6  mov     eax, ebx
0x18004a9e8  jmp     loc_18004AE39
0x18004a9ed  cmp     [rsp+138h+var_107], r12b
0x18004a9f2  jnz     loc_18004AAEB
0x18004a9f8  mov     [rsp+138h+var_108], r12b
0x18004a9fd  lea     r8, [rsp+138h+var_108]
0x18004aa02  lea     rdx, [rsp+138h+pv]
0x18004aa07  call    ?HasInprocMediaExtensionCapability@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@AEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::HasInprocMediaExtensionCapability(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,bool &)
0x18004aa0c  mov     ebx, eax
0x18004aa0e  test    eax, eax
0x18004aa10  jns     short loc_18004AA70
0x18004aa12  mov     rcx, [rsp+138h]; this
0x18004aa1a  lea     rax, aFailedToCheckP; "Failed to check package for inprocMedia"...
0x18004aa21  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004aa26  mov     r9d, ebx; char *
0x18004aa29  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004aa30  mov     edx, 49Ch; void *
0x18004aa35  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004aa3a  nop
0x18004aa3b  mov     rcx, [rsp+138h+pv]
0x18004aa40  test    rcx, rcx
0x18004aa43  jz      short loc_18004AA52
0x18004aa45  mov     rax, [rcx]
0x18004aa48  mov     rax, [rax+10h]
0x18004aa4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa51  nop
0x18004aa52  mov     rcx, [rsp+138h+var_100]
0x18004aa57  test    rcx, rcx
0x18004aa5a  jz      short loc_18004AA69
0x18004aa5c  mov     rax, [rcx]
0x18004aa5f  mov     rax, [rax+10h]
0x18004aa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa68  nop
0x18004aa69  mov     eax, ebx
0x18004aa6b  jmp     loc_18004AE39
0x18004aa70  cmp     [rsp+138h+var_108], r12b
0x18004aa75  jz      short loc_18004AAEB
0x18004aa77  mov     r8, rsi
0x18004aa7a  mov     rdx, r14
0x18004aa7d  call    ?SetFrameworkACLs@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEBGW4Flags@AppxAllUserStore@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::SetFrameworkACLs(ushort const *,AppxAllUserStore::Flags)
0x18004aa82  mov     ebx, eax
0x18004aa84  test    eax, eax
0x18004aa86  jns     short loc_18004AAEB
0x18004aa88  mov     rcx, [rsp+138h]; this
0x18004aa90  mov     [rsp+138h+var_110], r14; char *
0x18004aa95  lea     rax, aFailedWhileSet_0; "Failed while setting ACLs for package w"...
0x18004aa9c  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004aaa1  mov     r9d, ebx; char *
0x18004aaa4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004aaab  mov     edx, 4A5h; void *
0x18004aab0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004aab5  nop
0x18004aab6  mov     rcx, [rsp+138h+pv]
0x18004aabb  test    rcx, rcx
0x18004aabe  jz      short loc_18004AACD
0x18004aac0  mov     rax, [rcx]
0x18004aac3  mov     rax, [rax+10h]
0x18004aac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aacc  nop
0x18004aacd  mov     rcx, [rsp+138h+var_100]
0x18004aad2  test    rcx, rcx
0x18004aad5  jz      short loc_18004AAE4
0x18004aad7  mov     rax, [rcx]
0x18004aada  mov     rax, [rax+10h]
0x18004aade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aae3  nop
0x18004aae4  mov     eax, ebx
0x18004aae6  jmp     loc_18004AE39
0x18004aaeb  mov     [rsp+138h+var_108], r12b
0x18004aaf0  lea     r8, [rsp+138h+var_108]
0x18004aaf5  lea     rdx, [rsp+138h+pv]
0x18004aafa  call    ?HasDependencyTargetCapability@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@AEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::HasDependencyTargetCapability(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,bool &)
0x18004aaff  mov     ebx, eax
0x18004ab01  test    eax, eax
0x18004ab03  jns     short loc_18004AB63
0x18004ab05  mov     rcx, [rsp+138h]; this
0x18004ab0d  lea     rax, aFailedToCheckP_0; "Failed to check package for dependencyT"...
0x18004ab14  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004ab19  mov     r9d, ebx; char *
0x18004ab1c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ab23  mov     edx, 4AAh; void *
0x18004ab28  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ab2d  nop
0x18004ab2e  mov     rcx, [rsp+138h+pv]
0x18004ab33  test    rcx, rcx
0x18004ab36  jz      short loc_18004AB45
0x18004ab38  mov     rax, [rcx]
0x18004ab3b  mov     rax, [rax+10h]
0x18004ab3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab44  nop
0x18004ab45  mov     rcx, [rsp+138h+var_100]
0x18004ab4a  test    rcx, rcx
0x18004ab4d  jz      short loc_18004AB5C
0x18004ab4f  mov     rax, [rcx]
0x18004ab52  mov     rax, [rax+10h]
0x18004ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab5b  nop
0x18004ab5c  mov     eax, ebx
0x18004ab5e  jmp     loc_18004AE39
0x18004ab63  cmp     [rsp+138h+var_108], r12b
0x18004ab68  jz      short loc_18004ABB9
0x18004ab6a  mov     [rsp+138h+var_F0], r12
0x18004ab6f  mov     r8, r14
0x18004ab72  lea     rdx, aSProvisionedAs; "%s provisioned as dependencyTarget pack"...
0x18004ab79  lea     rcx, [rsp+138h+var_F0]
0x18004ab7e  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004ab83  mov     rcx, [rsp+138h]; this
0x18004ab8b  test    eax, eax
0x18004ab8d  jns     short loc_18004ABA3
0x18004ab8f  mov     r9d, eax; char *
0x18004ab92  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ab99  mov     edx, 4B4h; void *
0x18004ab9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004aba3  bts     rsi, 0Eh
0x18004aba8  mov     rcx, [rsp+138h+var_F0]; pv
0x18004abad  test    rcx, rcx
0x18004abb0  jz      short loc_18004ABB9
0x18004abb2  call    cs:__imp_CoTaskMemFree
0x18004abb8  nop
0x18004abb9  mov     rcx, [rsp+138h+pv]
0x18004abbe  test    rcx, rcx
0x18004abc1  jz      short loc_18004ABD0
0x18004abc3  mov     rax, [rcx]
0x18004abc6  mov     rax, [rax+10h]
0x18004abca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abcf  nop
0x18004abd0  mov     rcx, [rsp+138h+var_100]
0x18004abd5  test    rcx, rcx
0x18004abd8  jz      short loc_18004ABE7
0x18004abda  mov     rax, [rcx]
0x18004abdd  mov     rax, [rax+10h]
0x18004abe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abe6  nop
0x18004abe7  cmp     [rsp+138h+var_107], r12b
0x18004abec  jz      loc_18004AC7F
0x18004abf2  mov     [rsp+138h+var_F0], r12
0x18004abf7  mov     r8, r14
0x18004abfa  lea     rdx, aSProvisionedAs_0; "%s provisioned as full trust package."
0x18004ac01  lea     rcx, [rsp+138h+var_F0]
0x18004ac06  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004ac0b  mov     rcx, [rsp+138h]; this
0x18004ac13  test    eax, eax
0x18004ac15  jns     short loc_18004AC2B
0x18004ac17  mov     r9d, eax; char *
0x18004ac1a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ac21  mov     edx, 4C7h; void *
0x18004ac26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ac2b  mov     dword ptr [rsp+138h+var_110], r12d
0x18004ac30  mov     [rsp+138h+var_118], r13d; int
0x18004ac35  mov     edi, 4CFh
0x18004ac3a  mov     r9d, edi
0x18004ac3d  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004ac44  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ac4b  mov     rbx, [rsp+138h+var_F0]
0x18004ac50  mov     rcx, rbx
0x18004ac53  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004ac58  mov     rcx, [rsp+138h]; this
0x18004ac60  test    eax, eax
0x18004ac62  jns     short loc_18004AC76
0x18004ac64  mov     r9d, eax; char *
0x18004ac67  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ac6e  mov     edx, edi; void *
0x18004ac70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ac75  nop
0x18004ac76  or      rsi, 1
  ... truncated ...
```
