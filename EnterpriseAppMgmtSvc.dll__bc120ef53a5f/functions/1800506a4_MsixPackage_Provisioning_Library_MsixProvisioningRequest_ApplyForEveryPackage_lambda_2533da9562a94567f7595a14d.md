# MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_2533da9562a94567f7595a14d7cabddb___

- ea: `0x1800506a4`
- end: `0x180050afd`
- name: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::ApplyForEveryPackage__lambda_2533da9562a94567f7595a14d7cabddb___`
- size: `1113`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056068`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003c2c0`
- `0x18003c6d4`
- `0x18003d4ec`
- `0x180043fb4`
- `0x180048dec`
- `0x18004c710`
- `0x18004f030`
- `0x1800506a4`
- `0x180055cf8`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800508b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800508b9`

## string_xrefs

- `0x1800507a2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800507ef`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050856`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005089f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050949`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005097f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800509df`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050a3a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050aac`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180050881`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005087a`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::StageLooseFilePackagesOnline::<lambda_2533da9562a94567f7595a14d7cabddb>::operator ()`

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
  const unsigned __int16 *v17; // rdx
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
            v17 = (const unsigned __int16 *)((char *)v11 + 48);
          else
            v17 = (const unsigned __int16 *)*v13;
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
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v19,
              v23);
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
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v21,
              1);
          if ( v20 )
            CoTaskMemFree(v20);
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x365,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              (const char *)(unsigned int)v18,
              v23);
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
0x1800506a4  mov     [rsp-40h+arg_10], r8
0x1800506a9  mov     [rsp-40h+arg_8], rdx
0x1800506ae  mov     [rsp-40h+arg_0], rcx
0x1800506b3  push    rbp
0x1800506b4  push    rbx
0x1800506b5  push    rsi
0x1800506b6  push    rdi
0x1800506b7  push    r12
0x1800506b9  push    r13
0x1800506bb  push    r14
0x1800506bd  push    r15
0x1800506bf  mov     rbp, rsp
0x1800506c2  sub     rsp, 58h
0x1800506c6  mov     rdi, rcx
0x1800506c9  xor     r14d, r14d
0x1800506cc  xor     ebx, ebx
0x1800506ce  mov     [rbp+arg_10], rbx
0x1800506d2  mov     [rbp+arg_8], rbx
0x1800506d6  cmp     r14d, 1
0x1800506da  ja      short loc_1800506FD
0x1800506dc  mov     [rbp+arg_10], rbx
0x1800506e0  lea     r8, [rbp+arg_10]
0x1800506e4  lea     edx, [rbx+3]
0x1800506e7  mov     rcx, rdi
0x1800506ea  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x1800506ef  mov     ebx, eax
0x1800506f1  test    eax, eax
0x1800506f3  js      loc_180050936
0x1800506f9  mov     rbx, [rbp+arg_10]
0x1800506fd  mov     [rbp+arg_8], 0
0x180050705  lea     r8, [rbp+arg_8]
0x180050709  mov     edx, r14d
0x18005070c  mov     rcx, rdi
0x18005070f  call    ?PackageList@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJW4APPX_PACKAGE_TARGET_TYPE@234@PEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::MsixProvisioningRequest::PackageList(MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x180050714  mov     edi, eax
0x180050716  test    eax, eax
0x180050718  js      loc_180050A94
0x18005071e  xor     r13d, r13d
0x180050721  mov     rdi, [rbp+arg_8]
0x180050725  mov     rax, [rdi+18h]
0x180050729  sub     rax, [rdi+10h]
0x18005072d  sar     rax, 3
0x180050731  test    eax, eax
0x180050733  jz      loc_1800508F6
0x180050739  mov     [rbp+arg_18], 0
0x180050741  lea     r8, [rbp+arg_18]
0x180050745  mov     edx, r13d
0x180050748  mov     rcx, rdi
0x18005074b  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180050750  mov     esi, eax
0x180050752  test    eax, eax
0x180050754  js      loc_180050A1D
0x18005075a  mov     r15, [rbp+arg_18]
0x18005075e  test    r15, r15
0x180050761  jz      loc_1800509D3
0x180050767  mov     rcx, r15; this
0x18005076a  call    ?StagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::StagePackage(void)
0x18005076f  mov     r12d, eax
0x180050772  lea     rsi, [r15+30h]
0x180050776  cmp     qword ptr [r15+48h], 8
0x18005077b  jb      short loc_180050782
0x18005077d  mov     rdx, [rsi]
0x180050780  jmp     short loc_180050785
0x180050782  mov     rdx, rsi
0x180050785  mov     rcx, [rbp+40h]; this
0x180050789  mov     [rsp+58h+var_28], r14d
0x18005078e  mov     [rsp+58h+var_30], rdx; char *
0x180050793  lea     rax, aFailedToStageP; "Failed to stage package %ws while proce"...
0x18005079a  mov     qword ptr [rsp+58h+var_38], rax; int
0x18005079f  mov     r9d, r12d; char *
0x1800507a2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800507a9  mov     edx, 1E6h; void *
0x1800507ae  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800507b3  test    r12d, r12d
0x1800507b6  js      short loc_180050809
0x1800507b8  mov     rcx, r15; this
0x1800507bb  call    ?PreRegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixPackageAdapter::PreRegisterPackage(void)
0x1800507c0  mov     r12d, eax
0x1800507c3  cmp     qword ptr [r15+48h], 8
0x1800507c8  jb      short loc_1800507CF
0x1800507ca  mov     rdx, [rsi]
0x1800507cd  jmp     short loc_1800507D2
0x1800507cf  mov     rdx, rsi
0x1800507d2  mov     rcx, [rbp+40h]; this
0x1800507d6  mov     [rsp+58h+var_28], r14d
0x1800507db  mov     [rsp+58h+var_30], rdx; char *
0x1800507e0  lea     rax, aFailedToPreReg; "Failed to pre-register package %ws whil"...
0x1800507e7  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800507ec  mov     r9d, r12d; char *
0x1800507ef  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800507f6  mov     edx, 1E6h; void *
0x1800507fb  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180050800  test    r12d, r12d
0x180050803  jns     loc_1800508CE
0x180050809  cmp     qword ptr [r15+48h], 8
0x18005080e  jb      short loc_180050815
0x180050810  mov     rdx, [rsi]
0x180050813  jmp     short loc_180050818
0x180050815  mov     rdx, rsi; unsigned __int16 *
0x180050818  mov     rcx, r15; this
0x18005081b  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x180050820  mov     r12d, eax
0x180050823  mov     [rbp+pv], 0
0x18005082b  cmp     qword ptr [r15+48h], 8
0x180050830  jb      short loc_180050835
0x180050832  mov     rsi, [rsi]
0x180050835  mov     r9d, r14d
0x180050838  mov     r8, rsi
0x18005083b  lea     rdx, aUnableToDestag; "Unable to destage package %ws, processi"...
0x180050842  lea     rcx, [rbp+pv]
0x180050846  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005084b  mov     rcx, [rbp+40h]; this
0x18005084f  test    eax, eax
0x180050851  jns     short loc_180050867
0x180050853  mov     r9d, eax; char *
0x180050856  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005085d  mov     edx, 1E6h; void *
0x180050862  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050867  mov     dword ptr [rsp+58h+var_30], r12d
0x18005086c  mov     [rsp+58h+var_38], 1; int
0x180050874  mov     r9d, 1E6h
0x18005087a  lea     r8, aMsixpackagePro_4; "MsixPackage::Provisioning::Library::Msi"...
0x180050881  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050888  mov     rsi, [rbp+pv]
0x18005088c  mov     rcx, rsi
0x18005088f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180050894  mov     rcx, [rbp+40h]; this
0x180050898  test    eax, eax
0x18005089a  jns     short loc_1800508B1
0x18005089c  mov     r9d, eax; char *
0x18005089f  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800508a6  mov     edx, 1E6h; void *
0x1800508ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800508b0  nop
0x1800508b1  test    rsi, rsi
0x1800508b4  jz      short loc_1800508C5
0x1800508b6  mov     rcx, rsi; pv
0x1800508b9  call    cs:__imp_CoTaskMemFree
0x1800508c0  nop     dword ptr [rax+rax+00h]
0x1800508c5  test    r12d, r12d
0x1800508c8  js      loc_180050978
0x1800508ce  mov     rax, [r15]
0x1800508d1  mov     rcx, r15
0x1800508d4  mov     rax, [rax+10h]
0x1800508d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508dd  nop
0x1800508de  inc     r13d
0x1800508e1  mov     rax, [rdi+18h]
0x1800508e5  sub     rax, [rdi+10h]
0x1800508e9  sar     rax, 3
0x1800508ed  cmp     r13d, eax
0x1800508f0  jb      loc_180050739
0x1800508f6  test    rdi, rdi
0x1800508f9  jz      short loc_18005090B
0x1800508fb  mov     rax, [rdi]
0x1800508fe  mov     rcx, rdi
0x180050901  mov     rax, [rax+10h]
0x180050905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005090a  nop
0x18005090b  test    rbx, rbx
0x18005090e  jz      short loc_180050920
0x180050910  mov     rax, [rbx]
0x180050913  mov     rcx, rbx
0x180050916  mov     rax, [rax+10h]
0x18005091a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005091f  nop
0x180050920  inc     r14d
0x180050923  cmp     r14d, 5
0x180050927  jge     loc_180050A90
0x18005092d  mov     rdi, [rbp+arg_0]
0x180050931  jmp     loc_1800506CC
0x180050936  mov     rcx, [rbp+40h]; this
0x18005093a  lea     rax, aFailedToObtain_2; "Failed to obtain carried dependencies l"...
0x180050941  mov     qword ptr [rsp+58h+var_38], rax; int
0x180050946  mov     r9d, ebx; char *
0x180050949  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050950  mov     edx, 353h; void *
0x180050955  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005095a  nop
0x18005095b  mov     rcx, [rbp+arg_10]
0x18005095f  test    rcx, rcx
0x180050962  jz      short loc_180050971
0x180050964  mov     rax, [rcx]
0x180050967  mov     rax, [rax+10h]
0x18005096b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050970  nop
0x180050971  mov     eax, ebx
0x180050973  jmp     loc_180050AEB
0x180050978  mov     rcx, [rbp+40h]; this
0x18005097c  mov     r9d, r12d; char *
0x18005097f  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050986  mov     edx, 365h; void *
0x18005098b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050990  nop
0x180050991  mov     rax, [r15]
0x180050994  mov     rcx, r15
0x180050997  mov     rax, [rax+10h]
0x18005099b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509a0  nop
0x1800509a1  test    rdi, rdi
0x1800509a4  jz      short loc_1800509B6
0x1800509a6  mov     rax, [rdi]
0x1800509a9  mov     rcx, rdi
0x1800509ac  mov     rax, [rax+10h]
0x1800509b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509b5  nop
0x1800509b6  test    rbx, rbx
0x1800509b9  jz      short loc_1800509CB
0x1800509bb  mov     rax, [rbx]
0x1800509be  mov     rcx, rbx
0x1800509c1  mov     rax, [rax+10h]
0x1800509c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509ca  nop
0x1800509cb  mov     eax, r12d
0x1800509ce  jmp     loc_180050AEB
0x1800509d3  mov     rcx, [rbp+40h]; this
0x1800509d7  mov     esi, 8007000Eh
0x1800509dc  mov     r9d, esi; char *
0x1800509df  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800509e6  mov     edx, 363h; void *
0x1800509eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800509f0  nop
0x1800509f1  test    rdi, rdi
0x1800509f4  jz      short loc_180050A06
0x1800509f6  mov     rax, [rdi]
0x1800509f9  mov     rcx, rdi
0x1800509fc  mov     rax, [rax+10h]
0x180050a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a05  nop
0x180050a06  test    rbx, rbx
0x180050a09  jz      short loc_180050A1B
0x180050a0b  mov     rcx, [rbx]
0x180050a0e  mov     rax, [rcx+10h]
0x180050a12  mov     rcx, rbx
0x180050a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a1a  nop
0x180050a1b  jmp     short loc_180050A8C
0x180050a1d  mov     rcx, [rbp+40h]; this
0x180050a21  mov     [rsp+58h+var_28], r14d
0x180050a26  mov     dword ptr [rsp+58h+var_30], r13d; char *
0x180050a2b  lea     rax, aFailedToAcquir_0; "Failed to acquire package %d while proc"...
0x180050a32  mov     qword ptr [rsp+58h+var_38], rax; int
0x180050a37  mov     r9d, esi; char *
0x180050a3a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050a41  mov     edx, 362h; void *
0x180050a46  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050a4b  nop
0x180050a4c  mov     rcx, [rbp+arg_18]
0x180050a50  test    rcx, rcx
0x180050a53  jz      short loc_180050A62
0x180050a55  mov     rax, [rcx]
0x180050a58  mov     rax, [rax+10h]
0x180050a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a61  nop
0x180050a62  test    rdi, rdi
0x180050a65  jz      short loc_180050A77
0x180050a67  mov     rax, [rdi]
0x180050a6a  mov     rcx, rdi
0x180050a6d  mov     rax, [rax+10h]
0x180050a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a76  nop
0x180050a77  test    rbx, rbx
0x180050a7a  jz      short loc_180050A8C
0x180050a7c  mov     rax, [rbx]
0x180050a7f  mov     rcx, rbx
0x180050a82  mov     rax, [rax+10h]
0x180050a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a8b  nop
0x180050a8c  mov     eax, esi
0x180050a8e  jmp     short loc_180050AEB
0x180050a90  xor     eax, eax
0x180050a92  jmp     short loc_180050AEB
0x180050a94  mov     rcx, [rbp+40h]; this
0x180050a98  mov     dword ptr [rsp+58h+var_30], r14d; char *
0x180050a9d  lea     rax, aFailedToObtain_7; "Failed to obtain carried package list f"...
0x180050aa4  mov     qword ptr [rsp+58h+var_38], rax; int
0x180050aa9  mov     r9d, edi; char *
0x180050aac  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180050ab3  mov     edx, 35Ch; void *
0x180050ab8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050abd  nop
0x180050abe  mov     rcx, [rbp+arg_8]
0x180050ac2  test    rcx, rcx
0x180050ac5  jz      short loc_180050AD4
0x180050ac7  mov     rax, [rcx]
0x180050aca  mov     rax, [rax+10h]
0x180050ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ad3  nop
0x180050ad4  test    rbx, rbx
0x180050ad7  jz      short loc_180050AE9
0x180050ad9  mov     rax, [rbx]
0x180050adc  mov     rcx, rbx
0x180050adf  mov     rax, [rax+10h]
0x180050ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ae8  nop
0x180050ae9  mov     eax, edi
0x180050aeb  add     rsp, 58h
0x180050aef  pop     r15
0x180050af1  pop     r14
0x180050af3  pop     r13
  ... truncated ...
```
