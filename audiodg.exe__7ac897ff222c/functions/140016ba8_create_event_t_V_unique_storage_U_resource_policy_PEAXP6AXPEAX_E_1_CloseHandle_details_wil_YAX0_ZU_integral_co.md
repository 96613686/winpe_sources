# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140016ba8`
- end: `0x140016bf8`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400171a4`
- `0x14004b3e8`
- `0x14004bcc4`
- `0x140054964`
- `0x14005ae40`
- `0x140090884`

## callees

- `0x140016848`
- `0x140016ba8`
- `0x140016eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140016bc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140016bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016bd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016bd3`

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
0x140016ba8  mov     [rsp+arg_0], rbx
0x140016bad  push    rdi
0x140016bae  sub     rsp, 20h
0x140016bb2  and     edx, 3
0x140016bb5  mov     rdi, rcx
0x140016bb8  mov     r8d, edx; dwFlags
0x140016bbb  mov     r9d, 1F0003h; dwDesiredAccess
0x140016bc1  xor     edx, edx; lpName
0x140016bc3  xor     ecx, ecx; lpEventAttributes
0x140016bc5  call    cs:__imp_CreateEventExW
0x140016bcb  mov     rbx, rax
0x140016bce  test    rax, rax
0x140016bd1  jz      short loc_140016BF1
0x140016bd3  call    cs:__imp_GetLastError
0x140016bd9  mov     rdx, rbx
0x140016bdc  mov     rcx, rdi
0x140016bdf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140016be4  xor     eax, eax
0x140016be6  mov     rbx, [rsp+28h+arg_0]
0x140016beb  add     rsp, 20h
0x140016bef  pop     rdi
0x140016bf0  retn
0x140016bf1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140016bf6  jmp     short loc_140016BE6
```
