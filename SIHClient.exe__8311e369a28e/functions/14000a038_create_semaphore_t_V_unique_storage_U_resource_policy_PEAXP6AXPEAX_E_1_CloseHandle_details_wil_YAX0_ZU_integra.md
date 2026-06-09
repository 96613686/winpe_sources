# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000a038`
- end: `0x14000a0d4`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000aabc`

## callees

- `0x140008140`
- `0x140008e28`
- `0x14000a038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a095`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a07e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000a062`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x14000a062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a089`

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
0x14000a038  mov     rax, rsp
0x14000a03b  mov     [rax+8], rbx
0x14000a03f  mov     [rax+10h], rbp
0x14000a043  mov     [rax+18h], rsi
0x14000a047  mov     [rax+20h], rdi
0x14000a04b  push    r14
0x14000a04d  sub     rsp, 30h
0x14000a051  mov     rsi, rcx
0x14000a054  mov     dword ptr [rax-10h], 1F0003h
0x14000a05b  xor     ebx, ebx
0x14000a05d  xor     ecx, ecx; lpSemaphoreAttributes
0x14000a05f  mov     [rax-18h], ebx
0x14000a062  call    cs:__imp_CreateSemaphoreExW
0x14000a068  mov     r14, rax
0x14000a06b  test    rax, rax
0x14000a06e  jz      short loc_14000A0A0
0x14000a070  call    cs:__imp_GetLastError
0x14000a076  mov     rdi, [rsi]
0x14000a079  test    rdi, rdi
0x14000a07c  jz      short loc_14000A09B
0x14000a07e  call    cs:__imp_GetLastError
0x14000a084  mov     rcx, rdi; hObject
0x14000a087  mov     ebp, eax
0x14000a089  call    cs:__imp_CloseHandle
0x14000a08f  test    eax, eax
0x14000a091  jz      short loc_14000A0C4
0x14000a093  mov     ecx, ebp; dwErrCode
0x14000a095  call    cs:__imp_SetLastError
0x14000a09b  mov     [rsi], r14
0x14000a09e  jmp     short loc_14000A0A7
0x14000a0a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a0a5  mov     ebx, eax
0x14000a0a7  mov     rbp, [rsp+38h+arg_8]
0x14000a0ac  mov     eax, ebx
0x14000a0ae  mov     rbx, [rsp+38h+arg_0]
0x14000a0b3  mov     rsi, [rsp+38h+arg_10]
0x14000a0b8  mov     rdi, [rsp+38h+arg_18]
0x14000a0bd  add     rsp, 30h
0x14000a0c1  pop     r14
0x14000a0c3  retn
0x14000a0c4  mov     rcx, [rsp+38h]; this
0x14000a0c9  mov     edx, 9D1h; void *
0x14000a0ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
