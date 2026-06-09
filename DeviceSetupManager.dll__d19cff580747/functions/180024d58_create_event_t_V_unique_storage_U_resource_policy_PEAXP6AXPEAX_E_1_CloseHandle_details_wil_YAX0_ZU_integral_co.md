# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180024d58`
- end: `0x180024da8`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fa98`
- `0x180024814`

## callees

- `0x18001065c`
- `0x180010e84`
- `0x180024d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024d75`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d83`

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
0x180024d58  mov     [rsp+arg_0], rbx
0x180024d5d  push    rdi
0x180024d5e  sub     rsp, 20h
0x180024d62  and     edx, 3
0x180024d65  mov     rdi, rcx
0x180024d68  mov     r8d, edx; dwFlags
0x180024d6b  mov     r9d, 1F0003h; dwDesiredAccess
0x180024d71  xor     edx, edx; lpName
0x180024d73  xor     ecx, ecx; lpEventAttributes
0x180024d75  call    cs:__imp_CreateEventExW
0x180024d7b  mov     rbx, rax
0x180024d7e  test    rax, rax
0x180024d81  jz      short loc_180024D98
0x180024d83  call    cs:__imp_GetLastError
0x180024d89  mov     rdx, rbx
0x180024d8c  mov     rcx, rdi
0x180024d8f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180024d94  xor     eax, eax
0x180024d96  jmp     short loc_180024D9D
0x180024d98  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180024d9d  mov     rbx, [rsp+28h+arg_0]
0x180024da2  add     rsp, 20h
0x180024da6  pop     rdi
0x180024da7  retn
```
