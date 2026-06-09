# MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional(bool &)

- ea: `0x18004bbc4`
- end: `0x18004bf9b`
- name: `?IsPackageOptional@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJAEA_N@Z`
- size: `983`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004f924`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18004bbc4`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bc97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bc97`

## string_xrefs

- `0x18004bc32`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bc80`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bd09`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bdbb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004be65`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004beeb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bc62`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004bcfa`: `Failed to get manifest reader from package`
- `0x18004bdac`: `Failed to get internal manifest reader interface.`
- `0x18004bc5b`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::IsPackageOptional`
- `0x18004bc17`: `No package reader found for %ws, expected for bundles.`

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
  int v16; // [rsp+20h] [rbp-28h]
  const char *v17; // [rsp+28h] [rbp-20h]
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  int v20; // [rsp+70h] [rbp+28h] BYREF
  __int64 v21; // [rsp+78h] [rbp+30h] BYREF
  __int64 v22; // [rsp+80h] [rbp+38h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+40h] BYREF

  *a2 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v3 = (__int64 *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    v7 = *v3;
    v23 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v7 + 56))(
           v3,
           &v23);
    if ( v8 >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
      v11 = **v23;
      v12 = v22;
      v22 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v8 = v11(v10, &IID_IAppxManifestReader5, &v22);
      if ( v8 >= 0 )
      {
        v13 = v22;
        v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 24LL);
        v15 = v21;
        v21 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v8 = v14(v13, &v21);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 32LL))(v21, &v20);
          if ( v8 >= 0 )
          {
            if ( v20 )
              *a2 = 1;
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            goto LABEL_55;
          }
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x6FC,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v8,
            (int)"Failed to determine next main package dependency.",
            v17);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v23 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x6FB,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v8,
            (int)"Failed to get main package dependencies.",
            v17);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v23 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
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
          v17);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v23 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
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
        v17);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v23 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
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
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v4,
      v16);
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
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v6,
      2);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_55:
  if ( v23 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
  return 0;
}

```

## disassembly

```asm
0x18004bbc4  push    rbp
0x18004bbc6  push    rbx
0x18004bbc7  push    rsi
0x18004bbc8  push    rdi
0x18004bbc9  mov     rbp, rsp
0x18004bbcc  sub     rsp, 48h
0x18004bbd0  mov     rdi, rdx
0x18004bbd3  mov     byte ptr [rdx], 0
0x18004bbd6  mov     [rbp+arg_18], 0
0x18004bbde  mov     [rbp+arg_10], 0
0x18004bbe6  mov     [rbp+arg_8], 0
0x18004bbee  mov     [rbp+arg_0], 0
0x18004bbf5  mov     r8, [rcx+0F0h]
0x18004bbfc  test    r8, r8
0x18004bbff  jnz     loc_18004BCD5
0x18004bc05  mov     [rbp+pv], r8
0x18004bc09  lea     r8, [rcx+30h]
0x18004bc0d  cmp     qword ptr [r8+18h], 8
0x18004bc12  jb      short loc_18004BC17
0x18004bc14  mov     r8, [r8]
0x18004bc17  lea     rdx, aNoPackageReade; "No package reader found for %ws, expect"...
0x18004bc1e  lea     rcx, [rbp+pv]
0x18004bc22  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004bc27  mov     rcx, [rbp+20h]; this
0x18004bc2b  test    eax, eax
0x18004bc2d  jns     short loc_18004BC43
0x18004bc2f  mov     r9d, eax; char *
0x18004bc32  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bc39  mov     edx, 6EAh; void *
0x18004bc3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004bc43  mov     dword ptr [rsp+48h+var_20], 0
0x18004bc4b  mov     [rsp+48h+var_28], 2; int
0x18004bc53  mov     edi, 6F2h
0x18004bc58  mov     r9d, edi
0x18004bc5b  lea     r8, aMsixpackagePro_6; "MsixPackage::Provisioning::Library::Msi"...
0x18004bc62  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bc69  mov     rbx, [rbp+pv]
0x18004bc6d  mov     rcx, rbx
0x18004bc70  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004bc75  mov     rcx, [rbp+20h]; this
0x18004bc79  test    eax, eax
0x18004bc7b  jns     short loc_18004BC8F
0x18004bc7d  mov     r9d, eax; char *
0x18004bc80  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bc87  mov     edx, edi; void *
0x18004bc89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004bc8e  nop
0x18004bc8f  test    rbx, rbx
0x18004bc92  jz      short loc_18004BCA4
0x18004bc94  mov     rcx, rbx; pv
0x18004bc97  call    cs:__imp_CoTaskMemFree
0x18004bc9e  nop     dword ptr [rax+rax+00h]
0x18004bca3  nop
0x18004bca4  mov     rcx, [rbp+arg_8]
0x18004bca8  test    rcx, rcx
0x18004bcab  jz      short loc_18004BCBA
0x18004bcad  mov     rax, [rcx]
0x18004bcb0  mov     rax, [rax+10h]
0x18004bcb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcb9  nop
0x18004bcba  mov     rcx, [rbp+arg_10]
0x18004bcbe  test    rcx, rcx
0x18004bcc1  jz      short loc_18004BCD0
0x18004bcc3  mov     rax, [rcx]
0x18004bcc6  mov     rax, [rax+10h]
0x18004bcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bccf  nop
0x18004bcd0  jmp     loc_18004BF79
0x18004bcd5  mov     rax, [r8]
0x18004bcd8  mov     [rbp+arg_18], 0
0x18004bce0  lea     rdx, [rbp+arg_18]
0x18004bce4  mov     rcx, r8
0x18004bce7  mov     rax, [rax+38h]
0x18004bceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcf0  mov     ebx, eax
0x18004bcf2  test    eax, eax
0x18004bcf4  jns     short loc_18004BD64
0x18004bcf6  mov     rcx, [rbp+20h]; this
0x18004bcfa  lea     rax, aFailedToGetMan_2; "Failed to get manifest reader from pack"...
0x18004bd01  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004bd06  mov     r9d, ebx; char *
0x18004bd09  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bd10  mov     edx, 6F7h; void *
0x18004bd15  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bd1a  nop
0x18004bd1b  mov     rcx, [rbp+arg_8]
0x18004bd1f  test    rcx, rcx
0x18004bd22  jz      short loc_18004BD31
0x18004bd24  mov     rax, [rcx]
0x18004bd27  mov     rax, [rax+10h]
0x18004bd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd30  nop
0x18004bd31  mov     rcx, [rbp+arg_10]
0x18004bd35  test    rcx, rcx
0x18004bd38  jz      short loc_18004BD47
0x18004bd3a  mov     rax, [rcx]
0x18004bd3d  mov     rax, [rax+10h]
0x18004bd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd46  nop
0x18004bd47  mov     rcx, [rbp+arg_18]
0x18004bd4b  test    rcx, rcx
0x18004bd4e  jz      short loc_18004BD5D
0x18004bd50  mov     rax, [rcx]
0x18004bd53  mov     rax, [rax+10h]
0x18004bd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd5c  nop
0x18004bd5d  mov     eax, ebx
0x18004bd5f  jmp     loc_18004BF91
0x18004bd64  mov     rbx, [rbp+arg_18]
0x18004bd68  mov     rax, [rbx]
0x18004bd6b  mov     rsi, [rax]
0x18004bd6e  mov     rcx, [rbp+arg_10]
0x18004bd72  mov     [rbp+arg_10], 0
0x18004bd7a  test    rcx, rcx
0x18004bd7d  jz      short loc_18004BD8C
0x18004bd7f  mov     rdx, [rcx]
0x18004bd82  mov     rax, [rdx+10h]
0x18004bd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd8b  nop
0x18004bd8c  lea     r8, [rbp+arg_10]
0x18004bd90  lea     rdx, IID_IAppxManifestReader5
0x18004bd97  mov     rcx, rbx
0x18004bd9a  mov     rax, rsi
0x18004bd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bda2  mov     ebx, eax
0x18004bda4  test    eax, eax
0x18004bda6  jns     short loc_18004BE14
0x18004bda8  mov     rcx, [rbp+20h]; this
0x18004bdac  lea     rax, aFailedToGetInt; "Failed to get internal manifest reader "...
0x18004bdb3  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004bdb8  mov     r9d, ebx; char *
0x18004bdbb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bdc2  mov     edx, 6F9h; void *
0x18004bdc7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004bdcc  nop
0x18004bdcd  mov     rcx, [rbp+arg_8]
0x18004bdd1  test    rcx, rcx
0x18004bdd4  jz      short loc_18004BDE3
0x18004bdd6  mov     rax, [rcx]
0x18004bdd9  mov     rax, [rax+10h]
0x18004bddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bde2  nop
0x18004bde3  mov     rcx, [rbp+arg_10]
0x18004bde7  test    rcx, rcx
0x18004bdea  jz      short loc_18004BDF9
0x18004bdec  mov     rax, [rcx]
0x18004bdef  mov     rax, [rax+10h]
0x18004bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdf8  nop
0x18004bdf9  mov     rcx, [rbp+arg_18]
0x18004bdfd  test    rcx, rcx
0x18004be00  jz      short loc_18004BE0F
0x18004be02  mov     rax, [rcx]
0x18004be05  mov     rax, [rax+10h]
0x18004be09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be0e  nop
0x18004be0f  jmp     loc_18004BD5D
0x18004be14  mov     rbx, [rbp+arg_10]
0x18004be18  mov     rax, [rbx]
0x18004be1b  mov     rsi, [rax+18h]
0x18004be1f  mov     rcx, [rbp+arg_8]
0x18004be23  mov     [rbp+arg_8], 0
0x18004be2b  test    rcx, rcx
0x18004be2e  jz      short loc_18004BE3D
0x18004be30  mov     rdx, [rcx]
0x18004be33  mov     rax, [rdx+10h]
0x18004be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be3c  nop
0x18004be3d  lea     rdx, [rbp+arg_8]
0x18004be41  mov     rcx, rbx
0x18004be44  mov     rax, rsi
0x18004be47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be4c  mov     ebx, eax
0x18004be4e  test    eax, eax
0x18004be50  jns     short loc_18004BEBE
0x18004be52  mov     rcx, [rbp+20h]; this
0x18004be56  lea     rax, aFailedToGetMai; "Failed to get main package dependencies"...
0x18004be5d  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004be62  mov     r9d, ebx; char *
0x18004be65  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004be6c  mov     edx, 6FBh; void *
0x18004be71  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004be76  nop
0x18004be77  mov     rcx, [rbp+arg_8]
0x18004be7b  test    rcx, rcx
0x18004be7e  jz      short loc_18004BE8D
0x18004be80  mov     rax, [rcx]
0x18004be83  mov     rax, [rax+10h]
0x18004be87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004be8c  nop
0x18004be8d  mov     rcx, [rbp+arg_10]
0x18004be91  test    rcx, rcx
0x18004be94  jz      short loc_18004BEA3
0x18004be96  mov     rax, [rcx]
0x18004be99  mov     rax, [rax+10h]
0x18004be9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bea2  nop
0x18004bea3  mov     rcx, [rbp+arg_18]
0x18004bea7  test    rcx, rcx
0x18004beaa  jz      short loc_18004BEB9
0x18004beac  mov     rax, [rcx]
0x18004beaf  mov     rax, [rax+10h]
0x18004beb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beb8  nop
0x18004beb9  jmp     loc_18004BD5D
0x18004bebe  mov     rcx, [rbp+arg_8]
0x18004bec2  mov     rax, [rcx]
0x18004bec5  lea     rdx, [rbp+arg_0]
0x18004bec9  mov     rax, [rax+20h]
0x18004becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bed2  mov     ebx, eax
0x18004bed4  test    eax, eax
0x18004bed6  jns     short loc_18004BF44
0x18004bed8  mov     rcx, [rbp+20h]; this
0x18004bedc  lea     rax, aFailedToDeterm_7; "Failed to determine next main package d"...
0x18004bee3  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004bee8  mov     r9d, ebx; char *
0x18004beeb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004bef2  mov     edx, 6FCh; void *
0x18004bef7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004befc  nop
0x18004befd  mov     rcx, [rbp+arg_8]
0x18004bf01  test    rcx, rcx
0x18004bf04  jz      short loc_18004BF13
0x18004bf06  mov     rax, [rcx]
0x18004bf09  mov     rax, [rax+10h]
0x18004bf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf12  nop
0x18004bf13  mov     rcx, [rbp+arg_10]
0x18004bf17  test    rcx, rcx
0x18004bf1a  jz      short loc_18004BF29
0x18004bf1c  mov     rax, [rcx]
0x18004bf1f  mov     rax, [rax+10h]
0x18004bf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf28  nop
0x18004bf29  mov     rcx, [rbp+arg_18]
0x18004bf2d  test    rcx, rcx
0x18004bf30  jz      short loc_18004BF3F
0x18004bf32  mov     rax, [rcx]
0x18004bf35  mov     rax, [rax+10h]
0x18004bf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf3e  nop
0x18004bf3f  jmp     loc_18004BD5D
0x18004bf44  cmp     [rbp+arg_0], 0
0x18004bf48  jz      short loc_18004BF4D
0x18004bf4a  mov     byte ptr [rdi], 1
0x18004bf4d  mov     rcx, [rbp+arg_8]
0x18004bf51  test    rcx, rcx
0x18004bf54  jz      short loc_18004BF63
0x18004bf56  mov     rax, [rcx]
0x18004bf59  mov     rax, [rax+10h]
0x18004bf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf62  nop
0x18004bf63  mov     rcx, [rbp+arg_10]
0x18004bf67  test    rcx, rcx
0x18004bf6a  jz      short loc_18004BF79
0x18004bf6c  mov     rax, [rcx]
0x18004bf6f  mov     rax, [rax+10h]
0x18004bf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf78  nop
0x18004bf79  mov     rcx, [rbp+arg_18]
0x18004bf7d  test    rcx, rcx
0x18004bf80  jz      short loc_18004BF8F
0x18004bf82  mov     rax, [rcx]
0x18004bf85  mov     rax, [rax+10h]
0x18004bf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf8e  nop
0x18004bf8f  xor     eax, eax
0x18004bf91  add     rsp, 48h
0x18004bf95  pop     rdi
0x18004bf96  pop     rsi
0x18004bf97  pop     rbx
0x18004bf98  pop     rbp
0x18004bf99  retn
```
