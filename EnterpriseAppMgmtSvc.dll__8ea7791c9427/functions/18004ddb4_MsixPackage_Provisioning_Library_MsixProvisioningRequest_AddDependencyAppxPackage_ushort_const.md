# MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage(ushort const *)

- ea: `0x18004ddb4`
- end: `0x18004e1f6`
- name: `?AddDependencyAppxPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `1090`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *this, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035260`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003f030`
- `0x180040400`
- `0x180041e2c`
- `0x1800441c8`
- `0x180047338`
- `0x18004ddb4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004df76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e132`

## string_xrefs

- `0x18004de1a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004de9d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004df0d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004df5e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004dff4`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e0c9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e11a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004de0b`: `Failed to create adapter for '%ws'.`
- `0x18004dfe5`: `Failed to create adapter for existing package '%ws'.`
- `0x18004df3e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e0fa`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004df37`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage`
- `0x18004e0f3`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        const char *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  const char *v6; // r9
  __int64 result; // rax
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v8; // rbx
  unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // rdx
  int IsPackageArchitectureApplicable; // r15d
  int v12; // eax
  void *v13; // rdi
  int v14; // eax
  char *v15; // rcx
  int v16; // r15d
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v17; // rdi
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v18; // r15
  int v19; // eax
  void *v20; // rdi
  int v21; // eax
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v22; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF
  const char *v25; // [rsp+78h] [rbp+10h]
  int v26; // [rsp+80h] [rbp+18h] BYREF
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v27; // [rsp+88h] [rbp+20h] BYREF

  v25 = a2;
  v26 = 0;
  LOBYTE(pv) = 0;
  v27 = 0;
  v22 = 0;
  v4 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(a2, 3, *((_QWORD *)this + 2), &v22);
  try
  {
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4E7,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v4,
        (int)"Failed to create adapter for '%ws'.",
        a2);
      if ( v22 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v22 + 16LL))(v22);
      return v5;
    }
    v8 = v22;
    v9 = (unsigned __int16 *)((char *)v22 + 48);
    if ( *((_QWORD *)v22 + 9) < 8u )
      v10 = (const unsigned __int16 *)((char *)v22 + 48);
    else
      v10 = *(const unsigned __int16 **)v9;
    IsPackageArchitectureApplicable = MsixPackage::Provisioning::Library::MsixProvisioningContext::IsPackageArchitectureApplicable(
                                        *((MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
                                        v10,
                                        &v26);
    if ( IsPackageArchitectureApplicable < 0 )
    {
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(unsigned __int16 **)v9;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)IsPackageArchitectureApplicable,
        (int)"Failed while testing applicability of package moniker '%ws'",
        (const char *)v9);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)IsPackageArchitectureApplicable;
    }
    if ( !v26 )
    {
      pv = 0;
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(unsigned __int16 **)v9;
      v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&pv,
              L"Package moniker '%s' excluded as not applicable on this architecture",
              v9);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F5,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v12);
      v13 = pv;
      v14 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              pv,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
              L"MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage",
              1277);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4FD,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v14);
      if ( v13 )
        CoTaskMemFree(v13);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return 0;
    }
    v27 = 0;
    if ( *((_QWORD *)v9 + 3) < 8u )
      v15 = (char *)v9;
    else
      v15 = *(char **)v9;
    v16 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(
            v15,
            *((struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
            (bool *)&pv,
            &v27);
    if ( v16 < 0 )
    {
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(unsigned __int16 **)v9;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x50A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v16,
        (int)"Failed to create adapter for existing package '%ws'.",
        (const char *)v9);
      if ( v27 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)v16;
    }
    if ( !(_BYTE)pv )
    {
      v17 = v27;
LABEL_59:
      MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
        *((_QWORD *)this + 6),
        v8);
      if ( v17 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return 0;
    }
    if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 600LL) )
    {
      v17 = v27;
      v18 = v8;
      v8 = v27;
      v22 = v27;
      if ( v27 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 8LL))(v27);
      if ( v18 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_59;
    }
    pv = 0;
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(unsigned __int16 **)v9;
    v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&pv,
            L"Package moniker '%s' excluded as it is not applicable because an existing version was found",
            v9);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51B,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v19);
    v20 = pv;
    v21 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
            L"MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage",
            1315);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x523,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v21);
    if ( v20 )
      CoTaskMemFree(v20);
    if ( v27 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v8 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x531,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18004ddb4  mov     rax, rsp
0x18004ddb7  mov     [rax+10h], rdx
0x18004ddbb  push    rbx
0x18004ddbc  push    rdi
0x18004ddbd  push    r14
0x18004ddbf  push    r15
0x18004ddc1  sub     rsp, 48h
0x18004ddc5  mov     rbx, rdx
0x18004ddc8  mov     r14, rcx
0x18004ddcb  mov     dword ptr [rax+18h], 0
0x18004ddd2  mov     byte ptr [rax+8], 0
0x18004ddd6  mov     qword ptr [rax+20h], 0
0x18004ddde  mov     qword ptr [rax-38h], 0
0x18004dde6  lea     r9, [rax-38h]
0x18004ddea  mov     r8, [rcx+10h]
0x18004ddee  mov     edx, 3
0x18004ddf3  mov     rcx, rbx
0x18004ddf6  call    ?CreateFromPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGW4APPX_PACKAGE_TARGET_TYPE@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(ushort const *,MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004ddfb  mov     edi, eax
0x18004ddfd  test    eax, eax
0x18004ddff  jns     short loc_18004DE4A
0x18004de01  mov     rcx, [rsp+68h]; this
0x18004de06  mov     [rsp+68h+var_40], rbx; char *
0x18004de0b  lea     rax, aFailedToCreate_12; "Failed to create adapter for '%ws'."
0x18004de12  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004de17  mov     r9d, edi; char *
0x18004de1a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004de21  mov     edx, 4E7h; void *
0x18004de26  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004de2b  nop
0x18004de2c  mov     rcx, [rsp+68h+var_38]
0x18004de31  test    rcx, rcx
0x18004de34  jz      short loc_18004DE43
0x18004de36  mov     rax, [rcx]
0x18004de39  mov     rax, [rax+10h]
0x18004de3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de42  nop
0x18004de43  mov     eax, edi
0x18004de45  jmp     loc_18004E1EA
0x18004de4a  mov     rbx, [rsp+68h+var_38]
0x18004de4f  lea     rdi, [rbx+30h]
0x18004de53  cmp     qword ptr [rdi+18h], 8
0x18004de58  jb      short loc_18004DE5F
0x18004de5a  mov     rdx, [rdi]
0x18004de5d  jmp     short loc_18004DE62
0x18004de5f  mov     rdx, rdi; unsigned __int16 *
0x18004de62  lea     r8, [rsp+68h+arg_10]; int *
0x18004de6a  mov     rcx, [r14+10h]; this
0x18004de6e  call    ?IsPackageArchitectureApplicable@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::IsPackageArchitectureApplicable(ushort const *,int *)
0x18004de73  mov     r15d, eax
0x18004de76  test    eax, eax
0x18004de78  jns     short loc_18004DECC
0x18004de7a  cmp     qword ptr [rdi+18h], 8
0x18004de7f  jb      short loc_18004DE84
0x18004de81  mov     rdi, [rdi]
0x18004de84  mov     rcx, [rsp+68h]; this
0x18004de89  mov     [rsp+68h+var_40], rdi; char *
0x18004de8e  lea     rax, aFailedWhileTes_0; "Failed while testing applicability of p"...
0x18004de95  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004de9a  mov     r9d, r15d; char *
0x18004de9d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dea4  mov     edx, 4EBh; void *
0x18004dea9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004deae  nop
0x18004deaf  test    rbx, rbx
0x18004deb2  jz      short loc_18004DEC4
0x18004deb4  mov     rax, [rbx]
0x18004deb7  mov     rcx, rbx
0x18004deba  mov     rax, [rax+10h]
0x18004debe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dec3  nop
0x18004dec4  mov     eax, r15d
0x18004dec7  jmp     loc_18004E1EA
0x18004decc  cmp     [rsp+68h+arg_10], 0
0x18004ded4  jnz     loc_18004DF99
0x18004deda  mov     [rsp+68h+pv], 0
0x18004dee3  cmp     qword ptr [rdi+18h], 8
0x18004dee8  jb      short loc_18004DEED
0x18004deea  mov     rdi, [rdi]
0x18004deed  mov     r8, rdi
0x18004def0  lea     rdx, aPackageMoniker_0; "Package moniker '%s' excluded as not ap"...
0x18004def7  lea     rcx, [rsp+68h+pv]
0x18004defc  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004df01  mov     rcx, [rsp+68h]; this
0x18004df06  test    eax, eax
0x18004df08  jns     short loc_18004DF1E
0x18004df0a  mov     r9d, eax; char *
0x18004df0d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004df14  mov     edx, 4F5h; void *
0x18004df19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004df1e  mov     dword ptr [rsp+68h+var_40], 0
0x18004df26  mov     [rsp+68h+var_48], 2; int
0x18004df2e  mov     r14d, 4FDh
0x18004df34  mov     r9d, r14d
0x18004df37  lea     r8, aMsixpackagePro_5; "MsixPackage::Provisioning::Library::Msi"...
0x18004df3e  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004df45  mov     rdi, [rsp+68h+pv]
0x18004df4a  mov     rcx, rdi
0x18004df4d  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004df52  mov     rcx, [rsp+68h]; this
0x18004df57  test    eax, eax
0x18004df59  jns     short loc_18004DF6E
0x18004df5b  mov     r9d, eax; char *
0x18004df5e  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004df65  mov     edx, r14d; void *
0x18004df68  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004df6d  nop
0x18004df6e  test    rdi, rdi
0x18004df71  jz      short loc_18004DF7D
0x18004df73  mov     rcx, rdi; pv
0x18004df76  call    cs:__imp_CoTaskMemFree
0x18004df7c  nop
0x18004df7d  test    rbx, rbx
0x18004df80  jz      short loc_18004DF92
0x18004df82  mov     rax, [rbx]
0x18004df85  mov     rcx, rbx
0x18004df88  mov     rax, [rax+10h]
0x18004df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df91  nop
0x18004df92  xor     eax, eax
0x18004df94  jmp     loc_18004E1EA
0x18004df99  mov     [rsp+68h+arg_18], 0
0x18004dfa5  cmp     qword ptr [rdi+18h], 8
0x18004dfaa  jb      short loc_18004DFB1
0x18004dfac  mov     rcx, [rdi]
0x18004dfaf  jmp     short loc_18004DFB4
0x18004dfb1  mov     rcx, rdi; char *
0x18004dfb4  lea     r9, [rsp+68h+arg_18]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18004dfbc  lea     r8, [rsp+68h+pv]; bool *
0x18004dfc1  mov     rdx, [r14+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18004dfc5  call    ?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004dfca  mov     r15d, eax
0x18004dfcd  test    eax, eax
0x18004dfcf  jns     short loc_18004E03D
0x18004dfd1  cmp     qword ptr [rdi+18h], 8
0x18004dfd6  jb      short loc_18004DFDB
0x18004dfd8  mov     rdi, [rdi]
0x18004dfdb  mov     rcx, [rsp+68h]; this
0x18004dfe0  mov     [rsp+68h+var_40], rdi; char *
0x18004dfe5  lea     rax, aFailedToCreate_0; "Failed to create adapter for existing p"...
0x18004dfec  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004dff1  mov     r9d, r15d; char *
0x18004dff4  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004dffb  mov     edx, 50Ah; void *
0x18004e000  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e005  nop
0x18004e006  mov     rcx, [rsp+68h+arg_18]
0x18004e00e  test    rcx, rcx
0x18004e011  jz      short loc_18004E020
0x18004e013  mov     rax, [rcx]
0x18004e016  mov     rax, [rax+10h]
0x18004e01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e01f  nop
0x18004e020  test    rbx, rbx
0x18004e023  jz      short loc_18004E035
0x18004e025  mov     rax, [rbx]
0x18004e028  mov     rcx, rbx
0x18004e02b  mov     rax, [rax+10h]
0x18004e02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e034  nop
0x18004e035  mov     eax, r15d
0x18004e038  jmp     loc_18004E1EA
0x18004e03d  cmp     byte ptr [rsp+68h+pv], 0
0x18004e042  jz      loc_18004E16C
0x18004e048  mov     rax, [r14+10h]
0x18004e04c  cmp     dword ptr [rax+258h], 0
0x18004e053  jnz     short loc_18004E096
0x18004e055  mov     rdi, [rsp+68h+arg_18]
0x18004e05d  mov     r15, rbx
0x18004e060  mov     rbx, rdi
0x18004e063  mov     [rsp+68h+var_38], rbx
0x18004e068  test    rdi, rdi
0x18004e06b  jz      short loc_18004E07C
0x18004e06d  mov     rax, [rdi]
0x18004e070  mov     rcx, rdi
0x18004e073  mov     rax, [rax+8]
0x18004e077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e07c  test    r15, r15
0x18004e07f  jz      short loc_18004E091
0x18004e081  mov     rax, [r15]
0x18004e084  mov     rcx, r15
0x18004e087  mov     rax, [rax+10h]
0x18004e08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e090  nop
0x18004e091  jmp     loc_18004E174
0x18004e096  mov     [rsp+68h+pv], 0
0x18004e09f  cmp     qword ptr [rdi+18h], 8
0x18004e0a4  jb      short loc_18004E0A9
0x18004e0a6  mov     rdi, [rdi]
0x18004e0a9  mov     r8, rdi
0x18004e0ac  lea     rdx, aPackageMoniker; "Package moniker '%s' excluded as it is "...
0x18004e0b3  lea     rcx, [rsp+68h+pv]
0x18004e0b8  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004e0bd  mov     rcx, [rsp+68h]; this
0x18004e0c2  test    eax, eax
0x18004e0c4  jns     short loc_18004E0DA
0x18004e0c6  mov     r9d, eax; char *
0x18004e0c9  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e0d0  mov     edx, 51Bh; void *
0x18004e0d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e0da  mov     dword ptr [rsp+68h+var_40], 0
0x18004e0e2  mov     [rsp+68h+var_48], 2; int
0x18004e0ea  mov     r14d, 523h
0x18004e0f0  mov     r9d, r14d
0x18004e0f3  lea     r8, aMsixpackagePro_5; "MsixPackage::Provisioning::Library::Msi"...
0x18004e0fa  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e101  mov     rdi, [rsp+68h+pv]
0x18004e106  mov     rcx, rdi
0x18004e109  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e10e  mov     rcx, [rsp+68h]; this
0x18004e113  test    eax, eax
0x18004e115  jns     short loc_18004E12A
0x18004e117  mov     r9d, eax; char *
0x18004e11a  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e121  mov     edx, r14d; void *
0x18004e124  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e129  nop
0x18004e12a  test    rdi, rdi
0x18004e12d  jz      short loc_18004E139
0x18004e12f  mov     rcx, rdi; pv
0x18004e132  call    cs:__imp_CoTaskMemFree
0x18004e138  nop
0x18004e139  mov     rcx, [rsp+68h+arg_18]
0x18004e141  test    rcx, rcx
0x18004e144  jz      short loc_18004E153
0x18004e146  mov     rax, [rcx]
0x18004e149  mov     rax, [rax+10h]
0x18004e14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e152  nop
0x18004e153  test    rbx, rbx
0x18004e156  jz      short loc_18004E168
0x18004e158  mov     rax, [rbx]
0x18004e15b  mov     rcx, rbx
0x18004e15e  mov     rax, [rax+10h]
0x18004e162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e167  nop
0x18004e168  xor     eax, eax
0x18004e16a  jmp     short loc_18004E1EA
0x18004e16c  mov     rdi, [rsp+68h+arg_18]
0x18004e174  mov     rdx, rbx
0x18004e177  mov     rcx, [r14+30h]
0x18004e17b  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x18004e180  nop
0x18004e181  test    rdi, rdi
0x18004e184  jz      short loc_18004E196
0x18004e186  mov     rax, [rdi]
0x18004e189  mov     rcx, rdi
0x18004e18c  mov     rax, [rax+10h]
0x18004e190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e195  nop
0x18004e196  test    rbx, rbx
0x18004e199  jz      short loc_18004E1AB
0x18004e19b  mov     rax, [rbx]
0x18004e19e  mov     rcx, rbx
0x18004e1a1  mov     rax, [rax+10h]
0x18004e1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1aa  nop
0x18004e1ab  xor     eax, eax
0x18004e1ad  jmp     short loc_18004E1EA
0x18004e1af  mov     rcx, [rsp+68h+arg_18]
0x18004e1b7  test    rcx, rcx
0x18004e1ba  jz      short loc_18004E1C9
0x18004e1bc  mov     rax, [rcx]
0x18004e1bf  mov     rax, [rax+10h]
0x18004e1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1c8  nop
0x18004e1c9  mov     rcx, [rsp+68h+var_38]
0x18004e1ce  test    rcx, rcx
0x18004e1d1  jz      short loc_18004E1E0
0x18004e1d3  mov     rax, [rcx]
0x18004e1d6  mov     rax, [rax+10h]
0x18004e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1df  nop
0x18004e1e0  mov     eax, dword ptr [rsp+68h+pv]
0x18004e1e4  jmp     short loc_18004E1EA
0x18004e1e6  mov     eax, dword ptr [rsp+68h+pv]
0x18004e1ea  add     rsp, 48h
0x18004e1ee  pop     r15
0x18004e1f0  pop     r14
0x18004e1f2  pop     rdi
0x18004e1f3  pop     rbx
0x18004e1f4  retn
```
