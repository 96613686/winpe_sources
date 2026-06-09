# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180011048`
- end: `0x18001109a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a3ac`

## callees

- `0x18000b514`
- `0x180011048`
- `0x180011280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011075`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011067`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011067`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180011048  mov     [rsp+arg_0], rbx
0x18001104d  push    rdi
0x18001104e  sub     rsp, 30h
0x180011052  mov     rdi, rcx
0x180011055  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001105d  xor     ecx, ecx; lpSemaphoreAttributes
0x18001105f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180011067  call    cs:__imp_CreateSemaphoreExW
0x18001106d  mov     rbx, rax
0x180011070  test    rax, rax
0x180011073  jz      short loc_18001108A
0x180011075  call    cs:__imp_GetLastError
0x18001107b  mov     rdx, rbx
0x18001107e  mov     rcx, rdi
0x180011081  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180011086  xor     eax, eax
0x180011088  jmp     short loc_18001108F
0x18001108a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001108f  mov     rbx, [rsp+38h+arg_0]
0x180011094  add     rsp, 30h
0x180011098  pop     rdi
0x180011099  retn
```
