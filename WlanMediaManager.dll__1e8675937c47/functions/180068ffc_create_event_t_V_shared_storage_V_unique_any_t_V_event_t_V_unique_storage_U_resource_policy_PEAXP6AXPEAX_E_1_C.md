# ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180068ffc`
- end: `0x18006904b`
- name: `?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067110`

## callees

- `0x18006867c`
- `0x180068ffc`
- `0x180069054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180069017`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180069017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069025`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  void *v2; // rdx
  HANDLE Event; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  return _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180068ffc  mov     [rsp+arg_0], rbx
0x180069001  push    rdi
0x180069002  sub     rsp, 20h
0x180069006  xor     edx, edx; lpName
0x180069008  mov     rdi, rcx
0x18006900b  xor     ecx, ecx; lpEventAttributes
0x18006900d  mov     r9d, 1F0003h; dwDesiredAccess
0x180069013  lea     r8d, [rdx+1]; dwFlags
0x180069017  call    cs:__imp_CreateEventExW
0x18006901d  mov     rbx, rax
0x180069020  test    rax, rax
0x180069023  jz      short loc_180069040
0x180069025  call    cs:__imp_GetLastError
0x18006902b  mov     rdx, rbx
0x18006902e  mov     rcx, rdi
0x180069031  mov     rbx, [rsp+28h+arg_0]
0x180069036  add     rsp, 20h
0x18006903a  pop     rdi
0x18006903b  jmp     ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180069040  mov     rcx, [rsp+28h]; this
0x180069045  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
