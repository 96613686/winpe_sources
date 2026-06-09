# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18009255c`
- end: `0x1800925b9`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180081080`
- `0x1800c0b9c`

## callees

- `0x18003e940`
- `0x18009255c`
- `0x180093830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092587`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180092579`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180092579`

## string_xrefs

- `0x1800925a7`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  HANDLE Event; // rbx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x18009255c  mov     [rsp+arg_0], rbx
0x180092561  push    rdi
0x180092562  sub     rsp, 20h
0x180092566  and     edx, 3
0x180092569  mov     rdi, rcx
0x18009256c  mov     r8d, edx; dwFlags
0x18009256f  mov     r9d, 1F0003h; dwDesiredAccess
0x180092575  xor     edx, edx; lpName
0x180092577  xor     ecx, ecx; lpEventAttributes
0x180092579  call    cs:__imp_CreateEventExW
0x18009257f  mov     rbx, rax
0x180092582  test    rax, rax
0x180092585  jz      short loc_1800925A2
0x180092587  call    cs:__imp_GetLastError
0x18009258d  mov     rdx, rbx
0x180092590  mov     rcx, rdi
0x180092593  mov     rbx, [rsp+28h+arg_0]
0x180092598  add     rsp, 20h
0x18009259c  pop     rdi
0x18009259d  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800925a2  mov     rcx, [rsp+28h]; this
0x1800925a7  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x1800925ae  mov     edx, 1CC8h; void *
0x1800925b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
