# MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking(ushort const *)

- ea: `0x180051dcc`
- end: `0x180051ed5`
- name: `?RemoveDeprovisionedPackageMarking@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `265`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035260`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180051dcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051ec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051ec2`
- `AppXAllUserStore!RemoveDeprovisionedPackageMarking` at `0x180051df0`
- `AppXAllUserStore!RemoveDeprovisionedPackageMarking` at `0x180051df0`

## string_xrefs

- `0x180051e1d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051e5b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051eab`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051e8b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180051e0e`: `RemoveDeprovisionedPackageMarking %ws failed.`
- `0x180051e84`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking`
- `0x180051e3e`: `RemoveDeprovisionedPackageMarking %s couldn't find main package`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  int v5; // edi
  int v7; // eax
  void *v8; // rbx
  int v9; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v4 = *((_QWORD *)this + 8);
  if ( v4 )
  {
    v5 = RemoveDeprovisionedPackageMarking(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v4, a2);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x478,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v5,
        (int)"RemoveDeprovisionedPackageMarking %ws failed.",
        *((const char **)this + 8));
      return (unsigned int)v5;
    }
  }
  else
  {
    pv = 0;
    v7 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L"RemoveDeprovisionedPackageMarking %s couldn't find main package",
           a2);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x482,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v7);
    v8 = pv;
    v9 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
           L"MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking",
           1162);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48A,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v9);
    if ( v8 )
      CoTaskMemFree(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180051dcc  mov     [rsp+arg_8], rbx
0x180051dd1  push    rdi
0x180051dd2  sub     rsp, 30h
0x180051dd6  mov     r8, rdx
0x180051dd9  mov     rbx, rcx
0x180051ddc  mov     rdx, [rcx+40h]
0x180051de0  test    rdx, rdx
0x180051de3  jz      short loc_180051E35
0x180051de5  mov     rcx, [rcx+10h]
0x180051de9  mov     rcx, [rcx+248h]
0x180051df0  call    cs:__imp_RemoveDeprovisionedPackageMarking
0x180051df6  mov     edi, eax
0x180051df8  test    eax, eax
0x180051dfa  jns     loc_180051EC8
0x180051e00  mov     rcx, [rsp+38h]; this
0x180051e05  mov     rdx, [rbx+40h]
0x180051e09  mov     [rsp+38h+var_10], rdx; char *
0x180051e0e  lea     rax, aRemovedeprovis_0; "RemoveDeprovisionedPackageMarking %ws f"...
0x180051e15  mov     qword ptr [rsp+38h+var_18], rax; int
0x180051e1a  mov     r9d, edi; char *
0x180051e1d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051e24  mov     edx, 478h; void *
0x180051e29  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180051e2e  mov     eax, edi
0x180051e30  jmp     loc_180051ECA
0x180051e35  mov     [rsp+38h+pv], 0
0x180051e3e  lea     rdx, aRemovedeprovis_2; "RemoveDeprovisionedPackageMarking %s co"...
0x180051e45  lea     rcx, [rsp+38h+pv]
0x180051e4a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180051e4f  mov     rcx, [rsp+38h]; this
0x180051e54  test    eax, eax
0x180051e56  jns     short loc_180051E6C
0x180051e58  mov     r9d, eax; char *
0x180051e5b  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051e62  mov     edx, 482h; void *
0x180051e67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051e6c  mov     dword ptr [rsp+38h+var_10], 0
0x180051e74  mov     [rsp+38h+var_18], 1; int
0x180051e7c  mov     edi, 48Ah
0x180051e81  mov     r9d, edi
0x180051e84  lea     r8, aMsixpackagePro_24; "MsixPackage::Provisioning::Library::Msi"...
0x180051e8b  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051e92  mov     rbx, [rsp+38h+pv]
0x180051e97  mov     rcx, rbx
0x180051e9a  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180051e9f  mov     rcx, [rsp+38h]; this
0x180051ea4  test    eax, eax
0x180051ea6  jns     short loc_180051EBA
0x180051ea8  mov     r9d, eax; char *
0x180051eab  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180051eb2  mov     edx, edi; void *
0x180051eb4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051eb9  nop
0x180051eba  test    rbx, rbx
0x180051ebd  jz      short loc_180051EC8
0x180051ebf  mov     rcx, rbx; pv
0x180051ec2  call    cs:__imp_CoTaskMemFree
0x180051ec8  xor     eax, eax
0x180051eca  mov     rbx, [rsp+38h+arg_8]
0x180051ecf  add     rsp, 30h
0x180051ed3  pop     rdi
0x180051ed4  retn
```
