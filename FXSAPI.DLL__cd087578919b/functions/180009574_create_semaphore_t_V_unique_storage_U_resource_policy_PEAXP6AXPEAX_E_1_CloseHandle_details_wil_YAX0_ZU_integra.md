# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180009574`
- end: `0x18000960f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003dcc`

## callees

- `0x1800055d0`
- `0x180009500`
- `0x180009574`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180009592`
- `KERNEL32!CreateSemaphoreExW` at `0x180009592`
- `KERNEL32!CloseHandle` at `0x1800095cb`
- `KERNEL32!CloseHandle` at `0x1800095cb`
- `KERNEL32!SetLastError` at `0x1800095dd`
- `KERNEL32!SetLastError` at `0x1800095dd`
- `KERNEL32!GetLastError` at `0x1800095a6`
- `KERNEL32!GetLastError` at `0x1800095ba`
- `KERNEL32!GetLastError` at `0x1800095a6`
- `KERNEL32!GetLastError` at `0x1800095ba`

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
0x180009574  push    rbx
0x180009576  push    rbp
0x180009577  push    rsi
0x180009578  push    rdi
0x180009579  sub     rsp, 38h
0x18000957d  mov     rdi, rcx
0x180009580  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180009588  xor     ecx, ecx; lpSemaphoreAttributes
0x18000958a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180009592  call    cs:__imp_CreateSemaphoreExW
0x180009599  nop     dword ptr [rax+rax+00h]
0x18000959e  mov     rbp, rax
0x1800095a1  test    rax, rax
0x1800095a4  jz      short loc_1800095F0
0x1800095a6  call    cs:__imp_GetLastError
0x1800095ad  nop     dword ptr [rax+rax+00h]
0x1800095b2  mov     rbx, [rdi]
0x1800095b5  test    rbx, rbx
0x1800095b8  jz      short loc_1800095E9
0x1800095ba  call    cs:__imp_GetLastError
0x1800095c1  nop     dword ptr [rax+rax+00h]
0x1800095c6  mov     rcx, rbx; hObject
0x1800095c9  mov     esi, eax
0x1800095cb  call    cs:__imp_CloseHandle
0x1800095d2  nop     dword ptr [rax+rax+00h]
0x1800095d7  test    eax, eax
0x1800095d9  jz      short loc_1800095FF
0x1800095db  mov     ecx, esi; dwErrCode
0x1800095dd  call    cs:__imp_SetLastError
0x1800095e4  nop     dword ptr [rax+rax+00h]
0x1800095e9  mov     [rdi], rbp
0x1800095ec  xor     eax, eax
0x1800095ee  jmp     short loc_1800095F5
0x1800095f0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800095f5  add     rsp, 38h
0x1800095f9  pop     rdi
0x1800095fa  pop     rsi
0x1800095fb  pop     rbp
0x1800095fc  pop     rbx
0x1800095fd  retn
0x1800095ff  mov     rcx, [rsp+58h]; this
0x180009604  mov     edx, 0A0Bh; void *
0x180009609  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
