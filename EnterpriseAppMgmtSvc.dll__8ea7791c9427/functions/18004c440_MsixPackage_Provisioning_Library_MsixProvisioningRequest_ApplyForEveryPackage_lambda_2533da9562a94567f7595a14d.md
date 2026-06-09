# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_2533da9562a94567f7595a14d7cabddb___

- ea: `0x18004c440`
- end: `0x18004c892`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_2533da9562a94567f7595a14d7cabddb___`
- size: `1106`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180051c7c`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180038d54`
- `0x180039124`
- `0x180039e9c`
- `0x180040400`
- `0x180044ecc`
- `0x18004865c`
- `0x18004ae64`
- `0x18004c440`
- `0x18005192c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c655`

## string_xrefs

- `0x18004c53e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c58b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c5f2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c63b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c6df`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c715`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c775`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c7d0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c842`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c61d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004c616`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::StageLooseFilePackagesOnline::<lambda_2533da9562a94567f7595a14d7cabddb>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_2533da9562a94567f7595a14d7cabddb___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v4; // r14d
  __int64 v5; // rbx
  int v6; // ebx
  int v7; // edi
  unsigned int v8; // r13d
  _QWORD *v9; // rdi
  unsigned int v10; // esi
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v11; // r15
  int v12; // r12d
  const char **v13; // rsi
  const char *v14; // rdx
  int v15; // r12d
  const char *v16; // rdx
  unsigned __int16 *v17; // rdx
  int v18; // r12d
  int v19; // eax
  void *v20; // rsi
  int v21; // eax
  int v23; // [rsp+20h] [rbp-38h]
  char *v24; // [rsp+28h] [rbp-30h]
  __int64 v25; // [rsp+30h] [rbp-28h]
  LPVOID pv[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  _QWORD *v29; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v30; // [rsp+B0h] [rbp+58h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v31; // [rsp+B8h] [rbp+60h] BYREF

  v30 = a3;
  v29 = a2;
  v3 = a1;
  v4 = 0;
  while ( 1 )
  {
    v5 = 0;
    v30 = 0;
    v29 = 0;
    if ( v4 > 1 )
      goto LABEL_5;
    v30 = 0;
    v6 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(v3, 3, &v30);
    if ( v6 < 0 )
      break;
    v5 = v30;
LABEL_5:
    v29 = 0;
    v7 = MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(v3, v4, &v29);
    if ( v7 < 0 )
    {
      LODWORD(v24) = v4;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x35C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v7,
        (int)"Failed to obtain carried package list for target index %d.",
        v24);
      if ( v29 )
        (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)v7;
    }
    v8 = 0;
    v9 = v29;
    if ( (unsigned int)((__int64)(v29[3] - v29[2]) >> 3) )
    {
      while ( 1 )
      {
        v31 = 0;
        v10 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
                v9,
                v8,
                &v31);
        if ( (v10 & 0x80000000) != 0 )
          break;
        v11 = v31;
        if ( !v31 )
        {
          v10 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x363,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            (const char *)0x8007000ELL,
            v23);
          if ( v9 )
            (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
          if ( v5 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          return v10;
        }
        v12 = MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(v31);
        v13 = (const char **)((char *)v11 + 48);
        if ( *((_QWORD *)v11 + 9) < 8u )
          v14 = (char *)v11 + 48;
        else
          v14 = *v13;
        LODWORD(v25) = v4;
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x1E6,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v12,
          (int)"Failed to stage package %ws while processing target type = %d",
          v14,
          v25);
        if ( v12 < 0
          || ((v15 = MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(v11),
               *((_QWORD *)v11 + 9) < 8u)
            ? (v16 = (char *)v11 + 48)
            : (v16 = *v13),
              wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x1E6,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                (const char *)(unsigned int)v15,
                (int)"Failed to pre-register package %ws while processing target type = %d",
                v16),
              v15 < 0) )
        {
          if ( *((_QWORD *)v11 + 9) < 8u )
            v17 = (unsigned __int16 *)((char *)v11 + 48);
          else
            v17 = (unsigned __int16 *)*v13;
          v18 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(v11, v17);
          pv[0] = 0;
          if ( *((_QWORD *)v11 + 9) >= 8u )
            v13 = (const char **)*v13;
          v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  (char *)pv,
                  L"Unable to destage package %ws, processing target type = %d",
                  v13,
                  v4);
          if ( v19 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1E6,
              (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v19);
          LODWORD(v24) = v18;
          v23 = 1;
          v20 = pv[0];
          v21 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
                  pv[0],
                  L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                  L"MsixPackage::Provisioning::Library::MsixProvisioningRequest::StageLooseFilePackagesOnline::<lambda_253"
                   "3da9562a94567f7595a14d7cabddb>::operator ()",
                  486);
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1E6,
              (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v21);
          if ( v20 )
            CoTaskMemFree(v20);
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x365,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v18,
              1);
            (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v9 )
              (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
            if ( v5 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
            return (unsigned int)v18;
          }
        }
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v11 + 16LL))(v11);
        if ( ++v8 >= (unsigned int)((__int64)(v9[3] - v9[2]) >> 3) )
          goto LABEL_30;
      }
      LODWORD(v25) = v4;
      LODWORD(v24) = v8;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x362,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)v10,
        (int)"Failed to acquire package %d while processing target type = %d",
        v24,
        v25);
      if ( v31 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v9 )
        (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return v10;
    }
LABEL_30:
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    if ( (int)++v4 >= 5 )
      return 0;
    v3 = a1;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x353,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
    (const char *)(unsigned int)v6,
    (int)"Failed to obtain carried dependencies list.",
    v24);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004c440  mov     [rsp-40h+arg_10], r8
0x18004c445  mov     [rsp-40h+arg_8], rdx
0x18004c44a  mov     [rsp-40h+arg_0], rcx
0x18004c44f  push    rbp
0x18004c450  push    rbx
0x18004c451  push    rsi
0x18004c452  push    rdi
0x18004c453  push    r12
0x18004c455  push    r13
0x18004c457  push    r14
0x18004c459  push    r15
0x18004c45b  mov     rbp, rsp
0x18004c45e  sub     rsp, 58h
0x18004c462  mov     rdi, rcx
0x18004c465  xor     r14d, r14d
0x18004c468  xor     ebx, ebx
0x18004c46a  mov     [rbp+arg_10], rbx
0x18004c46e  mov     [rbp+arg_8], rbx
0x18004c472  cmp     r14d, 1
0x18004c476  ja      short loc_18004C499
0x18004c478  mov     [rbp+arg_10], rbx
0x18004c47c  lea     r8, [rbp+arg_10]
0x18004c480  lea     edx, [rbx+3]
0x18004c483  mov     rcx, rdi
0x18004c486  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x18004c48b  mov     ebx, eax
0x18004c48d  test    eax, eax
0x18004c48f  js      loc_18004C6CC
0x18004c495  mov     rbx, [rbp+arg_10]
0x18004c499  mov     [rbp+arg_8], 0
0x18004c4a1  lea     r8, [rbp+arg_8]
0x18004c4a5  mov     edx, r14d
0x18004c4a8  mov     rcx, rdi
0x18004c4ab  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x18004c4b0  mov     edi, eax
0x18004c4b2  test    eax, eax
0x18004c4b4  js      loc_18004C82A
0x18004c4ba  xor     r13d, r13d
0x18004c4bd  mov     rdi, [rbp+arg_8]
0x18004c4c1  mov     rax, [rdi+18h]
0x18004c4c5  sub     rax, [rdi+10h]
0x18004c4c9  sar     rax, 3
0x18004c4cd  test    eax, eax
0x18004c4cf  jz      loc_18004C68C
0x18004c4d5  mov     [rbp+arg_18], 0
0x18004c4dd  lea     r8, [rbp+arg_18]
0x18004c4e1  mov     edx, r13d
0x18004c4e4  mov     rcx, rdi
0x18004c4e7  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004c4ec  mov     esi, eax
0x18004c4ee  test    eax, eax
0x18004c4f0  js      loc_18004C7B3
0x18004c4f6  mov     r15, [rbp+arg_18]
0x18004c4fa  test    r15, r15
0x18004c4fd  jz      loc_18004C769
0x18004c503  mov     rcx, r15; this
0x18004c506  call    ?StagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(void)
0x18004c50b  mov     r12d, eax
0x18004c50e  lea     rsi, [r15+30h]
0x18004c512  cmp     qword ptr [r15+48h], 8
0x18004c517  jb      short loc_18004C51E
0x18004c519  mov     rdx, [rsi]
0x18004c51c  jmp     short loc_18004C521
0x18004c51e  mov     rdx, rsi
0x18004c521  mov     rcx, [rbp+40h]; this
0x18004c525  mov     [rsp+58h+var_28], r14d
0x18004c52a  mov     [rsp+58h+var_30], rdx; char *
0x18004c52f  lea     rax, aFailedToStageP; "Failed to stage package %ws while proce"...
0x18004c536  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c53b  mov     r9d, r12d; char *
0x18004c53e  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c545  mov     edx, 1E6h; void *
0x18004c54a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004c54f  test    r12d, r12d
0x18004c552  js      short loc_18004C5A5
0x18004c554  mov     rcx, r15; this
0x18004c557  call    ?PreRegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(void)
0x18004c55c  mov     r12d, eax
0x18004c55f  cmp     qword ptr [r15+48h], 8
0x18004c564  jb      short loc_18004C56B
0x18004c566  mov     rdx, [rsi]
0x18004c569  jmp     short loc_18004C56E
0x18004c56b  mov     rdx, rsi
0x18004c56e  mov     rcx, [rbp+40h]; this
0x18004c572  mov     [rsp+58h+var_28], r14d
0x18004c577  mov     [rsp+58h+var_30], rdx; char *
0x18004c57c  lea     rax, aFailedToPreReg; "Failed to pre-register package %ws whil"...
0x18004c583  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c588  mov     r9d, r12d; char *
0x18004c58b  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c592  mov     edx, 1E6h; void *
0x18004c597  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004c59c  test    r12d, r12d
0x18004c59f  jns     loc_18004C664
0x18004c5a5  cmp     qword ptr [r15+48h], 8
0x18004c5aa  jb      short loc_18004C5B1
0x18004c5ac  mov     rdx, [rsi]
0x18004c5af  jmp     short loc_18004C5B4
0x18004c5b1  mov     rdx, rsi; unsigned __int16 *
0x18004c5b4  mov     rcx, r15; this
0x18004c5b7  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x18004c5bc  mov     r12d, eax
0x18004c5bf  mov     [rbp+pv], 0
0x18004c5c7  cmp     qword ptr [r15+48h], 8
0x18004c5cc  jb      short loc_18004C5D1
0x18004c5ce  mov     rsi, [rsi]
0x18004c5d1  mov     r9d, r14d
0x18004c5d4  mov     r8, rsi
0x18004c5d7  lea     rdx, aUnableToDestag; "Unable to destage package %ws, processi"...
0x18004c5de  lea     rcx, [rbp+pv]
0x18004c5e2  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004c5e7  mov     rcx, [rbp+40h]; this
0x18004c5eb  test    eax, eax
0x18004c5ed  jns     short loc_18004C603
0x18004c5ef  mov     r9d, eax; char *
0x18004c5f2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c5f9  mov     edx, 1E6h; void *
0x18004c5fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c603  mov     dword ptr [rsp+58h+var_30], r12d
0x18004c608  mov     [rsp+58h+var_38], 1; int
0x18004c610  mov     r9d, 1E6h
0x18004c616  lea     r8, aMsixpackagePro_4; "MsixPackage::Provisioning::Library::Msi"...
0x18004c61d  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c624  mov     rsi, [rbp+pv]
0x18004c628  mov     rcx, rsi
0x18004c62b  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004c630  mov     rcx, [rbp+40h]; this
0x18004c634  test    eax, eax
0x18004c636  jns     short loc_18004C64D
0x18004c638  mov     r9d, eax; char *
0x18004c63b  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c642  mov     edx, 1E6h; void *
0x18004c647  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004c64c  nop
0x18004c64d  test    rsi, rsi
0x18004c650  jz      short loc_18004C65B
0x18004c652  mov     rcx, rsi; pv
0x18004c655  call    cs:__imp_CoTaskMemFree
0x18004c65b  test    r12d, r12d
0x18004c65e  js      loc_18004C70E
0x18004c664  mov     rax, [r15]
0x18004c667  mov     rcx, r15
0x18004c66a  mov     rax, [rax+10h]
0x18004c66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c673  nop
0x18004c674  inc     r13d
0x18004c677  mov     rax, [rdi+18h]
0x18004c67b  sub     rax, [rdi+10h]
0x18004c67f  sar     rax, 3
0x18004c683  cmp     r13d, eax
0x18004c686  jb      loc_18004C4D5
0x18004c68c  test    rdi, rdi
0x18004c68f  jz      short loc_18004C6A1
0x18004c691  mov     rax, [rdi]
0x18004c694  mov     rcx, rdi
0x18004c697  mov     rax, [rax+10h]
0x18004c69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6a0  nop
0x18004c6a1  test    rbx, rbx
0x18004c6a4  jz      short loc_18004C6B6
0x18004c6a6  mov     rax, [rbx]
0x18004c6a9  mov     rcx, rbx
0x18004c6ac  mov     rax, [rax+10h]
0x18004c6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6b5  nop
0x18004c6b6  inc     r14d
0x18004c6b9  cmp     r14d, 5
0x18004c6bd  jge     loc_18004C826
0x18004c6c3  mov     rdi, [rbp+arg_0]
0x18004c6c7  jmp     loc_18004C468
0x18004c6cc  mov     rcx, [rbp+40h]; this
0x18004c6d0  lea     rax, aFailedToObtain_2; "Failed to obtain carried dependencies l"...
0x18004c6d7  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c6dc  mov     r9d, ebx; char *
0x18004c6df  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c6e6  mov     edx, 353h; void *
0x18004c6eb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c6f0  nop
0x18004c6f1  mov     rcx, [rbp+arg_10]
0x18004c6f5  test    rcx, rcx
0x18004c6f8  jz      short loc_18004C707
0x18004c6fa  mov     rax, [rcx]
0x18004c6fd  mov     rax, [rax+10h]
0x18004c701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c706  nop
0x18004c707  mov     eax, ebx
0x18004c709  jmp     loc_18004C881
0x18004c70e  mov     rcx, [rbp+40h]; this
0x18004c712  mov     r9d, r12d; char *
0x18004c715  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c71c  mov     edx, 365h; void *
0x18004c721  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c726  nop
0x18004c727  mov     rax, [r15]
0x18004c72a  mov     rcx, r15
0x18004c72d  mov     rax, [rax+10h]
0x18004c731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c736  nop
0x18004c737  test    rdi, rdi
0x18004c73a  jz      short loc_18004C74C
0x18004c73c  mov     rax, [rdi]
0x18004c73f  mov     rcx, rdi
0x18004c742  mov     rax, [rax+10h]
0x18004c746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c74b  nop
0x18004c74c  test    rbx, rbx
0x18004c74f  jz      short loc_18004C761
0x18004c751  mov     rax, [rbx]
0x18004c754  mov     rcx, rbx
0x18004c757  mov     rax, [rax+10h]
0x18004c75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c760  nop
0x18004c761  mov     eax, r12d
0x18004c764  jmp     loc_18004C881
0x18004c769  mov     rcx, [rbp+40h]; this
0x18004c76d  mov     esi, 8007000Eh
0x18004c772  mov     r9d, esi; char *
0x18004c775  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c77c  mov     edx, 363h; void *
0x18004c781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c786  nop
0x18004c787  test    rdi, rdi
0x18004c78a  jz      short loc_18004C79C
0x18004c78c  mov     rax, [rdi]
0x18004c78f  mov     rcx, rdi
0x18004c792  mov     rax, [rax+10h]
0x18004c796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c79b  nop
0x18004c79c  test    rbx, rbx
0x18004c79f  jz      short loc_18004C7B1
0x18004c7a1  mov     rcx, [rbx]
0x18004c7a4  mov     rax, [rcx+10h]
0x18004c7a8  mov     rcx, rbx
0x18004c7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7b0  nop
0x18004c7b1  jmp     short loc_18004C822
0x18004c7b3  mov     rcx, [rbp+40h]; this
0x18004c7b7  mov     [rsp+58h+var_28], r14d
0x18004c7bc  mov     dword ptr [rsp+58h+var_30], r13d; char *
0x18004c7c1  lea     rax, aFailedToAcquir_0; "Failed to acquire package %d while proc"...
0x18004c7c8  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c7cd  mov     r9d, esi; char *
0x18004c7d0  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c7d7  mov     edx, 362h; void *
0x18004c7dc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c7e1  nop
0x18004c7e2  mov     rcx, [rbp+arg_18]
0x18004c7e6  test    rcx, rcx
0x18004c7e9  jz      short loc_18004C7F8
0x18004c7eb  mov     rax, [rcx]
0x18004c7ee  mov     rax, [rax+10h]
0x18004c7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7f7  nop
0x18004c7f8  test    rdi, rdi
0x18004c7fb  jz      short loc_18004C80D
0x18004c7fd  mov     rax, [rdi]
0x18004c800  mov     rcx, rdi
0x18004c803  mov     rax, [rax+10h]
0x18004c807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c80c  nop
0x18004c80d  test    rbx, rbx
0x18004c810  jz      short loc_18004C822
0x18004c812  mov     rax, [rbx]
0x18004c815  mov     rcx, rbx
0x18004c818  mov     rax, [rax+10h]
0x18004c81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c821  nop
0x18004c822  mov     eax, esi
0x18004c824  jmp     short loc_18004C881
0x18004c826  xor     eax, eax
0x18004c828  jmp     short loc_18004C881
0x18004c82a  mov     rcx, [rbp+40h]; this
0x18004c82e  mov     dword ptr [rsp+58h+var_30], r14d; char *
0x18004c833  lea     rax, aFailedToObtain_7; "Failed to obtain carried package list f"...
0x18004c83a  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004c83f  mov     r9d, edi; char *
0x18004c842  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c849  mov     edx, 35Ch; void *
0x18004c84e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c853  nop
0x18004c854  mov     rcx, [rbp+arg_8]
0x18004c858  test    rcx, rcx
0x18004c85b  jz      short loc_18004C86A
0x18004c85d  mov     rax, [rcx]
0x18004c860  mov     rax, [rax+10h]
0x18004c864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c869  nop
0x18004c86a  test    rbx, rbx
0x18004c86d  jz      short loc_18004C87F
0x18004c86f  mov     rax, [rbx]
0x18004c872  mov     rcx, rbx
0x18004c875  mov     rax, [rax+10h]
0x18004c879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c87e  nop
0x18004c87f  mov     eax, edi
0x18004c881  add     rsp, 58h
0x18004c885  pop     r15
0x18004c887  pop     r14
0x18004c889  pop     r13
0x18004c88b  pop     r12
  ... truncated ...
```
