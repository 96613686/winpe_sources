# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800cfd8c`
- end: `0x1800cfdd9`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cdb78`

## callees

- `0x180009da8`
- `0x18000dcb8`
- `0x1800cfd8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800cfda6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800cfda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfdb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfdb4`

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
0x1800cfd8c  mov     [rsp+arg_0], rbx
0x1800cfd91  push    rdi
0x1800cfd92  sub     rsp, 20h
0x1800cfd96  mov     rdi, rcx
0x1800cfd99  mov     r9d, 1F0003h; dwDesiredAccess
0x1800cfd9f  xor     ecx, ecx; lpEventAttributes
0x1800cfda1  xor     r8d, r8d; dwFlags
0x1800cfda4  xor     edx, edx; lpName
0x1800cfda6  call    cs:__imp_CreateEventExW
0x1800cfdac  mov     rbx, rax
0x1800cfdaf  test    rax, rax
0x1800cfdb2  jz      short loc_1800CFDC9
0x1800cfdb4  call    cs:__imp_GetLastError
0x1800cfdba  mov     rdx, rbx
0x1800cfdbd  mov     rcx, rdi
0x1800cfdc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800cfdc5  xor     eax, eax
0x1800cfdc7  jmp     short loc_1800CFDCE
0x1800cfdc9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800cfdce  mov     rbx, [rsp+28h+arg_0]
0x1800cfdd3  add     rsp, 20h
0x1800cfdd7  pop     rdi
0x1800cfdd8  retn
```
