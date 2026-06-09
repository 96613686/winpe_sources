# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140005e48`
- end: `0x140005e9a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003fbc`

## callees

- `0x1400046a8`
- `0x140005e48`
- `0x140005ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005e67`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e75`

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
0x140005e48  mov     [rsp+arg_0], rbx
0x140005e4d  push    rdi
0x140005e4e  sub     rsp, 30h
0x140005e52  mov     rdi, rcx
0x140005e55  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140005e5d  xor     ecx, ecx; lpSemaphoreAttributes
0x140005e5f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x140005e67  call    cs:__imp_CreateSemaphoreExW
0x140005e6d  mov     rbx, rax
0x140005e70  test    rax, rax
0x140005e73  jz      short loc_140005E8A
0x140005e75  call    cs:__imp_GetLastError
0x140005e7b  mov     rdx, rbx
0x140005e7e  mov     rcx, rdi
0x140005e81  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140005e86  xor     eax, eax
0x140005e88  jmp     short loc_140005E8F
0x140005e8a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005e8f  mov     rbx, [rsp+38h+arg_0]
0x140005e94  add     rsp, 30h
0x140005e98  pop     rdi
0x140005e99  retn
```
