# MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(int)

- ea: `0x180048bd8`
- end: `0x180048de4`
- name: `?DeregisterPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z`
- size: `524`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e4b0`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180048920`
- `0x180048bd8`
- `0x18005125c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048db6`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180048d03`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180048d03`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048c98`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048d30`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048dd1`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048c98`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048d30`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180048dd1`

## string_xrefs

- `0x180048c71`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048d75`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048d9f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048c48`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
           (__int64)&v14);
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
          &pv,
          L"Failed to deregister staged package'%s'",
          v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11,
      v13);
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
0x180048bd8  mov     [rsp-28h+arg_8], edx
0x180048bdc  push    rbp
0x180048bdd  push    rbx
0x180048bde  push    rsi
0x180048bdf  push    rdi
0x180048be0  push    r14
0x180048be2  mov     rbp, rsp
0x180048be5  sub     rsp, 60h
0x180048be9  mov     r14, rcx
0x180048bec  mov     [rbp+arg_8], 0
0x180048bf3  mov     [rbp+arg_0], 0
0x180048bfb  lea     rax, [rbp+arg_0]
0x180048bff  mov     [rbp+var_20], rax
0x180048c03  lea     rax, [rbp+arg_8]
0x180048c07  mov     [rbp+var_18], rax
0x180048c0b  mov     [rbp+var_10], 1
0x180048c0f  mov     rcx, [rcx+0D8h]
0x180048c16  test    rcx, rcx
0x180048c19  jz      loc_180048CAB
0x180048c1f  mov     [rbp+var_30], rcx
0x180048c23  mov     [rbp+var_28], 0
0x180048c2a  mov     eax, [rbp+var_24]
0x180048c2d  mov     [rbp+var_24], eax
0x180048c30  lea     r8, [rbp+var_30]
0x180048c34  xor     edx, edx
0x180048c36  call    MsixPackage__Provisioning__Library__MsixProvisioningRequest__ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___
0x180048c3b  mov     ebx, eax
0x180048c3d  test    eax, eax
0x180048c3f  jns     short loc_180048CAB
0x180048c41  mov     rcx, [rbp+28h]; this
0x180048c45  mov     r9d, eax; char *
0x180048c48  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048c4f  mov     edx, 322h; void *
0x180048c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048c59  lea     rax, aFailedToDeregi; "Failed to deregister related packages"
0x180048c60  mov     edx, 10Bh; void *
0x180048c65  mov     [rsp+60h+var_38], rax; char *
0x180048c6a  lea     rax, aWs; "%ws"
0x180048c71  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048c78  mov     r9d, ebx; char *
0x180048c7b  mov     qword ptr [rsp+60h+var_40], rax; int
0x180048c80  mov     rcx, [rbp+28h]; this
0x180048c84  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048c89  nop
0x180048c8a  cmp     [rbp+arg_0], 0
0x180048c8f  jz      short loc_180048CA4
0x180048c91  lea     rdx, [rbp+arg_0]
0x180048c95  mov     ecx, [rbp+arg_8]
0x180048c98  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180048c9f  nop     dword ptr [rax+rax+00h]
0x180048ca4  mov     eax, ebx
0x180048ca6  jmp     loc_180048D3E
0x180048cab  lea     r9, [rbp+arg_8]; unsigned int *
0x180048caf  lea     r8, [rbp+arg_0]; struct AppxAllUserStore::_PackageInfo **
0x180048cb3  xor     edx, edx; int
0x180048cb5  mov     rcx, r14; this
0x180048cb8  call    ?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)
0x180048cbd  mov     ebx, eax
0x180048cbf  test    eax, eax
0x180048cc1  jns     short loc_180048CD1
0x180048cc3  lea     rax, aFailedToDeregi_3; "Failed to deregister main package and g"...
0x180048cca  mov     edx, 112h
0x180048ccf  jmp     short loc_180048C65
0x180048cd1  mov     rdx, [rbp+arg_0]
0x180048cd5  mov     r8d, [rbp+arg_8]
0x180048cd9  test    rdx, rdx
0x180048cdc  jz      short loc_180048D24
0x180048cde  xor     ebx, ebx
0x180048ce0  test    r8d, r8d
0x180048ce3  jz      short loc_180048D24
0x180048ce5  lea     rcx, [rbx+rbx*2]
0x180048ce9  mov     rsi, [rdx+rcx*8]
0x180048ced  test    rsi, rsi
0x180048cf0  jz      short loc_180048D1D
0x180048cf2  mov     rcx, [r14+10h]
0x180048cf6  mov     r8b, 1
0x180048cf9  mov     rdx, rsi
0x180048cfc  mov     rcx, [rcx+248h]
0x180048d03  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180048d0a  nop     dword ptr [rax+rax+00h]
0x180048d0f  mov     edi, eax
0x180048d11  test    eax, eax
0x180048d13  js      short loc_180048D4A
0x180048d15  mov     r8d, [rbp+arg_8]
0x180048d19  mov     rdx, [rbp+arg_0]
0x180048d1d  inc     ebx
0x180048d1f  cmp     ebx, r8d
0x180048d22  jb      short loc_180048CE5
0x180048d24  test    rdx, rdx
0x180048d27  jz      short loc_180048D3C
0x180048d29  lea     rdx, [rbp+arg_0]
0x180048d2d  mov     ecx, r8d
0x180048d30  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180048d37  nop     dword ptr [rax+rax+00h]
0x180048d3c  xor     eax, eax
0x180048d3e  add     rsp, 60h
0x180048d42  pop     r14
0x180048d44  pop     rdi
0x180048d45  pop     rsi
0x180048d46  pop     rbx
0x180048d47  pop     rbp
0x180048d48  retn
0x180048d4a  mov     [rbp+pv], 0
0x180048d52  mov     r8, rsi
0x180048d55  lea     rdx, aFailedToDeregi_2; "Failed to deregister staged package'%s'"
0x180048d5c  lea     rcx, [rbp+pv]
0x180048d60  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180048d65  mov     rcx, [rbp+28h]; this
0x180048d69  mov     esi, 121h
0x180048d6e  test    eax, eax
0x180048d70  jns     short loc_180048D83
0x180048d72  mov     r9d, eax; char *
0x180048d75  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048d7c  mov     edx, esi; void *
0x180048d7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048d83  mov     rcx, [rbp+28h]; this
0x180048d87  mov     rbx, [rbp+pv]
0x180048d8b  mov     [rsp+60h+var_38], rbx; char *
0x180048d90  lea     rax, aWs; "%ws"
0x180048d97  mov     qword ptr [rsp+60h+var_40], rax; int
0x180048d9c  mov     r9d, edi; char *
0x180048d9f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048da6  mov     edx, esi; void *
0x180048da8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048dad  nop
0x180048dae  test    rbx, rbx
0x180048db1  jz      short loc_180048DC3
0x180048db3  mov     rcx, rbx; pv
0x180048db6  call    cs:__imp_CoTaskMemFree
0x180048dbd  nop     dword ptr [rax+rax+00h]
0x180048dc2  nop
0x180048dc3  cmp     [rbp+arg_0], 0
0x180048dc8  jz      short loc_180048DDD
0x180048dca  lea     rdx, [rbp+arg_0]
0x180048dce  mov     ecx, [rbp+arg_8]
0x180048dd1  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180048dd8  nop     dword ptr [rax+rax+00h]
0x180048ddd  mov     eax, edi
0x180048ddf  jmp     loc_180048D3E
```
