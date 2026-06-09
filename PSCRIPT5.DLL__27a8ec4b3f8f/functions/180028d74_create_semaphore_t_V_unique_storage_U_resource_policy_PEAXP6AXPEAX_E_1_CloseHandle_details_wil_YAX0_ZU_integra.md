# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180028d74`
- end: `0x180028e0f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: `signed int __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024d68`

## callees

- `0x180025b68`
- `0x180028d00`
- `0x180028d74`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180028d92`
- `KERNEL32!CreateSemaphoreExW` at `0x180028d92`
- `KERNEL32!CloseHandle` at `0x180028dcb`
- `KERNEL32!CloseHandle` at `0x180028dcb`
- `KERNEL32!SetLastError` at `0x180028ddd`
- `KERNEL32!SetLastError` at `0x180028ddd`
- `KERNEL32!GetLastError` at `0x180028da6`
- `KERNEL32!GetLastError` at `0x180028dba`
- `KERNEL32!GetLastError` at `0x180028da6`
- `KERNEL32!GetLastError` at `0x180028dba`

## pseudocode

```c
signed int __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  wil::details *v5; // rcx
  HANDLE Semaphore; // rbp
  void *v7; // rbx
  DWORD LastError; // esi
  __int64 v9; // r8
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
0x180028d74  push    rbx
0x180028d76  push    rbp
0x180028d77  push    rsi
0x180028d78  push    rdi
0x180028d79  sub     rsp, 38h
0x180028d7d  mov     rdi, rcx
0x180028d80  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180028d88  xor     ecx, ecx; lpSemaphoreAttributes
0x180028d8a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180028d92  call    cs:__imp_CreateSemaphoreExW
0x180028d99  nop     dword ptr [rax+rax+00h]
0x180028d9e  mov     rbp, rax
0x180028da1  test    rax, rax
0x180028da4  jz      short loc_180028DF0
0x180028da6  call    cs:__imp_GetLastError
0x180028dad  nop     dword ptr [rax+rax+00h]
0x180028db2  mov     rbx, [rdi]
0x180028db5  test    rbx, rbx
0x180028db8  jz      short loc_180028DE9
0x180028dba  call    cs:__imp_GetLastError
0x180028dc1  nop     dword ptr [rax+rax+00h]
0x180028dc6  mov     rcx, rbx; hObject
0x180028dc9  mov     esi, eax
0x180028dcb  call    cs:__imp_CloseHandle
0x180028dd2  nop     dword ptr [rax+rax+00h]
0x180028dd7  test    eax, eax
0x180028dd9  jz      short loc_180028DFF
0x180028ddb  mov     ecx, esi; dwErrCode
0x180028ddd  call    cs:__imp_SetLastError
0x180028de4  nop     dword ptr [rax+rax+00h]
0x180028de9  mov     [rdi], rbp
0x180028dec  xor     eax, eax
0x180028dee  jmp     short loc_180028DF5
0x180028df0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028df5  add     rsp, 38h
0x180028df9  pop     rdi
0x180028dfa  pop     rsi
0x180028dfb  pop     rbp
0x180028dfc  pop     rbx
0x180028dfd  retn
0x180028dff  mov     rcx, [rsp+58h]; this
0x180028e04  mov     edx, 0A0Bh; void *
0x180028e09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
