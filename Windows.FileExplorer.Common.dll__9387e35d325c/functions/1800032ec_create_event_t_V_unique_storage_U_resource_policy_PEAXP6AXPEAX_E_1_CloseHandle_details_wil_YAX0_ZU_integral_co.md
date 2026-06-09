# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800032ec`
- end: `0x18000334b`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003210`
- `0x18006dbac`

## callees

- `0x1800032ec`
- `0x180003830`
- `0x18006b7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000330b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000330b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003319`

## string_xrefs

- `0x1800032f9`: `Local\SyncRootManagerRegistryUpdateEvent`
- `0x180003339`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  HANDLE Event; // rbx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, L"Local\\SyncRootManagerRegistryUpdateEvent", 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x1800032ec  mov     [rsp+arg_0], rbx
0x1800032f1  push    rdi
0x1800032f2  sub     rsp, 20h
0x1800032f6  mov     rdi, rcx
0x1800032f9  lea     rdx, Name; "Local\\SyncRootManagerRegistryUpdateEve"...
0x180003300  xor     ecx, ecx; lpEventAttributes
0x180003302  mov     r9d, 1F0003h; dwDesiredAccess
0x180003308  xor     r8d, r8d; dwFlags
0x18000330b  call    cs:__imp_CreateEventExW
0x180003311  mov     rbx, rax
0x180003314  test    rax, rax
0x180003317  jz      short loc_180003334
0x180003319  call    cs:__imp_GetLastError
0x18000331f  mov     rdx, rbx
0x180003322  mov     rcx, rdi
0x180003325  mov     rbx, [rsp+28h+arg_0]
0x18000332a  add     rsp, 20h
0x18000332e  pop     rdi
0x18000332f  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003334  mov     rcx, [rsp+28h]; this
0x180003339  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003340  mov     edx, 1CC8h; void *
0x180003345  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
