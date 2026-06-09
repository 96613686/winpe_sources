# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800399b4`
- end: `0x180039a0e`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `90`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a4f0`
- `0x18001a624`
- `0x18001a758`
- `0x18002556c`
- `0x1800415e8`
- `0x1800976ac`

## callees

- `0x180009510`
- `0x18000b3cc`
- `0x1800399b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800399ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800399ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399e2`

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
0x1800399b4  mov     [rsp+arg_0], rbx
0x1800399b9  push    rdi
0x1800399ba  sub     rsp, 20h
0x1800399be  mov     rdi, rcx
0x1800399c1  mov     r9d, 1F0003h; dwDesiredAccess
0x1800399c7  xor     ecx, ecx; lpEventAttributes
0x1800399c9  xor     r8d, r8d; dwFlags
0x1800399cc  xor     edx, edx; lpName
0x1800399ce  call    cs:__imp_CreateEventExW
0x1800399d5  nop     dword ptr [rax+rax+00h]
0x1800399da  mov     rbx, rax
0x1800399dd  test    rax, rax
0x1800399e0  jz      short loc_1800399FD
0x1800399e2  call    cs:__imp_GetLastError
0x1800399e9  nop     dword ptr [rax+rax+00h]
0x1800399ee  mov     rdx, rbx
0x1800399f1  mov     rcx, rdi
0x1800399f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800399f9  xor     eax, eax
0x1800399fb  jmp     short loc_180039A02
0x1800399fd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180039a02  mov     rbx, [rsp+28h+arg_0]
0x180039a07  add     rsp, 20h
0x180039a0b  pop     rdi
0x180039a0c  retn
```
