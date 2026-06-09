# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18009589c`
- end: `0x1800958ec`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080184`
- `0x1800802b8`
- `0x1800803ec`
- `0x18009f6dc`
- `0x1800c9604`

## callees

- `0x180016140`
- `0x180020028`
- `0x18009589c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800958b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800958b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800958c7`

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
0x18009589c  mov     [rsp+arg_0], rbx
0x1800958a1  push    rdi
0x1800958a2  sub     rsp, 20h
0x1800958a6  and     edx, 3
0x1800958a9  mov     rdi, rcx
0x1800958ac  mov     r8d, edx; dwFlags
0x1800958af  mov     r9d, 1F0003h; dwDesiredAccess
0x1800958b5  xor     edx, edx; lpName
0x1800958b7  xor     ecx, ecx; lpEventAttributes
0x1800958b9  call    cs:__imp_CreateEventExW
0x1800958bf  mov     rbx, rax
0x1800958c2  test    rax, rax
0x1800958c5  jz      short loc_1800958DC
0x1800958c7  call    cs:__imp_GetLastError
0x1800958cd  mov     rdx, rbx
0x1800958d0  mov     rcx, rdi
0x1800958d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800958d8  xor     eax, eax
0x1800958da  jmp     short loc_1800958E1
0x1800958dc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800958e1  mov     rbx, [rsp+28h+arg_0]
0x1800958e6  add     rsp, 20h
0x1800958ea  pop     rdi
0x1800958eb  retn
```
