# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18005e96c`
- end: `0x18005e9be`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b348`

## callees

- `0x18005450c`
- `0x18005e96c`
- `0x18005eafc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005e98b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18005e98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e999`

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
0x18005e96c  mov     [rsp+arg_0], rbx
0x18005e971  push    rdi
0x18005e972  sub     rsp, 30h
0x18005e976  mov     rdi, rcx
0x18005e979  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18005e981  xor     ecx, ecx; lpSemaphoreAttributes
0x18005e983  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18005e98b  call    cs:__imp_CreateSemaphoreExW
0x18005e991  mov     rbx, rax
0x18005e994  test    rax, rax
0x18005e997  jz      short loc_18005E9AE
0x18005e999  call    cs:__imp_GetLastError
0x18005e99f  mov     rdx, rbx
0x18005e9a2  mov     rcx, rdi
0x18005e9a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005e9aa  xor     eax, eax
0x18005e9ac  jmp     short loc_18005E9B3
0x18005e9ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005e9b3  mov     rbx, [rsp+38h+arg_0]
0x18005e9b8  add     rsp, 30h
0x18005e9bc  pop     rdi
0x18005e9bd  retn
```
