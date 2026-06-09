# _lambda_374c045654eb315feffd7d269a1c6ea2_::operator()

- ea: `0x180032b74`
- end: `0x180032c6b`
- name: `_lambda_374c045654eb315feffd7d269a1c6ea2_::operator()`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032560`
- `0x180039edc`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180032b74`
- `0x180040400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c5f`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180032c25`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180032c25`

## string_xrefs

- `0x180032bc3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180032c0e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180032c37`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180032bf1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180032bea`: `MsixPackage::Provisioning::Library::MsixProvisioningManager::SetProvisionedAppxDataFile::<lambda_374c045654eb315feffd7d269a1c6ea2>::operator ()`
- `0x180032ba6`: `An attempt to rollback ownership on the root folder %ws and its children`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall lambda_374c045654eb315feffd7d269a1c6ea2_::operator()(__int64 a1)
{
  _QWORD *v2; // r8
  int v3; // eax
  int v4; // eax
  int v5; // eax
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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v3);
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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v4);
    v5 = RollbackTakeOwnershipSession(**(_QWORD **)a1);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x414,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v5);
    **(_QWORD **)a1 = 0;
    if ( pv )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180032b74  push    rdi
0x180032b76  sub     rsp, 30h
0x180032b7a  mov     rdi, rcx
0x180032b7d  mov     rax, [rcx]
0x180032b80  cmp     qword ptr [rax], 0
0x180032b84  jz      loc_180032C65
0x180032b8a  mov     [rsp+38h+pv], 0
0x180032b93  lea     rax, [rcx+8]
0x180032b97  mov     r8, [rax]
0x180032b9a  cmp     qword ptr [r8+18h], 8
0x180032b9f  cmovb   r8, rax
0x180032ba3  mov     r8, [r8]
0x180032ba6  lea     rdx, aAnAttemptToRol_0; "An attempt to rollback ownership on the"...
0x180032bad  lea     rcx, [rsp+38h+pv]
0x180032bb2  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180032bb7  mov     rcx, [rsp+38h]; this
0x180032bbc  test    eax, eax
0x180032bbe  jns     short loc_180032BD4
0x180032bc0  mov     r9d, eax; char *
0x180032bc3  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180032bca  mov     edx, 40Ah; void *
0x180032bcf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032bd4  mov     [rsp+38h+var_10], 0
0x180032bdc  mov     [rsp+38h+var_18], 2; int
0x180032be4  mov     r9d, 412h
0x180032bea  lea     r8, aMsixpackagePro_11; "MsixPackage::Provisioning::Library::Msi"...
0x180032bf1  lea     rdx, aOnecoreAdminAp_14; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180032bf8  mov     rcx, [rsp+38h+pv]
0x180032bfd  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180032c02  mov     rcx, [rsp+38h]; this
0x180032c07  test    eax, eax
0x180032c09  jns     short loc_180032C1F
0x180032c0b  mov     r9d, eax; char *
0x180032c0e  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180032c15  mov     edx, 412h; void *
0x180032c1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032c1f  mov     rcx, [rdi]
0x180032c22  mov     rcx, [rcx]
0x180032c25  call    cs:__imp_RollbackTakeOwnershipSession
0x180032c2b  mov     rcx, [rsp+38h]; this
0x180032c30  test    eax, eax
0x180032c32  jns     short loc_180032C48
0x180032c34  mov     r9d, eax; char *
0x180032c37  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180032c3e  mov     edx, 414h; void *
0x180032c43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032c48  mov     rax, [rdi]
0x180032c4b  mov     qword ptr [rax], 0
0x180032c52  cmp     [rsp+38h+pv], 0
0x180032c58  jz      short loc_180032C65
0x180032c5a  mov     rcx, [rsp+38h+pv]; pv
0x180032c5f  call    cs:__imp_CoTaskMemFree
0x180032c65  add     rsp, 30h
0x180032c69  pop     rdi
0x180032c6a  retn
```
