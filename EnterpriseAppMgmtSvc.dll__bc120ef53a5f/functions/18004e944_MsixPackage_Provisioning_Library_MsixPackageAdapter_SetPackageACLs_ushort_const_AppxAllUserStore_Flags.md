# MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs(ushort const *,AppxAllUserStore::Flags)

- ea: `0x18004e944`
- end: `0x18004f027`
- name: `?SetPackageACLs@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEBGW4Flags@AppxAllUserStore@@@Z`
- size: `1763`
- prototype: `int __high(const unsigned __int16 *, enum AppxAllUserStore::Flags)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004f030`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18004aa4c`
- `0x18004abb0`
- `0x18004e8dc`
- `0x18004e944`
- `0x18006c8d2`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ea47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004eebd`
- `AppXAllUserStore!ApplyPackageRootFolderACLs` at `0x18004ef8c`
- `AppXAllUserStore!ApplyPackageRootFolderACLs` at `0x18004ef8c`
- `AppXAllUserStore!PackageSidToPackageCapabilitySid` at `0x18004ef47`
- `AppXAllUserStore!PackageSidToPackageCapabilitySid` at `0x18004ef47`
- `AppXAllUserStore!HasCentennial` at `0x18004eb29`
- `AppXAllUserStore!HasCentennial` at `0x18004eb29`
- `AppXAllUserStore!FamilyMonikerStringToSid` at `0x18004ef10`
- `AppXAllUserStore!FamilyMonikerStringToSid` at `0x18004ef10`

## string_xrefs

- `0x18004e9e0`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ea2c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004eaac`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004eaf9`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004eb52`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ebd5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ec50`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ecc8`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ed3e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004edcc`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ee19`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ee59`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004eea6`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004efc5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004efe6`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ea09`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ead6`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004edf6`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004ee83`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004eb43`: `Failed to determine if the package in question contains any runFullTrust components.`
- `0x18004ea8c`: `Failed to get internal manifest reader interface.`
- `0x18004ea02`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004eacf`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004edef`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004ee7c`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs`
- `0x18004e9c0`: `Failed to get manifest reader from package. hr=0x%x`
- `0x18004ec41`: `Failed while setting ACLs for package with inprocMediaExtension capability on directory %ws`
- `0x18004ebc6`: `Failed to check package for inprocMediaExtension capability.`
- `0x18004ef2e`: `Failed to set package ACLs on %ws.`
- `0x18004efa3`: `Failed to set package ACLs on %ws.`
- `0x18004ef5e`: `Failed to get the package capability SID for package %ws.`
- `0x18004ef27`: `Failed to get the package SID for package %ws.`

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
  int v33; // [rsp+20h] [rbp-118h]
  char *v34; // [rsp+28h] [rbp-110h]
  char v35; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v36[7]; // [rsp+31h] [rbp-107h] BYREF
  __int64 v37; // [rsp+38h] [rbp-100h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-F8h] BYREF
  LPVOID v39; // [rsp+48h] [rbp-F0h] BYREF
  _BYTE v40[80]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v41[80]; // [rsp+A0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    v5 = a3 | 2;
    v36[0] = 0;
    v6 = *(__int64 **)(a1 + 240);
    if ( !v6 )
      goto LABEL_58;
    v37 = 0;
    v7 = *v6;
    v37 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 56))(v6, &v37);
    if ( v8 < 0 )
    {
      pv = 0;
      v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             &pv,
             L"Failed to get manifest reader from package. hr=0x%x",
             (unsigned int)v8);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x46D,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v9,
          v33);
      v33 = 2;
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v11,
          2);
      if ( v10 )
        CoTaskMemFree(v10);
      goto LABEL_50;
    }
    pv = 0;
    (**(void (__fastcall ***)(__int64, GUID *, LPVOID *))v37)(v37, &GUID_c43825ab_69b7_400a_9709_cc37f5a72d24, &pv);
    if ( v37 )
    {
      v17 = HasCentennial(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 584LL), v37, v36);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x496,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to determine if the package in question contains any runFullTrust components.",
          v34);
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        return (unsigned int)v17;
      }
      if ( !v36[0] )
      {
        v35 = 0;
        HasInprocMediaExtensionCapability = MsixPackage::Provisioning::Library::MsixPackageAdapter::HasInprocMediaExtensionCapability(
                                              v16,
                                              &pv,
                                              &v35);
        if ( HasInprocMediaExtensionCapability < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x49C,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)HasInprocMediaExtensionCapability,
            (int)"Failed to check package for inprocMediaExtension capability.",
            v34);
          if ( pv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( v37 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          return (unsigned int)HasInprocMediaExtensionCapability;
        }
        if ( v35 )
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
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            return (unsigned int)v21;
          }
        }
      }
      v35 = 0;
      HasDependencyTargetCapability = MsixPackage::Provisioning::Library::MsixPackageAdapter::HasDependencyTargetCapability(
                                        v16,
                                        &pv,
                                        &v35);
      if ( HasDependencyTargetCapability < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4AA,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)HasDependencyTargetCapability,
          (int)"Failed to check package for dependencyTarget capability.",
          v34);
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        return (unsigned int)HasDependencyTargetCapability;
      }
      if ( !v35 )
        goto LABEL_48;
      v39 = 0;
      v23 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v39,
              L"%s provisioned as dependencyTarget package.",
              a2);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B4,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v23,
          v33);
      v5 |= 0x4000uLL;
      v15 = v39;
      if ( !v39 )
        goto LABEL_48;
    }
    else
    {
      v39 = 0;
      v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v39,
              L"Failed to get internal manifest reader interface.");
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x485,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v12,
          v33);
      v33 = 2;
      v13 = v39;
      v14 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              v39,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
              1165);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x48D,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v14,
          2);
      if ( !v13 )
        goto LABEL_48;
      v15 = v13;
    }
    CoTaskMemFree(v15);
LABEL_48:
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_50:
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v36[0] )
    {
      v39 = 0;
      v24 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v39,
              L"%s provisioned as full trust package.",
              a2);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C7,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v24,
          v33);
      v25 = v39;
      v26 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              v39,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
              1231);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CF,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v26,
          2);
      v5 |= 1uLL;
LABEL_62:
      if ( v25 )
        CoTaskMemFree(v25);
      v29 = (const char *)(*(_QWORD *)(a1 + 16) + 768LL);
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 16) + 792LL) >= 8u )
        v29 = *(const char **)v29;
      memset_0(v40, 0, 0x44u);
      memset_0(v41, 0, 0x44u);
      v30 = FamilyMonikerStringToSid(v29, 68, v40);
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
      v30 = PackageSidToPackageCapabilitySid(v40, 68, v41);
      if ( v30 < 0 )
      {
        v31 = 1400;
        v32 = "Failed to get the package capability SID for package %ws.";
        goto LABEL_72;
      }
      v30 = ApplyPackageRootFolderACLs(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 584LL), a2, v40, v41, v29, v5);
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
    v39 = 0;
    v27 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v39,
            L"%s provisioned as partial trust package.",
            a2);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DD,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v27,
        v33);
    v25 = v39;
    v28 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            v39,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            L"MsixPackage::Provisioning::Library::MsixPackageAdapter::SetPackageACLs",
            1253);
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4E5,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v28,
        2);
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
0x18004e944  push    rbx
0x18004e946  push    rsi
0x18004e947  push    rdi
0x18004e948  push    r12
0x18004e94a  push    r13
0x18004e94c  push    r14
0x18004e94e  push    r15
0x18004e950  sub     rsp, 100h
0x18004e957  mov     rax, cs:__security_cookie
0x18004e95e  xor     rax, rsp
0x18004e961  mov     [rsp+138h+var_48], rax
0x18004e969  mov     rsi, r8
0x18004e96c  mov     r14, rdx
0x18004e96f  mov     r15, rcx
0x18004e972  mov     r13d, 2
0x18004e978  or      rsi, r13
0x18004e97b  xor     r12d, r12d
0x18004e97e  mov     [rsp+138h+var_107], r12b
0x18004e983  mov     rcx, [rcx+0F0h]
0x18004e98a  test    rcx, rcx
0x18004e98d  jz      loc_18004EE31
0x18004e993  mov     [rsp+138h+var_100], r12
0x18004e998  mov     rax, [rcx]
0x18004e99b  mov     [rsp+138h+var_100], r12
0x18004e9a0  lea     rdx, [rsp+138h+var_100]
0x18004e9a5  mov     rax, [rax+38h]
0x18004e9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9ae  mov     ebx, eax
0x18004e9b0  test    eax, eax
0x18004e9b2  jns     loc_18004EA58
0x18004e9b8  mov     [rsp+138h+pv], r12
0x18004e9bd  mov     r8d, eax
0x18004e9c0  lea     rdx, aFailedToGetMan_3; "Failed to get manifest reader from pack"...
0x18004e9c7  lea     rcx, [rsp+138h+pv]
0x18004e9cc  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004e9d1  mov     rcx, [rsp+138h]; this
0x18004e9d9  test    eax, eax
0x18004e9db  jns     short loc_18004E9F1
0x18004e9dd  mov     r9d, eax; char *
0x18004e9e0  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e9e7  mov     edx, 46Dh; void *
0x18004e9ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e9f1  mov     dword ptr [rsp+138h+var_110], ebx
0x18004e9f5  mov     [rsp+138h+var_118], r13d; int
0x18004e9fa  mov     edi, 476h
0x18004e9ff  mov     r9d, edi
0x18004ea02  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004ea09  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ea10  mov     rbx, [rsp+138h+pv]
0x18004ea15  mov     rcx, rbx
0x18004ea18  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004ea1d  mov     rcx, [rsp+138h]; this
0x18004ea25  test    eax, eax
0x18004ea27  jns     short loc_18004EA3B
0x18004ea29  mov     r9d, eax; char *
0x18004ea2c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ea33  mov     edx, edi; void *
0x18004ea35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ea3a  nop
0x18004ea3b  test    rbx, rbx
0x18004ea3e  jz      loc_18004ED82
0x18004ea44  mov     rcx, rbx; pv
0x18004ea47  call    cs:__imp_CoTaskMemFree
0x18004ea4e  nop     dword ptr [rax+rax+00h]
0x18004ea53  jmp     loc_18004ED82
0x18004ea58  mov     [rsp+138h+pv], r12
0x18004ea5d  mov     rcx, [rsp+138h+var_100]
0x18004ea62  mov     rax, [rcx]
0x18004ea65  lea     r8, [rsp+138h+pv]
0x18004ea6a  lea     rdx, _GUID_c43825ab_69b7_400a_9709_cc37f5a72d24
0x18004ea71  mov     rax, [rax]
0x18004ea74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea79  mov     rdx, [rsp+138h+var_100]
0x18004ea7e  test    rdx, rdx
0x18004ea81  jnz     loc_18004EB19
0x18004ea87  mov     [rsp+138h+var_F0], r12
0x18004ea8c  lea     rdx, aFailedToGetInt_0; "Failed to get internal manifest reader "...
0x18004ea93  lea     rcx, [rsp+138h+var_F0]
0x18004ea98  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004ea9d  mov     rcx, [rsp+138h]; this
0x18004eaa5  test    eax, eax
0x18004eaa7  jns     short loc_18004EABD
0x18004eaa9  mov     r9d, eax; char *
0x18004eaac  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004eab3  mov     edx, 485h; void *
0x18004eab8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eabd  mov     dword ptr [rsp+138h+var_110], r12d
0x18004eac2  mov     [rsp+138h+var_118], r13d; int
0x18004eac7  mov     edi, 48Dh
0x18004eacc  mov     r9d, edi
0x18004eacf  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004ead6  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004eadd  mov     rbx, [rsp+138h+var_F0]
0x18004eae2  mov     rcx, rbx
0x18004eae5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004eaea  mov     rcx, [rsp+138h]; this
0x18004eaf2  test    eax, eax
0x18004eaf4  jns     short loc_18004EB08
0x18004eaf6  mov     r9d, eax; char *
0x18004eaf9  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004eb00  mov     edx, edi; void *
0x18004eb02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eb07  nop
0x18004eb08  test    rbx, rbx
0x18004eb0b  jz      loc_18004ED6B
0x18004eb11  mov     rcx, rbx
0x18004eb14  jmp     loc_18004ED5E
0x18004eb19  mov     rcx, [r15+10h]
0x18004eb1d  lea     r8, [rsp+138h+var_107]
0x18004eb22  mov     rcx, [rcx+248h]
0x18004eb29  call    cs:__imp_HasCentennial
0x18004eb30  nop     dword ptr [rax+rax+00h]
0x18004eb35  mov     ebx, eax
0x18004eb37  test    eax, eax
0x18004eb39  jns     short loc_18004EB99
0x18004eb3b  mov     rcx, [rsp+138h]; this
0x18004eb43  lea     rax, aFailedToDeterm_9; "Failed to determine if the package in q"...
0x18004eb4a  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004eb4f  mov     r9d, ebx; char *
0x18004eb52  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004eb59  mov     edx, 496h; void *
0x18004eb5e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004eb63  nop
0x18004eb64  mov     rcx, [rsp+138h+pv]
0x18004eb69  test    rcx, rcx
0x18004eb6c  jz      short loc_18004EB7B
0x18004eb6e  mov     rax, [rcx]
0x18004eb71  mov     rax, [rax+10h]
0x18004eb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb7a  nop
0x18004eb7b  mov     rcx, [rsp+138h+var_100]
0x18004eb80  test    rcx, rcx
0x18004eb83  jz      short loc_18004EB92
0x18004eb85  mov     rax, [rcx]
0x18004eb88  mov     rax, [rax+10h]
0x18004eb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb91  nop
0x18004eb92  mov     eax, ebx
0x18004eb94  jmp     loc_18004F003
0x18004eb99  cmp     [rsp+138h+var_107], r12b
0x18004eb9e  jnz     loc_18004EC97
0x18004eba4  mov     [rsp+138h+var_108], r12b
0x18004eba9  lea     r8, [rsp+138h+var_108]
0x18004ebae  lea     rdx, [rsp+138h+pv]
0x18004ebb3  call    ?HasInprocMediaExtensionCapability@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@AEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::HasInprocMediaExtensionCapability(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,bool &)
0x18004ebb8  mov     ebx, eax
0x18004ebba  test    eax, eax
0x18004ebbc  jns     short loc_18004EC1C
0x18004ebbe  mov     rcx, [rsp+138h]; this
0x18004ebc6  lea     rax, aFailedToCheckP; "Failed to check package for inprocMedia"...
0x18004ebcd  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004ebd2  mov     r9d, ebx; char *
0x18004ebd5  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ebdc  mov     edx, 49Ch; void *
0x18004ebe1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ebe6  nop
0x18004ebe7  mov     rcx, [rsp+138h+pv]
0x18004ebec  test    rcx, rcx
0x18004ebef  jz      short loc_18004EBFE
0x18004ebf1  mov     rax, [rcx]
0x18004ebf4  mov     rax, [rax+10h]
0x18004ebf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebfd  nop
0x18004ebfe  mov     rcx, [rsp+138h+var_100]
0x18004ec03  test    rcx, rcx
0x18004ec06  jz      short loc_18004EC15
0x18004ec08  mov     rax, [rcx]
0x18004ec0b  mov     rax, [rax+10h]
0x18004ec0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec14  nop
0x18004ec15  mov     eax, ebx
0x18004ec17  jmp     loc_18004F003
0x18004ec1c  cmp     [rsp+138h+var_108], r12b
0x18004ec21  jz      short loc_18004EC97
0x18004ec23  mov     r8, rsi
0x18004ec26  mov     rdx, r14
0x18004ec29  call    ?SetFrameworkACLs@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEBGW4Flags@AppxAllUserStore@@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::SetFrameworkACLs(ushort const *,AppxAllUserStore::Flags)
0x18004ec2e  mov     ebx, eax
0x18004ec30  test    eax, eax
0x18004ec32  jns     short loc_18004EC97
0x18004ec34  mov     rcx, [rsp+138h]; this
0x18004ec3c  mov     [rsp+138h+var_110], r14; char *
0x18004ec41  lea     rax, aFailedWhileSet_0; "Failed while setting ACLs for package w"...
0x18004ec48  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004ec4d  mov     r9d, ebx; char *
0x18004ec50  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ec57  mov     edx, 4A5h; void *
0x18004ec5c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ec61  nop
0x18004ec62  mov     rcx, [rsp+138h+pv]
0x18004ec67  test    rcx, rcx
0x18004ec6a  jz      short loc_18004EC79
0x18004ec6c  mov     rax, [rcx]
0x18004ec6f  mov     rax, [rax+10h]
0x18004ec73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec78  nop
0x18004ec79  mov     rcx, [rsp+138h+var_100]
0x18004ec7e  test    rcx, rcx
0x18004ec81  jz      short loc_18004EC90
0x18004ec83  mov     rax, [rcx]
0x18004ec86  mov     rax, [rax+10h]
0x18004ec8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec8f  nop
0x18004ec90  mov     eax, ebx
0x18004ec92  jmp     loc_18004F003
0x18004ec97  mov     [rsp+138h+var_108], r12b
0x18004ec9c  lea     r8, [rsp+138h+var_108]
0x18004eca1  lea     rdx, [rsp+138h+pv]
0x18004eca6  call    ?HasDependencyTargetCapability@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@AEA_N@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::HasDependencyTargetCapability(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,bool &)
0x18004ecab  mov     ebx, eax
0x18004ecad  test    eax, eax
0x18004ecaf  jns     short loc_18004ED0F
0x18004ecb1  mov     rcx, [rsp+138h]; this
0x18004ecb9  lea     rax, aFailedToCheckP_0; "Failed to check package for dependencyT"...
0x18004ecc0  mov     qword ptr [rsp+138h+var_118], rax; int
0x18004ecc5  mov     r9d, ebx; char *
0x18004ecc8  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004eccf  mov     edx, 4AAh; void *
0x18004ecd4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004ecd9  nop
0x18004ecda  mov     rcx, [rsp+138h+pv]
0x18004ecdf  test    rcx, rcx
0x18004ece2  jz      short loc_18004ECF1
0x18004ece4  mov     rax, [rcx]
0x18004ece7  mov     rax, [rax+10h]
0x18004eceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecf0  nop
0x18004ecf1  mov     rcx, [rsp+138h+var_100]
0x18004ecf6  test    rcx, rcx
0x18004ecf9  jz      short loc_18004ED08
0x18004ecfb  mov     rax, [rcx]
0x18004ecfe  mov     rax, [rax+10h]
0x18004ed02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed07  nop
0x18004ed08  mov     eax, ebx
0x18004ed0a  jmp     loc_18004F003
0x18004ed0f  cmp     [rsp+138h+var_108], r12b
0x18004ed14  jz      short loc_18004ED6B
0x18004ed16  mov     [rsp+138h+var_F0], r12
0x18004ed1b  mov     r8, r14
0x18004ed1e  lea     rdx, aSProvisionedAs; "%s provisioned as dependencyTarget pack"...
0x18004ed25  lea     rcx, [rsp+138h+var_F0]
0x18004ed2a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004ed2f  mov     rcx, [rsp+138h]; this
0x18004ed37  test    eax, eax
0x18004ed39  jns     short loc_18004ED4F
0x18004ed3b  mov     r9d, eax; char *
0x18004ed3e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ed45  mov     edx, 4B4h; void *
0x18004ed4a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ed4f  bts     rsi, 0Eh
0x18004ed54  mov     rcx, [rsp+138h+var_F0]; pv
0x18004ed59  test    rcx, rcx
0x18004ed5c  jz      short loc_18004ED6B
0x18004ed5e  call    cs:__imp_CoTaskMemFree
0x18004ed65  nop     dword ptr [rax+rax+00h]
0x18004ed6a  nop
0x18004ed6b  mov     rcx, [rsp+138h+pv]
0x18004ed70  test    rcx, rcx
0x18004ed73  jz      short loc_18004ED82
0x18004ed75  mov     rax, [rcx]
0x18004ed78  mov     rax, [rax+10h]
0x18004ed7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed81  nop
0x18004ed82  mov     rcx, [rsp+138h+var_100]
0x18004ed87  test    rcx, rcx
0x18004ed8a  jz      short loc_18004ED99
0x18004ed8c  mov     rax, [rcx]
0x18004ed8f  mov     rax, [rax+10h]
0x18004ed93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed98  nop
0x18004ed99  cmp     [rsp+138h+var_107], r12b
0x18004ed9e  jz      loc_18004EE31
0x18004eda4  mov     [rsp+138h+var_F0], r12
0x18004eda9  mov     r8, r14
0x18004edac  lea     rdx, aSProvisionedAs_0; "%s provisioned as full trust package."
0x18004edb3  lea     rcx, [rsp+138h+var_F0]
0x18004edb8  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004edbd  mov     rcx, [rsp+138h]; this
0x18004edc5  test    eax, eax
0x18004edc7  jns     short loc_18004EDDD
0x18004edc9  mov     r9d, eax; char *
0x18004edcc  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004edd3  mov     edx, 4C7h; void *
0x18004edd8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eddd  mov     dword ptr [rsp+138h+var_110], r12d
0x18004ede2  mov     [rsp+138h+var_118], r13d; int
0x18004ede7  mov     edi, 4CFh
0x18004edec  mov     r9d, edi
0x18004edef  lea     r8, aMsixpackagePro_20; "MsixPackage::Provisioning::Library::Msi"...
0x18004edf6  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004edfd  mov     rbx, [rsp+138h+var_F0]
0x18004ee02  mov     rcx, rbx
0x18004ee05  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004ee0a  mov     rcx, [rsp+138h]; this
0x18004ee12  test    eax, eax
0x18004ee14  jns     short loc_18004EE28
0x18004ee16  mov     r9d, eax; char *
0x18004ee19  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004ee20  mov     edx, edi; void *
  ... truncated ...
```
