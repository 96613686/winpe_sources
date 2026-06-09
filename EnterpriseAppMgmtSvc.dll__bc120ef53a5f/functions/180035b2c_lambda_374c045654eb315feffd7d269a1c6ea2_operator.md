# _lambda_374c045654eb315feffd7d269a1c6ea2_::operator()

- ea: `0x180035b2c`
- end: `0x180035c30`
- name: `_lambda_374c045654eb315feffd7d269a1c6ea2_::operator()`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003545c`
- `0x18003d52c`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x180035b2c`
- `0x180043fb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c1d`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180035bdd`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180035bdd`

## string_xrefs

- `0x180035b7b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180035bc6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180035bf5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180035ba2`: `MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile::<lambda_374c045654eb315feffd7d269a1c6ea2>::operator ()`
- `0x180035b5e`: `An attempt to rollback ownership on the root folder %ws and its children`
- `0x180035ba9`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(__int64 a1)
{
  _QWORD *v2; // r8
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // [rsp+20h] [rbp-18h]
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  if ( **(_QWORD **)a1 )
  {
    pv = 0;
    v2 = *(_QWORD **)(a1 + 8);
    if ( v2[3] < 8u )
      v2 = (_QWORD *)(a1 + 8);
    v3 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L"An attempt to rollback ownership on the root folder %ws and its children",
           *v2);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v3,
        v6);
    v7 = 2;
    v4 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
           L"MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile::<lambda_374c045654eb"
            "315feffd7d269a1c6ea2>::operator ()",
           1042);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x412,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v4,
        2);
    v5 = RollbackTakeOwnershipSession(**(_QWORD **)a1);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v5,
        v7);
    **(_QWORD **)a1 = 0;
    if ( pv )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180035b2c  push    rdi
0x180035b2e  sub     rsp, 30h
0x180035b32  mov     rdi, rcx
0x180035b35  mov     rax, [rcx]
0x180035b38  cmp     qword ptr [rax], 0
0x180035b3c  jz      loc_180035C29
0x180035b42  mov     [rsp+38h+pv], 0
0x180035b4b  lea     rax, [rcx+8]
0x180035b4f  mov     r8, [rax]
0x180035b52  cmp     qword ptr [r8+18h], 8
0x180035b57  cmovb   r8, rax
0x180035b5b  mov     r8, [r8]
0x180035b5e  lea     rdx, aAnAttemptToRol_0; "An attempt to rollback ownership on the"...
0x180035b65  lea     rcx, [rsp+38h+pv]
0x180035b6a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180035b6f  mov     rcx, [rsp+38h]; this
0x180035b74  test    eax, eax
0x180035b76  jns     short loc_180035B8C
0x180035b78  mov     r9d, eax; char *
0x180035b7b  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180035b82  mov     edx, 40Ah; void *
0x180035b87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b8c  mov     [rsp+38h+var_10], 0
0x180035b94  mov     [rsp+38h+var_18], 2; int
0x180035b9c  mov     r9d, 412h
0x180035ba2  lea     r8, aMsixpackagePro_11; "MsixPackage::Provisioning::Library::Msi"...
0x180035ba9  lea     rdx, aOnecoreAdminAp_14; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180035bb0  mov     rcx, [rsp+38h+pv]
0x180035bb5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180035bba  mov     rcx, [rsp+38h]; this
0x180035bbf  test    eax, eax
0x180035bc1  jns     short loc_180035BD7
0x180035bc3  mov     r9d, eax; char *
0x180035bc6  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180035bcd  mov     edx, 412h; void *
0x180035bd2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035bd7  mov     rcx, [rdi]
0x180035bda  mov     rcx, [rcx]
0x180035bdd  call    cs:__imp_RollbackTakeOwnershipSession
0x180035be4  nop     dword ptr [rax+rax+00h]
0x180035be9  mov     rcx, [rsp+38h]; this
0x180035bee  test    eax, eax
0x180035bf0  jns     short loc_180035C06
0x180035bf2  mov     r9d, eax; char *
0x180035bf5  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180035bfc  mov     edx, 414h; void *
0x180035c01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035c06  mov     rax, [rdi]
0x180035c09  mov     qword ptr [rax], 0
0x180035c10  cmp     [rsp+38h+pv], 0
0x180035c16  jz      short loc_180035C29
0x180035c18  mov     rcx, [rsp+38h+pv]; pv
0x180035c1d  call    cs:__imp_CoTaskMemFree
0x180035c24  nop     dword ptr [rax+rax+00h]
0x180035c29  add     rsp, 30h
0x180035c2d  pop     rdi
0x180035c2e  retn
```
