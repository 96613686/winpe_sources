# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800325d0`
- end: `0x180032624`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ee78`
- `0x180039fa0`
- `0x18004860c`

## callees

- `0x180008408`
- `0x18000c68c`
- `0x1800325d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800325f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800325f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800325ff`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  wil::details *v4; // rcx
  HANDLE Event; // rbx

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return 0;
}

```

## disassembly

```asm
0x1800325d0  mov     [rsp+arg_0], rbx
0x1800325d5  push    rdi
0x1800325d6  sub     rsp, 20h
0x1800325da  and     edx, 3
0x1800325dd  mov     rax, r8
0x1800325e0  mov     r8d, edx; dwFlags
0x1800325e3  mov     rdi, rcx
0x1800325e6  mov     rdx, rax; lpName
0x1800325e9  mov     r9d, 1F0003h; dwDesiredAccess
0x1800325ef  xor     ecx, ecx; lpEventAttributes
0x1800325f1  call    cs:__imp_CreateEventExW
0x1800325f7  mov     rbx, rax
0x1800325fa  test    rax, rax
0x1800325fd  jz      short loc_180032614
0x1800325ff  call    cs:__imp_GetLastError
0x180032605  mov     rdx, rbx
0x180032608  mov     rcx, rdi
0x18003260b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180032610  xor     eax, eax
0x180032612  jmp     short loc_180032619
0x180032614  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032619  mov     rbx, [rsp+28h+arg_0]
0x18003261e  add     rsp, 20h
0x180032622  pop     rdi
0x180032623  retn
```
