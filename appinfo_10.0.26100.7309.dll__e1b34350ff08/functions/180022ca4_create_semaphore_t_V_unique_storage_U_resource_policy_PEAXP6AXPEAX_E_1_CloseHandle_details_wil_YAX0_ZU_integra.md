# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180022ca4`
- end: `0x180022d0c`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eb70`

## callees

- `0x1800186c0`
- `0x18001b1f0`
- `0x180022ca4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022cc5`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180022cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022cd9`

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
0x180022ca4  mov     rax, rsp
0x180022ca7  mov     [rax+8], rbx
0x180022cab  mov     [rax+10h], rsi
0x180022caf  push    rdi
0x180022cb0  sub     rsp, 30h
0x180022cb4  mov     rsi, rcx
0x180022cb7  mov     dword ptr [rax-10h], 1F0003h
0x180022cbe  xor     ebx, ebx
0x180022cc0  xor     ecx, ecx; lpSemaphoreAttributes
0x180022cc2  mov     [rax-18h], ebx
0x180022cc5  call    cs:__imp_CreateSemaphoreExW
0x180022ccc  nop     dword ptr [rax+rax+00h]
0x180022cd1  mov     rdi, rax
0x180022cd4  test    rax, rax
0x180022cd7  jz      short loc_180022CF2
0x180022cd9  call    cs:__imp_GetLastError
0x180022ce0  nop     dword ptr [rax+rax+00h]
0x180022ce5  mov     rdx, rdi
0x180022ce8  mov     rcx, rsi
0x180022ceb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180022cf0  jmp     short loc_180022CF9
0x180022cf2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180022cf7  mov     ebx, eax
0x180022cf9  mov     rsi, [rsp+38h+arg_8]
0x180022cfe  mov     eax, ebx
0x180022d00  mov     rbx, [rsp+38h+arg_0]
0x180022d05  add     rsp, 30h
0x180022d09  pop     rdi
0x180022d0a  retn
```
