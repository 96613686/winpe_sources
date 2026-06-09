# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180019ec8`
- end: `0x180019f16`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `78`
- prototype: `__int64 __fastcall(int, int, int, int, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800953d0`

## callees

- `0x1800092a8`
- `0x18000b014`
- `0x180019ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019ee3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180019ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef1`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        LPSECURITY_ATTRIBUTES lpMutexAttributes)
{
  wil::details *v6; // rcx
  HANDLE Mutex; // rbx

  Mutex = CreateMutexExW(lpMutexAttributes, a2, 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Mutex);
  return 0;
}

```

## disassembly

```asm
0x180019ec8  mov     [rsp+arg_0], rbx
0x180019ecd  push    rdi
0x180019ece  sub     rsp, 20h
0x180019ed2  mov     rdi, rcx
0x180019ed5  mov     r9d, 1F0001h; dwDesiredAccess
0x180019edb  mov     rcx, [rsp+28h+lpMutexAttributes]; lpMutexAttributes
0x180019ee0  xor     r8d, r8d; dwFlags
0x180019ee3  call    cs:__imp_CreateMutexExW
0x180019ee9  mov     rbx, rax
0x180019eec  test    rax, rax
0x180019eef  jz      short loc_180019F06
0x180019ef1  call    cs:__imp_GetLastError
0x180019ef7  mov     rdx, rbx
0x180019efa  mov     rcx, rdi
0x180019efd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019f02  xor     eax, eax
0x180019f04  jmp     short loc_180019F0B
0x180019f06  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019f0b  mov     rbx, [rsp+28h+arg_0]
0x180019f10  add     rsp, 20h
0x180019f14  pop     rdi
0x180019f15  retn
```
