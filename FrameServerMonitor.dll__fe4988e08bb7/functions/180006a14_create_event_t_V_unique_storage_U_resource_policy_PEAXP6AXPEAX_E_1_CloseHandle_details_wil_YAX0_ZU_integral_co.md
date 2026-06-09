# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180006a14`
- end: `0x180006a61`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006370`
- `0x18000c100`
- `0x180015180`
- `0x18001f6a8`

## callees

- `0x180003c90`
- `0x1800056a8`
- `0x180006a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180006a2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180006a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a3c`

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
0x180006a14  mov     [rsp+arg_0], rbx
0x180006a19  push    rdi
0x180006a1a  sub     rsp, 20h
0x180006a1e  mov     rdi, rcx
0x180006a21  mov     r9d, 1F0003h; dwDesiredAccess
0x180006a27  xor     ecx, ecx; lpEventAttributes
0x180006a29  xor     r8d, r8d; dwFlags
0x180006a2c  xor     edx, edx; lpName
0x180006a2e  call    cs:__imp_CreateEventExW
0x180006a34  mov     rbx, rax
0x180006a37  test    rax, rax
0x180006a3a  jz      short loc_180006A51
0x180006a3c  call    cs:__imp_GetLastError
0x180006a42  mov     rdx, rbx
0x180006a45  mov     rcx, rdi
0x180006a48  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006a4d  xor     eax, eax
0x180006a4f  jmp     short loc_180006A56
0x180006a51  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006a56  mov     rbx, [rsp+28h+arg_0]
0x180006a5b  add     rsp, 20h
0x180006a5f  pop     rdi
0x180006a60  retn
```
