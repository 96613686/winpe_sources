# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000925c`
- end: `0x1400092ac`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006788`
- `0x140008fdc`

## callees

- `0x140003cc8`
- `0x140005f54`
- `0x14000925c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140009279`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140009279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009287`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  wil::details *v3; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v3);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x14000925c  mov     [rsp+arg_0], rbx
0x140009261  push    rdi
0x140009262  sub     rsp, 20h
0x140009266  and     edx, 3
0x140009269  mov     rdi, rcx
0x14000926c  mov     r8d, edx; dwFlags
0x14000926f  mov     r9d, 1F0003h; dwDesiredAccess
0x140009275  xor     edx, edx; lpName
0x140009277  xor     ecx, ecx; lpEventAttributes
0x140009279  call    cs:__imp_CreateEventExW
0x14000927f  mov     rbx, rax
0x140009282  test    rax, rax
0x140009285  jz      short loc_14000929C
0x140009287  call    cs:__imp_GetLastError
0x14000928d  mov     rdx, rbx
0x140009290  mov     rcx, rdi
0x140009293  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009298  xor     eax, eax
0x14000929a  jmp     short loc_1400092A1
0x14000929c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400092a1  mov     rbx, [rsp+28h+arg_0]
0x1400092a6  add     rsp, 20h
0x1400092aa  pop     rdi
0x1400092ab  retn
```
