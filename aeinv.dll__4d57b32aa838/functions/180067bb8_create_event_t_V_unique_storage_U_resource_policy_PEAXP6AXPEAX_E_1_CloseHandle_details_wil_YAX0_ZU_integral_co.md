# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180067bb8`
- end: `0x180067c05`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048468`

## callees

- `0x180040658`
- `0x1800407d8`
- `0x180067bb8`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x180067bd2`
- `KERNEL32!CreateEventExW` at `0x180067bd2`
- `KERNEL32!GetLastError` at `0x180067be0`
- `KERNEL32!GetLastError` at `0x180067be0`

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
0x180067bb8  mov     [rsp+arg_0], rbx
0x180067bbd  push    rdi
0x180067bbe  sub     rsp, 20h
0x180067bc2  mov     rdi, rcx
0x180067bc5  mov     r9d, 1F0003h; dwDesiredAccess
0x180067bcb  xor     ecx, ecx; lpEventAttributes
0x180067bcd  xor     r8d, r8d; dwFlags
0x180067bd0  xor     edx, edx; lpName
0x180067bd2  call    cs:__imp_CreateEventExW
0x180067bd8  mov     rbx, rax
0x180067bdb  test    rax, rax
0x180067bde  jz      short loc_180067BF5
0x180067be0  call    cs:__imp_GetLastError
0x180067be6  mov     rdx, rbx
0x180067be9  mov     rcx, rdi
0x180067bec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180067bf1  xor     eax, eax
0x180067bf3  jmp     short loc_180067BFA
0x180067bf5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180067bfa  mov     rbx, [rsp+28h+arg_0]
0x180067bff  add     rsp, 20h
0x180067c03  pop     rdi
0x180067c04  retn
```
