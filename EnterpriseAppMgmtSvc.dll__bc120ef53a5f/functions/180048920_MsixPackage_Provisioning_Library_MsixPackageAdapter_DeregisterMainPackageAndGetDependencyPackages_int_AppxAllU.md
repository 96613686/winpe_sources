# MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterMainPackageAndGetDependencyPackages(int,AppxAllUserStore::_PackageInfo * *,uint *)

- ea: `0x180048920`
- end: `0x180048bcf`
- name: `?DeregisterMainPackageAndGetDependencyPackages@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAPEAU_PackageInfo@AppxAllUserStore@@PEAI@Z`
- size: `687`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, struct AppxAllUserStore::_PackageInfo **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048bd8`
- `0x18004db50`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x180048920`
- `0x18004e0e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048b8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048a8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048b8d`
- `AppXAllUserStore!RemovePackageFromRegistryStore` at `0x18004898d`
- `AppXAllUserStore!RemovePackageFromRegistryStore` at `0x18004898d`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180048ab5`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180048ab5`

## string_xrefs

- `0x180048949`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800489bc`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048a5c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048ae4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048a10`: `Failed to remove license for package '%s'`
- `0x1800489c3`: `Failed to get the list of packages to remove`
- `0x180048b32`: `Failed to get the list of packages to remove`
- `0x180048aeb`: `Failed to remove package from all staged packages list in all user store`
- `0x180048ba0`: `Failed to remove package from all staged packages list in all user store`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int v20; // [rsp+20h] [rbp-28h]
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
    v20 = 1;
    v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            L"Failed to get the list of packages to remove",
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            1820);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x71C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12,
        1);
  }
  v11 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(this);
  if ( v11 < 0 )
  {
    pv = 0;
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(char **)v9;
    v13 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            L"Failed to remove license for package '%s'",
            v9);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x722,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v13,
        v20);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v15,
          1);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18,
        1);
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
0x180048920  mov     [rsp+arg_8], rbx
0x180048925  mov     [rsp+arg_10], rbp
0x18004892a  push    rsi
0x18004892b  push    rdi
0x18004892c  push    r15
0x18004892e  sub     rsp, 30h
0x180048932  mov     ebp, edx
0x180048934  mov     rdi, rcx
0x180048937  mov     dword ptr [r9], 0
0x18004893e  mov     qword ptr [r8], 0
0x180048945  mov     r10d, [rcx+24h]
0x180048949  lea     r15, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048950  test    r10d, r10d
0x180048953  jz      short loc_18004896F
0x180048955  sub     r10d, 1
0x180048959  jz      short loc_18004896F
0x18004895b  sub     r10d, 1
0x18004895f  jz      loc_180048A99
0x180048965  cmp     r10d, 2
0x180048969  jnz     loc_180048B10
0x18004896f  lea     rbx, [rcx+30h]
0x180048973  cmp     qword ptr [rbx+18h], 8
0x180048978  jb      short loc_18004897F
0x18004897a  mov     rdx, [rbx]
0x18004897d  jmp     short loc_180048982
0x18004897f  mov     rdx, rbx
0x180048982  mov     rcx, [rcx+10h]
0x180048986  mov     rcx, [rcx+248h]
0x18004898d  call    cs:__imp_RemovePackageFromRegistryStore
0x180048994  nop     dword ptr [rax+rax+00h]
0x180048999  mov     esi, eax
0x18004899b  test    eax, eax
0x18004899d  jns     short loc_1800489E8
0x18004899f  test    ebp, ebp
0x1800489a1  jz      loc_180048B2D
0x1800489a7  mov     dword ptr [rsp+48h+var_20], eax
0x1800489ab  mov     [rsp+48h+var_28], 1; int
0x1800489b3  mov     r9d, 71Ch
0x1800489b9  xor     r8d, r8d
0x1800489bc  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800489c3  lea     rcx, aFailedToGetThe_1; "Failed to get the list of packages to r"...
0x1800489ca  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x1800489cf  mov     rcx, [rsp+48h]; this
0x1800489d4  test    eax, eax
0x1800489d6  jns     short loc_1800489E8
0x1800489d8  mov     r9d, eax; char *
0x1800489db  mov     r8, r15; unsigned int
0x1800489de  mov     edx, 71Ch; void *
0x1800489e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800489e8  mov     rcx, rdi; this
0x1800489eb  call    ?RemovePackageLicense@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(void)
0x1800489f0  mov     esi, eax
0x1800489f2  test    eax, eax
0x1800489f4  jns     loc_180048A99
0x1800489fa  mov     [rsp+48h+pv], 0
0x180048a03  cmp     qword ptr [rbx+18h], 8
0x180048a08  jb      short loc_180048A0D
0x180048a0a  mov     rbx, [rbx]
0x180048a0d  mov     r8, rbx
0x180048a10  lea     rdx, aFailedToRemove_3; "Failed to remove license for package '%"...
0x180048a17  lea     rcx, [rsp+48h+pv]
0x180048a1c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180048a21  mov     rcx, [rsp+48h]; this
0x180048a26  test    eax, eax
0x180048a28  jns     short loc_180048A3A
0x180048a2a  mov     r9d, eax; char *
0x180048a2d  mov     r8, r15; unsigned int
0x180048a30  mov     edx, 722h; void *
0x180048a35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048a3a  mov     rbx, [rsp+48h+pv]
0x180048a3f  test    ebp, ebp
0x180048a41  jz      loc_180048B5E
0x180048a47  mov     dword ptr [rsp+48h+var_20], esi
0x180048a4b  mov     [rsp+48h+var_28], 1; int
0x180048a53  mov     r9d, 722h
0x180048a59  xor     r8d, r8d
0x180048a5c  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048a63  mov     rcx, rbx
0x180048a66  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180048a6b  mov     rcx, [rsp+48h]; this
0x180048a70  test    eax, eax
0x180048a72  jns     short loc_180048A85
0x180048a74  mov     r9d, eax; char *
0x180048a77  mov     r8, r15; unsigned int
0x180048a7a  mov     edx, 722h; void *
0x180048a7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048a84  nop
0x180048a85  test    rbx, rbx
0x180048a88  jz      short loc_180048A99
0x180048a8a  mov     rcx, rbx; pv
0x180048a8d  call    cs:__imp_CoTaskMemFree
0x180048a94  nop     dword ptr [rax+rax+00h]
0x180048a99  lea     rdx, [rdi+30h]
0x180048a9d  cmp     qword ptr [rdx+18h], 8
0x180048aa2  jb      short loc_180048AA7
0x180048aa4  mov     rdx, [rdx]
0x180048aa7  mov     rcx, [rdi+10h]
0x180048aab  xor     r8d, r8d
0x180048aae  mov     rcx, [rcx+248h]
0x180048ab5  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180048abc  nop     dword ptr [rax+rax+00h]
0x180048ac1  mov     ebx, eax
0x180048ac3  test    eax, eax
0x180048ac5  jns     short loc_180048B10
0x180048ac7  test    ebp, ebp
0x180048ac9  jz      loc_180048B9B
0x180048acf  mov     dword ptr [rsp+48h+var_20], eax
0x180048ad3  mov     [rsp+48h+var_28], 1; int
0x180048adb  mov     r9d, 729h
0x180048ae1  xor     r8d, r8d
0x180048ae4  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048aeb  lea     rcx, aFailedToRemove_6; "Failed to remove package from all stage"...
0x180048af2  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180048af7  test    eax, eax
0x180048af9  jns     short loc_180048B10
0x180048afb  mov     rcx, [rsp+48h]; this
0x180048b00  mov     r9d, eax; char *
0x180048b03  mov     r8, r15; unsigned int
0x180048b06  mov     edx, 729h; void *
0x180048b0b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048b10  mov     dword ptr [rdi+18h], 4
0x180048b17  xor     eax, eax
0x180048b19  mov     rbx, [rsp+48h+arg_8]
0x180048b1e  mov     rbp, [rsp+48h+arg_10]
0x180048b23  add     rsp, 30h
0x180048b27  pop     r15
0x180048b29  pop     rdi
0x180048b2a  pop     rsi
0x180048b2b  retn
0x180048b2d  mov     rcx, [rsp+48h]; this
0x180048b32  lea     rax, aFailedToGetThe_1; "Failed to get the list of packages to r"...
0x180048b39  mov     [rsp+48h+var_20], rax; char *
0x180048b3e  lea     rax, aWs; "%ws"
0x180048b45  mov     qword ptr [rsp+48h+var_28], rax; int
0x180048b4a  mov     r9d, esi; char *
0x180048b4d  mov     r8, r15; unsigned int
0x180048b50  mov     edx, 71Ch; void *
0x180048b55  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048b5a  mov     eax, esi
0x180048b5c  jmp     short loc_180048B19
0x180048b5e  mov     rcx, [rsp+48h]; this
0x180048b63  mov     [rsp+48h+var_20], rbx; char *
0x180048b68  lea     rax, aWs; "%ws"
0x180048b6f  mov     qword ptr [rsp+48h+var_28], rax; int
0x180048b74  mov     r9d, esi; char *
0x180048b77  mov     r8, r15; unsigned int
0x180048b7a  mov     edx, 722h; void *
0x180048b7f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048b84  nop
0x180048b85  test    rbx, rbx
0x180048b88  jz      short loc_180048B5A
0x180048b8a  mov     rcx, rbx; pv
0x180048b8d  call    cs:__imp_CoTaskMemFree
0x180048b94  nop     dword ptr [rax+rax+00h]
0x180048b99  jmp     short loc_180048B5A
0x180048b9b  mov     rcx, [rsp+48h]; this
0x180048ba0  lea     rax, aFailedToRemove_6; "Failed to remove package from all stage"...
0x180048ba7  mov     [rsp+48h+var_20], rax; char *
0x180048bac  lea     rax, aWs; "%ws"
0x180048bb3  mov     qword ptr [rsp+48h+var_28], rax; int
0x180048bb8  mov     r9d, ebx; char *
0x180048bbb  mov     r8, r15; unsigned int
0x180048bbe  mov     edx, 729h; void *
0x180048bc3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048bc8  mov     eax, ebx
0x180048bca  jmp     loc_180048B19
```
