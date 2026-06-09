# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012bf8`
- end: `0x180012c49`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800141ec`
- `0x180015920`
- `0x180019da0`
- `0x180019ec8`
- `0x18001f200`
- `0x18001f410`
- `0x1800480fc`

## callees

- `0x180011a98`
- `0x180012bf8`
- `0x180014054`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180012c15`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180012c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c23`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2)
{
  void *v3; // rdx
  HANDLE Event; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Event);
}

```

## disassembly

```asm
0x180012bf8  mov     [rsp+arg_0], rbx
0x180012bfd  push    rdi
0x180012bfe  sub     rsp, 20h
0x180012c02  and     edx, 3
0x180012c05  mov     rdi, rcx
0x180012c08  mov     r8d, edx; dwFlags
0x180012c0b  mov     r9d, 1F0003h; dwDesiredAccess
0x180012c11  xor     edx, edx; lpName
0x180012c13  xor     ecx, ecx; lpEventAttributes
0x180012c15  call    cs:__imp_CreateEventExW
0x180012c1b  mov     rbx, rax
0x180012c1e  test    rax, rax
0x180012c21  jz      short loc_180012C3E
0x180012c23  call    cs:__imp_GetLastError
0x180012c29  mov     rdx, rbx
0x180012c2c  mov     rcx, rdi
0x180012c2f  mov     rbx, [rsp+28h+arg_0]
0x180012c34  add     rsp, 20h
0x180012c38  pop     rdi
0x180012c39  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012c3e  mov     rcx, [rsp+28h]; this
0x180012c43  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
