# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180019eb8`
- end: `0x180019f53`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018b4c`

## callees

- `0x180018684`
- `0x180019e9c`
- `0x180019eb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019efe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f0f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180019ed6`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180019ed6`

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
0x180019eb8  push    rbx
0x180019eba  push    rbp
0x180019ebb  push    rsi
0x180019ebc  push    rdi
0x180019ebd  sub     rsp, 38h
0x180019ec1  mov     rdi, rcx
0x180019ec4  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180019ecc  xor     ecx, ecx; lpSemaphoreAttributes
0x180019ece  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180019ed6  call    cs:__imp_CreateSemaphoreExW
0x180019edd  nop     dword ptr [rax+rax+00h]
0x180019ee2  mov     rbp, rax
0x180019ee5  test    rax, rax
0x180019ee8  jz      short loc_180019F34
0x180019eea  call    cs:__imp_GetLastError
0x180019ef1  nop     dword ptr [rax+rax+00h]
0x180019ef6  mov     rbx, [rdi]
0x180019ef9  test    rbx, rbx
0x180019efc  jz      short loc_180019F2D
0x180019efe  call    cs:__imp_GetLastError
0x180019f05  nop     dword ptr [rax+rax+00h]
0x180019f0a  mov     rcx, rbx; hObject
0x180019f0d  mov     esi, eax
0x180019f0f  call    cs:__imp_CloseHandle
0x180019f16  nop     dword ptr [rax+rax+00h]
0x180019f1b  test    eax, eax
0x180019f1d  jz      short loc_180019F43
0x180019f1f  mov     ecx, esi; dwErrCode
0x180019f21  call    cs:__imp_SetLastError
0x180019f28  nop     dword ptr [rax+rax+00h]
0x180019f2d  mov     [rdi], rbp
0x180019f30  xor     eax, eax
0x180019f32  jmp     short loc_180019F39
0x180019f34  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180019f39  add     rsp, 38h
0x180019f3d  pop     rdi
0x180019f3e  pop     rsi
0x180019f3f  pop     rbp
0x180019f40  pop     rbx
0x180019f41  retn
0x180019f43  mov     rcx, [rsp+58h]; this
0x180019f48  mov     edx, 0A0Bh; void *
0x180019f4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
