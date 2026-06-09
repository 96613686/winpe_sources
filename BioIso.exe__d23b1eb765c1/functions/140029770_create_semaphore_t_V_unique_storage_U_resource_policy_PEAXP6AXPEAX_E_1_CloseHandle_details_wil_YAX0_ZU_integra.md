# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140029770`
- end: `0x1400297cf`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025f84`

## callees

- `0x140018ef8`
- `0x140029770`
- `0x14002986c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14002978f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14002978f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400297a3`

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
0x140029770  mov     [rsp+arg_0], rbx
0x140029775  push    rdi
0x140029776  sub     rsp, 30h
0x14002977a  mov     rdi, rcx
0x14002977d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140029785  xor     ecx, ecx; lpSemaphoreAttributes
0x140029787  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14002978f  call    cs:__imp_CreateSemaphoreExW
0x140029796  nop     dword ptr [rax+rax+00h]
0x14002979b  mov     rbx, rax
0x14002979e  test    rax, rax
0x1400297a1  jz      short loc_1400297BE
0x1400297a3  call    cs:__imp_GetLastError
0x1400297aa  nop     dword ptr [rax+rax+00h]
0x1400297af  mov     rdx, rbx
0x1400297b2  mov     rcx, rdi
0x1400297b5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400297ba  xor     eax, eax
0x1400297bc  jmp     short loc_1400297C3
0x1400297be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400297c3  mov     rbx, [rsp+38h+arg_0]
0x1400297c8  add     rsp, 30h
0x1400297cc  pop     rdi
0x1400297cd  retn
```
