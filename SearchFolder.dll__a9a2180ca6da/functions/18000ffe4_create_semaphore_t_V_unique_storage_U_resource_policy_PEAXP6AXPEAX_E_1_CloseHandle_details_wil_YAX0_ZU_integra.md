# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000ffe4`
- end: `0x180010036`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009f1c`

## callees

- `0x18000b6b8`
- `0x18000ffe4`
- `0x180010230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180010003`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180010003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010011`

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
0x18000ffe4  mov     [rsp+arg_0], rbx
0x18000ffe9  push    rdi
0x18000ffea  sub     rsp, 30h
0x18000ffee  mov     rdi, rcx
0x18000fff1  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000fff9  xor     ecx, ecx; lpSemaphoreAttributes
0x18000fffb  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180010003  call    cs:__imp_CreateSemaphoreExW
0x180010009  mov     rbx, rax
0x18001000c  test    rax, rax
0x18001000f  jz      short loc_180010026
0x180010011  call    cs:__imp_GetLastError
0x180010017  mov     rdx, rbx
0x18001001a  mov     rcx, rdi
0x18001001d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180010022  xor     eax, eax
0x180010024  jmp     short loc_18001002B
0x180010026  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001002b  mov     rbx, [rsp+38h+arg_0]
0x180010030  add     rsp, 30h
0x180010034  pop     rdi
0x180010035  retn
```
