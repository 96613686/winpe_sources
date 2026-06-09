# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18003a690`
- end: `0x18003a6dd`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c030`
- `0x18001c160`
- `0x18001c290`
- `0x180026e0c`
- `0x180041b98`
- `0x180094d94`

## callees

- `0x1800092a8`
- `0x18000b014`
- `0x18003a690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a6aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6b8`

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
0x18003a690  mov     [rsp+arg_0], rbx
0x18003a695  push    rdi
0x18003a696  sub     rsp, 20h
0x18003a69a  mov     rdi, rcx
0x18003a69d  mov     r9d, 1F0003h; dwDesiredAccess
0x18003a6a3  xor     ecx, ecx; lpEventAttributes
0x18003a6a5  xor     r8d, r8d; dwFlags
0x18003a6a8  xor     edx, edx; lpName
0x18003a6aa  call    cs:__imp_CreateEventExW
0x18003a6b0  mov     rbx, rax
0x18003a6b3  test    rax, rax
0x18003a6b6  jz      short loc_18003A6CD
0x18003a6b8  call    cs:__imp_GetLastError
0x18003a6be  mov     rdx, rbx
0x18003a6c1  mov     rcx, rdi
0x18003a6c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003a6c9  xor     eax, eax
0x18003a6cb  jmp     short loc_18003A6D2
0x18003a6cd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003a6d2  mov     rbx, [rsp+28h+arg_0]
0x18003a6d7  add     rsp, 20h
0x18003a6db  pop     rdi
0x18003a6dc  retn
```
