# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___

- ea: `0x18004d360`
- end: `0x18004d6d2`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180049a44`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180038d54`
- `0x180039e9c`
- `0x180040400`
- `0x18004d360`
- `0x18004d950`
- `0x18005192c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d50a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d50a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d63c`

## string_xrefs

- `0x18004d3d5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d41d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d4a2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d4f0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d535`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d5ce`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d622`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d67a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d403`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d4d6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___(
        __int64 a1,
        int a2,
        __int64 a3)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  int v6; // edi
  int v7; // eax
  void *v8; // rbx
  int v9; // eax
  _QWORD *v10; // rbx
  __int64 v11; // r15
  unsigned int v12; // r12d
  unsigned int v13; // r14d
  int v14; // eax
  char *v15; // rdi
  int v16; // eax
  LPVOID v17; // rdi
  int v18; // eax
  int v19; // eax
  int v21; // [rsp+20h] [rbp-20h]
  _QWORD *v22; // [rsp+30h] [rbp-10h] BYREF
  char *v23; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  v4 = a1;
  v5 = 0;
  while ( 1 )
  {
    v22 = 0;
    v6 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(v4, v5, &v22);
    if ( v6 < 0 )
    {
      pv = 0;
      v7 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             (char *)&pv,
             L"Failed to obtain carried package list for target index %d.",
             v5);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37C,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v7);
      v8 = pv;
      if ( !a2 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x37C,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v6,
          (int)"%ws",
          (const char *)pv);
        if ( v8 )
          CoTaskMemFree(v8);
        if ( v22 )
          (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
        return (unsigned int)v6;
      }
      v21 = 1;
      v9 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
             pv,
             L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
             0,
             892);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37C,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v9);
      if ( v8 )
        CoTaskMemFree(v8);
    }
    v10 = v22;
    v11 = (__int64)(v22[3] - v22[2]) >> 3;
    v12 = 0;
    if ( (_DWORD)v11 )
      break;
LABEL_26:
    if ( v10 )
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    if ( (int)++v5 >= 5 )
      return 0;
    v4 = a1;
  }
  while ( 1 )
  {
    pv = 0;
    v13 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
            v10,
            v12,
            &pv);
    if ( (v13 & 0x80000000) != 0 )
    {
      v23 = 0;
      v14 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&v23,
              L"Failed to acquire package %d while processing target type = %d",
              v12,
              v5);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x388,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v14);
      v15 = v23;
      if ( !a2 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x388,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)v13,
          (int)"%ws",
          v23);
        if ( v15 )
          CoTaskMemFree(v15);
        if ( pv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( v10 )
          (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
        return v13;
      }
      v21 = 1;
      v16 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              v23,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              0,
              904);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x388,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v16);
      if ( v15 )
        CoTaskMemFree(v15);
LABEL_20:
      v17 = pv;
      v18 = lambda_cc1c45b1d917546f0a98e9573c2425ef_::operator()(a3, pv, v5);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x38C,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v18);
      goto LABEL_23;
    }
    if ( a2 )
      goto LABEL_20;
    v17 = pv;
    v19 = lambda_cc1c45b1d917546f0a98e9573c2425ef_::operator()(a3, pv, v5);
    v13 = v19;
    if ( v19 < 0 )
      break;
LABEL_23:
    if ( v17 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    if ( ++v12 >= (unsigned int)v11 )
      goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x390,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
    (const char *)(unsigned int)v19,
    v21);
  if ( v17 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v10 )
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  return v13;
}

```

## disassembly

```asm
0x18004d360  mov     [rsp-38h+arg_8], rbx
0x18004d365  mov     [rsp-38h+arg_10], r8
0x18004d36a  mov     [rsp-38h+arg_0], rcx
0x18004d36f  push    rbp
0x18004d370  push    rsi
0x18004d371  push    rdi
0x18004d372  push    r12
0x18004d374  push    r13
0x18004d376  push    r14
0x18004d378  push    r15
0x18004d37a  mov     rbp, rsp
0x18004d37d  sub     rsp, 40h
0x18004d381  mov     r13d, edx
0x18004d384  mov     rax, rcx
0x18004d387  xor     esi, esi
0x18004d389  mov     r14d, 37Ch
0x18004d38f  mov     [rbp+var_10], 0
0x18004d397  lea     r8, [rbp+var_10]
0x18004d39b  mov     edx, esi
0x18004d39d  mov     rcx, rax
0x18004d3a0  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x18004d3a5  mov     edi, eax
0x18004d3a7  test    eax, eax
0x18004d3a9  jns     loc_18004D43B
0x18004d3af  mov     [rbp+pv], 0
0x18004d3b7  mov     r8d, esi
0x18004d3ba  lea     rdx, aFailedToObtain_6; "Failed to obtain carried package list f"...
0x18004d3c1  lea     rcx, [rbp+pv]
0x18004d3c5  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004d3ca  mov     rcx, [rbp+38h]; this
0x18004d3ce  test    eax, eax
0x18004d3d0  jns     short loc_18004D3E4
0x18004d3d2  mov     r9d, eax; char *
0x18004d3d5  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d3dc  mov     edx, r14d; void *
0x18004d3df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d3e4  mov     rbx, [rbp+pv]
0x18004d3e8  test    r13d, r13d
0x18004d3eb  jz      loc_18004D5B6
0x18004d3f1  mov     dword ptr [rsp+40h+var_18], edi
0x18004d3f5  mov     [rsp+40h+var_20], 1; int
0x18004d3fd  mov     r9d, r14d
0x18004d400  xor     r8d, r8d
0x18004d403  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d40a  mov     rcx, rbx
0x18004d40d  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004d412  mov     rcx, [rbp+38h]; this
0x18004d416  test    eax, eax
0x18004d418  jns     short loc_18004D42D
0x18004d41a  mov     r9d, eax; char *
0x18004d41d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d424  mov     edx, r14d; void *
0x18004d427  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d42c  nop
0x18004d42d  test    rbx, rbx
0x18004d430  jz      short loc_18004D43B
0x18004d432  mov     rcx, rbx; pv
0x18004d435  call    cs:__imp_CoTaskMemFree
0x18004d43b  mov     rbx, [rbp+var_10]
0x18004d43f  mov     r15, [rbx+18h]
0x18004d443  sub     r15, [rbx+10h]
0x18004d447  sar     r15, 3
0x18004d44b  xor     r12d, r12d
0x18004d44e  test    r15d, r15d
0x18004d451  jz      loc_18004D58D
0x18004d457  mov     [rbp+pv], 0
0x18004d45f  lea     r8, [rbp+pv]
0x18004d463  mov     edx, r12d
0x18004d466  mov     rcx, rbx
0x18004d469  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004d46e  mov     r14d, eax
0x18004d471  test    eax, eax
0x18004d473  jns     loc_18004D512
0x18004d479  mov     [rbp+var_8], 0
0x18004d481  mov     r9d, esi
0x18004d484  mov     r8d, r12d
0x18004d487  lea     rdx, aFailedToAcquir_3; "Failed to acquire package %d while proc"...
0x18004d48e  lea     rcx, [rbp+var_8]
0x18004d492  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004d497  mov     rcx, [rbp+38h]; this
0x18004d49b  test    eax, eax
0x18004d49d  jns     short loc_18004D4B3
0x18004d49f  mov     r9d, eax; char *
0x18004d4a2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d4a9  mov     edx, 388h; void *
0x18004d4ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d4b3  mov     rdi, [rbp+var_8]
0x18004d4b7  test    r13d, r13d
0x18004d4ba  jz      loc_18004D60A
0x18004d4c0  mov     dword ptr [rsp+40h+var_18], r14d
0x18004d4c5  mov     [rsp+40h+var_20], 1; int
0x18004d4cd  mov     r9d, 388h
0x18004d4d3  xor     r8d, r8d
0x18004d4d6  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d4dd  mov     rcx, rdi
0x18004d4e0  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004d4e5  mov     rcx, [rbp+38h]; this
0x18004d4e9  test    eax, eax
0x18004d4eb  jns     short loc_18004D502
0x18004d4ed  mov     r9d, eax; char *
0x18004d4f0  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d4f7  mov     edx, 388h; void *
0x18004d4fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d501  nop
0x18004d502  test    rdi, rdi
0x18004d505  jz      short loc_18004D517
0x18004d507  mov     rcx, rdi; pv
0x18004d50a  call    cs:__imp_CoTaskMemFree
0x18004d510  jmp     short loc_18004D517
0x18004d512  test    r13d, r13d
0x18004d515  jz      short loc_18004D548
0x18004d517  mov     r8d, esi
0x18004d51a  mov     rdi, [rbp+pv]
0x18004d51e  mov     rdx, rdi
0x18004d521  mov     rcx, [rbp+arg_10]
0x18004d525  call    _lambda_cc1c45b1d917546f0a98e9573c2425ef___operator__
0x18004d52a  mov     rcx, [rbp+38h]; this
0x18004d52e  test    eax, eax
0x18004d530  jns     short loc_18004D566
0x18004d532  mov     r9d, eax; char *
0x18004d535  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d53c  mov     edx, 38Ch; void *
0x18004d541  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d546  jmp     short loc_18004D566
0x18004d548  mov     r8d, esi
0x18004d54b  mov     rdi, [rbp+pv]
0x18004d54f  mov     rdx, rdi
0x18004d552  mov     rcx, [rbp+arg_10]
0x18004d556  call    _lambda_cc1c45b1d917546f0a98e9573c2425ef___operator__
0x18004d55b  mov     r14d, eax
0x18004d55e  test    eax, eax
0x18004d560  js      loc_18004D673
0x18004d566  test    rdi, rdi
0x18004d569  jz      short loc_18004D57B
0x18004d56b  mov     rax, [rdi]
0x18004d56e  mov     rcx, rdi
0x18004d571  mov     rax, [rax+10h]
0x18004d575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d57a  nop
0x18004d57b  inc     r12d
0x18004d57e  cmp     r12d, r15d
0x18004d581  jb      loc_18004D457
0x18004d587  mov     r14d, 37Ch
0x18004d58d  test    rbx, rbx
0x18004d590  jz      short loc_18004D5A2
0x18004d592  mov     rax, [rbx]
0x18004d595  mov     rcx, rbx
0x18004d598  mov     rax, [rax+10h]
0x18004d59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5a1  nop
0x18004d5a2  inc     esi
0x18004d5a4  cmp     esi, 5
0x18004d5a7  jge     loc_18004D6B8
0x18004d5ad  mov     rax, [rbp+arg_0]
0x18004d5b1  jmp     loc_18004D38F
0x18004d5b6  mov     rcx, [rbp+38h]; this
0x18004d5ba  mov     [rsp+40h+var_18], rbx; char *
0x18004d5bf  lea     rax, aWs; "%ws"
0x18004d5c6  mov     qword ptr [rsp+40h+var_20], rax; int
0x18004d5cb  mov     r9d, edi; char *
0x18004d5ce  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d5d5  mov     edx, r14d; void *
0x18004d5d8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d5dd  nop
0x18004d5de  test    rbx, rbx
0x18004d5e1  jz      short loc_18004D5ED
0x18004d5e3  mov     rcx, rbx; pv
0x18004d5e6  call    cs:__imp_CoTaskMemFree
0x18004d5ec  nop
0x18004d5ed  mov     rcx, [rbp+var_10]
0x18004d5f1  test    rcx, rcx
0x18004d5f4  jz      short loc_18004D603
0x18004d5f6  mov     rax, [rcx]
0x18004d5f9  mov     rax, [rax+10h]
0x18004d5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d602  nop
0x18004d603  mov     eax, edi
0x18004d605  jmp     loc_18004D6BA
0x18004d60a  mov     rcx, [rbp+38h]; this
0x18004d60e  mov     [rsp+40h+var_18], rdi; char *
0x18004d613  lea     rax, aWs; "%ws"
0x18004d61a  mov     qword ptr [rsp+40h+var_20], rax; int
0x18004d61f  mov     r9d, r14d; char *
0x18004d622  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d629  mov     edx, 388h; void *
0x18004d62e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d633  nop
0x18004d634  test    rdi, rdi
0x18004d637  jz      short loc_18004D643
0x18004d639  mov     rcx, rdi; pv
0x18004d63c  call    cs:__imp_CoTaskMemFree
0x18004d642  nop
0x18004d643  mov     rcx, [rbp+pv]
0x18004d647  test    rcx, rcx
0x18004d64a  jz      short loc_18004D659
0x18004d64c  mov     rax, [rcx]
0x18004d64f  mov     rax, [rax+10h]
0x18004d653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d658  nop
0x18004d659  test    rbx, rbx
0x18004d65c  jz      short loc_18004D66E
0x18004d65e  mov     rax, [rbx]
0x18004d661  mov     rcx, rbx
0x18004d664  mov     rax, [rax+10h]
0x18004d668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d66d  nop
0x18004d66e  mov     eax, r14d
0x18004d671  jmp     short loc_18004D6BA
0x18004d673  mov     rcx, [rbp+38h]; this
0x18004d677  mov     r9d, r14d; char *
0x18004d67a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d681  mov     edx, 390h; void *
0x18004d686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d68b  nop
0x18004d68c  test    rdi, rdi
0x18004d68f  jz      short loc_18004D6A1
0x18004d691  mov     rax, [rdi]
0x18004d694  mov     rcx, rdi
0x18004d697  mov     rax, [rax+10h]
0x18004d69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6a0  nop
0x18004d6a1  test    rbx, rbx
0x18004d6a4  jz      short loc_18004D6B6
0x18004d6a6  mov     rax, [rbx]
0x18004d6a9  mov     rcx, rbx
0x18004d6ac  mov     rax, [rax+10h]
0x18004d6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6b5  nop
0x18004d6b6  jmp     short loc_18004D66E
0x18004d6b8  xor     eax, eax
0x18004d6ba  mov     rbx, [rsp+40h+arg_8]
0x18004d6c2  add     rsp, 40h
0x18004d6c6  pop     r15
0x18004d6c8  pop     r14
0x18004d6ca  pop     r13
0x18004d6cc  pop     r12
0x18004d6ce  pop     rdi
0x18004d6cf  pop     rsi
0x18004d6d0  pop     rbp
0x18004d6d1  retn
```
