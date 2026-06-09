# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000fd50`
- end: `0x18000fda2`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a938`

## callees

- `0x18000b418`
- `0x18000fd50`
- `0x18000ffe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000fd6f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000fd6f`

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
0x18000fd50  mov     [rsp+arg_0], rbx
0x18000fd55  push    rdi
0x18000fd56  sub     rsp, 30h
0x18000fd5a  mov     rdi, rcx
0x18000fd5d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000fd65  xor     ecx, ecx; lpSemaphoreAttributes
0x18000fd67  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000fd6f  call    cs:__imp_CreateSemaphoreExW
0x18000fd75  mov     rbx, rax
0x18000fd78  test    rax, rax
0x18000fd7b  jz      short loc_18000FD92
0x18000fd7d  call    cs:__imp_GetLastError
0x18000fd83  mov     rdx, rbx
0x18000fd86  mov     rcx, rdi
0x18000fd89  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000fd8e  xor     eax, eax
0x18000fd90  jmp     short loc_18000FD97
0x18000fd92  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000fd97  mov     rbx, [rsp+38h+arg_0]
0x18000fd9c  add     rsp, 30h
0x18000fda0  pop     rdi
0x18000fda1  retn
```
