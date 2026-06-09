# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___

- ea: `0x18005125c`
- end: `0x1800515e7`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048bd8`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003c2c0`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18005125c`
- `0x180051ae0`
- `0x180055cf8`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051331`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005140c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800514ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005154a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051331`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005140c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800514ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005154a`

## string_xrefs

- `0x1800512d1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051319`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800513a4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800513f2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005143d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800514d6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051530`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005158e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800512ff`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800513d8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___(
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
      v18 = lambda_c4fd5793b212773cfd0419fc43cad62c_::operator()(a3, pv, v5);
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
    v19 = lambda_c4fd5793b212773cfd0419fc43cad62c_::operator()(a3, pv, v5);
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
0x18005125c  mov     [rsp-38h+arg_8], rbx
0x180051261  mov     [rsp-38h+arg_10], r8
0x180051266  mov     [rsp-38h+arg_0], rcx
0x18005126b  push    rbp
0x18005126c  push    rsi
0x18005126d  push    rdi
0x18005126e  push    r12
0x180051270  push    r13
0x180051272  push    r14
0x180051274  push    r15
0x180051276  mov     rbp, rsp
0x180051279  sub     rsp, 40h
0x18005127d  mov     r13d, edx
0x180051280  mov     rax, rcx
0x180051283  xor     esi, esi
0x180051285  mov     r14d, 37Ch
0x18005128b  mov     [rbp+var_10], 0
0x180051293  lea     r8, [rbp+var_10]
0x180051297  mov     edx, esi
0x180051299  mov     rcx, rax
0x18005129c  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x1800512a1  mov     edi, eax
0x1800512a3  test    eax, eax
0x1800512a5  jns     loc_18005133D
0x1800512ab  mov     [rbp+pv], 0
0x1800512b3  mov     r8d, esi
0x1800512b6  lea     rdx, aFailedToObtain_6; "Failed to obtain carried package list f"...
0x1800512bd  lea     rcx, [rbp+pv]
0x1800512c1  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800512c6  mov     rcx, [rbp+38h]; this
0x1800512ca  test    eax, eax
0x1800512cc  jns     short loc_1800512E0
0x1800512ce  mov     r9d, eax; char *
0x1800512d1  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800512d8  mov     edx, r14d; void *
0x1800512db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800512e0  mov     rbx, [rbp+pv]
0x1800512e4  test    r13d, r13d
0x1800512e7  jz      loc_1800514BE
0x1800512ed  mov     dword ptr [rsp+40h+var_18], edi
0x1800512f1  mov     [rsp+40h+var_20], 1; int
0x1800512f9  mov     r9d, r14d
0x1800512fc  xor     r8d, r8d
0x1800512ff  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051306  mov     rcx, rbx
0x180051309  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18005130e  mov     rcx, [rbp+38h]; this
0x180051312  test    eax, eax
0x180051314  jns     short loc_180051329
0x180051316  mov     r9d, eax; char *
0x180051319  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051320  mov     edx, r14d; void *
0x180051323  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051328  nop
0x180051329  test    rbx, rbx
0x18005132c  jz      short loc_18005133D
0x18005132e  mov     rcx, rbx; pv
0x180051331  call    cs:__imp_CoTaskMemFree
0x180051338  nop     dword ptr [rax+rax+00h]
0x18005133d  mov     rbx, [rbp+var_10]
0x180051341  mov     r15, [rbx+18h]
0x180051345  sub     r15, [rbx+10h]
0x180051349  sar     r15, 3
0x18005134d  xor     r12d, r12d
0x180051350  test    r15d, r15d
0x180051353  jz      loc_180051495
0x180051359  mov     [rbp+pv], 0
0x180051361  lea     r8, [rbp+pv]
0x180051365  mov     edx, r12d
0x180051368  mov     rcx, rbx
0x18005136b  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180051370  mov     r14d, eax
0x180051373  test    eax, eax
0x180051375  jns     loc_18005141A
0x18005137b  mov     [rbp+var_8], 0
0x180051383  mov     r9d, esi
0x180051386  mov     r8d, r12d
0x180051389  lea     rdx, aFailedToAcquir_3; "Failed to acquire package %d while proc"...
0x180051390  lea     rcx, [rbp+var_8]
0x180051394  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180051399  mov     rcx, [rbp+38h]; this
0x18005139d  test    eax, eax
0x18005139f  jns     short loc_1800513B5
0x1800513a1  mov     r9d, eax; char *
0x1800513a4  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800513ab  mov     edx, 388h; void *
0x1800513b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800513b5  mov     rdi, [rbp+var_8]
0x1800513b9  test    r13d, r13d
0x1800513bc  jz      loc_180051518
0x1800513c2  mov     dword ptr [rsp+40h+var_18], r14d
0x1800513c7  mov     [rsp+40h+var_20], 1; int
0x1800513cf  mov     r9d, 388h
0x1800513d5  xor     r8d, r8d
0x1800513d8  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800513df  mov     rcx, rdi
0x1800513e2  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x1800513e7  mov     rcx, [rbp+38h]; this
0x1800513eb  test    eax, eax
0x1800513ed  jns     short loc_180051404
0x1800513ef  mov     r9d, eax; char *
0x1800513f2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800513f9  mov     edx, 388h; void *
0x1800513fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051403  nop
0x180051404  test    rdi, rdi
0x180051407  jz      short loc_18005141F
0x180051409  mov     rcx, rdi; pv
0x18005140c  call    cs:__imp_CoTaskMemFree
0x180051413  nop     dword ptr [rax+rax+00h]
0x180051418  jmp     short loc_18005141F
0x18005141a  test    r13d, r13d
0x18005141d  jz      short loc_180051450
0x18005141f  mov     r8d, esi
0x180051422  mov     rdi, [rbp+pv]
0x180051426  mov     rdx, rdi
0x180051429  mov     rcx, [rbp+arg_10]
0x18005142d  call    _lambda_c4fd5793b212773cfd0419fc43cad62c___operator__
0x180051432  mov     rcx, [rbp+38h]; this
0x180051436  test    eax, eax
0x180051438  jns     short loc_18005146E
0x18005143a  mov     r9d, eax; char *
0x18005143d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051444  mov     edx, 38Ch; void *
0x180051449  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005144e  jmp     short loc_18005146E
0x180051450  mov     r8d, esi
0x180051453  mov     rdi, [rbp+pv]
0x180051457  mov     rdx, rdi
0x18005145a  mov     rcx, [rbp+arg_10]
0x18005145e  call    _lambda_c4fd5793b212773cfd0419fc43cad62c___operator__
0x180051463  mov     r14d, eax
0x180051466  test    eax, eax
0x180051468  js      loc_180051587
0x18005146e  test    rdi, rdi
0x180051471  jz      short loc_180051483
0x180051473  mov     rax, [rdi]
0x180051476  mov     rcx, rdi
0x180051479  mov     rax, [rax+10h]
0x18005147d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051482  nop
0x180051483  inc     r12d
0x180051486  cmp     r12d, r15d
0x180051489  jb      loc_180051359
0x18005148f  mov     r14d, 37Ch
0x180051495  test    rbx, rbx
0x180051498  jz      short loc_1800514AA
0x18005149a  mov     rax, [rbx]
0x18005149d  mov     rcx, rbx
0x1800514a0  mov     rax, [rax+10h]
0x1800514a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514a9  nop
0x1800514aa  inc     esi
0x1800514ac  cmp     esi, 5
0x1800514af  jge     loc_1800515CC
0x1800514b5  mov     rax, [rbp+arg_0]
0x1800514b9  jmp     loc_18005128B
0x1800514be  mov     rcx, [rbp+38h]; this
0x1800514c2  mov     [rsp+40h+var_18], rbx; char *
0x1800514c7  lea     rax, aWs; "%ws"
0x1800514ce  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800514d3  mov     r9d, edi; char *
0x1800514d6  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800514dd  mov     edx, r14d; void *
0x1800514e0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800514e5  nop
0x1800514e6  test    rbx, rbx
0x1800514e9  jz      short loc_1800514FB
0x1800514eb  mov     rcx, rbx; pv
0x1800514ee  call    cs:__imp_CoTaskMemFree
0x1800514f5  nop     dword ptr [rax+rax+00h]
0x1800514fa  nop
0x1800514fb  mov     rcx, [rbp+var_10]
0x1800514ff  test    rcx, rcx
0x180051502  jz      short loc_180051511
0x180051504  mov     rax, [rcx]
0x180051507  mov     rax, [rax+10h]
0x18005150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051510  nop
0x180051511  mov     eax, edi
0x180051513  jmp     loc_1800515CE
0x180051518  mov     rcx, [rbp+38h]; this
0x18005151c  mov     [rsp+40h+var_18], rdi; char *
0x180051521  lea     rax, aWs; "%ws"
0x180051528  mov     qword ptr [rsp+40h+var_20], rax; int
0x18005152d  mov     r9d, r14d; char *
0x180051530  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051537  mov     edx, 388h; void *
0x18005153c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180051541  nop
0x180051542  test    rdi, rdi
0x180051545  jz      short loc_180051557
0x180051547  mov     rcx, rdi; pv
0x18005154a  call    cs:__imp_CoTaskMemFree
0x180051551  nop     dword ptr [rax+rax+00h]
0x180051556  nop
0x180051557  mov     rcx, [rbp+pv]
0x18005155b  test    rcx, rcx
0x18005155e  jz      short loc_18005156D
0x180051560  mov     rax, [rcx]
0x180051563  mov     rax, [rax+10h]
0x180051567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005156c  nop
0x18005156d  test    rbx, rbx
0x180051570  jz      short loc_180051582
0x180051572  mov     rax, [rbx]
0x180051575  mov     rcx, rbx
0x180051578  mov     rax, [rax+10h]
0x18005157c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051581  nop
0x180051582  mov     eax, r14d
0x180051585  jmp     short loc_1800515CE
0x180051587  mov     rcx, [rbp+38h]; this
0x18005158b  mov     r9d, r14d; char *
0x18005158e  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051595  mov     edx, 390h; void *
0x18005159a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005159f  nop
0x1800515a0  test    rdi, rdi
0x1800515a3  jz      short loc_1800515B5
0x1800515a5  mov     rax, [rdi]
0x1800515a8  mov     rcx, rdi
0x1800515ab  mov     rax, [rax+10h]
0x1800515af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515b4  nop
0x1800515b5  test    rbx, rbx
0x1800515b8  jz      short loc_1800515CA
0x1800515ba  mov     rax, [rbx]
0x1800515bd  mov     rcx, rbx
0x1800515c0  mov     rax, [rax+10h]
0x1800515c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515c9  nop
0x1800515ca  jmp     short loc_180051582
0x1800515cc  xor     eax, eax
0x1800515ce  mov     rbx, [rsp+40h+arg_8]
0x1800515d6  add     rsp, 40h
0x1800515da  pop     r15
0x1800515dc  pop     r14
0x1800515de  pop     r13
0x1800515e0  pop     r12
0x1800515e2  pop     rdi
0x1800515e3  pop     rsi
0x1800515e4  pop     rbp
0x1800515e5  retn
```
