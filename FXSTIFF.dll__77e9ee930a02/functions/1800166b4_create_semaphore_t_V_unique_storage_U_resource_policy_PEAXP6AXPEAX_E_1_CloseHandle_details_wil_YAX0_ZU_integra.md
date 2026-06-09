# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800166b4`
- end: `0x180016750`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011df8`

## callees

- `0x180012b20`
- `0x180016644`
- `0x1800166b4`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x1800166d2`
- `KERNEL32!CreateSemaphoreExW` at `0x1800166d2`
- `KERNEL32!GetLastError` at `0x1800166e6`
- `KERNEL32!GetLastError` at `0x1800166fa`
- `KERNEL32!GetLastError` at `0x1800166e6`
- `KERNEL32!GetLastError` at `0x1800166fa`
- `KERNEL32!SetLastError` at `0x180016722`
- `KERNEL32!SetLastError` at `0x180016722`
- `KERNEL32!CloseHandle` at `0x18001670b`
- `KERNEL32!CloseHandle` at `0x18001670b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800166b4  push    rbx
0x1800166b6  push    rbp
0x1800166b7  push    rsi
0x1800166b8  push    rdi
0x1800166b9  sub     rsp, 38h
0x1800166bd  mov     rdi, rcx
0x1800166c0  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800166c8  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800166d0  xor     ecx, ecx; lpSemaphoreAttributes
0x1800166d2  call    cs:__imp_CreateSemaphoreExW
0x1800166d9  nop     dword ptr [rax+rax+00h]
0x1800166de  mov     rbp, rax
0x1800166e1  test    rax, rax
0x1800166e4  jz      short loc_180016736
0x1800166e6  call    cs:__imp_GetLastError
0x1800166ed  nop     dword ptr [rax+rax+00h]
0x1800166f2  mov     rbx, [rdi]
0x1800166f5  test    rbx, rbx
0x1800166f8  jz      short loc_18001672F
0x1800166fa  call    cs:__imp_GetLastError
0x180016701  nop     dword ptr [rax+rax+00h]
0x180016706  mov     esi, eax
0x180016708  mov     rcx, rbx; hObject
0x18001670b  call    cs:__imp_CloseHandle
0x180016712  nop     dword ptr [rax+rax+00h]
0x180016717  mov     rcx, [rsp+58h]; this
0x18001671c  test    eax, eax
0x18001671e  jz      short loc_180016745
0x180016720  mov     ecx, esi; dwErrCode
0x180016722  call    cs:__imp_SetLastError
0x180016729  nop     dword ptr [rax+rax+00h]
0x18001672e  nop
0x18001672f  mov     [rdi], rbp
0x180016732  xor     eax, eax
0x180016734  jmp     short loc_18001673B
0x180016736  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001673b  add     rsp, 38h
0x18001673f  pop     rdi
0x180016740  pop     rsi
0x180016741  pop     rbp
0x180016742  pop     rbx
0x180016743  retn
0x180016745  mov     edx, 0A0Bh; void *
0x18001674a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
