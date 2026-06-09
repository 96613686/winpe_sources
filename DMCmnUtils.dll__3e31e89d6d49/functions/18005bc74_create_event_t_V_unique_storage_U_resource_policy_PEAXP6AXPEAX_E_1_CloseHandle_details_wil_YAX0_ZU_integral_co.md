# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18005bc74`
- end: `0x18005bcd1`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008aed0`
- `0x18008b100`

## callees

- `0x1800555b0`
- `0x18005958c`
- `0x18005bc74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005bc91`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005bc91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bca5`

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
0x18005bc74  mov     [rsp+arg_0], rbx
0x18005bc79  push    rdi
0x18005bc7a  sub     rsp, 20h
0x18005bc7e  and     edx, 3
0x18005bc81  mov     rdi, rcx
0x18005bc84  mov     r8d, edx; dwFlags
0x18005bc87  mov     r9d, 1F0003h; dwDesiredAccess
0x18005bc8d  xor     edx, edx; lpName
0x18005bc8f  xor     ecx, ecx; lpEventAttributes
0x18005bc91  call    cs:__imp_CreateEventExW
0x18005bc98  nop     dword ptr [rax+rax+00h]
0x18005bc9d  mov     rbx, rax
0x18005bca0  test    rax, rax
0x18005bca3  jz      short loc_18005BCC0
0x18005bca5  call    cs:__imp_GetLastError
0x18005bcac  nop     dword ptr [rax+rax+00h]
0x18005bcb1  mov     rdx, rbx
0x18005bcb4  mov     rcx, rdi
0x18005bcb7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005bcbc  xor     eax, eax
0x18005bcbe  jmp     short loc_18005BCC5
0x18005bcc0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005bcc5  mov     rbx, [rsp+28h+arg_0]
0x18005bcca  add     rsp, 20h
0x18005bcce  pop     rdi
0x18005bccf  retn
```
