# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140007ac8`
- end: `0x140007b1a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004fe4`

## callees

- `0x1400056c8`
- `0x140007ac8`
- `0x140007b88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007ae7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140007ae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007af5`

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
0x140007ac8  mov     [rsp+arg_0], rbx
0x140007acd  push    rdi
0x140007ace  sub     rsp, 30h
0x140007ad2  mov     rdi, rcx
0x140007ad5  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140007add  xor     ecx, ecx; lpSemaphoreAttributes
0x140007adf  mov     [rsp+38h+dwFlags], 0; dwFlags
0x140007ae7  call    cs:__imp_CreateSemaphoreExW
0x140007aed  mov     rbx, rax
0x140007af0  test    rax, rax
0x140007af3  jz      short loc_140007B0A
0x140007af5  call    cs:__imp_GetLastError
0x140007afb  mov     rdx, rbx
0x140007afe  mov     rcx, rdi
0x140007b01  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140007b06  xor     eax, eax
0x140007b08  jmp     short loc_140007B0F
0x140007b0a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007b0f  mov     rbx, [rsp+38h+arg_0]
0x140007b14  add     rsp, 30h
0x140007b18  pop     rdi
0x140007b19  retn
```
