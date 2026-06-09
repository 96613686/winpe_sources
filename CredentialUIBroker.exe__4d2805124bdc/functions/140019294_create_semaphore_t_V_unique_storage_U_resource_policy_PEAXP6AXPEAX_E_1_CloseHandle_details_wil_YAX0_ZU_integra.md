# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140019294`
- end: `0x1400192e6`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b0d8`

## callees

- `0x14000d9e8`
- `0x140019294`
- `0x14001af84`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1400192b3`
- `KERNEL32!CreateSemaphoreExW` at `0x1400192b3`
- `KERNEL32!GetLastError` at `0x1400192c1`
- `KERNEL32!GetLastError` at `0x1400192c1`

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
0x140019294  mov     [rsp+arg_0], rbx
0x140019299  push    rdi
0x14001929a  sub     rsp, 30h
0x14001929e  mov     rdi, rcx
0x1400192a1  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1400192a9  xor     ecx, ecx; lpSemaphoreAttributes
0x1400192ab  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1400192b3  call    cs:__imp_CreateSemaphoreExW
0x1400192b9  mov     rbx, rax
0x1400192bc  test    rax, rax
0x1400192bf  jz      short loc_1400192D6
0x1400192c1  call    cs:__imp_GetLastError
0x1400192c7  mov     rdx, rbx
0x1400192ca  mov     rcx, rdi
0x1400192cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400192d2  xor     eax, eax
0x1400192d4  jmp     short loc_1400192DB
0x1400192d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400192db  mov     rbx, [rsp+38h+arg_0]
0x1400192e0  add     rsp, 30h
0x1400192e4  pop     rdi
0x1400192e5  retn
```
