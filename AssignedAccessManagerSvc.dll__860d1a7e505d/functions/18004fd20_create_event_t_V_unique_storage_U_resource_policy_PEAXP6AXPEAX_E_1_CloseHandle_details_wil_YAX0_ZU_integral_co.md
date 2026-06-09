# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18004fd20`
- end: `0x18004fd6d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e5ec`
- `0x18006d250`
- `0x180085dc0`
- `0x180089154`
- `0x180089284`
- `0x18008af78`
- `0x18008b0a8`

## callees

- `0x18000a698`
- `0x18000c398`
- `0x18004fd20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004fd3a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004fd3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fd48`

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
0x18004fd20  mov     [rsp+arg_0], rbx
0x18004fd25  push    rdi
0x18004fd26  sub     rsp, 20h
0x18004fd2a  mov     rdi, rcx
0x18004fd2d  mov     r9d, 1F0003h; dwDesiredAccess
0x18004fd33  xor     ecx, ecx; lpEventAttributes
0x18004fd35  xor     r8d, r8d; dwFlags
0x18004fd38  xor     edx, edx; lpName
0x18004fd3a  call    cs:__imp_CreateEventExW
0x18004fd40  mov     rbx, rax
0x18004fd43  test    rax, rax
0x18004fd46  jz      short loc_18004FD5D
0x18004fd48  call    cs:__imp_GetLastError
0x18004fd4e  mov     rdx, rbx
0x18004fd51  mov     rcx, rdi
0x18004fd54  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004fd59  xor     eax, eax
0x18004fd5b  jmp     short loc_18004FD62
0x18004fd5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004fd62  mov     rbx, [rsp+28h+arg_0]
0x18004fd67  add     rsp, 20h
0x18004fd6b  pop     rdi
0x18004fd6c  retn
```
