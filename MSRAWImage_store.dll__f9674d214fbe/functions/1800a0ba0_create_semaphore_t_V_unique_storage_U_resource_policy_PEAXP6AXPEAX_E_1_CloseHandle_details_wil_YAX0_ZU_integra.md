# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800a0ba0`
- end: `0x1800a0c08`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f384`

## callees

- `0x18009f710`
- `0x1800a0ba0`
- `0x1800a0c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800a0bc1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800a0bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0bd5`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // rdi

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1,
      Semaphore);
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x1800a0ba0  mov     rax, rsp
0x1800a0ba3  mov     [rax+8], rbx
0x1800a0ba7  mov     [rax+10h], rsi
0x1800a0bab  push    rdi
0x1800a0bac  sub     rsp, 30h
0x1800a0bb0  mov     rsi, rcx
0x1800a0bb3  mov     dword ptr [rax-10h], 1F0003h
0x1800a0bba  xor     ebx, ebx
0x1800a0bbc  xor     ecx, ecx; lpSemaphoreAttributes
0x1800a0bbe  mov     [rax-18h], ebx
0x1800a0bc1  call    cs:__imp_CreateSemaphoreExW
0x1800a0bc8  nop     dword ptr [rax+rax+00h]
0x1800a0bcd  mov     rdi, rax
0x1800a0bd0  test    rax, rax
0x1800a0bd3  jz      short loc_1800A0BEE
0x1800a0bd5  call    cs:__imp_GetLastError
0x1800a0bdc  nop     dword ptr [rax+rax+00h]
0x1800a0be1  mov     rdx, rdi
0x1800a0be4  mov     rcx, rsi
0x1800a0be7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800a0bec  jmp     short loc_1800A0BF5
0x1800a0bee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a0bf3  mov     ebx, eax
0x1800a0bf5  mov     rsi, [rsp+38h+arg_8]
0x1800a0bfa  mov     eax, ebx
0x1800a0bfc  mov     rbx, [rsp+38h+arg_0]
0x1800a0c01  add     rsp, 30h
0x1800a0c05  pop     rdi
0x1800a0c06  retn
```
