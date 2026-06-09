# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180061e00`
- end: `0x180061e4e`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061d78`

## callees

- `0x180061e00`
- `0x180061e54`
- `0x180080308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180061e1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180061e1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e29`

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
0x180061e00  mov     [rsp+arg_0], rbx
0x180061e05  push    rdi
0x180061e06  sub     rsp, 20h
0x180061e0a  xor     edx, edx; lpName
0x180061e0c  mov     rdi, rcx
0x180061e0f  xor     ecx, ecx; lpEventAttributes
0x180061e11  mov     r9d, 1F0003h; dwDesiredAccess
0x180061e17  lea     r8d, [rdx+1]; dwFlags
0x180061e1b  call    cs:__imp_CreateEventExW
0x180061e21  mov     rbx, rax
0x180061e24  test    rax, rax
0x180061e27  jz      short loc_180061E47
0x180061e29  call    cs:__imp_GetLastError
0x180061e2f  mov     rdx, rbx
0x180061e32  mov     rcx, rdi
0x180061e35  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180061e3a  xor     eax, eax
0x180061e3c  mov     rbx, [rsp+28h+arg_0]
0x180061e41  add     rsp, 20h
0x180061e45  pop     rdi
0x180061e46  retn
0x180061e47  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180061e4c  jmp     short loc_180061E3C
```
