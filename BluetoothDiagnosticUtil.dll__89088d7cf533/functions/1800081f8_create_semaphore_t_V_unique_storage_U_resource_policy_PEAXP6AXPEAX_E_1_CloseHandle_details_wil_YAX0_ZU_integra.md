# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800081f8`
- end: `0x180008293`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800063e0`

## callees

- `0x180005640`
- `0x180008068`
- `0x1800081f8`

## import_xrefs

- `KERNEL32!CreateSemaphoreExW` at `0x180008216`
- `KERNEL32!CreateSemaphoreExW` at `0x180008216`
- `KERNEL32!CloseHandle` at `0x18000824f`
- `KERNEL32!CloseHandle` at `0x18000824f`
- `KERNEL32!SetLastError` at `0x180008261`
- `KERNEL32!SetLastError` at `0x180008261`
- `KERNEL32!GetLastError` at `0x18000822a`
- `KERNEL32!GetLastError` at `0x18000823e`
- `KERNEL32!GetLastError` at `0x18000822a`
- `KERNEL32!GetLastError` at `0x18000823e`

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
0x1800081f8  push    rbx
0x1800081fa  push    rbp
0x1800081fb  push    rsi
0x1800081fc  push    rdi
0x1800081fd  sub     rsp, 38h
0x180008201  mov     rdi, rcx
0x180008204  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18000820c  xor     ecx, ecx; lpSemaphoreAttributes
0x18000820e  mov     [rsp+58h+dwFlags], 0; dwFlags
0x180008216  call    cs:__imp_CreateSemaphoreExW
0x18000821d  nop     dword ptr [rax+rax+00h]
0x180008222  mov     rbp, rax
0x180008225  test    rax, rax
0x180008228  jz      short loc_180008274
0x18000822a  call    cs:__imp_GetLastError
0x180008231  nop     dword ptr [rax+rax+00h]
0x180008236  mov     rbx, [rdi]
0x180008239  test    rbx, rbx
0x18000823c  jz      short loc_18000826D
0x18000823e  call    cs:__imp_GetLastError
0x180008245  nop     dword ptr [rax+rax+00h]
0x18000824a  mov     rcx, rbx; hObject
0x18000824d  mov     esi, eax
0x18000824f  call    cs:__imp_CloseHandle
0x180008256  nop     dword ptr [rax+rax+00h]
0x18000825b  test    eax, eax
0x18000825d  jz      short loc_180008283
0x18000825f  mov     ecx, esi; dwErrCode
0x180008261  call    cs:__imp_SetLastError
0x180008268  nop     dword ptr [rax+rax+00h]
0x18000826d  mov     [rdi], rbp
0x180008270  xor     eax, eax
0x180008272  jmp     short loc_180008279
0x180008274  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008279  add     rsp, 38h
0x18000827d  pop     rdi
0x18000827e  pop     rsi
0x18000827f  pop     rbp
0x180008280  pop     rbx
0x180008281  retn
0x180008283  mov     rcx, [rsp+58h]; this
0x180008288  mov     edx, 0A0Bh; void *
0x18000828d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
