# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18004ded0`
- end: `0x18004df1d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003824c`
- `0x180060964`

## callees

- `0x18003d738`
- `0x18003d76c`
- `0x18004ded0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004deea`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004deea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004def8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004def8`

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
0x18004ded0  mov     [rsp+arg_0], rbx
0x18004ded5  push    rdi
0x18004ded6  sub     rsp, 20h
0x18004deda  mov     rdi, rcx
0x18004dedd  mov     r9d, 1F0003h; dwDesiredAccess
0x18004dee3  xor     ecx, ecx; lpEventAttributes
0x18004dee5  xor     r8d, r8d; dwFlags
0x18004dee8  xor     edx, edx; lpName
0x18004deea  call    cs:__imp_CreateEventExW
0x18004def0  mov     rbx, rax
0x18004def3  test    rax, rax
0x18004def6  jz      short loc_18004DF0D
0x18004def8  call    cs:__imp_GetLastError
0x18004defe  mov     rdx, rbx
0x18004df01  mov     rcx, rdi
0x18004df04  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004df09  xor     eax, eax
0x18004df0b  jmp     short loc_18004DF12
0x18004df0d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004df12  mov     rbx, [rsp+28h+arg_0]
0x18004df17  add     rsp, 20h
0x18004df1b  pop     rdi
0x18004df1c  retn
```
