# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180016e28`
- end: `0x180016e80`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800164a4`
- `0x18001a970`

## callees

- `0x18000fe08`
- `0x180014030`
- `0x180016e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016e4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e5b`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  wil::details *v5; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(a4, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x180016e28  mov     [rsp+arg_0], rbx
0x180016e2d  push    rdi
0x180016e2e  sub     rsp, 20h
0x180016e32  and     edx, 3
0x180016e35  mov     r10, r9
0x180016e38  mov     rax, r8
0x180016e3b  mov     rdi, rcx
0x180016e3e  mov     r8d, edx; dwFlags
0x180016e41  mov     r9d, 1F0003h; dwDesiredAccess
0x180016e47  mov     rdx, rax; lpName
0x180016e4a  mov     rcx, r10; lpEventAttributes
0x180016e4d  call    cs:__imp_CreateEventExW
0x180016e53  mov     rbx, rax
0x180016e56  test    rax, rax
0x180016e59  jz      short loc_180016E70
0x180016e5b  call    cs:__imp_GetLastError
0x180016e61  mov     rdx, rbx
0x180016e64  mov     rcx, rdi
0x180016e67  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016e6c  xor     eax, eax
0x180016e6e  jmp     short loc_180016E75
0x180016e70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016e75  mov     rbx, [rsp+28h+arg_0]
0x180016e7a  add     rsp, 20h
0x180016e7e  pop     rdi
0x180016e7f  retn
```
