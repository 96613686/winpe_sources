# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180057f4c`
- end: `0x180057fab`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: `signed int __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005344c`

## callees

- `0x180049590`
- `0x180057f4c`
- `0x1800582c8`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180057f6b`
- `KERNEL32!CreateSemaphoreExW` at `0x180057f6b`
- `KERNEL32!GetLastError` at `0x180057f7f`
- `KERNEL32!GetLastError` at `0x180057f7f`

## pseudocode

```c
signed int __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::details **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  __int64 v5; // rdx
  wil::details *v6; // rcx
  wil::details *Semaphore; // rbx
  __int64 v8; // r8
  const char *v9; // r9

  Semaphore = (wil::details *)CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v6, v5, v8, v9);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x180057f4c  mov     [rsp+arg_0], rbx
0x180057f51  push    rdi
0x180057f52  sub     rsp, 30h
0x180057f56  mov     rdi, rcx
0x180057f59  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180057f61  xor     ecx, ecx; lpSemaphoreAttributes
0x180057f63  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180057f6b  call    cs:__imp_CreateSemaphoreExW
0x180057f72  nop     dword ptr [rax+rax+00h]
0x180057f77  mov     rbx, rax
0x180057f7a  test    rax, rax
0x180057f7d  jz      short loc_180057F9A
0x180057f7f  call    cs:__imp_GetLastError
0x180057f86  nop     dword ptr [rax+rax+00h]
0x180057f8b  mov     rdx, rbx
0x180057f8e  mov     rcx, rdi
0x180057f91  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180057f96  xor     eax, eax
0x180057f98  jmp     short loc_180057F9F
0x180057f9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180057f9f  mov     rbx, [rsp+38h+arg_0]
0x180057fa4  add     rsp, 30h
0x180057fa8  pop     rdi
0x180057fa9  retn
```
