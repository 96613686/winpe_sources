# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180017d98`
- end: `0x180017df2`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000dda8`
- `0x18000dedc`
- `0x180021bb4`

## callees

- `0x180006ef0`
- `0x18000b090`
- `0x180017d98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017db2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dc6`

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
0x180017d98  mov     [rsp+arg_0], rbx
0x180017d9d  push    rdi
0x180017d9e  sub     rsp, 20h
0x180017da2  mov     rdi, rcx
0x180017da5  mov     r9d, 1F0003h; dwDesiredAccess
0x180017dab  xor     ecx, ecx; lpEventAttributes
0x180017dad  xor     r8d, r8d; dwFlags
0x180017db0  xor     edx, edx; lpName
0x180017db2  call    cs:__imp_CreateEventExW
0x180017db9  nop     dword ptr [rax+rax+00h]
0x180017dbe  mov     rbx, rax
0x180017dc1  test    rax, rax
0x180017dc4  jz      short loc_180017DE1
0x180017dc6  call    cs:__imp_GetLastError
0x180017dcd  nop     dword ptr [rax+rax+00h]
0x180017dd2  mov     rdx, rbx
0x180017dd5  mov     rcx, rdi
0x180017dd8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017ddd  xor     eax, eax
0x180017ddf  jmp     short loc_180017DE6
0x180017de1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017de6  mov     rbx, [rsp+28h+arg_0]
0x180017deb  add     rsp, 20h
0x180017def  pop     rdi
0x180017df0  retn
```
