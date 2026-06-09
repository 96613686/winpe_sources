# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180007654`
- end: `0x1800076f0`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ef8`

## callees

- `0x180005450`
- `0x180006444`
- `0x180007654`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000767e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000767e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000768c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000769a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000768c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000769a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a5`

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
0x180007654  mov     rax, rsp
0x180007657  mov     [rax+8], rbx
0x18000765b  mov     [rax+10h], rbp
0x18000765f  mov     [rax+18h], rsi
0x180007663  mov     [rax+20h], rdi
0x180007667  push    r14
0x180007669  sub     rsp, 30h
0x18000766d  mov     rsi, rcx
0x180007670  mov     dword ptr [rax-10h], 1F0003h
0x180007677  xor     ebx, ebx
0x180007679  xor     ecx, ecx; lpSemaphoreAttributes
0x18000767b  mov     [rax-18h], ebx
0x18000767e  call    cs:__imp_CreateSemaphoreExW
0x180007684  mov     r14, rax
0x180007687  test    rax, rax
0x18000768a  jz      short loc_1800076BC
0x18000768c  call    cs:__imp_GetLastError
0x180007692  mov     rdi, [rsi]
0x180007695  test    rdi, rdi
0x180007698  jz      short loc_1800076B7
0x18000769a  call    cs:__imp_GetLastError
0x1800076a0  mov     rcx, rdi; hObject
0x1800076a3  mov     ebp, eax
0x1800076a5  call    cs:__imp_CloseHandle
0x1800076ab  test    eax, eax
0x1800076ad  jz      short loc_1800076E0
0x1800076af  mov     ecx, ebp; dwErrCode
0x1800076b1  call    cs:__imp_SetLastError
0x1800076b7  mov     [rsi], r14
0x1800076ba  jmp     short loc_1800076C3
0x1800076bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800076c1  mov     ebx, eax
0x1800076c3  mov     rbp, [rsp+38h+arg_8]
0x1800076c8  mov     eax, ebx
0x1800076ca  mov     rbx, [rsp+38h+arg_0]
0x1800076cf  mov     rsi, [rsp+38h+arg_10]
0x1800076d4  mov     rdi, [rsp+38h+arg_18]
0x1800076d9  add     rsp, 30h
0x1800076dd  pop     r14
0x1800076df  retn
0x1800076e0  mov     rcx, [rsp+38h]; this
0x1800076e5  mov     edx, 9D1h; void *
0x1800076ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
