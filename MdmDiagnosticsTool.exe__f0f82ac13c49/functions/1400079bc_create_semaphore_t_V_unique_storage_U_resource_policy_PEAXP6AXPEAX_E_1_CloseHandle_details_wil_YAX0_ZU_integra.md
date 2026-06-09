# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1400079bc`
- end: `0x140007a0e`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400039ac`

## callees

- `0x140004598`
- `0x1400079bc`
- `0x140007eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400079db`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1400079db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400079e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400079e9`

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
0x1400079bc  mov     [rsp+arg_0], rbx
0x1400079c1  push    rdi
0x1400079c2  sub     rsp, 30h
0x1400079c6  mov     rdi, rcx
0x1400079c9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400079d1  xor     ecx, ecx; lpSemaphoreAttributes
0x1400079d3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1400079db  call    cs:__imp_CreateSemaphoreExW
0x1400079e1  mov     rbx, rax
0x1400079e4  test    rax, rax
0x1400079e7  jz      short loc_1400079FE
0x1400079e9  call    cs:__imp_GetLastError
0x1400079ef  mov     rdx, rbx
0x1400079f2  mov     rcx, rdi
0x1400079f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400079fa  xor     eax, eax
0x1400079fc  jmp     short loc_140007A03
0x1400079fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007a03  mov     rbx, [rsp+38h+arg_0]
0x140007a08  add     rsp, 30h
0x140007a0c  pop     rdi
0x140007a0d  retn
```
