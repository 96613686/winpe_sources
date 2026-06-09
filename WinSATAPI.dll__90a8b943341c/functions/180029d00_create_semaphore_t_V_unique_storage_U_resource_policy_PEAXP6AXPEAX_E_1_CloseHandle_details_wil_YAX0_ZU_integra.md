# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180029d00`
- end: `0x180029d68`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002409c`

## callees

- `0x180024f50`
- `0x180029d00`
- `0x18002b26c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d35`
- `KERNEL32!CreateSemaphoreExW` at `0x180029d21`
- `KERNEL32!CreateSemaphoreExW` at `0x180029d21`

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
0x180029d00  mov     rax, rsp
0x180029d03  mov     [rax+8], rbx
0x180029d07  mov     [rax+10h], rsi
0x180029d0b  push    rdi
0x180029d0c  sub     rsp, 30h
0x180029d10  mov     rsi, rcx
0x180029d13  mov     dword ptr [rax-10h], 1F0003h
0x180029d1a  xor     ebx, ebx
0x180029d1c  xor     ecx, ecx; lpSemaphoreAttributes
0x180029d1e  mov     [rax-18h], ebx
0x180029d21  call    cs:__imp_CreateSemaphoreExW
0x180029d28  nop     dword ptr [rax+rax+00h]
0x180029d2d  mov     rdi, rax
0x180029d30  test    rax, rax
0x180029d33  jz      short loc_180029D4E
0x180029d35  call    cs:__imp_GetLastError
0x180029d3c  nop     dword ptr [rax+rax+00h]
0x180029d41  mov     rdx, rdi
0x180029d44  mov     rcx, rsi
0x180029d47  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180029d4c  jmp     short loc_180029D55
0x180029d4e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180029d53  mov     ebx, eax
0x180029d55  mov     rsi, [rsp+38h+arg_8]
0x180029d5a  mov     eax, ebx
0x180029d5c  mov     rbx, [rsp+38h+arg_0]
0x180029d61  add     rsp, 30h
0x180029d65  pop     rdi
0x180029d66  retn
```
