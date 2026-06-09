# MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(int)

- ea: `0x180044cd8`
- end: `0x180044ec5`
- name: `?DeregisterPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z`
- size: `493`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a334`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180044a3c`
- `0x180044cd8`
- `0x18004cfe8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ea3`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180044dfd`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180044dfd`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044d98`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044e24`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044eb8`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044d98`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044e24`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180044eb8`

## string_xrefs

- `0x180044d71`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044e62`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044e8c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180044d48`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int DependencyPackages; // ebx
  struct AppxAllUserStore::_PackageInfo *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rsi
  int v10; // edi
  int v11; // eax
  void *v12; // rbx
  int v13; // [rsp+20h] [rbp-40h]
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+38h] [rbp-28h]
  struct AppxAllUserStore::_PackageInfo **v16; // [rsp+40h] [rbp-20h]
  unsigned int *v17; // [rsp+48h] [rbp-18h]
  char v18; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  struct AppxAllUserStore::_PackageInfo *v20; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF

  v21 = 0;
  v20 = 0;
  v16 = &v20;
  v17 = &v21;
  v18 = 1;
  v2 = *((_QWORD *)this + 27);
  if ( v2 )
  {
    v14 = v2;
    v15 = 0;
    v3 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___(
           v2,
           0,
           &v14);
    DependencyPackages = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x322,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v3,
        v13);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)DependencyPackages,
        (int)"%ws",
        L"Failed to deregister related packages");
LABEL_4:
      if ( v20 )
        DeleteAllPackagesFromPackageArray(v21);
      return DependencyPackages;
    }
  }
  DependencyPackages = MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(
                         this,
                         0,
                         &v20,
                         &v21);
  if ( (DependencyPackages & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)DependencyPackages,
      (int)"%ws",
      (const char *)L"Failed to deregister main package and get its dependent packages");
    goto LABEL_4;
  }
  v6 = v20;
  v7 = v21;
  if ( !v20 || (v8 = 0, !v21) )
  {
LABEL_15:
    if ( v6 )
      DeleteAllPackagesFromPackageArray((unsigned int)v7);
    return 0;
  }
  while ( 1 )
  {
    v9 = *((_QWORD *)v6 + 3 * v8);
    if ( v9 )
      break;
LABEL_14:
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= (unsigned int)v7 )
      goto LABEL_15;
  }
  LOBYTE(v7) = 1;
  v10 = RemoveStagedPackageFromRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), *((_QWORD *)v6 + 3 * v8), v7);
  if ( v10 >= 0 )
  {
    v7 = v21;
    v6 = v20;
    goto LABEL_14;
  }
  pv = 0;
  v11 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (char *)&pv,
          L"Failed to deregister staged package'%s'",
          v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x121,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11);
  v12 = pv;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x121,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v10,
    (int)"%ws",
    (const char *)pv);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v20 )
    DeleteAllPackagesFromPackageArray(v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180044cd8  mov     [rsp-28h+arg_8], edx
0x180044cdc  push    rbp
0x180044cdd  push    rbx
0x180044cde  push    rsi
0x180044cdf  push    rdi
0x180044ce0  push    r14
0x180044ce2  mov     rbp, rsp
0x180044ce5  sub     rsp, 60h
0x180044ce9  mov     r14, rcx
0x180044cec  mov     [rbp+arg_8], 0
0x180044cf3  mov     [rbp+arg_0], 0
0x180044cfb  lea     rax, [rbp+arg_0]
0x180044cff  mov     [rbp+var_20], rax
0x180044d03  lea     rax, [rbp+arg_8]
0x180044d07  mov     [rbp+var_18], rax
0x180044d0b  mov     [rbp+var_10], 1
0x180044d0f  mov     rcx, [rcx+0D8h]
0x180044d16  test    rcx, rcx
0x180044d19  jz      loc_180044DA5
0x180044d1f  mov     [rbp+var_30], rcx
0x180044d23  mov     [rbp+var_28], 0
0x180044d2a  mov     eax, [rbp+var_24]
0x180044d2d  mov     [rbp+var_24], eax
0x180044d30  lea     r8, [rbp+var_30]
0x180044d34  xor     edx, edx
0x180044d36  call    MsixPackage__Provisioning__Library__MsixProvisioningRequest__ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___
0x180044d3b  mov     ebx, eax
0x180044d3d  test    eax, eax
0x180044d3f  jns     short loc_180044DA5
0x180044d41  mov     rcx, [rbp+28h]; this
0x180044d45  mov     r9d, eax; char *
0x180044d48  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044d4f  mov     edx, 322h; void *
0x180044d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044d59  lea     rax, aFailedToDeregi; "Failed to deregister related packages"
0x180044d60  mov     edx, 10Bh; void *
0x180044d65  mov     [rsp+60h+var_38], rax; char *
0x180044d6a  lea     rax, aWs; "%ws"
0x180044d71  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044d78  mov     r9d, ebx; char *
0x180044d7b  mov     qword ptr [rsp+60h+var_40], rax; int
0x180044d80  mov     rcx, [rbp+28h]; this
0x180044d84  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044d89  nop
0x180044d8a  cmp     [rbp+arg_0], 0
0x180044d8f  jz      short loc_180044D9E
0x180044d91  lea     rdx, [rbp+arg_0]
0x180044d95  mov     ecx, [rbp+arg_8]
0x180044d98  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180044d9e  mov     eax, ebx
0x180044da0  jmp     loc_180044E2C
0x180044da5  lea     r9, [rbp+arg_8]; unsigned int *
0x180044da9  lea     r8, [rbp+arg_0]; struct AppxAllUserStore::_PackageInfo **
0x180044dad  xor     edx, edx; int
0x180044daf  mov     rcx, r14; this
0x180044db2  call    ?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)
0x180044db7  mov     ebx, eax
0x180044db9  test    eax, eax
0x180044dbb  jns     short loc_180044DCB
0x180044dbd  lea     rax, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x180044dc4  mov     edx, 112h
0x180044dc9  jmp     short loc_180044D65
0x180044dcb  mov     rdx, [rbp+arg_0]
0x180044dcf  mov     r8d, [rbp+arg_8]
0x180044dd3  test    rdx, rdx
0x180044dd6  jz      short loc_180044E18
0x180044dd8  xor     ebx, ebx
0x180044dda  test    r8d, r8d
0x180044ddd  jz      short loc_180044E18
0x180044ddf  lea     rcx, [rbx+rbx*2]
0x180044de3  mov     rsi, [rdx+rcx*8]
0x180044de7  test    rsi, rsi
0x180044dea  jz      short loc_180044E11
0x180044dec  mov     rcx, [r14+10h]
0x180044df0  mov     r8b, 1
0x180044df3  mov     rdx, rsi
0x180044df6  mov     rcx, [rcx+248h]
0x180044dfd  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180044e03  mov     edi, eax
0x180044e05  test    eax, eax
0x180044e07  js      short loc_180044E37
0x180044e09  mov     r8d, [rbp+arg_8]
0x180044e0d  mov     rdx, [rbp+arg_0]
0x180044e11  inc     ebx
0x180044e13  cmp     ebx, r8d
0x180044e16  jb      short loc_180044DDF
0x180044e18  test    rdx, rdx
0x180044e1b  jz      short loc_180044E2A
0x180044e1d  lea     rdx, [rbp+arg_0]
0x180044e21  mov     ecx, r8d
0x180044e24  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180044e2a  xor     eax, eax
0x180044e2c  add     rsp, 60h
0x180044e30  pop     r14
0x180044e32  pop     rdi
0x180044e33  pop     rsi
0x180044e34  pop     rbx
0x180044e35  pop     rbp
0x180044e36  retn
0x180044e37  mov     [rbp+pv], 0
0x180044e3f  mov     r8, rsi
0x180044e42  lea     rdx, aFailedToDeregi_2; "Failed to deregister staged package'%s'"
0x180044e49  lea     rcx, [rbp+pv]
0x180044e4d  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180044e52  mov     rcx, [rbp+28h]; this
0x180044e56  mov     esi, 121h
0x180044e5b  test    eax, eax
0x180044e5d  jns     short loc_180044E70
0x180044e5f  mov     r9d, eax; char *
0x180044e62  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044e69  mov     edx, esi; void *
0x180044e6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044e70  mov     rcx, [rbp+28h]; this
0x180044e74  mov     rbx, [rbp+pv]
0x180044e78  mov     [rsp+60h+var_38], rbx; char *
0x180044e7d  lea     rax, aWs; "%ws"
0x180044e84  mov     qword ptr [rsp+60h+var_40], rax; int
0x180044e89  mov     r9d, edi; char *
0x180044e8c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180044e93  mov     edx, esi; void *
0x180044e95  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180044e9a  nop
0x180044e9b  test    rbx, rbx
0x180044e9e  jz      short loc_180044EAA
0x180044ea0  mov     rcx, rbx; pv
0x180044ea3  call    cs:__imp_CoTaskMemFree
0x180044ea9  nop
0x180044eaa  cmp     [rbp+arg_0], 0
0x180044eaf  jz      short loc_180044EBE
0x180044eb1  lea     rdx, [rbp+arg_0]
0x180044eb5  mov     ecx, [rbp+arg_8]
0x180044eb8  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180044ebe  mov     eax, edi
0x180044ec0  jmp     loc_180044E2C
```
