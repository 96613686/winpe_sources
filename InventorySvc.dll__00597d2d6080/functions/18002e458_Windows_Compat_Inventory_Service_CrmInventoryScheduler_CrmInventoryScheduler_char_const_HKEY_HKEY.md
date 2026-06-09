# Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler(char const *,HKEY__ *,HKEY__ *)

- ea: `0x18002e458`
- end: `0x18002e58c`
- name: `??0CrmInventoryScheduler@Service@Inventory@Compat@Windows@@QEAA@PEBDPEAUHKEY__@@1@Z`
- size: `308`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::Service::CrmInventoryScheduler *__hidden this, const char *, HKEY, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002867c`

## callees

- `0x1800108d4`
- `0x1800110f8`
- `0x1800152d0`
- `0x18001ff40`
- `0x18002e458`
- `0x18002f5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e52b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e52b`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002e512`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002e512`

## string_xrefs

- `0x18002e548`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002e502`: `Inventory and Compatibility Appraisal service`
- `0x18002e56d`: `Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HANDLE *__fastcall Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler(
        HANDLE *this,
        const char *a2,
        HKEY a3,
        HKEY a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  const char *v14; // r9
  unsigned int v16; // r8d
  int v17; // [rsp+20h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES v18; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Windows::Compat::Inventory::Service::InventoryScheduler::InventoryScheduler(
    (Windows::Compat::Inventory::Service::InventoryScheduler *)this,
    a2,
    a3,
    a4);
  *this = &Windows::Compat::Inventory::Service::CrmInventoryScheduler::`vftable';
  this[15] = 0;
  this[16] = 0;
  this[17] = 0;
  *((_DWORD *)this + 36) = 1200;
  *((_DWORD *)this + 37) = 1200;
  *((_DWORD *)this + 38) = 86400;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    this + 6,
    v5,
    v6,
    0);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    this + 7,
    v7,
    v8,
    0);
  *(_QWORD *)&v18.nLength = 24;
  *(_QWORD *)&v18.bInheritHandle = 1;
  v18.lpSecurityDescriptor = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    this + 8,
    v9,
    v10,
    &v18);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    this + 9,
    v11,
    v12,
    &v18);
  v13 = CrmRegister(this + 15, 305, L"Inventory and Compatibility Appraisal service");
  if ( (v13 & 0xC0000000) == 0xC0000000 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::CrmInventoryScheduler::CrmInventoryScheduler",
      18,
      "failed [%#x]",
      v13);
    wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x12, v16, (const char *)v13, v17);
  }
  if ( !SetEvent(this[5]) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v14);
  return this;
}

```

## disassembly

```asm
0x18002e458  mov     [rsp+arg_8], rbx
0x18002e45d  mov     [rsp+arg_0], rcx
0x18002e462  push    rdi
0x18002e463  sub     rsp, 50h
0x18002e467  mov     rdi, rcx
0x18002e46a  call    ??0InventoryScheduler@Service@Inventory@Compat@Windows@@IEAA@PEBDPEAUHKEY__@@1@Z; Windows::Compat::Inventory::Service::InventoryScheduler::InventoryScheduler(char const *,HKEY__ *,HKEY__ *)
0x18002e46f  nop
0x18002e470  lea     rax, ??_7CrmInventoryScheduler@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::CrmInventoryScheduler::`vftable'
0x18002e477  mov     [rdi], rax
0x18002e47a  mov     qword ptr [rdi+78h], 0
0x18002e482  mov     qword ptr [rdi+80h], 0
0x18002e48d  mov     qword ptr [rdi+88h], 0
0x18002e498  mov     eax, 4B0h
0x18002e49d  mov     [rdi+90h], eax
0x18002e4a3  mov     [rdi+94h], eax
0x18002e4a9  mov     dword ptr [rdi+98h], 15180h
0x18002e4b3  lea     rcx, [rdi+30h]
0x18002e4b7  xor     r9d, r9d
0x18002e4ba  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002e4bf  lea     rcx, [rdi+38h]
0x18002e4c3  xor     r9d, r9d
0x18002e4c6  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002e4cb  mov     [rsp+58h+var_28], 18h
0x18002e4d4  mov     [rsp+58h+var_18], 1
0x18002e4dd  mov     [rsp+58h+var_20], 0
0x18002e4e6  lea     rcx, [rdi+40h]
0x18002e4ea  lea     r9, [rsp+58h+var_28]
0x18002e4ef  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002e4f4  lea     rcx, [rdi+48h]
0x18002e4f8  lea     r9, [rsp+58h+var_28]
0x18002e4fd  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002e502  lea     r8, aInventoryAndCo; "Inventory and Compatibility Appraisal s"...
0x18002e509  mov     edx, 131h
0x18002e50e  lea     rcx, [rdi+78h]
0x18002e512  call    cs:__imp_CrmRegister
0x18002e518  mov     ebx, eax
0x18002e51a  mov     edx, eax
0x18002e51c  mov     eax, 0C0000000h
0x18002e521  and     edx, eax
0x18002e523  cmp     edx, eax
0x18002e525  jz      short loc_18002E55A
0x18002e527  mov     rcx, [rdi+28h]; hEvent
0x18002e52b  call    cs:__imp_SetEvent
0x18002e531  mov     rcx, [rsp+58h]; this
0x18002e536  test    eax, eax
0x18002e538  jz      short loc_18002E548
0x18002e53a  mov     rax, rdi
0x18002e53d  mov     rbx, [rsp+58h+arg_8]
0x18002e542  add     rsp, 50h
0x18002e546  pop     rdi
0x18002e547  retn
0x18002e548  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e54f  mov     edx, 0A01h; void *
0x18002e554  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e55a  mov     [rsp+58h+var_38], ebx; int
0x18002e55e  lea     r9, aFailedX; "failed [%#x]"
0x18002e565  mov     edi, 12h
0x18002e56a  mov     r8d, edi
0x18002e56d  lea     rdx, aWindowsCompatI_18; "Windows::Compat::Inventory::Service::Cr"...
0x18002e574  lea     ecx, [rdi-11h]
0x18002e577  call    AslLogCallPrintf
0x18002e57c  mov     rcx, [rsp+58h]; this
0x18002e581  mov     r9d, ebx; char *
0x18002e584  mov     edx, edi; void *
0x18002e586  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
