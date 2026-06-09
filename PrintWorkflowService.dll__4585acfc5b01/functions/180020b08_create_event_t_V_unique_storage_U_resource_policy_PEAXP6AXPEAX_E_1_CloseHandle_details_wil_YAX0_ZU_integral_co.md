# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180020b08`
- end: `0x180020b58`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020288`
- `0x180020c78`

## callees

- `0x18000d158`
- `0x180014054`
- `0x180020b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020b25`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180020b25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b33`

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
0x180020b08  mov     [rsp+arg_0], rbx
0x180020b0d  push    rdi
0x180020b0e  sub     rsp, 20h
0x180020b12  and     edx, 3
0x180020b15  mov     rdi, rcx
0x180020b18  mov     r8d, edx; dwFlags
0x180020b1b  mov     r9d, 1F0003h; dwDesiredAccess
0x180020b21  xor     edx, edx; lpName
0x180020b23  xor     ecx, ecx; lpEventAttributes
0x180020b25  call    cs:__imp_CreateEventExW
0x180020b2b  mov     rbx, rax
0x180020b2e  test    rax, rax
0x180020b31  jz      short loc_180020B48
0x180020b33  call    cs:__imp_GetLastError
0x180020b39  mov     rdx, rbx
0x180020b3c  mov     rcx, rdi
0x180020b3f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020b44  xor     eax, eax
0x180020b46  jmp     short loc_180020B4D
0x180020b48  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180020b4d  mov     rbx, [rsp+28h+arg_0]
0x180020b52  add     rsp, 20h
0x180020b56  pop     rdi
0x180020b57  retn
```
