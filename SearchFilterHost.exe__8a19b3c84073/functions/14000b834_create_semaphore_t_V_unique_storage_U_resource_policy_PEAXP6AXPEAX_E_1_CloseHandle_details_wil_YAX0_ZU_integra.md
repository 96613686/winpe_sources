# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000b834`
- end: `0x14000b886`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400070b0`

## callees

- `0x140007bb0`
- `0x14000b834`
- `0x14000bc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000b853`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000b853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b861`

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
0x14000b834  mov     [rsp+arg_0], rbx
0x14000b839  push    rdi
0x14000b83a  sub     rsp, 30h
0x14000b83e  mov     rdi, rcx
0x14000b841  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000b849  xor     ecx, ecx; lpSemaphoreAttributes
0x14000b84b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000b853  call    cs:__imp_CreateSemaphoreExW
0x14000b859  mov     rbx, rax
0x14000b85c  test    rax, rax
0x14000b85f  jz      short loc_14000B876
0x14000b861  call    cs:__imp_GetLastError
0x14000b867  mov     rdx, rbx
0x14000b86a  mov     rcx, rdi
0x14000b86d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000b872  xor     eax, eax
0x14000b874  jmp     short loc_14000B87B
0x14000b876  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000b87b  mov     rbx, [rsp+38h+arg_0]
0x14000b880  add     rsp, 30h
0x14000b884  pop     rdi
0x14000b885  retn
```
