# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180009a54`
- end: `0x180009aa6`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005520`

## callees

- `0x180005ff8`
- `0x180009a54`
- `0x180009e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009a73`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a81`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x180009a54  mov     [rsp+arg_0], rbx
0x180009a59  push    rdi
0x180009a5a  sub     rsp, 30h
0x180009a5e  mov     rdi, rcx
0x180009a61  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009a69  xor     ecx, ecx; lpSemaphoreAttributes
0x180009a6b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180009a73  call    cs:__imp_CreateSemaphoreExW
0x180009a79  mov     rbx, rax
0x180009a7c  test    rax, rax
0x180009a7f  jz      short loc_180009A96
0x180009a81  call    cs:__imp_GetLastError
0x180009a87  mov     rdx, rbx
0x180009a8a  mov     rcx, rdi
0x180009a8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009a92  xor     eax, eax
0x180009a94  jmp     short loc_180009A9B
0x180009a96  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009a9b  mov     rbx, [rsp+38h+arg_0]
0x180009aa0  add     rsp, 30h
0x180009aa4  pop     rdi
0x180009aa5  retn
```
