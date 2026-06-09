# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000d6f0`
- end: `0x14000d73c`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `76`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d884`

## callees

- `0x140007884`
- `0x14000d1e4`
- `0x14000d6f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d708`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000d708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d716`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        const WCHAR *a2)
{
  void *v3; // rdx
  HANDLE Mutex; // rbx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Mutex = CreateMutexExW(0, a2, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  return _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
           a1,
           Mutex);
}

```

## disassembly

```asm
0x14000d6f0  mov     [rsp+arg_0], rbx
0x14000d6f5  push    rdi
0x14000d6f6  sub     rsp, 20h
0x14000d6fa  mov     rdi, rcx
0x14000d6fd  mov     r9d, 1F0001h; dwDesiredAccess
0x14000d703  xor     ecx, ecx; lpMutexAttributes
0x14000d705  xor     r8d, r8d; dwFlags
0x14000d708  call    cs:__imp_CreateMutexExW
0x14000d70e  mov     rbx, rax
0x14000d711  test    rax, rax
0x14000d714  jz      short loc_14000D731
0x14000d716  call    cs:__imp_GetLastError
0x14000d71c  mov     rdx, rbx
0x14000d71f  mov     rcx, rdi
0x14000d722  mov     rbx, [rsp+28h+arg_0]
0x14000d727  add     rsp, 20h
0x14000d72b  pop     rdi
0x14000d72c  jmp     ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000d731  mov     rcx, [rsp+28h]; this
0x14000d736  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
