# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180009984`
- end: `0x180009a20`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e48`

## callees

- `0x1800080c0`
- `0x180008bf8`
- `0x180009984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800099e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099d5`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800099ae`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800099ae`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  unsigned int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v10, v11);
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180009984  mov     rax, rsp
0x180009987  mov     [rax+8], rbx
0x18000998b  mov     [rax+10h], rbp
0x18000998f  mov     [rax+18h], rsi
0x180009993  mov     [rax+20h], rdi
0x180009997  push    r14
0x180009999  sub     rsp, 30h
0x18000999d  mov     rsi, rcx
0x1800099a0  mov     dword ptr [rax-10h], 1F0003h
0x1800099a7  xor     ebx, ebx
0x1800099a9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800099ab  mov     [rax-18h], ebx
0x1800099ae  call    cs:__imp_CreateSemaphoreExW
0x1800099b4  mov     r14, rax
0x1800099b7  test    rax, rax
0x1800099ba  jz      short loc_1800099EC
0x1800099bc  call    cs:__imp_GetLastError
0x1800099c2  mov     rdi, [rsi]
0x1800099c5  test    rdi, rdi
0x1800099c8  jz      short loc_1800099E7
0x1800099ca  call    cs:__imp_GetLastError
0x1800099d0  mov     rcx, rdi; hObject
0x1800099d3  mov     ebp, eax
0x1800099d5  call    cs:__imp_CloseHandle
0x1800099db  test    eax, eax
0x1800099dd  jz      short loc_180009A10
0x1800099df  mov     ecx, ebp; dwErrCode
0x1800099e1  call    cs:__imp_SetLastError
0x1800099e7  mov     [rsi], r14
0x1800099ea  jmp     short loc_1800099F3
0x1800099ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800099f1  mov     ebx, eax
0x1800099f3  mov     rbp, [rsp+38h+arg_8]
0x1800099f8  mov     eax, ebx
0x1800099fa  mov     rbx, [rsp+38h+arg_0]
0x1800099ff  mov     rsi, [rsp+38h+arg_10]
0x180009a04  mov     rdi, [rsp+38h+arg_18]
0x180009a09  add     rsp, 30h
0x180009a0d  pop     r14
0x180009a0f  retn
0x180009a10  mov     rcx, [rsp+38h]; this
0x180009a15  mov     edx, 9D1h; void *
0x180009a1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
