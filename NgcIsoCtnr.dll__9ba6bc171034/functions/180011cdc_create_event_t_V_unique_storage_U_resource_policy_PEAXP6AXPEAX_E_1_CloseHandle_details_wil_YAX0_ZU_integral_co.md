# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180011cdc`
- end: `0x180011d3d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fa44`

## callees

- `0x18000eeb8`
- `0x180011a60`
- `0x180011cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011cfd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d0b`

## string_xrefs

- `0x180011d2b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  HANDLE Event; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180011cdc  mov     [rsp+arg_0], rbx
0x180011ce1  push    rdi
0x180011ce2  sub     rsp, 20h
0x180011ce6  and     edx, 3
0x180011ce9  mov     rax, r8
0x180011cec  mov     r8d, edx; dwFlags
0x180011cef  mov     rdi, rcx
0x180011cf2  mov     rdx, rax; lpName
0x180011cf5  mov     r9d, 1F0003h; dwDesiredAccess
0x180011cfb  xor     ecx, ecx; lpEventAttributes
0x180011cfd  call    cs:__imp_CreateEventExW
0x180011d03  mov     rbx, rax
0x180011d06  test    rax, rax
0x180011d09  jz      short loc_180011D26
0x180011d0b  call    cs:__imp_GetLastError
0x180011d11  mov     rdx, rbx
0x180011d14  mov     rcx, rdi
0x180011d17  mov     rbx, [rsp+28h+arg_0]
0x180011d1c  add     rsp, 20h
0x180011d20  pop     rdi
0x180011d21  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011d26  mov     rcx, [rsp+28h]; this
0x180011d2b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011d32  mov     edx, 1CC8h; void *
0x180011d37  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
