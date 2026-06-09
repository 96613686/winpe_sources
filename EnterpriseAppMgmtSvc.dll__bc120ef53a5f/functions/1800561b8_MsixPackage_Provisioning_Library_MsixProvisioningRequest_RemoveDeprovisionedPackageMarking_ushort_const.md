# MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking(ushort const *)

- ea: `0x1800561b8`
- end: `0x1800562ce`
- name: `?RemoveDeprovisionedPackageMarking@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `278`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003856c`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x1800561b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800562b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800562b4`
- `AppXAllUserStore!RemoveDeprovisionedPackageMarking` at `0x1800561dc`
- `AppXAllUserStore!RemoveDeprovisionedPackageMarking` at `0x1800561dc`

## string_xrefs

- `0x18005620f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005624d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005629d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18005627d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180056230`: `RemoveDeprovisionedPackageMarking %s couldn't find main package`
- `0x180056200`: `RemoveDeprovisionedPackageMarking %ws failed.`
- `0x180056276`: `MsixPackage::Provisioning::Library::MsixProvisioningRequest::RemoveDeprovisionedPackageMarking`

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
  int v10; // [rsp+20h] [rbp-18h]
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v7,
        v10);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v9,
        1);
    if ( v8 )
      CoTaskMemFree(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x1800561b8  mov     [rsp+arg_8], rbx
0x1800561bd  push    rdi
0x1800561be  sub     rsp, 30h
0x1800561c2  mov     r8, rdx
0x1800561c5  mov     rbx, rcx
0x1800561c8  mov     rdx, [rcx+40h]
0x1800561cc  test    rdx, rdx
0x1800561cf  jz      short loc_180056227
0x1800561d1  mov     rcx, [rcx+10h]
0x1800561d5  mov     rcx, [rcx+248h]
0x1800561dc  call    cs:__imp_RemoveDeprovisionedPackageMarking
0x1800561e3  nop     dword ptr [rax+rax+00h]
0x1800561e8  mov     edi, eax
0x1800561ea  test    eax, eax
0x1800561ec  jns     loc_1800562C0
0x1800561f2  mov     rcx, [rsp+38h]; this
0x1800561f7  mov     rdx, [rbx+40h]
0x1800561fb  mov     [rsp+38h+var_10], rdx; char *
0x180056200  lea     rax, aRemovedeprovis_0; "RemoveDeprovisionedPackageMarking %ws f"...
0x180056207  mov     qword ptr [rsp+38h+var_18], rax; int
0x18005620c  mov     r9d, edi; char *
0x18005620f  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180056216  mov     edx, 478h; void *
0x18005621b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180056220  mov     eax, edi
0x180056222  jmp     loc_1800562C2
0x180056227  mov     [rsp+38h+pv], 0
0x180056230  lea     rdx, aRemovedeprovis_2; "RemoveDeprovisionedPackageMarking %s co"...
0x180056237  lea     rcx, [rsp+38h+pv]
0x18005623c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180056241  mov     rcx, [rsp+38h]; this
0x180056246  test    eax, eax
0x180056248  jns     short loc_18005625E
0x18005624a  mov     r9d, eax; char *
0x18005624d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180056254  mov     edx, 482h; void *
0x180056259  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005625e  mov     dword ptr [rsp+38h+var_10], 0
0x180056266  mov     [rsp+38h+var_18], 1; int
0x18005626e  mov     edi, 48Ah
0x180056273  mov     r9d, edi
0x180056276  lea     r8, aMsixpackagePro_24; "MsixPackage::Provisioning::Library::Msi"...
0x18005627d  lea     rdx, aOnecoreAdminAp; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180056284  mov     rbx, [rsp+38h+pv]
0x180056289  mov     rcx, rbx
0x18005628c  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180056291  mov     rcx, [rsp+38h]; this
0x180056296  test    eax, eax
0x180056298  jns     short loc_1800562AC
0x18005629a  mov     r9d, eax; char *
0x18005629d  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800562a4  mov     edx, edi; void *
0x1800562a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800562ab  nop
0x1800562ac  test    rbx, rbx
0x1800562af  jz      short loc_1800562C0
0x1800562b1  mov     rcx, rbx; pv
0x1800562b4  call    cs:__imp_CoTaskMemFree
0x1800562bb  nop     dword ptr [rax+rax+00h]
0x1800562c0  xor     eax, eax
0x1800562c2  mov     rbx, [rsp+38h+arg_8]
0x1800562c7  add     rsp, 30h
0x1800562cb  pop     rdi
0x1800562cc  retn
```
