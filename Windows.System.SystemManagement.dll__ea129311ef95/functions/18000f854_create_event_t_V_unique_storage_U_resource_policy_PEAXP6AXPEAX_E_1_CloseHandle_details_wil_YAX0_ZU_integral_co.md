# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000f854`
- end: `0x18000f8a1`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d670`
- `0x180010088`
- `0x180018a1c`
- `0x180018b2c`
- `0x18001b854`

## callees

- `0x180006b08`
- `0x1800093bc`
- `0x18000f854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f86e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f87c`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x18000f854  mov     [rsp+arg_0], rbx
0x18000f859  push    rdi
0x18000f85a  sub     rsp, 20h
0x18000f85e  mov     rdi, rcx
0x18000f861  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f867  xor     ecx, ecx; lpEventAttributes
0x18000f869  xor     r8d, r8d; dwFlags
0x18000f86c  xor     edx, edx; lpName
0x18000f86e  call    cs:__imp_CreateEventExW
0x18000f874  mov     rbx, rax
0x18000f877  test    rax, rax
0x18000f87a  jz      short loc_18000F891
0x18000f87c  call    cs:__imp_GetLastError
0x18000f882  mov     rdx, rbx
0x18000f885  mov     rcx, rdi
0x18000f888  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f88d  xor     eax, eax
0x18000f88f  jmp     short loc_18000F896
0x18000f891  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f896  mov     rbx, [rsp+28h+arg_0]
0x18000f89b  add     rsp, 20h
0x18000f89f  pop     rdi
0x18000f8a0  retn
```
