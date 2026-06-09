# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002b70c`
- end: `0x18002b759`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016b6c`
- `0x1800465c8`

## callees

- `0x18000c8a8`
- `0x1800103c8`
- `0x18002b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002b726`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002b726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b734`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002b70c  mov     [rsp+arg_0], rbx
0x18002b711  push    rdi
0x18002b712  sub     rsp, 20h
0x18002b716  mov     rdi, rcx
0x18002b719  mov     r9d, 1F0003h; dwDesiredAccess
0x18002b71f  xor     ecx, ecx; lpEventAttributes
0x18002b721  xor     r8d, r8d; dwFlags
0x18002b724  xor     edx, edx; lpName
0x18002b726  call    cs:__imp_CreateEventExW
0x18002b72c  mov     rbx, rax
0x18002b72f  test    rax, rax
0x18002b732  jz      short loc_18002B749
0x18002b734  call    cs:__imp_GetLastError
0x18002b73a  mov     rdx, rbx
0x18002b73d  mov     rcx, rdi
0x18002b740  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002b745  xor     eax, eax
0x18002b747  jmp     short loc_18002B74E
0x18002b749  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002b74e  mov     rbx, [rsp+28h+arg_0]
0x18002b753  add     rsp, 20h
0x18002b757  pop     rdi
0x18002b758  retn
```
