# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001c3ac`
- end: `0x18001c3fc`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `54`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c404`
- `0x180024e08`
- `0x18003173c`
- `0x1800342dc`
- `0x180039160`
- `0x18004afd8`
- `0x18005078c`
- `0x18005824c`
- `0x18005c558`
- `0x18006ea28`
- `0x1800767c8`
- `0x18007b404`
- `0x180094c10`
- `0x18009a27c`
- `0x1800a204c`
- `0x1800a223c`
- `0x1800a2410`
- `0x1800a2620`
- `0x1800a2830`
- `0x1800a2a20`
- `0x1800a2c10`
- `0x1800a2e00`
- `0x1800a2ff0`
- `0x1800a31e0`
- `0x1800a33d0`
- `0x1800a35c0`
- `0x1800a37b0`
- `0x1800a394c`
- `0x1800a3ae8`
- `0x1800a3c84`
- `0x1800a3e20`
- `0x1800a3fbc`
- `0x1800a4158`
- `0x1800a42f4`
- `0x1800a44e4`
- `0x1800a46d4`
- `0x1800a48c4`
- `0x1800a4abc`
- `0x1800a4cb4`
- `0x1800a4eac`
- `0x1800a50b4`
- `0x1800a52c4`
- `0x1800a54cc`
- `0x1800a56c8`
- `0x1800a58b8`
- `0x1800a5aa8`
- `0x1800a5c98`
- `0x1800a5e34`
- `0x1800a5fd0`
- `0x1800a616c`

## callees

- `0x18000b418`
- `0x18000ffe0`
- `0x18001c3ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d7`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c3c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001c3c9`

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
0x18001c3ac  mov     [rsp+arg_0], rbx
0x18001c3b1  push    rdi
0x18001c3b2  sub     rsp, 20h
0x18001c3b6  and     edx, 3
0x18001c3b9  mov     rdi, rcx
0x18001c3bc  mov     r8d, edx; dwFlags
0x18001c3bf  mov     r9d, 1F0003h; dwDesiredAccess
0x18001c3c5  xor     edx, edx; lpName
0x18001c3c7  xor     ecx, ecx; lpEventAttributes
0x18001c3c9  call    cs:__imp_CreateEventExW
0x18001c3cf  mov     rbx, rax
0x18001c3d2  test    rax, rax
0x18001c3d5  jz      short loc_18001C3EC
0x18001c3d7  call    cs:__imp_GetLastError
0x18001c3dd  mov     rdx, rbx
0x18001c3e0  mov     rcx, rdi
0x18001c3e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001c3e8  xor     eax, eax
0x18001c3ea  jmp     short loc_18001C3F1
0x18001c3ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c3f1  mov     rbx, [rsp+28h+arg_0]
0x18001c3f6  add     rsp, 20h
0x18001c3fa  pop     rdi
0x18001c3fb  retn
```
