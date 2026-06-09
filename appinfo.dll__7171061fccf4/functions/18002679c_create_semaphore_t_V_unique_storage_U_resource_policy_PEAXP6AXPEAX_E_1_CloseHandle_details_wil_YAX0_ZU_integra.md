# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18002679c`
- end: `0x1800267ee`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021ba0`

## callees

- `0x18001a110`
- `0x18001a1ac`
- `0x18002679c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800267bb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800267bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267c9`

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
0x18002679c  mov     [rsp+arg_0], rbx
0x1800267a1  push    rdi
0x1800267a2  sub     rsp, 30h
0x1800267a6  mov     rdi, rcx
0x1800267a9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800267b1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800267b3  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800267bb  call    cs:__imp_CreateSemaphoreExW
0x1800267c1  mov     rbx, rax
0x1800267c4  test    rax, rax
0x1800267c7  jz      short loc_1800267DE
0x1800267c9  call    cs:__imp_GetLastError
0x1800267cf  mov     rdx, rbx
0x1800267d2  mov     rcx, rdi
0x1800267d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800267da  xor     eax, eax
0x1800267dc  jmp     short loc_1800267E3
0x1800267de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800267e3  mov     rbx, [rsp+38h+arg_0]
0x1800267e8  add     rsp, 30h
0x1800267ec  pop     rdi
0x1800267ed  retn
```
