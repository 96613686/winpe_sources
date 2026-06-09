# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18005c8b0`
- end: `0x18005c8fe`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b56c`
- `0x18005bbf0`
- `0x18005bc94`
- `0x18005ef00`

## callees

- `0x180018598`
- `0x18001c770`
- `0x18005c8b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005c8cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005c8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c8d9`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
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
0x18005c8b0  mov     [rsp+arg_0], rbx
0x18005c8b5  push    rdi
0x18005c8b6  sub     rsp, 20h
0x18005c8ba  xor     edx, edx; lpName
0x18005c8bc  mov     rdi, rcx
0x18005c8bf  xor     ecx, ecx; lpEventAttributes
0x18005c8c1  mov     r9d, 1F0003h; dwDesiredAccess
0x18005c8c7  lea     r8d, [rdx+1]; dwFlags
0x18005c8cb  call    cs:__imp_CreateEventExW
0x18005c8d1  mov     rbx, rax
0x18005c8d4  test    rax, rax
0x18005c8d7  jz      short loc_18005C8EE
0x18005c8d9  call    cs:__imp_GetLastError
0x18005c8df  mov     rdx, rbx
0x18005c8e2  mov     rcx, rdi
0x18005c8e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005c8ea  xor     eax, eax
0x18005c8ec  jmp     short loc_18005C8F3
0x18005c8ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005c8f3  mov     rbx, [rsp+28h+arg_0]
0x18005c8f8  add     rsp, 20h
0x18005c8fc  pop     rdi
0x18005c8fd  retn
```
