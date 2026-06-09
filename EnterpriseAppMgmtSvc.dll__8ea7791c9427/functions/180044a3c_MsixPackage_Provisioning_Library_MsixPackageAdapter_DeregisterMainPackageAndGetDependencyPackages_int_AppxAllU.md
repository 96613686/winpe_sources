# MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)

- ea: `0x180044a3c`
- end: `0x180044cd2`
- name: `?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z`
- size: `662`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, struct AppxAllUserStore::_PackageInfo **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044cd8`
- `0x180049a44`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180044a3c`
- `0x180049f94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044c96`
- `AppXAllUserStore!RemovePackageFromRegistryStore` at `0x180044aa9`
- `AppXAllUserStore!RemovePackageFromRegistryStore` at `0x180044aa9`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180044bc5`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180044bc5`

## string_xrefs

- `0x180044ad2`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044b72`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044bee`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044a65`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044bf5`: `Failed to remove package from all staged packages list in all user store`
- `0x180044ca3`: `Failed to remove package from all staged packages list in all user store`
- `0x180044b26`: `Failed to remove license for package '%s'`
- `0x180044ad9`: `Failed to get the list of packages to remove`
- `0x180044c3b`: `Failed to get the list of packages to remove`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        int a2,
        struct AppxAllUserStore::_PackageInfo **a3,
        unsigned int *a4)
{
  int v6; // r10d
  int v7; // r10d
  int v8; // r10d
  char *v9; // rbx
  char *v10; // rdx
  int v11; // esi
  int v12; // eax
  int v13; // eax
  void *v14; // rbx
  int v15; // eax
  _QWORD *v16; // rdx
  int v17; // ebx
  int v18; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  *a4 = 0;
  *a3 = 0;
  v6 = *((_DWORD *)this + 9);
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 )
        goto LABEL_22;
      if ( v8 != 2 )
      {
LABEL_28:
        *((_DWORD *)this + 6) = 4;
        return 0;
      }
    }
  }
  v9 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v10 = (char *)this + 48;
  else
    v10 = *(char **)v9;
  v11 = RemovePackageFromRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v10);
  if ( v11 < 0 )
  {
    if ( !a2 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x71C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v11,
        (int)"%ws",
        L"Failed to get the list of packages to remove");
      return (unsigned int)v11;
    }
    v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            L"Failed to get the list of packages to remove",
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1820);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x71C,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12);
  }
  v11 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(this);
  if ( v11 < 0 )
  {
    pv = 0;
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(char **)v9;
    v13 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&pv,
            L"Failed to remove license for package '%s'",
            v9);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x722,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v13);
    v14 = pv;
    if ( a2 )
    {
      v15 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              pv,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              0,
              1826);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x722,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v15);
      if ( v14 )
        CoTaskMemFree(v14);
      goto LABEL_22;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x722,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11,
      (int)"%ws",
      (const char *)pv);
    if ( v14 )
      CoTaskMemFree(v14);
    return (unsigned int)v11;
  }
LABEL_22:
  v16 = (_QWORD *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) >= 8u )
    v16 = (_QWORD *)*v16;
  v17 = RemoveStagedPackageFromRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v16, 0);
  if ( v17 >= 0 )
    goto LABEL_28;
  if ( a2 )
  {
    v18 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            L"Failed to remove package from all staged packages list in all user store",
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1833);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x729,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x729,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v17,
    (int)"%ws",
    L"Failed to remove package from all staged packages list in all user store");
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180044a3c  mov     [rsp+arg_8], rbx
0x180044a41  mov     [rsp+arg_10], rbp
0x180044a46  push    rsi
0x180044a47  push    rdi
0x180044a48  push    r15
0x180044a4a  sub     rsp, 30h
0x180044a4e  mov     ebp, edx
0x180044a50  mov     rdi, rcx
0x180044a53  mov     dword ptr [r9], 0
0x180044a5a  mov     qword ptr [r8], 0
0x180044a61  mov     r10d, [rcx+24h]
0x180044a65  lea     r15, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044a6c  test    r10d, r10d
0x180044a6f  jz      short loc_180044A8B
0x180044a71  sub     r10d, 1
0x180044a75  jz      short loc_180044A8B
0x180044a77  sub     r10d, 1
0x180044a7b  jz      loc_180044BA9
0x180044a81  cmp     r10d, 2
0x180044a85  jnz     loc_180044C1A
0x180044a8b  lea     rbx, [rcx+30h]
0x180044a8f  cmp     qword ptr [rbx+18h], 8
0x180044a94  jb      short loc_180044A9B
0x180044a96  mov     rdx, [rbx]
0x180044a99  jmp     short loc_180044A9E
0x180044a9b  mov     rdx, rbx
0x180044a9e  mov     rcx, [rcx+10h]
0x180044aa2  mov     rcx, [rcx+248h]
0x180044aa9  call    cs:__imp_RemovePackageFromRegistryStore
0x180044aaf  mov     esi, eax
0x180044ab1  test    eax, eax
0x180044ab3  jns     short loc_180044AFE
0x180044ab5  test    ebp, ebp
0x180044ab7  jz      loc_180044C36
0x180044abd  mov     dword ptr [rsp+48h+var_20], eax
0x180044ac1  mov     [rsp+48h+var_28], 1; int
0x180044ac9  mov     r9d, 71Ch
0x180044acf  xor     r8d, r8d
0x180044ad2  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044ad9  lea     rcx, aFailedToGetThe_1; "Failed to get the list of packages to r"...
0x180044ae0  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180044ae5  mov     rcx, [rsp+48h]; this
0x180044aea  test    eax, eax
0x180044aec  jns     short loc_180044AFE
0x180044aee  mov     r9d, eax; char *
0x180044af1  mov     r8, r15; unsigned int
0x180044af4  mov     edx, 71Ch; void *
0x180044af9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044afe  mov     rcx, rdi; this
0x180044b01  call    ?RemovePackageLicense@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(void)
0x180044b06  mov     esi, eax
0x180044b08  test    eax, eax
0x180044b0a  jns     loc_180044BA9
0x180044b10  mov     [rsp+48h+pv], 0
0x180044b19  cmp     qword ptr [rbx+18h], 8
0x180044b1e  jb      short loc_180044B23
0x180044b20  mov     rbx, [rbx]
0x180044b23  mov     r8, rbx
0x180044b26  lea     rdx, aFailedToRemove_3; "Failed to remove license for package '%"...
0x180044b2d  lea     rcx, [rsp+48h+pv]
0x180044b32  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180044b37  mov     rcx, [rsp+48h]; this
0x180044b3c  test    eax, eax
0x180044b3e  jns     short loc_180044B50
0x180044b40  mov     r9d, eax; char *
0x180044b43  mov     r8, r15; unsigned int
0x180044b46  mov     edx, 722h; void *
0x180044b4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044b50  mov     rbx, [rsp+48h+pv]
0x180044b55  test    ebp, ebp
0x180044b57  jz      loc_180044C67
0x180044b5d  mov     dword ptr [rsp+48h+var_20], esi
0x180044b61  mov     [rsp+48h+var_28], 1; int
0x180044b69  mov     r9d, 722h
0x180044b6f  xor     r8d, r8d
0x180044b72  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044b79  mov     rcx, rbx
0x180044b7c  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180044b81  mov     rcx, [rsp+48h]; this
0x180044b86  test    eax, eax
0x180044b88  jns     short loc_180044B9B
0x180044b8a  mov     r9d, eax; char *
0x180044b8d  mov     r8, r15; unsigned int
0x180044b90  mov     edx, 722h; void *
0x180044b95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044b9a  nop
0x180044b9b  test    rbx, rbx
0x180044b9e  jz      short loc_180044BA9
0x180044ba0  mov     rcx, rbx; pv
0x180044ba3  call    cs:__imp_CoTaskMemFree
0x180044ba9  lea     rdx, [rdi+30h]
0x180044bad  cmp     qword ptr [rdx+18h], 8
0x180044bb2  jb      short loc_180044BB7
0x180044bb4  mov     rdx, [rdx]
0x180044bb7  mov     rcx, [rdi+10h]
0x180044bbb  xor     r8d, r8d
0x180044bbe  mov     rcx, [rcx+248h]
0x180044bc5  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180044bcb  mov     ebx, eax
0x180044bcd  test    eax, eax
0x180044bcf  jns     short loc_180044C1A
0x180044bd1  test    ebp, ebp
0x180044bd3  jz      loc_180044C9E
0x180044bd9  mov     dword ptr [rsp+48h+var_20], eax
0x180044bdd  mov     [rsp+48h+var_28], 1; int
0x180044be5  mov     r9d, 729h
0x180044beb  xor     r8d, r8d
0x180044bee  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044bf5  lea     rcx, aFailedToRemove_6; "Failed to remove package from all stage"...
0x180044bfc  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180044c01  test    eax, eax
0x180044c03  jns     short loc_180044C1A
0x180044c05  mov     rcx, [rsp+48h]; this
0x180044c0a  mov     r9d, eax; char *
0x180044c0d  mov     r8, r15; unsigned int
0x180044c10  mov     edx, 729h; void *
0x180044c15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044c1a  mov     dword ptr [rdi+18h], 4
0x180044c21  xor     eax, eax
0x180044c23  mov     rbx, [rsp+48h+arg_8]
0x180044c28  mov     rbp, [rsp+48h+arg_10]
0x180044c2d  add     rsp, 30h
0x180044c31  pop     r15
0x180044c33  pop     rdi
0x180044c34  pop     rsi
0x180044c35  retn
0x180044c36  mov     rcx, [rsp+48h]; this
0x180044c3b  lea     rax, aFailedToGetThe_1; "Failed to get the list of packages to r"...
0x180044c42  mov     [rsp+48h+var_20], rax; char *
0x180044c47  lea     rax, aWs; "%ws"
0x180044c4e  mov     qword ptr [rsp+48h+var_28], rax; int
0x180044c53  mov     r9d, esi; char *
0x180044c56  mov     r8, r15; unsigned int
0x180044c59  mov     edx, 71Ch; void *
0x180044c5e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044c63  mov     eax, esi
0x180044c65  jmp     short loc_180044C23
0x180044c67  mov     rcx, [rsp+48h]; this
0x180044c6c  mov     [rsp+48h+var_20], rbx; char *
0x180044c71  lea     rax, aWs; "%ws"
0x180044c78  mov     qword ptr [rsp+48h+var_28], rax; int
0x180044c7d  mov     r9d, esi; char *
0x180044c80  mov     r8, r15; unsigned int
0x180044c83  mov     edx, 722h; void *
0x180044c88  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044c8d  nop
0x180044c8e  test    rbx, rbx
0x180044c91  jz      short loc_180044C63
0x180044c93  mov     rcx, rbx; pv
0x180044c96  call    cs:__imp_CoTaskMemFree
0x180044c9c  jmp     short loc_180044C63
0x180044c9e  mov     rcx, [rsp+48h]; this
0x180044ca3  lea     rax, aFailedToRemove_6; "Failed to remove package from all stage"...
0x180044caa  mov     [rsp+48h+var_20], rax; char *
0x180044caf  lea     rax, aWs; "%ws"
0x180044cb6  mov     qword ptr [rsp+48h+var_28], rax; int
0x180044cbb  mov     r9d, ebx; char *
0x180044cbe  mov     r8, r15; unsigned int
0x180044cc1  mov     edx, 729h; void *
0x180044cc6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044ccb  mov     eax, ebx
0x180044ccd  jmp     loc_180044C23
```
