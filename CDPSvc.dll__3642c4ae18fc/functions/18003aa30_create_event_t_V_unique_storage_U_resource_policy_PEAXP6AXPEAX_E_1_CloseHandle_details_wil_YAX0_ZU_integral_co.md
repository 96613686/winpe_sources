# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18003aa30`
- end: `0x18003aa7d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a750`
- `0x18003d480`

## callees

- `0x18001d128`
- `0x18001d15c`
- `0x18003aa30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003aa4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003aa4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa58`

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
0x18003aa30  mov     [rsp+arg_0], rbx
0x18003aa35  push    rdi
0x18003aa36  sub     rsp, 20h
0x18003aa3a  mov     rdi, rcx
0x18003aa3d  mov     r9d, 1F0003h; dwDesiredAccess
0x18003aa43  xor     ecx, ecx; lpEventAttributes
0x18003aa45  xor     r8d, r8d; dwFlags
0x18003aa48  xor     edx, edx; lpName
0x18003aa4a  call    cs:__imp_CreateEventExW
0x18003aa50  mov     rbx, rax
0x18003aa53  test    rax, rax
0x18003aa56  jz      short loc_18003AA6D
0x18003aa58  call    cs:__imp_GetLastError
0x18003aa5e  mov     rdx, rbx
0x18003aa61  mov     rcx, rdi
0x18003aa64  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003aa69  xor     eax, eax
0x18003aa6b  jmp     short loc_18003AA72
0x18003aa6d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003aa72  mov     rbx, [rsp+28h+arg_0]
0x18003aa77  add     rsp, 20h
0x18003aa7b  pop     rdi
0x18003aa7c  retn
```
