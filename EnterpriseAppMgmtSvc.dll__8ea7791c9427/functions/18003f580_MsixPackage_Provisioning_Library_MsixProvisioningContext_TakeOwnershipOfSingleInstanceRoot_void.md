# MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(void)

- ea: `0x18003f580`
- end: `0x18003f6a6`
- name: `?TakeOwnershipOfSingleInstanceRoot@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `294`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c740`
- `0x18004ae64`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003f580`
- `0x180040400`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f693`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003f631`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18003f631`

## string_xrefs

- `0x18003f5c5`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18003f610`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18003f65d`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18003f5a8`: `An attempt to obtain ownership on the root folder %ws and its children`
- `0x18003f5ec`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot`
- `0x18003f5f3`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // esi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 15) )
    return 0;
  pv = 0;
  v2 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         (char *)&pv,
         L"An attempt to obtain ownership on the root folder %ws and its children",
         *((_QWORD *)this + 70));
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD1,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
      (const char *)(unsigned int)v2);
  v3 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
         pv,
         L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
         L"MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot",
         217);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD9,
      (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
      (const char *)(unsigned int)v3);
  v4 = TakeOwnershipOnFolder(*((_QWORD *)this + 70), 1, (char *)this + 120);
  if ( v4 >= 0 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xE0,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
    (const char *)(unsigned int)v4,
    (int)"Failed while trying to take ownership of '%ws'",
    *((const char **)this + 70));
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f580  mov     [rsp+arg_8], rsi
0x18003f585  push    rdi
0x18003f586  sub     rsp, 30h
0x18003f58a  mov     rdi, rcx
0x18003f58d  cmp     qword ptr [rcx+78h], 0
0x18003f592  jnz     loc_18003F699
0x18003f598  mov     [rsp+38h+pv], 0
0x18003f5a1  mov     r8, [rcx+230h]
0x18003f5a8  lea     rdx, aAnAttemptToObt_0; "An attempt to obtain ownership on the r"...
0x18003f5af  lea     rcx, [rsp+38h+pv]
0x18003f5b4  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003f5b9  mov     rcx, [rsp+38h]; this
0x18003f5be  test    eax, eax
0x18003f5c0  jns     short loc_18003F5D6
0x18003f5c2  mov     r9d, eax; char *
0x18003f5c5  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f5cc  mov     edx, 0D1h; void *
0x18003f5d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f5d6  mov     dword ptr [rsp+38h+var_10], 0
0x18003f5de  mov     [rsp+38h+var_18], 2; int
0x18003f5e6  mov     r9d, 0D9h
0x18003f5ec  lea     r8, aMsixpackagePro_7; "MsixPackage::Provisioning::Library::Msi"...
0x18003f5f3  lea     rdx, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f5fa  mov     rcx, [rsp+38h+pv]
0x18003f5ff  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003f604  mov     rcx, [rsp+38h]; this
0x18003f609  test    eax, eax
0x18003f60b  jns     short loc_18003F621
0x18003f60d  mov     r9d, eax; char *
0x18003f610  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f617  mov     edx, 0D9h; void *
0x18003f61c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f621  lea     r8, [rdi+78h]
0x18003f625  mov     edx, 1
0x18003f62a  mov     rcx, [rdi+230h]
0x18003f631  call    cs:__imp_TakeOwnershipOnFolder
0x18003f637  mov     esi, eax
0x18003f639  test    eax, eax
0x18003f63b  jns     short loc_18003F686
0x18003f63d  mov     rcx, [rsp+38h]; this
0x18003f642  mov     rdx, [rdi+230h]
0x18003f649  mov     [rsp+38h+var_10], rdx; char *
0x18003f64e  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x18003f655  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003f65a  mov     r9d, esi; char *
0x18003f65d  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003f664  mov     edx, 0E0h; void *
0x18003f669  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f66e  nop
0x18003f66f  cmp     [rsp+38h+pv], 0
0x18003f675  jz      short loc_18003F682
0x18003f677  mov     rcx, [rsp+38h+pv]; pv
0x18003f67c  call    cs:__imp_CoTaskMemFree
0x18003f682  mov     eax, esi
0x18003f684  jmp     short loc_18003F69B
0x18003f686  cmp     [rsp+38h+pv], 0
0x18003f68c  jz      short loc_18003F699
0x18003f68e  mov     rcx, [rsp+38h+pv]; pv
0x18003f693  call    cs:__imp_CoTaskMemFree
0x18003f699  xor     eax, eax
0x18003f69b  mov     rsi, [rsp+38h+arg_8]
0x18003f6a0  add     rsp, 30h
0x18003f6a4  pop     rdi
0x18003f6a5  retn
```
