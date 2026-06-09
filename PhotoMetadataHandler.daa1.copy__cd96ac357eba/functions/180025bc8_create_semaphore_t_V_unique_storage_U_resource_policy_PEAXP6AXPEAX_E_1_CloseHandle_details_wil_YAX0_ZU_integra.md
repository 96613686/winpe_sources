# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180025bc8`
- end: `0x180025c19`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022e3c`

## callees

- `0x180015374`
- `0x180016c26`
- `0x180025bc8`
- `0x180025d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180025be7`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180025be7`

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
  GetLastError_0();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x180025bc8  mov     [rsp+arg_0], rbx
0x180025bcd  push    rdi
0x180025bce  sub     rsp, 30h
0x180025bd2  mov     rdi, rcx
0x180025bd5  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180025bdd  xor     ecx, ecx; lpSemaphoreAttributes
0x180025bdf  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180025be7  call    cs:__imp_CreateSemaphoreExW
0x180025bed  mov     rbx, rax
0x180025bf0  test    rax, rax
0x180025bf3  jz      short loc_180025C09
0x180025bf5  call    GetLastError_0
0x180025bfa  mov     rdx, rbx
0x180025bfd  mov     rcx, rdi
0x180025c00  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180025c05  xor     eax, eax
0x180025c07  jmp     short loc_180025C0E
0x180025c09  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025c0e  mov     rbx, [rsp+38h+arg_0]
0x180025c13  add     rsp, 30h
0x180025c17  pop     rdi
0x180025c18  retn
```
