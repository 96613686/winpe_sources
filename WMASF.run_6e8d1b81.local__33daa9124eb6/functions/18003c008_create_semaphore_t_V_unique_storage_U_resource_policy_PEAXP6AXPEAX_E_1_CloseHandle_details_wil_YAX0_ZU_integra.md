# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18003c008`
- end: `0x18003c05a`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003475c`

## callees

- `0x1800379ec`
- `0x18003c008`
- `0x18003c1dc`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x18003c027`
- `KERNEL32!CreateSemaphoreExW` at `0x18003c027`
- `KERNEL32!GetLastError` at `0x18003c035`
- `KERNEL32!GetLastError` at `0x18003c035`

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
0x18003c008  mov     [rsp+arg_0], rbx
0x18003c00d  push    rdi
0x18003c00e  sub     rsp, 30h
0x18003c012  mov     rdi, rcx
0x18003c015  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18003c01d  xor     ecx, ecx; lpSemaphoreAttributes
0x18003c01f  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18003c027  call    cs:__imp_CreateSemaphoreExW
0x18003c02d  mov     rbx, rax
0x18003c030  test    rax, rax
0x18003c033  jz      short loc_18003C04A
0x18003c035  call    cs:__imp_GetLastError
0x18003c03b  mov     rdx, rbx
0x18003c03e  mov     rcx, rdi
0x18003c041  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003c046  xor     eax, eax
0x18003c048  jmp     short loc_18003C04F
0x18003c04a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003c04f  mov     rbx, [rsp+38h+arg_0]
0x18003c054  add     rsp, 30h
0x18003c058  pop     rdi
0x18003c059  retn
```
