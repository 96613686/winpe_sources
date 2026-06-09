# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000fcf4`
- end: `0x18000fd4a`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `86`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c58`
- `0x18007b404`
- `0x18007d56c`
- `0x1800ab000`

## callees

- `0x18000ec7c`
- `0x18000fcf4`
- `0x18000ffe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000fd11`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000fd11`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  HANDLE Event; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x1CC8, v4, v5);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x18000fcf4  mov     [rsp+arg_0], rbx
0x18000fcf9  push    rdi
0x18000fcfa  sub     rsp, 20h
0x18000fcfe  and     edx, 3
0x18000fd01  mov     rdi, rcx
0x18000fd04  mov     r8d, edx; dwFlags
0x18000fd07  mov     r9d, 1F0003h; dwDesiredAccess
0x18000fd0d  xor     edx, edx; lpName
0x18000fd0f  xor     ecx, ecx; lpEventAttributes
0x18000fd11  call    cs:__imp_CreateEventExW
0x18000fd17  mov     rbx, rax
0x18000fd1a  test    rax, rax
0x18000fd1d  jz      short loc_18000FD3A
0x18000fd1f  call    cs:__imp_GetLastError
0x18000fd25  mov     rdx, rbx
0x18000fd28  mov     rcx, rdi
0x18000fd2b  mov     rbx, [rsp+28h+arg_0]
0x18000fd30  add     rsp, 20h
0x18000fd34  pop     rdi
0x18000fd35  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000fd3a  mov     rcx, [rsp+28h]; this
0x18000fd3f  mov     edx, 1CC8h; void *
0x18000fd44  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
