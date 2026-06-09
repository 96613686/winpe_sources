# MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional(bool &)

- ea: `0x180047b50`
- end: `0x180047f20`
- name: `?IsPackageOptional@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEA_N@Z`
- size: `976`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b70c`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180047b50`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047c23`

## string_xrefs

- `0x180047bee`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047bbe`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047c0c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047c8f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047d41`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047deb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047e71`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047c80`: `Failed to get manifest reader from package`
- `0x180047ba3`: `No package reader found for %ws, expected for bundles.`
- `0x180047d32`: `Failed to get internal manifest reader interface.`
- `0x180047be7`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        bool *a2)
{
  __int64 *v3; // r8
  int v4; // eax
  void *v5; // rbx
  int v6; // eax
  __int64 v7; // rax
  int v8; // ebx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rsi
  __int64 v15; // rcx
  const char *v16; // [rsp+28h] [rbp-20h]
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int v19; // [rsp+70h] [rbp+28h] BYREF
  __int64 v20; // [rsp+78h] [rbp+30h] BYREF
  __int64 v21; // [rsp+80h] [rbp+38h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+40h] BYREF

  *a2 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    v7 = *v3;
    v22 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v7 + 56))(
           v3,
           &v22);
    if ( v8 >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
      v11 = **v22;
      v12 = v21;
      v21 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v8 = v11(v10, &IID_IAppxManifestReader5, &v21);
      if ( v8 >= 0 )
      {
        v13 = v21;
        v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL);
        v15 = v20;
        v20 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v8 = v14(v13, &v20);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 32LL))(v20, &v19);
          if ( v8 >= 0 )
          {
            if ( v19 )
              *a2 = 1;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            goto LABEL_55;
          }
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x6FC,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v8,
            (int)"Failed to determine next main package dependency.",
            v16);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x6FB,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v8,
            (int)"Failed to get main package dependencies.",
            v16);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x6F9,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v8,
          (int)"Failed to get internal manifest reader interface.",
          v16);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v22 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x6F7,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v8,
        (int)"Failed to get manifest reader from package",
        v16);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v22 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
    }
    return (unsigned int)v8;
  }
  pv[0] = 0;
  v4 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         (char *)pv,
         L"No package reader found for %ws, expected for bundles.");
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6EA,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v4);
  v5 = pv[0];
  v6 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
         pv[0],
         L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
         L"MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional",
         1778);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6F2,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v6);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_55:
  if ( v22 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
  return 0;
}

```

## disassembly

```asm
0x180047b50  push    rbp
0x180047b52  push    rbx
0x180047b53  push    rsi
0x180047b54  push    rdi
0x180047b55  mov     rbp, rsp
0x180047b58  sub     rsp, 48h
0x180047b5c  mov     rdi, rdx
0x180047b5f  mov     byte ptr [rdx], 0
0x180047b62  mov     [rbp+arg_18], 0
0x180047b6a  mov     [rbp+arg_10], 0
0x180047b72  mov     [rbp+arg_8], 0
0x180047b7a  mov     [rbp+arg_0], 0
0x180047b81  mov     r8, [rcx+0F0h]
0x180047b88  test    r8, r8
0x180047b8b  jnz     loc_180047C5B
0x180047b91  mov     [rbp+pv], r8
0x180047b95  lea     r8, [rcx+30h]
0x180047b99  cmp     qword ptr [r8+18h], 8
0x180047b9e  jb      short loc_180047BA3
0x180047ba0  mov     r8, [r8]
0x180047ba3  lea     rdx, aNoPackageReade; "No package reader found for %ws, expect"...
0x180047baa  lea     rcx, [rbp+pv]
0x180047bae  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180047bb3  mov     rcx, [rbp+20h]; this
0x180047bb7  test    eax, eax
0x180047bb9  jns     short loc_180047BCF
0x180047bbb  mov     r9d, eax; char *
0x180047bbe  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047bc5  mov     edx, 6EAh; void *
0x180047bca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047bcf  mov     dword ptr [rsp+48h+var_20], 0
0x180047bd7  mov     [rsp+48h+var_28], 2; int
0x180047bdf  mov     edi, 6F2h
0x180047be4  mov     r9d, edi
0x180047be7  lea     r8, aMsixpackagePro_6; "MsixPackage::Provisioning::Library::Msi"...
0x180047bee  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047bf5  mov     rbx, [rbp+pv]
0x180047bf9  mov     rcx, rbx
0x180047bfc  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180047c01  mov     rcx, [rbp+20h]; this
0x180047c05  test    eax, eax
0x180047c07  jns     short loc_180047C1B
0x180047c09  mov     r9d, eax; char *
0x180047c0c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047c13  mov     edx, edi; void *
0x180047c15  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047c1a  nop
0x180047c1b  test    rbx, rbx
0x180047c1e  jz      short loc_180047C2A
0x180047c20  mov     rcx, rbx; pv
0x180047c23  call    cs:__imp_CoTaskMemFree
0x180047c29  nop
0x180047c2a  mov     rcx, [rbp+arg_8]
0x180047c2e  test    rcx, rcx
0x180047c31  jz      short loc_180047C40
0x180047c33  mov     rax, [rcx]
0x180047c36  mov     rax, [rax+10h]
0x180047c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c3f  nop
0x180047c40  mov     rcx, [rbp+arg_10]
0x180047c44  test    rcx, rcx
0x180047c47  jz      short loc_180047C56
0x180047c49  mov     rax, [rcx]
0x180047c4c  mov     rax, [rax+10h]
0x180047c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c55  nop
0x180047c56  jmp     loc_180047EFF
0x180047c5b  mov     rax, [r8]
0x180047c5e  mov     [rbp+arg_18], 0
0x180047c66  lea     rdx, [rbp+arg_18]
0x180047c6a  mov     rcx, r8
0x180047c6d  mov     rax, [rax+38h]
0x180047c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047c76  mov     ebx, eax
0x180047c78  test    eax, eax
0x180047c7a  jns     short loc_180047CEA
0x180047c7c  mov     rcx, [rbp+20h]; this
0x180047c80  lea     rax, aFailedToGetMan_2; "Failed to get manifest reader from pack"...
0x180047c87  mov     qword ptr [rsp+48h+var_28], rax; int
0x180047c8c  mov     r9d, ebx; char *
0x180047c8f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047c96  mov     edx, 6F7h; void *
0x180047c9b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047ca0  nop
0x180047ca1  mov     rcx, [rbp+arg_8]
0x180047ca5  test    rcx, rcx
0x180047ca8  jz      short loc_180047CB7
0x180047caa  mov     rax, [rcx]
0x180047cad  mov     rax, [rax+10h]
0x180047cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cb6  nop
0x180047cb7  mov     rcx, [rbp+arg_10]
0x180047cbb  test    rcx, rcx
0x180047cbe  jz      short loc_180047CCD
0x180047cc0  mov     rax, [rcx]
0x180047cc3  mov     rax, [rax+10h]
0x180047cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ccc  nop
0x180047ccd  mov     rcx, [rbp+arg_18]
0x180047cd1  test    rcx, rcx
0x180047cd4  jz      short loc_180047CE3
0x180047cd6  mov     rax, [rcx]
0x180047cd9  mov     rax, [rax+10h]
0x180047cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ce2  nop
0x180047ce3  mov     eax, ebx
0x180047ce5  jmp     loc_180047F17
0x180047cea  mov     rbx, [rbp+arg_18]
0x180047cee  mov     rax, [rbx]
0x180047cf1  mov     rsi, [rax]
0x180047cf4  mov     rcx, [rbp+arg_10]
0x180047cf8  mov     [rbp+arg_10], 0
0x180047d00  test    rcx, rcx
0x180047d03  jz      short loc_180047D12
0x180047d05  mov     rdx, [rcx]
0x180047d08  mov     rax, [rdx+10h]
0x180047d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d11  nop
0x180047d12  lea     r8, [rbp+arg_10]
0x180047d16  lea     rdx, IID_IAppxManifestReader5
0x180047d1d  mov     rcx, rbx
0x180047d20  mov     rax, rsi
0x180047d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d28  mov     ebx, eax
0x180047d2a  test    eax, eax
0x180047d2c  jns     short loc_180047D9A
0x180047d2e  mov     rcx, [rbp+20h]; this
0x180047d32  lea     rax, aFailedToGetInt; "Failed to get internal manifest reader "...
0x180047d39  mov     qword ptr [rsp+48h+var_28], rax; int
0x180047d3e  mov     r9d, ebx; char *
0x180047d41  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047d48  mov     edx, 6F9h; void *
0x180047d4d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047d52  nop
0x180047d53  mov     rcx, [rbp+arg_8]
0x180047d57  test    rcx, rcx
0x180047d5a  jz      short loc_180047D69
0x180047d5c  mov     rax, [rcx]
0x180047d5f  mov     rax, [rax+10h]
0x180047d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d68  nop
0x180047d69  mov     rcx, [rbp+arg_10]
0x180047d6d  test    rcx, rcx
0x180047d70  jz      short loc_180047D7F
0x180047d72  mov     rax, [rcx]
0x180047d75  mov     rax, [rax+10h]
0x180047d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d7e  nop
0x180047d7f  mov     rcx, [rbp+arg_18]
0x180047d83  test    rcx, rcx
0x180047d86  jz      short loc_180047D95
0x180047d88  mov     rax, [rcx]
0x180047d8b  mov     rax, [rax+10h]
0x180047d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d94  nop
0x180047d95  jmp     loc_180047CE3
0x180047d9a  mov     rbx, [rbp+arg_10]
0x180047d9e  mov     rax, [rbx]
0x180047da1  mov     rsi, [rax+18h]
0x180047da5  mov     rcx, [rbp+arg_8]
0x180047da9  mov     [rbp+arg_8], 0
0x180047db1  test    rcx, rcx
0x180047db4  jz      short loc_180047DC3
0x180047db6  mov     rdx, [rcx]
0x180047db9  mov     rax, [rdx+10h]
0x180047dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dc2  nop
0x180047dc3  lea     rdx, [rbp+arg_8]
0x180047dc7  mov     rcx, rbx
0x180047dca  mov     rax, rsi
0x180047dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dd2  mov     ebx, eax
0x180047dd4  test    eax, eax
0x180047dd6  jns     short loc_180047E44
0x180047dd8  mov     rcx, [rbp+20h]; this
0x180047ddc  lea     rax, aFailedToGetMai; "Failed to get main package dependencies"...
0x180047de3  mov     qword ptr [rsp+48h+var_28], rax; int
0x180047de8  mov     r9d, ebx; char *
0x180047deb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047df2  mov     edx, 6FBh; void *
0x180047df7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047dfc  nop
0x180047dfd  mov     rcx, [rbp+arg_8]
0x180047e01  test    rcx, rcx
0x180047e04  jz      short loc_180047E13
0x180047e06  mov     rax, [rcx]
0x180047e09  mov     rax, [rax+10h]
0x180047e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e12  nop
0x180047e13  mov     rcx, [rbp+arg_10]
0x180047e17  test    rcx, rcx
0x180047e1a  jz      short loc_180047E29
0x180047e1c  mov     rax, [rcx]
0x180047e1f  mov     rax, [rax+10h]
0x180047e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e28  nop
0x180047e29  mov     rcx, [rbp+arg_18]
0x180047e2d  test    rcx, rcx
0x180047e30  jz      short loc_180047E3F
0x180047e32  mov     rax, [rcx]
0x180047e35  mov     rax, [rax+10h]
0x180047e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e3e  nop
0x180047e3f  jmp     loc_180047CE3
0x180047e44  mov     rcx, [rbp+arg_8]
0x180047e48  mov     rax, [rcx]
0x180047e4b  lea     rdx, [rbp+arg_0]
0x180047e4f  mov     rax, [rax+20h]
0x180047e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e58  mov     ebx, eax
0x180047e5a  test    eax, eax
0x180047e5c  jns     short loc_180047ECA
0x180047e5e  mov     rcx, [rbp+20h]; this
0x180047e62  lea     rax, aFailedToDeterm_7; "Failed to determine next main package d"...
0x180047e69  mov     qword ptr [rsp+48h+var_28], rax; int
0x180047e6e  mov     r9d, ebx; char *
0x180047e71  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047e78  mov     edx, 6FCh; void *
0x180047e7d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047e82  nop
0x180047e83  mov     rcx, [rbp+arg_8]
0x180047e87  test    rcx, rcx
0x180047e8a  jz      short loc_180047E99
0x180047e8c  mov     rax, [rcx]
0x180047e8f  mov     rax, [rax+10h]
0x180047e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e98  nop
0x180047e99  mov     rcx, [rbp+arg_10]
0x180047e9d  test    rcx, rcx
0x180047ea0  jz      short loc_180047EAF
0x180047ea2  mov     rax, [rcx]
0x180047ea5  mov     rax, [rax+10h]
0x180047ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eae  nop
0x180047eaf  mov     rcx, [rbp+arg_18]
0x180047eb3  test    rcx, rcx
0x180047eb6  jz      short loc_180047EC5
0x180047eb8  mov     rax, [rcx]
0x180047ebb  mov     rax, [rax+10h]
0x180047ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ec4  nop
0x180047ec5  jmp     loc_180047CE3
0x180047eca  cmp     [rbp+arg_0], 0
0x180047ece  jz      short loc_180047ED3
0x180047ed0  mov     byte ptr [rdi], 1
0x180047ed3  mov     rcx, [rbp+arg_8]
0x180047ed7  test    rcx, rcx
0x180047eda  jz      short loc_180047EE9
0x180047edc  mov     rax, [rcx]
0x180047edf  mov     rax, [rax+10h]
0x180047ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ee8  nop
0x180047ee9  mov     rcx, [rbp+arg_10]
0x180047eed  test    rcx, rcx
0x180047ef0  jz      short loc_180047EFF
0x180047ef2  mov     rax, [rcx]
0x180047ef5  mov     rax, [rax+10h]
0x180047ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047efe  nop
0x180047eff  mov     rcx, [rbp+arg_18]
0x180047f03  test    rcx, rcx
0x180047f06  jz      short loc_180047F15
0x180047f08  mov     rax, [rcx]
0x180047f0b  mov     rax, [rax+10h]
0x180047f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f14  nop
0x180047f15  xor     eax, eax
0x180047f17  add     rsp, 48h
0x180047f1b  pop     rdi
0x180047f1c  pop     rsi
0x180047f1d  pop     rbx
0x180047f1e  pop     rbp
0x180047f1f  retn
```
