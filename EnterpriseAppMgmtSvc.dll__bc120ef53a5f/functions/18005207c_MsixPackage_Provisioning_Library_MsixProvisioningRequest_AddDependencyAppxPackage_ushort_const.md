# MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage(ushort const *)

- ea: `0x18005207c`
- end: `0x1800524ca`
- name: `?AddDependencyAppxPackage@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `1102`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003856c`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180042a64`
- `0x180043fb4`
- `0x180045b3c`
- `0x18004804c`
- `0x18004b384`
- `0x18005207c`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005223e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052400`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005223e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052400`

## string_xrefs

- `0x1800520e2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052165`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800521d5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052226`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800522c2`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052397`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800523e8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800520d3`: `Failed to create adapter for '%ws'.`
- `0x1800522b3`: `Failed to create adapter for existing package '%ws'.`
- `0x180052206`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800523c8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x1800521ff`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage`
- `0x1800523c1`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::AddDependencyAppxPackage(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  const char *v6; // r9
  __int64 result; // rax
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v8; // rbx
  char *v9; // rdi
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
  int v22; // [rsp+20h] [rbp-48h]
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v23; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v26; // [rsp+78h] [rbp+10h]
  int v27; // [rsp+80h] [rbp+18h] BYREF
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v28; // [rsp+88h] [rbp+20h] BYREF

  v26 = a2;
  v27 = 0;
  LOBYTE(pv) = 0;
  v28 = 0;
  v23 = 0;
  v4 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(a2, 3, *((_QWORD *)this + 2), &v23);
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
        (const char *)a2);
      if ( v23 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v23 + 16LL))(v23);
      return v5;
    }
    v8 = v23;
    v9 = (char *)v23 + 48;
    if ( *((_QWORD *)v23 + 9) < 8u )
      v10 = (const unsigned __int16 *)((char *)v23 + 48);
    else
      v10 = *(const unsigned __int16 **)v9;
    IsPackageArchitectureApplicable = MsixPackage::Provisioning::Library::MsixProvisioningContext::IsPackageArchitectureApplicable(
                                        *((MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
                                        v10,
                                        &v27);
    if ( IsPackageArchitectureApplicable < 0 )
    {
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(char **)v9;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)IsPackageArchitectureApplicable,
        (int)"Failed while testing applicability of package moniker '%ws'",
        v9);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)IsPackageArchitectureApplicable;
    }
    if ( !v27 )
    {
      pv = 0;
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(char **)v9;
      v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pv,
              L"Package moniker '%s' excluded as not applicable on this architecture",
              v9);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F5,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v12,
          v22);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
          (const char *)(unsigned int)v14,
          2);
      if ( v13 )
        CoTaskMemFree(v13);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return 0;
    }
    v28 = 0;
    if ( *((_QWORD *)v9 + 3) < 8u )
      v15 = v9;
    else
      v15 = *(char **)v9;
    v16 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(
            v15,
            *((struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
            (bool *)&pv,
            &v28);
    if ( v16 < 0 )
    {
      if ( *((_QWORD *)v9 + 3) >= 8u )
        v9 = *(char **)v9;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x50A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v16,
        (int)"Failed to create adapter for existing package '%ws'.",
        v9);
      if ( v28 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v8 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v8 + 16LL))(v8);
      return (unsigned int)v16;
    }
    if ( !(_BYTE)pv )
    {
      v17 = v28;
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
      v17 = v28;
      v18 = v8;
      v8 = v28;
      v23 = v28;
      if ( v28 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v28 + 8LL))(v28);
      if ( v18 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_59;
    }
    pv = 0;
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(char **)v9;
    v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            L"Package moniker '%s' excluded as it is not applicable because an existing version was found",
            v9);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51B,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v19,
        v22);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v21,
        2);
    if ( v20 )
      CoTaskMemFree(v20);
    if ( v28 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v28 + 16LL))(v28);
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
0x18005207c  mov     rax, rsp
0x18005207f  mov     [rax+10h], rdx
0x180052083  push    rbx
0x180052084  push    rdi
0x180052085  push    r14
0x180052087  push    r15
0x180052089  sub     rsp, 48h
0x18005208d  mov     rbx, rdx
0x180052090  mov     r14, rcx
0x180052093  mov     dword ptr [rax+18h], 0
0x18005209a  mov     byte ptr [rax+8], 0
0x18005209e  mov     qword ptr [rax+20h], 0
0x1800520a6  mov     qword ptr [rax-38h], 0
0x1800520ae  lea     r9, [rax-38h]
0x1800520b2  mov     r8, [rcx+10h]
0x1800520b6  mov     edx, 3
0x1800520bb  mov     rcx, rbx
0x1800520be  call    ?CreateFromPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGW4APPX_PACKAGE_TARGET_TYPE@234@PEAVMsixProvisioningContext@234@PEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateFromPath(ushort const *,MsixPackage::Provisioning::Library::APPX_PACKAGE_TARGET_TYPE,MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x1800520c3  mov     edi, eax
0x1800520c5  test    eax, eax
0x1800520c7  jns     short loc_180052112
0x1800520c9  mov     rcx, [rsp+68h]; this
0x1800520ce  mov     [rsp+68h+var_40], rbx; char *
0x1800520d3  lea     rax, aFailedToCreate_12; "Failed to create adapter for '%ws'."
0x1800520da  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800520df  mov     r9d, edi; char *
0x1800520e2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800520e9  mov     edx, 4E7h; void *
0x1800520ee  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800520f3  nop
0x1800520f4  mov     rcx, [rsp+68h+var_38]
0x1800520f9  test    rcx, rcx
0x1800520fc  jz      short loc_18005210B
0x1800520fe  mov     rax, [rcx]
0x180052101  mov     rax, [rax+10h]
0x180052105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005210a  nop
0x18005210b  mov     eax, edi
0x18005210d  jmp     loc_1800524BE
0x180052112  mov     rbx, [rsp+68h+var_38]
0x180052117  lea     rdi, [rbx+30h]
0x18005211b  cmp     qword ptr [rdi+18h], 8
0x180052120  jb      short loc_180052127
0x180052122  mov     rdx, [rdi]
0x180052125  jmp     short loc_18005212A
0x180052127  mov     rdx, rdi; unsigned __int16 *
0x18005212a  lea     r8, [rsp+68h+arg_10]; int *
0x180052132  mov     rcx, [r14+10h]; this
0x180052136  call    ?IsPackageArchitectureApplicable@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::IsPackageArchitectureApplicable(ushort const *,int *)
0x18005213b  mov     r15d, eax
0x18005213e  test    eax, eax
0x180052140  jns     short loc_180052194
0x180052142  cmp     qword ptr [rdi+18h], 8
0x180052147  jb      short loc_18005214C
0x180052149  mov     rdi, [rdi]
0x18005214c  mov     rcx, [rsp+68h]; this
0x180052151  mov     [rsp+68h+var_40], rdi; char *
0x180052156  lea     rax, aFailedWhileTes_0; "Failed while testing applicability of p"...
0x18005215d  mov     qword ptr [rsp+68h+var_48], rax; int
0x180052162  mov     r9d, r15d; char *
0x180052165  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005216c  mov     edx, 4EBh; void *
0x180052171  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052176  nop
0x180052177  test    rbx, rbx
0x18005217a  jz      short loc_18005218C
0x18005217c  mov     rax, [rbx]
0x18005217f  mov     rcx, rbx
0x180052182  mov     rax, [rax+10h]
0x180052186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005218b  nop
0x18005218c  mov     eax, r15d
0x18005218f  jmp     loc_1800524BE
0x180052194  cmp     [rsp+68h+arg_10], 0
0x18005219c  jnz     loc_180052267
0x1800521a2  mov     [rsp+68h+pv], 0
0x1800521ab  cmp     qword ptr [rdi+18h], 8
0x1800521b0  jb      short loc_1800521B5
0x1800521b2  mov     rdi, [rdi]
0x1800521b5  mov     r8, rdi
0x1800521b8  lea     rdx, aPackageMoniker_0; "Package moniker '%s' excluded as not ap"...
0x1800521bf  lea     rcx, [rsp+68h+pv]
0x1800521c4  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800521c9  mov     rcx, [rsp+68h]; this
0x1800521ce  test    eax, eax
0x1800521d0  jns     short loc_1800521E6
0x1800521d2  mov     r9d, eax; char *
0x1800521d5  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800521dc  mov     edx, 4F5h; void *
0x1800521e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800521e6  mov     dword ptr [rsp+68h+var_40], 0
0x1800521ee  mov     [rsp+68h+var_48], 2; int
0x1800521f6  mov     r14d, 4FDh
0x1800521fc  mov     r9d, r14d
0x1800521ff  lea     r8, aMsixpackagePro_5; "MsixPackage::Provisioning::Library::Msi"...
0x180052206  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005220d  mov     rdi, [rsp+68h+pv]
0x180052212  mov     rcx, rdi
0x180052215  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18005221a  mov     rcx, [rsp+68h]; this
0x18005221f  test    eax, eax
0x180052221  jns     short loc_180052236
0x180052223  mov     r9d, eax; char *
0x180052226  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005222d  mov     edx, r14d; void *
0x180052230  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180052235  nop
0x180052236  test    rdi, rdi
0x180052239  jz      short loc_18005224B
0x18005223b  mov     rcx, rdi; pv
0x18005223e  call    cs:__imp_CoTaskMemFree
0x180052245  nop     dword ptr [rax+rax+00h]
0x18005224a  nop
0x18005224b  test    rbx, rbx
0x18005224e  jz      short loc_180052260
0x180052250  mov     rax, [rbx]
0x180052253  mov     rcx, rbx
0x180052256  mov     rax, [rax+10h]
0x18005225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005225f  nop
0x180052260  xor     eax, eax
0x180052262  jmp     loc_1800524BE
0x180052267  mov     [rsp+68h+arg_18], 0
0x180052273  cmp     qword ptr [rdi+18h], 8
0x180052278  jb      short loc_18005227F
0x18005227a  mov     rcx, [rdi]
0x18005227d  jmp     short loc_180052282
0x18005227f  mov     rcx, rdi; char *
0x180052282  lea     r9, [rsp+68h+arg_18]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18005228a  lea     r8, [rsp+68h+pv]; bool *
0x18005228f  mov     rdx, [r14+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x180052293  call    ?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180052298  mov     r15d, eax
0x18005229b  test    eax, eax
0x18005229d  jns     short loc_18005230B
0x18005229f  cmp     qword ptr [rdi+18h], 8
0x1800522a4  jb      short loc_1800522A9
0x1800522a6  mov     rdi, [rdi]
0x1800522a9  mov     rcx, [rsp+68h]; this
0x1800522ae  mov     [rsp+68h+var_40], rdi; char *
0x1800522b3  lea     rax, aFailedToCreate_0; "Failed to create adapter for existing p"...
0x1800522ba  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800522bf  mov     r9d, r15d; char *
0x1800522c2  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800522c9  mov     edx, 50Ah; void *
0x1800522ce  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800522d3  nop
0x1800522d4  mov     rcx, [rsp+68h+arg_18]
0x1800522dc  test    rcx, rcx
0x1800522df  jz      short loc_1800522EE
0x1800522e1  mov     rax, [rcx]
0x1800522e4  mov     rax, [rax+10h]
0x1800522e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522ed  nop
0x1800522ee  test    rbx, rbx
0x1800522f1  jz      short loc_180052303
0x1800522f3  mov     rax, [rbx]
0x1800522f6  mov     rcx, rbx
0x1800522f9  mov     rax, [rax+10h]
0x1800522fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052302  nop
0x180052303  mov     eax, r15d
0x180052306  jmp     loc_1800524BE
0x18005230b  cmp     byte ptr [rsp+68h+pv], 0
0x180052310  jz      loc_180052440
0x180052316  mov     rax, [r14+10h]
0x18005231a  cmp     dword ptr [rax+258h], 0
0x180052321  jnz     short loc_180052364
0x180052323  mov     rdi, [rsp+68h+arg_18]
0x18005232b  mov     r15, rbx
0x18005232e  mov     rbx, rdi
0x180052331  mov     [rsp+68h+var_38], rbx
0x180052336  test    rdi, rdi
0x180052339  jz      short loc_18005234A
0x18005233b  mov     rax, [rdi]
0x18005233e  mov     rcx, rdi
0x180052341  mov     rax, [rax+8]
0x180052345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005234a  test    r15, r15
0x18005234d  jz      short loc_18005235F
0x18005234f  mov     rax, [r15]
0x180052352  mov     rcx, r15
0x180052355  mov     rax, [rax+10h]
0x180052359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005235e  nop
0x18005235f  jmp     loc_180052448
0x180052364  mov     [rsp+68h+pv], 0
0x18005236d  cmp     qword ptr [rdi+18h], 8
0x180052372  jb      short loc_180052377
0x180052374  mov     rdi, [rdi]
0x180052377  mov     r8, rdi
0x18005237a  lea     rdx, aPackageMoniker; "Package moniker '%s' excluded as it is "...
0x180052381  lea     rcx, [rsp+68h+pv]
0x180052386  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18005238b  mov     rcx, [rsp+68h]; this
0x180052390  test    eax, eax
0x180052392  jns     short loc_1800523A8
0x180052394  mov     r9d, eax; char *
0x180052397  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005239e  mov     edx, 51Bh; void *
0x1800523a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800523a8  mov     dword ptr [rsp+68h+var_40], 0
0x1800523b0  mov     [rsp+68h+var_48], 2; int
0x1800523b8  mov     r14d, 523h
0x1800523be  mov     r9d, r14d
0x1800523c1  lea     r8, aMsixpackagePro_5; "MsixPackage::Provisioning::Library::Msi"...
0x1800523c8  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800523cf  mov     rdi, [rsp+68h+pv]
0x1800523d4  mov     rcx, rdi
0x1800523d7  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x1800523dc  mov     rcx, [rsp+68h]; this
0x1800523e1  test    eax, eax
0x1800523e3  jns     short loc_1800523F8
0x1800523e5  mov     r9d, eax; char *
0x1800523e8  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800523ef  mov     edx, r14d; void *
0x1800523f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800523f7  nop
0x1800523f8  test    rdi, rdi
0x1800523fb  jz      short loc_18005240D
0x1800523fd  mov     rcx, rdi; pv
0x180052400  call    cs:__imp_CoTaskMemFree
0x180052407  nop     dword ptr [rax+rax+00h]
0x18005240c  nop
0x18005240d  mov     rcx, [rsp+68h+arg_18]
0x180052415  test    rcx, rcx
0x180052418  jz      short loc_180052427
0x18005241a  mov     rax, [rcx]
0x18005241d  mov     rax, [rax+10h]
0x180052421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052426  nop
0x180052427  test    rbx, rbx
0x18005242a  jz      short loc_18005243C
0x18005242c  mov     rax, [rbx]
0x18005242f  mov     rcx, rbx
0x180052432  mov     rax, [rax+10h]
0x180052436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005243b  nop
0x18005243c  xor     eax, eax
0x18005243e  jmp     short loc_1800524BE
0x180052440  mov     rdi, [rsp+68h+arg_18]
0x180052448  mov     rdx, rbx
0x18005244b  mov     rcx, [r14+30h]
0x18005244f  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x180052454  nop
0x180052455  test    rdi, rdi
0x180052458  jz      short loc_18005246A
0x18005245a  mov     rax, [rdi]
0x18005245d  mov     rcx, rdi
0x180052460  mov     rax, [rax+10h]
0x180052464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052469  nop
0x18005246a  test    rbx, rbx
0x18005246d  jz      short loc_18005247F
0x18005246f  mov     rax, [rbx]
0x180052472  mov     rcx, rbx
0x180052475  mov     rax, [rax+10h]
0x180052479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005247e  nop
0x18005247f  xor     eax, eax
0x180052481  jmp     short loc_1800524BE
0x180052483  mov     rcx, [rsp+68h+arg_18]
0x18005248b  test    rcx, rcx
0x18005248e  jz      short loc_18005249D
0x180052490  mov     rax, [rcx]
0x180052493  mov     rax, [rax+10h]
0x180052497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005249c  nop
0x18005249d  mov     rcx, [rsp+68h+var_38]
0x1800524a2  test    rcx, rcx
0x1800524a5  jz      short loc_1800524B4
0x1800524a7  mov     rax, [rcx]
0x1800524aa  mov     rax, [rax+10h]
0x1800524ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524b3  nop
0x1800524b4  mov     eax, dword ptr [rsp+68h+pv]
0x1800524b8  jmp     short loc_1800524BE
0x1800524ba  mov     eax, dword ptr [rsp+68h+pv]
0x1800524be  add     rsp, 48h
0x1800524c2  pop     r15
0x1800524c4  pop     r14
0x1800524c6  pop     rdi
0x1800524c7  pop     rbx
0x1800524c8  retn
```
