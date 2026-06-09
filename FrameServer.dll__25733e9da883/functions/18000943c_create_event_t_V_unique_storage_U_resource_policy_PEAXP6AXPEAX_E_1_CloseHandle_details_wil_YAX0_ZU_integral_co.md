# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000943c`
- end: `0x18000948c`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008f34`
- `0x18001aadc`
- `0x180023f08`
- `0x1800708b8`
- `0x18008f300`
- `0x180099d4c`
- `0x1800a9e20`
- `0x1800b34e0`
- `0x1800b5710`
- `0x1800b5930`
- `0x1800b6ab0`
- `0x1800e47d0`

## callees

- `0x180006890`
- `0x180008338`
- `0x18000943c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009459`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009467`

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
0x18000943c  mov     [rsp+arg_0], rbx
0x180009441  push    rdi
0x180009442  sub     rsp, 20h
0x180009446  and     edx, 3
0x180009449  mov     rdi, rcx
0x18000944c  mov     r8d, edx; dwFlags
0x18000944f  mov     r9d, 1F0003h; dwDesiredAccess
0x180009455  xor     edx, edx; lpName
0x180009457  xor     ecx, ecx; lpEventAttributes
0x180009459  call    cs:__imp_CreateEventExW
0x18000945f  mov     rbx, rax
0x180009462  test    rax, rax
0x180009465  jz      short loc_18000947C
0x180009467  call    cs:__imp_GetLastError
0x18000946d  mov     rdx, rbx
0x180009470  mov     rcx, rdi
0x180009473  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009478  xor     eax, eax
0x18000947a  jmp     short loc_180009481
0x18000947c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009481  mov     rbx, [rsp+28h+arg_0]
0x180009486  add     rsp, 20h
0x18000948a  pop     rdi
0x18000948b  retn
```
