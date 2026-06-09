# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180008188`
- end: `0x180008223`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ad8`

## callees

- `0x1800046f8`
- `0x18000787c`
- `0x180008188`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800081df`
- `KERNEL32!CloseHandle` at `0x1800081df`
- `KERNEL32!GetLastError` at `0x1800081ba`
- `KERNEL32!GetLastError` at `0x1800081ce`
- `KERNEL32!GetLastError` at `0x1800081ba`
- `KERNEL32!GetLastError` at `0x1800081ce`
- `KERNEL32!SetLastError` at `0x1800081f1`
- `KERNEL32!SetLastError` at `0x1800081f1`
- `KERNEL32!CreateSemaphoreExW` at `0x1800081a6`
- `KERNEL32!CreateSemaphoreExW` at `0x1800081a6`

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
0x180008188  push    rbx
0x18000818a  push    rbp
0x18000818b  push    rsi
0x18000818c  push    rdi
0x18000818d  sub     rsp, 38h
0x180008191  mov     rdi, rcx
0x180008194  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000819c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000819e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800081a6  call    cs:__imp_CreateSemaphoreExW
0x1800081ad  nop     dword ptr [rax+rax+00h]
0x1800081b2  mov     rbp, rax
0x1800081b5  test    rax, rax
0x1800081b8  jz      short loc_180008204
0x1800081ba  call    cs:__imp_GetLastError
0x1800081c1  nop     dword ptr [rax+rax+00h]
0x1800081c6  mov     rbx, [rdi]
0x1800081c9  test    rbx, rbx
0x1800081cc  jz      short loc_1800081FD
0x1800081ce  call    cs:__imp_GetLastError
0x1800081d5  nop     dword ptr [rax+rax+00h]
0x1800081da  mov     rcx, rbx; hObject
0x1800081dd  mov     esi, eax
0x1800081df  call    cs:__imp_CloseHandle
0x1800081e6  nop     dword ptr [rax+rax+00h]
0x1800081eb  test    eax, eax
0x1800081ed  jz      short loc_180008213
0x1800081ef  mov     ecx, esi; dwErrCode
0x1800081f1  call    cs:__imp_SetLastError
0x1800081f8  nop     dword ptr [rax+rax+00h]
0x1800081fd  mov     [rdi], rbp
0x180008200  xor     eax, eax
0x180008202  jmp     short loc_180008209
0x180008204  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008209  add     rsp, 38h
0x18000820d  pop     rdi
0x18000820e  pop     rsi
0x18000820f  pop     rbp
0x180008210  pop     rbx
0x180008211  retn
0x180008213  mov     rcx, [rsp+58h]; this
0x180008218  mov     edx, 0A0Bh; void *
0x18000821d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
