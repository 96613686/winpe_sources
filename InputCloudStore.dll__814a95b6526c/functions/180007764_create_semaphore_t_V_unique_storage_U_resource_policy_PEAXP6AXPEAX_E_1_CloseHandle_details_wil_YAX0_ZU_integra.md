# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180007764`
- end: `0x1800077b6`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052e0`

## callees

- `0x1800059f8`
- `0x180007764`
- `0x1800077bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007783`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180007783`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007791`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x180007764  mov     [rsp+arg_0], rbx
0x180007769  push    rdi
0x18000776a  sub     rsp, 30h
0x18000776e  mov     rdi, rcx
0x180007771  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180007779  xor     ecx, ecx; lpSemaphoreAttributes
0x18000777b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180007783  call    cs:__imp_CreateSemaphoreExW
0x180007789  mov     rbx, rax
0x18000778c  test    rax, rax
0x18000778f  jz      short loc_1800077A6
0x180007791  call    cs:__imp_GetLastError
0x180007797  mov     rdx, rbx
0x18000779a  mov     rcx, rdi
0x18000779d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800077a2  xor     eax, eax
0x1800077a4  jmp     short loc_1800077AB
0x1800077a6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800077ab  mov     rbx, [rsp+38h+arg_0]
0x1800077b0  add     rsp, 30h
0x1800077b4  pop     rdi
0x1800077b5  retn
```
