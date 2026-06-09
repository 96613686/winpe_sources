# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001de88`
- end: `0x18001ded8`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `80`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fa98`
- `0x18000fbc0`
- `0x18000fce8`
- `0x180023538`
- `0x180024fe0`

## callees

- `0x180009638`
- `0x18000e838`
- `0x18001de88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dea5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deb3`

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
0x18001de88  mov     [rsp+arg_0], rbx
0x18001de8d  push    rdi
0x18001de8e  sub     rsp, 20h
0x18001de92  and     edx, 3
0x18001de95  mov     rdi, rcx
0x18001de98  mov     r8d, edx; dwFlags
0x18001de9b  mov     r9d, 1F0003h; dwDesiredAccess
0x18001dea1  xor     edx, edx; lpName
0x18001dea3  xor     ecx, ecx; lpEventAttributes
0x18001dea5  call    cs:__imp_CreateEventExW
0x18001deab  mov     rbx, rax
0x18001deae  test    rax, rax
0x18001deb1  jz      short loc_18001DEC8
0x18001deb3  call    cs:__imp_GetLastError
0x18001deb9  mov     rdx, rbx
0x18001debc  mov     rcx, rdi
0x18001debf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001dec4  xor     eax, eax
0x18001dec6  jmp     short loc_18001DECD
0x18001dec8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001decd  mov     rbx, [rsp+28h+arg_0]
0x18001ded2  add     rsp, 20h
0x18001ded6  pop     rdi
0x18001ded7  retn
```
