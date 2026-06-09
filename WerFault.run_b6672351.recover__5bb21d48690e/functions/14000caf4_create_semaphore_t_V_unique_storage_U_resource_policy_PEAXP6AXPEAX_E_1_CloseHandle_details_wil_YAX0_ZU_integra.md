# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000caf4`
- end: `0x14000cb8f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006ab0`

## callees

- `0x140007d58`
- `0x14000c720`
- `0x14000caf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000cb12`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000cb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cb3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cb5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cb5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cb4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000cb4b`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
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
0x14000caf4  push    rbx
0x14000caf6  push    rbp
0x14000caf7  push    rsi
0x14000caf8  push    rdi
0x14000caf9  sub     rsp, 38h
0x14000cafd  mov     rdi, rcx
0x14000cb00  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x14000cb08  xor     ecx, ecx; lpSemaphoreAttributes
0x14000cb0a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x14000cb12  call    cs:__imp_CreateSemaphoreExW
0x14000cb19  nop     dword ptr [rax+rax+00h]
0x14000cb1e  mov     rbp, rax
0x14000cb21  test    rax, rax
0x14000cb24  jz      short loc_14000CB70
0x14000cb26  call    cs:__imp_GetLastError
0x14000cb2d  nop     dword ptr [rax+rax+00h]
0x14000cb32  mov     rbx, [rdi]
0x14000cb35  test    rbx, rbx
0x14000cb38  jz      short loc_14000CB69
0x14000cb3a  call    cs:__imp_GetLastError
0x14000cb41  nop     dword ptr [rax+rax+00h]
0x14000cb46  mov     rcx, rbx; hObject
0x14000cb49  mov     esi, eax
0x14000cb4b  call    cs:__imp_CloseHandle
0x14000cb52  nop     dword ptr [rax+rax+00h]
0x14000cb57  test    eax, eax
0x14000cb59  jz      short loc_14000CB7F
0x14000cb5b  mov     ecx, esi; dwErrCode
0x14000cb5d  call    cs:__imp_SetLastError
0x14000cb64  nop     dword ptr [rax+rax+00h]
0x14000cb69  mov     [rdi], rbp
0x14000cb6c  xor     eax, eax
0x14000cb6e  jmp     short loc_14000CB75
0x14000cb70  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000cb75  add     rsp, 38h
0x14000cb79  pop     rdi
0x14000cb7a  pop     rsi
0x14000cb7b  pop     rbp
0x14000cb7c  pop     rbx
0x14000cb7d  retn
0x14000cb7f  mov     rcx, [rsp+58h]; this
0x14000cb84  mov     edx, 0A0Bh; void *
0x14000cb89  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
