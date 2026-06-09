# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___

- ea: `0x18004cfe8`
- end: `0x18004d35a`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_c4fd5793b212773cfd0419fc43cad62c___`
- size: `882`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044cd8`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180038d54`
- `0x180039e9c`
- `0x180040400`
- `0x18004cfe8`
- `0x18004d82c`
- `0x18005192c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d2c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d0bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d2c4`

## string_xrefs

- `0x18004d05d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d0a5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d12a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d178`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d1bd`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d256`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d2aa`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d302`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d08b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004d15e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`

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
      v18 = lambda_c4fd5793b212773cfd0419fc43cad62c_::operator()(a3, pv, v5);
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
0x18004cfe8  mov     [rsp-38h+arg_8], rbx
0x18004cfed  mov     [rsp-38h+arg_10], r8
0x18004cff2  mov     [rsp-38h+arg_0], rcx
0x18004cff7  push    rbp
0x18004cff8  push    rsi
0x18004cff9  push    rdi
0x18004cffa  push    r12
0x18004cffc  push    r13
0x18004cffe  push    r14
0x18004d000  push    r15
0x18004d002  mov     rbp, rsp
0x18004d005  sub     rsp, 40h
0x18004d009  mov     r13d, edx
0x18004d00c  mov     rax, rcx
0x18004d00f  xor     esi, esi
0x18004d011  mov     r14d, 37Ch
0x18004d017  mov     [rbp+var_10], 0
0x18004d01f  lea     r8, [rbp+var_10]
0x18004d023  mov     edx, esi
0x18004d025  mov     rcx, rax
0x18004d028  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x18004d02d  mov     edi, eax
0x18004d02f  test    eax, eax
0x18004d031  jns     loc_18004D0C3
0x18004d037  mov     [rbp+pv], 0
0x18004d03f  mov     r8d, esi
0x18004d042  lea     rdx, aFailedToObtain_6; "Failed to obtain carried package list f"...
0x18004d049  lea     rcx, [rbp+pv]
0x18004d04d  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004d052  mov     rcx, [rbp+38h]; this
0x18004d056  test    eax, eax
0x18004d058  jns     short loc_18004D06C
0x18004d05a  mov     r9d, eax; char *
0x18004d05d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d064  mov     edx, r14d; void *
0x18004d067  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d06c  mov     rbx, [rbp+pv]
0x18004d070  test    r13d, r13d
0x18004d073  jz      loc_18004D23E
0x18004d079  mov     dword ptr [rsp+40h+var_18], edi
0x18004d07d  mov     [rsp+40h+var_20], 1; int
0x18004d085  mov     r9d, r14d
0x18004d088  xor     r8d, r8d
0x18004d08b  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d092  mov     rcx, rbx
0x18004d095  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004d09a  mov     rcx, [rbp+38h]; this
0x18004d09e  test    eax, eax
0x18004d0a0  jns     short loc_18004D0B5
0x18004d0a2  mov     r9d, eax; char *
0x18004d0a5  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d0ac  mov     edx, r14d; void *
0x18004d0af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d0b4  nop
0x18004d0b5  test    rbx, rbx
0x18004d0b8  jz      short loc_18004D0C3
0x18004d0ba  mov     rcx, rbx; pv
0x18004d0bd  call    cs:__imp_CoTaskMemFree
0x18004d0c3  mov     rbx, [rbp+var_10]
0x18004d0c7  mov     r15, [rbx+18h]
0x18004d0cb  sub     r15, [rbx+10h]
0x18004d0cf  sar     r15, 3
0x18004d0d3  xor     r12d, r12d
0x18004d0d6  test    r15d, r15d
0x18004d0d9  jz      loc_18004D215
0x18004d0df  mov     [rbp+pv], 0
0x18004d0e7  lea     r8, [rbp+pv]
0x18004d0eb  mov     edx, r12d
0x18004d0ee  mov     rcx, rbx
0x18004d0f1  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004d0f6  mov     r14d, eax
0x18004d0f9  test    eax, eax
0x18004d0fb  jns     loc_18004D19A
0x18004d101  mov     [rbp+var_8], 0
0x18004d109  mov     r9d, esi
0x18004d10c  mov     r8d, r12d
0x18004d10f  lea     rdx, aFailedToAcquir_3; "Failed to acquire package %d while proc"...
0x18004d116  lea     rcx, [rbp+var_8]
0x18004d11a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004d11f  mov     rcx, [rbp+38h]; this
0x18004d123  test    eax, eax
0x18004d125  jns     short loc_18004D13B
0x18004d127  mov     r9d, eax; char *
0x18004d12a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d131  mov     edx, 388h; void *
0x18004d136  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d13b  mov     rdi, [rbp+var_8]
0x18004d13f  test    r13d, r13d
0x18004d142  jz      loc_18004D292
0x18004d148  mov     dword ptr [rsp+40h+var_18], r14d
0x18004d14d  mov     [rsp+40h+var_20], 1; int
0x18004d155  mov     r9d, 388h
0x18004d15b  xor     r8d, r8d
0x18004d15e  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d165  mov     rcx, rdi
0x18004d168  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004d16d  mov     rcx, [rbp+38h]; this
0x18004d171  test    eax, eax
0x18004d173  jns     short loc_18004D18A
0x18004d175  mov     r9d, eax; char *
0x18004d178  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d17f  mov     edx, 388h; void *
0x18004d184  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d189  nop
0x18004d18a  test    rdi, rdi
0x18004d18d  jz      short loc_18004D19F
0x18004d18f  mov     rcx, rdi; pv
0x18004d192  call    cs:__imp_CoTaskMemFree
0x18004d198  jmp     short loc_18004D19F
0x18004d19a  test    r13d, r13d
0x18004d19d  jz      short loc_18004D1D0
0x18004d19f  mov     r8d, esi
0x18004d1a2  mov     rdi, [rbp+pv]
0x18004d1a6  mov     rdx, rdi
0x18004d1a9  mov     rcx, [rbp+arg_10]
0x18004d1ad  call    _lambda_c4fd5793b212773cfd0419fc43cad62c___operator__
0x18004d1b2  mov     rcx, [rbp+38h]; this
0x18004d1b6  test    eax, eax
0x18004d1b8  jns     short loc_18004D1EE
0x18004d1ba  mov     r9d, eax; char *
0x18004d1bd  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d1c4  mov     edx, 38Ch; void *
0x18004d1c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d1ce  jmp     short loc_18004D1EE
0x18004d1d0  mov     r8d, esi
0x18004d1d3  mov     rdi, [rbp+pv]
0x18004d1d7  mov     rdx, rdi
0x18004d1da  mov     rcx, [rbp+arg_10]
0x18004d1de  call    _lambda_c4fd5793b212773cfd0419fc43cad62c___operator__
0x18004d1e3  mov     r14d, eax
0x18004d1e6  test    eax, eax
0x18004d1e8  js      loc_18004D2FB
0x18004d1ee  test    rdi, rdi
0x18004d1f1  jz      short loc_18004D203
0x18004d1f3  mov     rax, [rdi]
0x18004d1f6  mov     rcx, rdi
0x18004d1f9  mov     rax, [rax+10h]
0x18004d1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d202  nop
0x18004d203  inc     r12d
0x18004d206  cmp     r12d, r15d
0x18004d209  jb      loc_18004D0DF
0x18004d20f  mov     r14d, 37Ch
0x18004d215  test    rbx, rbx
0x18004d218  jz      short loc_18004D22A
0x18004d21a  mov     rax, [rbx]
0x18004d21d  mov     rcx, rbx
0x18004d220  mov     rax, [rax+10h]
0x18004d224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d229  nop
0x18004d22a  inc     esi
0x18004d22c  cmp     esi, 5
0x18004d22f  jge     loc_18004D340
0x18004d235  mov     rax, [rbp+arg_0]
0x18004d239  jmp     loc_18004D017
0x18004d23e  mov     rcx, [rbp+38h]; this
0x18004d242  mov     [rsp+40h+var_18], rbx; char *
0x18004d247  lea     rax, aWs; "%ws"
0x18004d24e  mov     qword ptr [rsp+40h+var_20], rax; int
0x18004d253  mov     r9d, edi; char *
0x18004d256  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d25d  mov     edx, r14d; void *
0x18004d260  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d265  nop
0x18004d266  test    rbx, rbx
0x18004d269  jz      short loc_18004D275
0x18004d26b  mov     rcx, rbx; pv
0x18004d26e  call    cs:__imp_CoTaskMemFree
0x18004d274  nop
0x18004d275  mov     rcx, [rbp+var_10]
0x18004d279  test    rcx, rcx
0x18004d27c  jz      short loc_18004D28B
0x18004d27e  mov     rax, [rcx]
0x18004d281  mov     rax, [rax+10h]
0x18004d285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d28a  nop
0x18004d28b  mov     eax, edi
0x18004d28d  jmp     loc_18004D342
0x18004d292  mov     rcx, [rbp+38h]; this
0x18004d296  mov     [rsp+40h+var_18], rdi; char *
0x18004d29b  lea     rax, aWs; "%ws"
0x18004d2a2  mov     qword ptr [rsp+40h+var_20], rax; int
0x18004d2a7  mov     r9d, r14d; char *
0x18004d2aa  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d2b1  mov     edx, 388h; void *
0x18004d2b6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d2bb  nop
0x18004d2bc  test    rdi, rdi
0x18004d2bf  jz      short loc_18004D2CB
0x18004d2c1  mov     rcx, rdi; pv
0x18004d2c4  call    cs:__imp_CoTaskMemFree
0x18004d2ca  nop
0x18004d2cb  mov     rcx, [rbp+pv]
0x18004d2cf  test    rcx, rcx
0x18004d2d2  jz      short loc_18004D2E1
0x18004d2d4  mov     rax, [rcx]
0x18004d2d7  mov     rax, [rax+10h]
0x18004d2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2e0  nop
0x18004d2e1  test    rbx, rbx
0x18004d2e4  jz      short loc_18004D2F6
0x18004d2e6  mov     rax, [rbx]
0x18004d2e9  mov     rcx, rbx
0x18004d2ec  mov     rax, [rax+10h]
0x18004d2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2f5  nop
0x18004d2f6  mov     eax, r14d
0x18004d2f9  jmp     short loc_18004D342
0x18004d2fb  mov     rcx, [rbp+38h]; this
0x18004d2ff  mov     r9d, r14d; char *
0x18004d302  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004d309  mov     edx, 390h; void *
0x18004d30e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d313  nop
0x18004d314  test    rdi, rdi
0x18004d317  jz      short loc_18004D329
0x18004d319  mov     rax, [rdi]
0x18004d31c  mov     rcx, rdi
0x18004d31f  mov     rax, [rax+10h]
0x18004d323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d328  nop
0x18004d329  test    rbx, rbx
0x18004d32c  jz      short loc_18004D33E
0x18004d32e  mov     rax, [rbx]
0x18004d331  mov     rcx, rbx
0x18004d334  mov     rax, [rax+10h]
0x18004d338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d33d  nop
0x18004d33e  jmp     short loc_18004D2F6
0x18004d340  xor     eax, eax
0x18004d342  mov     rbx, [rsp+40h+arg_8]
0x18004d34a  add     rsp, 40h
0x18004d34e  pop     r15
0x18004d350  pop     r14
0x18004d352  pop     r13
0x18004d354  pop     r12
0x18004d356  pop     rdi
0x18004d357  pop     rsi
0x18004d358  pop     rbp
0x18004d359  retn
```
