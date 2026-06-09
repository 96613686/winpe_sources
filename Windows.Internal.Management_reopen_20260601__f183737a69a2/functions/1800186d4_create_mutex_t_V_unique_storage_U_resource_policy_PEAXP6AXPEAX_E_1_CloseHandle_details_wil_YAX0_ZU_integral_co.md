# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800186d4`
- end: `0x18001872f`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `91`
- prototype: `__int64 __fastcall(int, int, int, int, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180097d10`

## callees

- `0x180009510`
- `0x18000b3cc`
- `0x1800186d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800186ef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800186ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018703`

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
0x1800186d4  mov     [rsp+arg_0], rbx
0x1800186d9  push    rdi
0x1800186da  sub     rsp, 20h
0x1800186de  mov     rdi, rcx
0x1800186e1  mov     r9d, 1F0001h; dwDesiredAccess
0x1800186e7  mov     rcx, [rsp+28h+lpMutexAttributes]; lpMutexAttributes
0x1800186ec  xor     r8d, r8d; dwFlags
0x1800186ef  call    cs:__imp_CreateMutexExW
0x1800186f6  nop     dword ptr [rax+rax+00h]
0x1800186fb  mov     rbx, rax
0x1800186fe  test    rax, rax
0x180018701  jz      short loc_18001871E
0x180018703  call    cs:__imp_GetLastError
0x18001870a  nop     dword ptr [rax+rax+00h]
0x18001870f  mov     rdx, rbx
0x180018712  mov     rcx, rdi
0x180018715  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001871a  xor     eax, eax
0x18001871c  jmp     short loc_180018723
0x18001871e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018723  mov     rbx, [rsp+28h+arg_0]
0x180018728  add     rsp, 20h
0x18001872c  pop     rdi
0x18001872d  retn
```
