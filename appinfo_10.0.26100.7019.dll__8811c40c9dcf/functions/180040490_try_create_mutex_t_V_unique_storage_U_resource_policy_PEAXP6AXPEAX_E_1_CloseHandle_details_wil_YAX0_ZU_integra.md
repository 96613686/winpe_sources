# ?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180040490`
- end: `0x1800404e3`
- name: `?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800400fc`

## callees

- `0x18001ae20`
- `0x180040490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800404aa`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800404aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800404be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800404be`

## pseudocode

```c
char __fastcall _try_create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1)
{
  HANDLE Mutex; // rax
  HANDLE v3; // rbx

  Mutex = CreateMutexExW(0, 0, 0, 0x1F0001u);
  v3 = Mutex;
  if ( Mutex )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1,
      v3);
    LOBYTE(Mutex) = 1;
  }
  return (char)Mutex;
}

```

## disassembly

```asm
0x180040490  mov     [rsp+arg_0], rbx
0x180040495  push    rdi
0x180040496  sub     rsp, 20h
0x18004049a  mov     rdi, rcx
0x18004049d  mov     r9d, 1F0001h; dwDesiredAccess
0x1800404a3  xor     ecx, ecx; lpMutexAttributes
0x1800404a5  xor     r8d, r8d; dwFlags
0x1800404a8  xor     edx, edx; lpName
0x1800404aa  call    cs:__imp_CreateMutexExW
0x1800404b1  nop     dword ptr [rax+rax+00h]
0x1800404b6  mov     rbx, rax
0x1800404b9  test    rax, rax
0x1800404bc  jz      short loc_1800404D7
0x1800404be  call    cs:__imp_GetLastError
0x1800404c5  nop     dword ptr [rax+rax+00h]
0x1800404ca  mov     rdx, rbx
0x1800404cd  mov     rcx, rdi
0x1800404d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800404d5  mov     al, 1
0x1800404d7  mov     rbx, [rsp+28h+arg_0]
0x1800404dc  add     rsp, 20h
0x1800404e0  pop     rdi
0x1800404e1  retn
```
