# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002a5d4`
- end: `0x18002a635`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x180023568`
- `0x18002a5d4`
- `0x18003b450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a5f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002a5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a609`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  void *v4; // rdx
  HANDLE Event; // rbx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v6, v7);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x18002a5d4  mov     [rsp+arg_0], rbx
0x18002a5d9  push    rdi
0x18002a5da  sub     rsp, 20h
0x18002a5de  and     edx, 3
0x18002a5e1  mov     rax, r8
0x18002a5e4  mov     r8d, edx; dwFlags
0x18002a5e7  mov     rdi, rcx
0x18002a5ea  mov     rdx, rax; lpName
0x18002a5ed  mov     r9d, 1F0003h; dwDesiredAccess
0x18002a5f3  xor     ecx, ecx; lpEventAttributes
0x18002a5f5  call    cs:__imp_CreateEventExW
0x18002a5fc  nop     dword ptr [rax+rax+00h]
0x18002a601  mov     rbx, rax
0x18002a604  test    rax, rax
0x18002a607  jz      short loc_18002A62A
0x18002a609  call    cs:__imp_GetLastError
0x18002a610  nop     dword ptr [rax+rax+00h]
0x18002a615  mov     rdx, rbx
0x18002a618  mov     rcx, rdi
0x18002a61b  mov     rbx, [rsp+28h+arg_0]
0x18002a620  add     rsp, 20h
0x18002a624  pop     rdi
0x18002a625  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002a62a  mov     rcx, [rsp+28h]; this
0x18002a62f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
