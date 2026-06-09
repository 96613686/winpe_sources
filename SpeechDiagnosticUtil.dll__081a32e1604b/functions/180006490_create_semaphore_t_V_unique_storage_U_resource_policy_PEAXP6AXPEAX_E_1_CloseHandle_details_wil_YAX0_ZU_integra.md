# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180006490`
- end: `0x18000652b`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005434`

## callees

- `0x180004960`
- `0x180006474`
- `0x180006490`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800064e7`
- `KERNEL32!CloseHandle` at `0x1800064e7`
- `KERNEL32!GetLastError` at `0x1800064c2`
- `KERNEL32!GetLastError` at `0x1800064d6`
- `KERNEL32!GetLastError` at `0x1800064c2`
- `KERNEL32!GetLastError` at `0x1800064d6`
- `KERNEL32!SetLastError` at `0x1800064f9`
- `KERNEL32!SetLastError` at `0x1800064f9`
- `KERNEL32!CreateSemaphoreExW` at `0x1800064ae`
- `KERNEL32!CreateSemaphoreExW` at `0x1800064ae`

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
0x180006490  push    rbx
0x180006492  push    rbp
0x180006493  push    rsi
0x180006494  push    rdi
0x180006495  sub     rsp, 38h
0x180006499  mov     rdi, rcx
0x18000649c  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800064a4  xor     ecx, ecx; lpSemaphoreAttributes
0x1800064a6  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800064ae  call    cs:__imp_CreateSemaphoreExW
0x1800064b5  nop     dword ptr [rax+rax+00h]
0x1800064ba  mov     rbp, rax
0x1800064bd  test    rax, rax
0x1800064c0  jz      short loc_18000650C
0x1800064c2  call    cs:__imp_GetLastError
0x1800064c9  nop     dword ptr [rax+rax+00h]
0x1800064ce  mov     rbx, [rdi]
0x1800064d1  test    rbx, rbx
0x1800064d4  jz      short loc_180006505
0x1800064d6  call    cs:__imp_GetLastError
0x1800064dd  nop     dword ptr [rax+rax+00h]
0x1800064e2  mov     rcx, rbx; hObject
0x1800064e5  mov     esi, eax
0x1800064e7  call    cs:__imp_CloseHandle
0x1800064ee  nop     dword ptr [rax+rax+00h]
0x1800064f3  test    eax, eax
0x1800064f5  jz      short loc_18000651B
0x1800064f7  mov     ecx, esi; dwErrCode
0x1800064f9  call    cs:__imp_SetLastError
0x180006500  nop     dword ptr [rax+rax+00h]
0x180006505  mov     [rdi], rbp
0x180006508  xor     eax, eax
0x18000650a  jmp     short loc_180006511
0x18000650c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006511  add     rsp, 38h
0x180006515  pop     rdi
0x180006516  pop     rsi
0x180006517  pop     rbp
0x180006518  pop     rbx
0x180006519  retn
0x18000651b  mov     rcx, [rsp+58h]; this
0x180006520  mov     edx, 0A0Bh; void *
0x180006525  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
