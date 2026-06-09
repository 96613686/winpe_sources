# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180029cfc`
- end: `0x180029d4e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800252bc`

## callees

- `0x18001ef6c`
- `0x180029cfc`
- `0x180029d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d29`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180029d1b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180029d1b`

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
0x180029cfc  mov     [rsp+arg_0], rbx
0x180029d01  push    rdi
0x180029d02  sub     rsp, 30h
0x180029d06  mov     rdi, rcx
0x180029d09  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180029d11  xor     ecx, ecx; lpSemaphoreAttributes
0x180029d13  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180029d1b  call    cs:__imp_CreateSemaphoreExW
0x180029d21  mov     rbx, rax
0x180029d24  test    rax, rax
0x180029d27  jz      short loc_180029D3E
0x180029d29  call    cs:__imp_GetLastError
0x180029d2f  mov     rdx, rbx
0x180029d32  mov     rcx, rdi
0x180029d35  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029d3a  xor     eax, eax
0x180029d3c  jmp     short loc_180029D43
0x180029d3e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029d43  mov     rbx, [rsp+38h+arg_0]
0x180029d48  add     rsp, 30h
0x180029d4c  pop     rdi
0x180029d4d  retn
```
