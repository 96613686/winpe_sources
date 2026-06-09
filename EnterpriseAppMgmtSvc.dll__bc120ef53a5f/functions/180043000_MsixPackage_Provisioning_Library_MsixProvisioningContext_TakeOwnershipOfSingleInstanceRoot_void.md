# MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(void)

- ea: `0x180043000`
- end: `0x180043139`
- name: `?TakeOwnershipOfSingleInstanceRoot@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `313`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ff14`
- `0x18004f030`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043000`
- `0x180043fb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004311f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004311f`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x1800430b1`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x1800430b1`

## string_xrefs

- `0x180043045`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x180043090`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x1800430e3`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x180043028`: `An attempt to obtain ownership on the root folder %ws and its children`
- `0x180043073`: `onecore\admin\appmodel\utilities\provisionhelper\MsixPackageAdapter.h`
- `0x18004306c`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // esi
  int v6; // [rsp+20h] [rbp-18h]
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
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
      (const char *)(unsigned int)v2,
      v6);
  v3 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
         pv,
         L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
         L"MsixPackage::Provisioning::Library::MsixProvisioningContext::TakeOwnershipOfSingleInstanceRoot",
         217);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixPackageAdapter.h",
      (const char *)(unsigned int)v3,
      2);
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
0x180043000  mov     [rsp+arg_8], rsi
0x180043005  push    rdi
0x180043006  sub     rsp, 30h
0x18004300a  mov     rdi, rcx
0x18004300d  cmp     qword ptr [rcx+78h], 0
0x180043012  jnz     loc_18004312B
0x180043018  mov     [rsp+38h+pv], 0
0x180043021  mov     r8, [rcx+230h]
0x180043028  lea     rdx, aAnAttemptToObt_0; "An attempt to obtain ownership on the r"...
0x18004302f  lea     rcx, [rsp+38h+pv]
0x180043034  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180043039  mov     rcx, [rsp+38h]; this
0x18004303e  test    eax, eax
0x180043040  jns     short loc_180043056
0x180043042  mov     r9d, eax; char *
0x180043045  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004304c  mov     edx, 0D1h; void *
0x180043051  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043056  mov     dword ptr [rsp+38h+var_10], 0
0x18004305e  mov     [rsp+38h+var_18], 2; int
0x180043066  mov     r9d, 0D9h
0x18004306c  lea     r8, aMsixpackagePro_7; "MsixPackage::Provisioning::Library::Msi"...
0x180043073  lea     rdx, aOnecoreAdminAp_12; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004307a  mov     rcx, [rsp+38h+pv]
0x18004307f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180043084  mov     rcx, [rsp+38h]; this
0x180043089  test    eax, eax
0x18004308b  jns     short loc_1800430A1
0x18004308d  mov     r9d, eax; char *
0x180043090  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180043097  mov     edx, 0D9h; void *
0x18004309c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800430a1  lea     r8, [rdi+78h]
0x1800430a5  mov     edx, 1
0x1800430aa  mov     rcx, [rdi+230h]
0x1800430b1  call    cs:__imp_TakeOwnershipOnFolder
0x1800430b8  nop     dword ptr [rax+rax+00h]
0x1800430bd  mov     esi, eax
0x1800430bf  test    eax, eax
0x1800430c1  jns     short loc_180043112
0x1800430c3  mov     rcx, [rsp+38h]; this
0x1800430c8  mov     rdx, [rdi+230h]
0x1800430cf  mov     [rsp+38h+var_10], rdx; char *
0x1800430d4  lea     rax, aFailedWhileTry_0; "Failed while trying to take ownership o"...
0x1800430db  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800430e0  mov     r9d, esi; char *
0x1800430e3  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800430ea  mov     edx, 0E0h; void *
0x1800430ef  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800430f4  nop
0x1800430f5  cmp     [rsp+38h+pv], 0
0x1800430fb  jz      short loc_18004310E
0x1800430fd  mov     rcx, [rsp+38h+pv]; pv
0x180043102  call    cs:__imp_CoTaskMemFree
0x180043109  nop     dword ptr [rax+rax+00h]
0x18004310e  mov     eax, esi
0x180043110  jmp     short loc_18004312D
0x180043112  cmp     [rsp+38h+pv], 0
0x180043118  jz      short loc_18004312B
0x18004311a  mov     rcx, [rsp+38h+pv]; pv
0x18004311f  call    cs:__imp_CoTaskMemFree
0x180043126  nop     dword ptr [rax+rax+00h]
0x18004312b  xor     eax, eax
0x18004312d  mov     rsi, [rsp+38h+arg_8]
0x180043132  add     rsp, 30h
0x180043136  pop     rdi
0x180043137  retn
```
