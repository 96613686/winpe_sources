# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800245b8`
- end: `0x180024620`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e730`

## callees

- `0x180018410`
- `0x18001ae20`
- `0x1800245b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800245d9`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800245d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245ed`

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
0x1800245b8  mov     rax, rsp
0x1800245bb  mov     [rax+8], rbx
0x1800245bf  mov     [rax+10h], rsi
0x1800245c3  push    rdi
0x1800245c4  sub     rsp, 30h
0x1800245c8  mov     rsi, rcx
0x1800245cb  mov     dword ptr [rax-10h], 1F0003h
0x1800245d2  xor     ebx, ebx
0x1800245d4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800245d6  mov     [rax-18h], ebx
0x1800245d9  call    cs:__imp_CreateSemaphoreExW
0x1800245e0  nop     dword ptr [rax+rax+00h]
0x1800245e5  mov     rdi, rax
0x1800245e8  test    rax, rax
0x1800245eb  jz      short loc_180024606
0x1800245ed  call    cs:__imp_GetLastError
0x1800245f4  nop     dword ptr [rax+rax+00h]
0x1800245f9  mov     rdx, rdi
0x1800245fc  mov     rcx, rsi
0x1800245ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180024604  jmp     short loc_18002460D
0x180024606  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002460b  mov     ebx, eax
0x18002460d  mov     rsi, [rsp+38h+arg_8]
0x180024612  mov     eax, ebx
0x180024614  mov     rbx, [rsp+38h+arg_0]
0x180024619  add     rsp, 30h
0x18002461d  pop     rdi
0x18002461e  retn
```
