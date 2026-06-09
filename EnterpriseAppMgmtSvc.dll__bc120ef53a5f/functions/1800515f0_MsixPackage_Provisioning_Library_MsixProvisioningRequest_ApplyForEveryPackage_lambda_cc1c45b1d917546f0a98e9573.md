# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___

- ea: `0x1800515f0`
- end: `0x18005197b`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_cc1c45b1d917546f0a98e9573c2425ef___`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004db50`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003c2c0`
- `0x18003d4ec`
- `0x180043fb4`
- `0x1800515f0`
- `0x180051c10`
- `0x180055cf8`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800518de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800516c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800518de`

## string_xrefs

- `0x180051665`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800516ad`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051738`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051786`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800517d1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005186a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800518c4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051922`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051693`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005176c`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

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
             &pv,
             L"Failed to obtain carried package list for target index %d.",
             v5);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x37C,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v7,
          v21);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v9,
          1);
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
              &v23,
              L"Failed to acquire package %d while processing target type = %d",
              v12,
              v5);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x388,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v14,
          v21);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v16,
          1);
      if ( v15 )
        CoTaskMemFree(v15);
LABEL_20:
      v17 = pv;
      v18 = lambda_cc1c45b1d917546f0a98e9573c2425ef_::operator()(a3, pv, v5);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x38C,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v18,
          v21);
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
0x1800515f0  mov     [rsp-38h+arg_8], rbx
0x1800515f5  mov     [rsp-38h+arg_10], r8
0x1800515fa  mov     [rsp-38h+arg_0], rcx
0x1800515ff  push    rbp
0x180051600  push    rsi
0x180051601  push    rdi
0x180051602  push    r12
0x180051604  push    r13
0x180051606  push    r14
0x180051608  push    r15
0x18005160a  mov     rbp, rsp
0x18005160d  sub     rsp, 40h
0x180051611  mov     r13d, edx
0x180051614  mov     rax, rcx
0x180051617  xor     esi, esi
0x180051619  mov     r14d, 37Ch
0x18005161f  mov     [rbp+var_10], 0
0x180051627  lea     r8, [rbp+var_10]
0x18005162b  mov     edx, esi
0x18005162d  mov     rcx, rax
0x180051630  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x180051635  mov     edi, eax
0x180051637  test    eax, eax
0x180051639  jns     loc_1800516D1
0x18005163f  mov     [rbp+pv], 0
0x180051647  mov     r8d, esi
0x18005164a  lea     rdx, aFailedToObtain_6; "Failed to obtain carried package list f"...
0x180051651  lea     rcx, [rbp+pv]
0x180051655  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005165a  mov     rcx, [rbp+38h]; this
0x18005165e  test    eax, eax
0x180051660  jns     short loc_180051674
0x180051662  mov     r9d, eax; char *
0x180051665  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005166c  mov     edx, r14d; void *
0x18005166f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051674  mov     rbx, [rbp+pv]
0x180051678  test    r13d, r13d
0x18005167b  jz      loc_180051852
0x180051681  mov     dword ptr [rsp+40h+var_18], edi
0x180051685  mov     [rsp+40h+var_20], 1; int
0x18005168d  mov     r9d, r14d
0x180051690  xor     r8d, r8d
0x180051693  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005169a  mov     rcx, rbx
0x18005169d  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x1800516a2  mov     rcx, [rbp+38h]; this
0x1800516a6  test    eax, eax
0x1800516a8  jns     short loc_1800516BD
0x1800516aa  mov     r9d, eax; char *
0x1800516ad  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800516b4  mov     edx, r14d; void *
0x1800516b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800516bc  nop
0x1800516bd  test    rbx, rbx
0x1800516c0  jz      short loc_1800516D1
0x1800516c2  mov     rcx, rbx; pv
0x1800516c5  call    cs:__imp_CoTaskMemFree
0x1800516cc  nop     dword ptr [rax+rax+00h]
0x1800516d1  mov     rbx, [rbp+var_10]
0x1800516d5  mov     r15, [rbx+18h]
0x1800516d9  sub     r15, [rbx+10h]
0x1800516dd  sar     r15, 3
0x1800516e1  xor     r12d, r12d
0x1800516e4  test    r15d, r15d
0x1800516e7  jz      loc_180051829
0x1800516ed  mov     [rbp+pv], 0
0x1800516f5  lea     r8, [rbp+pv]
0x1800516f9  mov     edx, r12d
0x1800516fc  mov     rcx, rbx
0x1800516ff  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180051704  mov     r14d, eax
0x180051707  test    eax, eax
0x180051709  jns     loc_1800517AE
0x18005170f  mov     [rbp+var_8], 0
0x180051717  mov     r9d, esi
0x18005171a  mov     r8d, r12d
0x18005171d  lea     rdx, aFailedToAcquir_3; "Failed to acquire package %d while proc"...
0x180051724  lea     rcx, [rbp+var_8]
0x180051728  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005172d  mov     rcx, [rbp+38h]; this
0x180051731  test    eax, eax
0x180051733  jns     short loc_180051749
0x180051735  mov     r9d, eax; char *
0x180051738  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005173f  mov     edx, 388h; void *
0x180051744  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051749  mov     rdi, [rbp+var_8]
0x18005174d  test    r13d, r13d
0x180051750  jz      loc_1800518AC
0x180051756  mov     dword ptr [rsp+40h+var_18], r14d
0x18005175b  mov     [rsp+40h+var_20], 1; int
0x180051763  mov     r9d, 388h
0x180051769  xor     r8d, r8d
0x18005176c  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051773  mov     rcx, rdi
0x180051776  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18005177b  mov     rcx, [rbp+38h]; this
0x18005177f  test    eax, eax
0x180051781  jns     short loc_180051798
0x180051783  mov     r9d, eax; char *
0x180051786  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005178d  mov     edx, 388h; void *
0x180051792  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051797  nop
0x180051798  test    rdi, rdi
0x18005179b  jz      short loc_1800517B3
0x18005179d  mov     rcx, rdi; pv
0x1800517a0  call    cs:__imp_CoTaskMemFree
0x1800517a7  nop     dword ptr [rax+rax+00h]
0x1800517ac  jmp     short loc_1800517B3
0x1800517ae  test    r13d, r13d
0x1800517b1  jz      short loc_1800517E4
0x1800517b3  mov     r8d, esi
0x1800517b6  mov     rdi, [rbp+pv]
0x1800517ba  mov     rdx, rdi
0x1800517bd  mov     rcx, [rbp+arg_10]
0x1800517c1  call    _lambda_cc1c45b1d917546f0a98e9573c2425ef___operator__
0x1800517c6  mov     rcx, [rbp+38h]; this
0x1800517ca  test    eax, eax
0x1800517cc  jns     short loc_180051802
0x1800517ce  mov     r9d, eax; char *
0x1800517d1  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800517d8  mov     edx, 38Ch; void *
0x1800517dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800517e2  jmp     short loc_180051802
0x1800517e4  mov     r8d, esi
0x1800517e7  mov     rdi, [rbp+pv]
0x1800517eb  mov     rdx, rdi
0x1800517ee  mov     rcx, [rbp+arg_10]
0x1800517f2  call    _lambda_cc1c45b1d917546f0a98e9573c2425ef___operator__
0x1800517f7  mov     r14d, eax
0x1800517fa  test    eax, eax
0x1800517fc  js      loc_18005191B
0x180051802  test    rdi, rdi
0x180051805  jz      short loc_180051817
0x180051807  mov     rax, [rdi]
0x18005180a  mov     rcx, rdi
0x18005180d  mov     rax, [rax+10h]
0x180051811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051816  nop
0x180051817  inc     r12d
0x18005181a  cmp     r12d, r15d
0x18005181d  jb      loc_1800516ED
0x180051823  mov     r14d, 37Ch
0x180051829  test    rbx, rbx
0x18005182c  jz      short loc_18005183E
0x18005182e  mov     rax, [rbx]
0x180051831  mov     rcx, rbx
0x180051834  mov     rax, [rax+10h]
0x180051838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005183d  nop
0x18005183e  inc     esi
0x180051840  cmp     esi, 5
0x180051843  jge     loc_180051960
0x180051849  mov     rax, [rbp+arg_0]
0x18005184d  jmp     loc_18005161F
0x180051852  mov     rcx, [rbp+38h]; this
0x180051856  mov     [rsp+40h+var_18], rbx; char *
0x18005185b  lea     rax, aWs; "%ws"
0x180051862  mov     qword ptr [rsp+40h+var_20], rax; int
0x180051867  mov     r9d, edi; char *
0x18005186a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051871  mov     edx, r14d; void *
0x180051874  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180051879  nop
0x18005187a  test    rbx, rbx
0x18005187d  jz      short loc_18005188F
0x18005187f  mov     rcx, rbx; pv
0x180051882  call    cs:__imp_CoTaskMemFree
0x180051889  nop     dword ptr [rax+rax+00h]
0x18005188e  nop
0x18005188f  mov     rcx, [rbp+var_10]
0x180051893  test    rcx, rcx
0x180051896  jz      short loc_1800518A5
0x180051898  mov     rax, [rcx]
0x18005189b  mov     rax, [rax+10h]
0x18005189f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518a4  nop
0x1800518a5  mov     eax, edi
0x1800518a7  jmp     loc_180051962
0x1800518ac  mov     rcx, [rbp+38h]; this
0x1800518b0  mov     [rsp+40h+var_18], rdi; char *
0x1800518b5  lea     rax, aWs; "%ws"
0x1800518bc  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800518c1  mov     r9d, r14d; char *
0x1800518c4  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800518cb  mov     edx, 388h; void *
0x1800518d0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800518d5  nop
0x1800518d6  test    rdi, rdi
0x1800518d9  jz      short loc_1800518EB
0x1800518db  mov     rcx, rdi; pv
0x1800518de  call    cs:__imp_CoTaskMemFree
0x1800518e5  nop     dword ptr [rax+rax+00h]
0x1800518ea  nop
0x1800518eb  mov     rcx, [rbp+pv]
0x1800518ef  test    rcx, rcx
0x1800518f2  jz      short loc_180051901
0x1800518f4  mov     rax, [rcx]
0x1800518f7  mov     rax, [rax+10h]
0x1800518fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051900  nop
0x180051901  test    rbx, rbx
0x180051904  jz      short loc_180051916
0x180051906  mov     rax, [rbx]
0x180051909  mov     rcx, rbx
0x18005190c  mov     rax, [rax+10h]
0x180051910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051915  nop
0x180051916  mov     eax, r14d
0x180051919  jmp     short loc_180051962
0x18005191b  mov     rcx, [rbp+38h]; this
0x18005191f  mov     r9d, r14d; char *
0x180051922  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051929  mov     edx, 390h; void *
0x18005192e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051933  nop
0x180051934  test    rdi, rdi
0x180051937  jz      short loc_180051949
0x180051939  mov     rax, [rdi]
0x18005193c  mov     rcx, rdi
0x18005193f  mov     rax, [rax+10h]
0x180051943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051948  nop
0x180051949  test    rbx, rbx
0x18005194c  jz      short loc_18005195E
0x18005194e  mov     rax, [rbx]
0x180051951  mov     rcx, rbx
0x180051954  mov     rax, [rax+10h]
0x180051958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005195d  nop
0x18005195e  jmp     short loc_180051916
0x180051960  xor     eax, eax
0x180051962  mov     rbx, [rsp+40h+arg_8]
0x18005196a  add     rsp, 40h
0x18005196e  pop     r15
0x180051970  pop     r14
0x180051972  pop     r13
0x180051974  pop     r12
0x180051976  pop     rdi
0x180051977  pop     rsi
0x180051978  pop     rbp
0x180051979  retn
```
