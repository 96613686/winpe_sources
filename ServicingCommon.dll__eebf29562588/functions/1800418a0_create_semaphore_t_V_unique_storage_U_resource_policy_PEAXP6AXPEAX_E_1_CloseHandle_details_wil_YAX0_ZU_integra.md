# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800418a0`
- end: `0x1800418ff`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040974`

## callees

- `0x18001e3c8`
- `0x1800418a0`
- `0x180041908`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800418d3`
- `KERNEL32!GetLastError` at `0x1800418d3`
- `KERNEL32!CreateSemaphoreExW` at `0x1800418bf`
- `KERNEL32!CreateSemaphoreExW` at `0x1800418bf`

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
0x1800418a0  mov     [rsp+arg_0], rbx
0x1800418a5  push    rdi
0x1800418a6  sub     rsp, 30h
0x1800418aa  mov     rdi, rcx
0x1800418ad  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800418b5  xor     ecx, ecx; lpSemaphoreAttributes
0x1800418b7  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800418bf  call    cs:__imp_CreateSemaphoreExW
0x1800418c6  nop     dword ptr [rax+rax+00h]
0x1800418cb  mov     rbx, rax
0x1800418ce  test    rax, rax
0x1800418d1  jz      short loc_1800418EE
0x1800418d3  call    cs:__imp_GetLastError
0x1800418da  nop     dword ptr [rax+rax+00h]
0x1800418df  mov     rdx, rbx
0x1800418e2  mov     rcx, rdi
0x1800418e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800418ea  xor     eax, eax
0x1800418ec  jmp     short loc_1800418F3
0x1800418ee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800418f3  mov     rbx, [rsp+38h+arg_0]
0x1800418f8  add     rsp, 30h
0x1800418fc  pop     rdi
0x1800418fd  retn
```
