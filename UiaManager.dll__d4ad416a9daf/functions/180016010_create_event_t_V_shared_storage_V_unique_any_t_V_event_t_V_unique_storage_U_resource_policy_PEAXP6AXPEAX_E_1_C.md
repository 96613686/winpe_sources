# ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180016010`
- end: `0x180016075`
- name: `?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015a70`
- `0x180017600`
- `0x180021c80`

## callees

- `0x180016010`
- `0x1800160fc`
- `0x18002a514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016035`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016035`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016043`

## string_xrefs

- `0x180016063`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  HANDLE Event; // rbx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(a4, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v6);
  GetLastError();
  return _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180016010  mov     [rsp+arg_0], rbx
0x180016015  push    rdi
0x180016016  sub     rsp, 20h
0x18001601a  and     edx, 3
0x18001601d  mov     r10, r9
0x180016020  mov     rax, r8
0x180016023  mov     rdi, rcx
0x180016026  mov     r8d, edx; dwFlags
0x180016029  mov     r9d, 1F0003h; dwDesiredAccess
0x18001602f  mov     rdx, rax; lpName
0x180016032  mov     rcx, r10; lpEventAttributes
0x180016035  call    cs:__imp_CreateEventExW
0x18001603b  mov     rbx, rax
0x18001603e  test    rax, rax
0x180016041  jz      short loc_18001605E
0x180016043  call    cs:__imp_GetLastError
0x180016049  mov     rdx, rbx
0x18001604c  mov     rcx, rdi
0x18001604f  mov     rbx, [rsp+28h+arg_0]
0x180016054  add     rsp, 20h
0x180016058  pop     rdi
0x180016059  jmp     ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18001605e  mov     rcx, [rsp+28h]; this
0x180016063  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001606a  mov     edx, 1CC8h; void *
0x18001606f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
