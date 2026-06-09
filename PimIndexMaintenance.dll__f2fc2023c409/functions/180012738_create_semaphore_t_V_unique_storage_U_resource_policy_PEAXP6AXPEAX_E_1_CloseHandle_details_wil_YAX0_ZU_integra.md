# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012738`
- end: `0x18001278a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed04`

## callees

- `0x18000f8b0`
- `0x180012738`
- `0x180012850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012757`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180012757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012765`

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
0x180012738  mov     [rsp+arg_0], rbx
0x18001273d  push    rdi
0x18001273e  sub     rsp, 30h
0x180012742  mov     rdi, rcx
0x180012745  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001274d  xor     ecx, ecx; lpSemaphoreAttributes
0x18001274f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180012757  call    cs:__imp_CreateSemaphoreExW
0x18001275d  mov     rbx, rax
0x180012760  test    rax, rax
0x180012763  jz      short loc_18001277A
0x180012765  call    cs:__imp_GetLastError
0x18001276b  mov     rdx, rbx
0x18001276e  mov     rcx, rdi
0x180012771  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012776  xor     eax, eax
0x180012778  jmp     short loc_18001277F
0x18001277a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001277f  mov     rbx, [rsp+38h+arg_0]
0x180012784  add     rsp, 30h
0x180012788  pop     rdi
0x180012789  retn
```
