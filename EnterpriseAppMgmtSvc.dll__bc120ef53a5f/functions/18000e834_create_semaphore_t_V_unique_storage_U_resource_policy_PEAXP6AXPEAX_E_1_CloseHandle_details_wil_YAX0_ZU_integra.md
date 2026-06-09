# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000e834`
- end: `0x18000e8cf`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aa68`

## callees

- `0x18000b5b8`
- `0x18000e7c8`
- `0x18000e834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e87a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e89d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e89d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e88b`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e852`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000e852`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v5);
  GetLastError();
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  *a1 = Semaphore;
  return 0;
}

```

## disassembly

```asm
0x18000e834  push    rbx
0x18000e836  push    rbp
0x18000e837  push    rsi
0x18000e838  push    rdi
0x18000e839  sub     rsp, 38h
0x18000e83d  mov     rdi, rcx
0x18000e840  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000e848  xor     ecx, ecx; lpSemaphoreAttributes
0x18000e84a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18000e852  call    cs:__imp_CreateSemaphoreExW
0x18000e859  nop     dword ptr [rax+rax+00h]
0x18000e85e  mov     rbp, rax
0x18000e861  test    rax, rax
0x18000e864  jz      short loc_18000E8B0
0x18000e866  call    cs:__imp_GetLastError
0x18000e86d  nop     dword ptr [rax+rax+00h]
0x18000e872  mov     rbx, [rdi]
0x18000e875  test    rbx, rbx
0x18000e878  jz      short loc_18000E8A9
0x18000e87a  call    cs:__imp_GetLastError
0x18000e881  nop     dword ptr [rax+rax+00h]
0x18000e886  mov     rcx, rbx; hObject
0x18000e889  mov     esi, eax
0x18000e88b  call    cs:__imp_CloseHandle
0x18000e892  nop     dword ptr [rax+rax+00h]
0x18000e897  test    eax, eax
0x18000e899  jz      short loc_18000E8BF
0x18000e89b  mov     ecx, esi; dwErrCode
0x18000e89d  call    cs:__imp_SetLastError
0x18000e8a4  nop     dword ptr [rax+rax+00h]
0x18000e8a9  mov     [rdi], rbp
0x18000e8ac  xor     eax, eax
0x18000e8ae  jmp     short loc_18000E8B5
0x18000e8b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e8b5  add     rsp, 38h
0x18000e8b9  pop     rdi
0x18000e8ba  pop     rsi
0x18000e8bb  pop     rbp
0x18000e8bc  pop     rbx
0x18000e8bd  retn
0x18000e8bf  mov     rcx, [rsp+58h]; this
0x18000e8c4  mov     edx, 0A0Bh; void *
0x18000e8c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
