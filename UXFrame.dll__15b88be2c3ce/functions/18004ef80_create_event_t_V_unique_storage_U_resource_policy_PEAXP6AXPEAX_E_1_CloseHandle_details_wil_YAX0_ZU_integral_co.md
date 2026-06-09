# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18004ef80`
- end: `0x18004efcd`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004488c`
- `0x18004efd4`

## callees

- `0x18001a878`
- `0x180043a20`
- `0x18004ef80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004ef9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004ef9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efa8`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x18004ef80  mov     [rsp+arg_0], rbx
0x18004ef85  push    rdi
0x18004ef86  sub     rsp, 20h
0x18004ef8a  mov     rdi, rcx
0x18004ef8d  mov     r9d, 1F0003h; dwDesiredAccess
0x18004ef93  xor     ecx, ecx; lpEventAttributes
0x18004ef95  xor     r8d, r8d; dwFlags
0x18004ef98  xor     edx, edx; lpName
0x18004ef9a  call    cs:__imp_CreateEventExW
0x18004efa0  mov     rbx, rax
0x18004efa3  test    rax, rax
0x18004efa6  jz      short loc_18004EFBD
0x18004efa8  call    cs:__imp_GetLastError
0x18004efae  mov     rdx, rbx
0x18004efb1  mov     rcx, rdi
0x18004efb4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004efb9  xor     eax, eax
0x18004efbb  jmp     short loc_18004EFC2
0x18004efbd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004efc2  mov     rbx, [rsp+28h+arg_0]
0x18004efc7  add     rsp, 20h
0x18004efcb  pop     rdi
0x18004efcc  retn
```
