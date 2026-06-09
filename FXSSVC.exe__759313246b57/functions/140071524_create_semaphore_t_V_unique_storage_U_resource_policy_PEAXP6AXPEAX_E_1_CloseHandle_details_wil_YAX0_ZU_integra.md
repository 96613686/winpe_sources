# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140071524`
- end: `0x1400715bf`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006ce4c`

## callees

- `0x14006da90`
- `0x1400714b0`
- `0x140071524`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x140071542`
- `KERNEL32!CreateSemaphoreExW` at `0x140071542`
- `KERNEL32!GetLastError` at `0x140071556`
- `KERNEL32!GetLastError` at `0x14007156a`
- `KERNEL32!GetLastError` at `0x140071556`
- `KERNEL32!GetLastError` at `0x14007156a`
- `KERNEL32!SetLastError` at `0x14007158d`
- `KERNEL32!SetLastError` at `0x14007158d`
- `KERNEL32!CloseHandle` at `0x14007157b`
- `KERNEL32!CloseHandle` at `0x14007157b`

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
0x140071524  push    rbx
0x140071526  push    rbp
0x140071527  push    rsi
0x140071528  push    rdi
0x140071529  sub     rsp, 38h
0x14007152d  mov     rdi, rcx
0x140071530  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x140071538  xor     ecx, ecx; lpSemaphoreAttributes
0x14007153a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x140071542  call    cs:__imp_CreateSemaphoreExW
0x140071549  nop     dword ptr [rax+rax+00h]
0x14007154e  mov     rbp, rax
0x140071551  test    rax, rax
0x140071554  jz      short loc_1400715A0
0x140071556  call    cs:__imp_GetLastError
0x14007155d  nop     dword ptr [rax+rax+00h]
0x140071562  mov     rbx, [rdi]
0x140071565  test    rbx, rbx
0x140071568  jz      short loc_140071599
0x14007156a  call    cs:__imp_GetLastError
0x140071571  nop     dword ptr [rax+rax+00h]
0x140071576  mov     rcx, rbx; hObject
0x140071579  mov     esi, eax
0x14007157b  call    cs:__imp_CloseHandle
0x140071582  nop     dword ptr [rax+rax+00h]
0x140071587  test    eax, eax
0x140071589  jz      short loc_1400715AF
0x14007158b  mov     ecx, esi; dwErrCode
0x14007158d  call    cs:__imp_SetLastError
0x140071594  nop     dword ptr [rax+rax+00h]
0x140071599  mov     [rdi], rbp
0x14007159c  xor     eax, eax
0x14007159e  jmp     short loc_1400715A5
0x1400715a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400715a5  add     rsp, 38h
0x1400715a9  pop     rdi
0x1400715aa  pop     rsi
0x1400715ab  pop     rbp
0x1400715ac  pop     rbx
0x1400715ad  retn
0x1400715af  mov     rcx, [rsp+58h]; this
0x1400715b4  mov     edx, 0A0Bh; void *
0x1400715b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
