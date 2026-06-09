# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002f164`
- end: `0x18002f1b2`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ec54`
- `0x18002ecf8`

## callees

- `0x18000bf68`
- `0x18000fda0`
- `0x18002f164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f17f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002f17f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f18d`

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
0x18002f164  mov     [rsp+arg_0], rbx
0x18002f169  push    rdi
0x18002f16a  sub     rsp, 20h
0x18002f16e  xor     edx, edx; lpName
0x18002f170  mov     rdi, rcx
0x18002f173  xor     ecx, ecx; lpEventAttributes
0x18002f175  mov     r9d, 1F0003h; dwDesiredAccess
0x18002f17b  lea     r8d, [rdx+1]; dwFlags
0x18002f17f  call    cs:__imp_CreateEventExW
0x18002f185  mov     rbx, rax
0x18002f188  test    rax, rax
0x18002f18b  jz      short loc_18002F1A2
0x18002f18d  call    cs:__imp_GetLastError
0x18002f193  mov     rdx, rbx
0x18002f196  mov     rcx, rdi
0x18002f199  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002f19e  xor     eax, eax
0x18002f1a0  jmp     short loc_18002F1A7
0x18002f1a2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002f1a7  mov     rbx, [rsp+28h+arg_0]
0x18002f1ac  add     rsp, 20h
0x18002f1b0  pop     rdi
0x18002f1b1  retn
```
