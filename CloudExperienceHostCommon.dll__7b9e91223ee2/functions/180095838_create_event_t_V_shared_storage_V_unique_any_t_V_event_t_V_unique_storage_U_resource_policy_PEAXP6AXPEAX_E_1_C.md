# ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180095838`
- end: `0x180095893`
- name: `?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180083528`

## callees

- `0x180022790`
- `0x180095838`
- `0x180095d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180095853`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180095853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095861`

## string_xrefs

- `0x180095881`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  HANDLE Event; // rbx
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v3);
  GetLastError();
  return _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180095838  mov     [rsp+arg_0], rbx
0x18009583d  push    rdi
0x18009583e  sub     rsp, 20h
0x180095842  xor     edx, edx; lpName
0x180095844  mov     rdi, rcx
0x180095847  xor     ecx, ecx; lpEventAttributes
0x180095849  mov     r9d, 1F0003h; dwDesiredAccess
0x18009584f  lea     r8d, [rdx+1]; dwFlags
0x180095853  call    cs:__imp_CreateEventExW
0x180095859  mov     rbx, rax
0x18009585c  test    rax, rax
0x18009585f  jz      short loc_18009587C
0x180095861  call    cs:__imp_GetLastError
0x180095867  mov     rdx, rbx
0x18009586a  mov     rcx, rdi
0x18009586d  mov     rbx, [rsp+28h+arg_0]
0x180095872  add     rsp, 20h
0x180095876  pop     rdi
0x180095877  jmp     ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18009587c  mov     rcx, [rsp+28h]; this
0x180095881  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180095888  mov     edx, 1CC8h; void *
0x18009588d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
