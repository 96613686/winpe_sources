# ?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180042060`
- end: `0x1800420b3`
- name: `?try_create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041ccc`

## callees

- `0x18001b1f0`
- `0x180042060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004207a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004207a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004208e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004208e`

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
0x180042060  mov     [rsp+arg_0], rbx
0x180042065  push    rdi
0x180042066  sub     rsp, 20h
0x18004206a  mov     rdi, rcx
0x18004206d  mov     r9d, 1F0001h; dwDesiredAccess
0x180042073  xor     ecx, ecx; lpMutexAttributes
0x180042075  xor     r8d, r8d; dwFlags
0x180042078  xor     edx, edx; lpName
0x18004207a  call    cs:__imp_CreateMutexExW
0x180042081  nop     dword ptr [rax+rax+00h]
0x180042086  mov     rbx, rax
0x180042089  test    rax, rax
0x18004208c  jz      short loc_1800420A7
0x18004208e  call    cs:__imp_GetLastError
0x180042095  nop     dword ptr [rax+rax+00h]
0x18004209a  mov     rdx, rbx
0x18004209d  mov     rcx, rdi
0x1800420a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800420a5  mov     al, 1
0x1800420a7  mov     rbx, [rsp+28h+arg_0]
0x1800420ac  add     rsp, 20h
0x1800420b0  pop     rdi
0x1800420b1  retn
```
