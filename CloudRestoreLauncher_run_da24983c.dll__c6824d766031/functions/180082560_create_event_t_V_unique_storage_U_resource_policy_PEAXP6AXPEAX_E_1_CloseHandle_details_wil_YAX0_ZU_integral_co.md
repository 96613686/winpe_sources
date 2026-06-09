# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180082560`
- end: `0x1800825b4`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800825bc`
- `0x18010fe9c`

## callees

- `0x180010ca8`
- `0x180012f30`
- `0x180082560`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x180082581`
- `KERNEL32!CreateEventExW` at `0x180082581`
- `KERNEL32!GetLastError` at `0x18008258f`
- `KERNEL32!GetLastError` at `0x18008258f`

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
0x180082560  mov     [rsp+arg_0], rbx
0x180082565  push    rdi
0x180082566  sub     rsp, 20h
0x18008256a  and     edx, 3
0x18008256d  mov     rax, r8
0x180082570  mov     r8d, edx; dwFlags
0x180082573  mov     rdi, rcx
0x180082576  mov     rdx, rax; lpName
0x180082579  mov     r9d, 1F0003h; dwDesiredAccess
0x18008257f  xor     ecx, ecx; lpEventAttributes
0x180082581  call    cs:__imp_CreateEventExW
0x180082587  mov     rbx, rax
0x18008258a  test    rax, rax
0x18008258d  jz      short loc_1800825A4
0x18008258f  call    cs:__imp_GetLastError
0x180082595  mov     rdx, rbx
0x180082598  mov     rcx, rdi
0x18008259b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800825a0  xor     eax, eax
0x1800825a2  jmp     short loc_1800825A9
0x1800825a4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800825a9  mov     rbx, [rsp+28h+arg_0]
0x1800825ae  add     rsp, 20h
0x1800825b2  pop     rdi
0x1800825b3  retn
```
