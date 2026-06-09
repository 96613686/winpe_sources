# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180016bcc`
- end: `0x180016c19`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8d4`
- `0x18000fa04`

## callees

- `0x1800060e8`
- `0x180007e34`
- `0x180016bcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016be6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bf4`

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
0x180016bcc  mov     [rsp+arg_0], rbx
0x180016bd1  push    rdi
0x180016bd2  sub     rsp, 20h
0x180016bd6  mov     rdi, rcx
0x180016bd9  mov     r9d, 1F0003h; dwDesiredAccess
0x180016bdf  xor     ecx, ecx; lpEventAttributes
0x180016be1  xor     r8d, r8d; dwFlags
0x180016be4  xor     edx, edx; lpName
0x180016be6  call    cs:__imp_CreateEventExW
0x180016bec  mov     rbx, rax
0x180016bef  test    rax, rax
0x180016bf2  jz      short loc_180016C09
0x180016bf4  call    cs:__imp_GetLastError
0x180016bfa  mov     rdx, rbx
0x180016bfd  mov     rcx, rdi
0x180016c00  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016c05  xor     eax, eax
0x180016c07  jmp     short loc_180016C0E
0x180016c09  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016c0e  mov     rbx, [rsp+28h+arg_0]
0x180016c13  add     rsp, 20h
0x180016c17  pop     rdi
0x180016c18  retn
```
