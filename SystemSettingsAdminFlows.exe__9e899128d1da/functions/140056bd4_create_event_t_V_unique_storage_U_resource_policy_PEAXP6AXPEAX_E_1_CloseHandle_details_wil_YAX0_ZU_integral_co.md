# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140056bd4`
- end: `0x140056c21`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140045bb8`
- `0x140045ce8`

## callees

- `0x1400199b8`
- `0x14002c37c`
- `0x140056bd4`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x140056bee`
- `KERNEL32!CreateEventExW` at `0x140056bee`
- `KERNEL32!GetLastError` at `0x140056bfc`
- `KERNEL32!GetLastError` at `0x140056bfc`

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
0x140056bd4  mov     [rsp+arg_0], rbx
0x140056bd9  push    rdi
0x140056bda  sub     rsp, 20h
0x140056bde  mov     rdi, rcx
0x140056be1  mov     r9d, 1F0003h; dwDesiredAccess
0x140056be7  xor     ecx, ecx; lpEventAttributes
0x140056be9  xor     r8d, r8d; dwFlags
0x140056bec  xor     edx, edx; lpName
0x140056bee  call    cs:__imp_CreateEventExW
0x140056bf4  mov     rbx, rax
0x140056bf7  test    rax, rax
0x140056bfa  jz      short loc_140056C11
0x140056bfc  call    cs:__imp_GetLastError
0x140056c02  mov     rdx, rbx
0x140056c05  mov     rcx, rdi
0x140056c08  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140056c0d  xor     eax, eax
0x140056c0f  jmp     short loc_140056C16
0x140056c11  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140056c16  mov     rbx, [rsp+28h+arg_0]
0x140056c1b  add     rsp, 20h
0x140056c1f  pop     rdi
0x140056c20  retn
```
