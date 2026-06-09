# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14002b1ac`
- end: `0x14002b1fe`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001164c`

## callees

- `0x1400199b8`
- `0x14002b1ac`
- `0x14002c37c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002b1d9`
- `KERNEL32!GetLastError` at `0x14002b1d9`
- `KERNEL32!CreateSemaphoreExW` at `0x14002b1cb`
- `KERNEL32!CreateSemaphoreExW` at `0x14002b1cb`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbx

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x14002b1ac  mov     [rsp+arg_0], rbx
0x14002b1b1  push    rdi
0x14002b1b2  sub     rsp, 30h
0x14002b1b6  mov     rdi, rcx
0x14002b1b9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14002b1c1  xor     ecx, ecx; lpSemaphoreAttributes
0x14002b1c3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002b1cb  call    cs:__imp_CreateSemaphoreExW
0x14002b1d1  mov     rbx, rax
0x14002b1d4  test    rax, rax
0x14002b1d7  jz      short loc_14002B1EE
0x14002b1d9  call    cs:__imp_GetLastError
0x14002b1df  mov     rdx, rbx
0x14002b1e2  mov     rcx, rdi
0x14002b1e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14002b1ea  xor     eax, eax
0x14002b1ec  jmp     short loc_14002B1F3
0x14002b1ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14002b1f3  mov     rbx, [rsp+38h+arg_0]
0x14002b1f8  add     rsp, 30h
0x14002b1fc  pop     rdi
0x14002b1fd  retn
```
