# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180005d6c`
- end: `0x180005e08`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006230`

## callees

- `0x180004170`
- `0x180004d64`
- `0x180005d6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005db2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005d96`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005d96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005dbd`

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
0x180005d6c  mov     rax, rsp
0x180005d6f  mov     [rax+8], rbx
0x180005d73  mov     [rax+10h], rbp
0x180005d77  mov     [rax+18h], rsi
0x180005d7b  mov     [rax+20h], rdi
0x180005d7f  push    r14
0x180005d81  sub     rsp, 30h
0x180005d85  mov     rsi, rcx
0x180005d88  mov     dword ptr [rax-10h], 1F0003h
0x180005d8f  xor     ebx, ebx
0x180005d91  xor     ecx, ecx; lpSemaphoreAttributes
0x180005d93  mov     [rax-18h], ebx
0x180005d96  call    cs:__imp_CreateSemaphoreExW
0x180005d9c  mov     r14, rax
0x180005d9f  test    rax, rax
0x180005da2  jz      short loc_180005DD4
0x180005da4  call    cs:__imp_GetLastError
0x180005daa  mov     rdi, [rsi]
0x180005dad  test    rdi, rdi
0x180005db0  jz      short loc_180005DCF
0x180005db2  call    cs:__imp_GetLastError
0x180005db8  mov     rcx, rdi; hObject
0x180005dbb  mov     ebp, eax
0x180005dbd  call    cs:__imp_CloseHandle
0x180005dc3  test    eax, eax
0x180005dc5  jz      short loc_180005DF8
0x180005dc7  mov     ecx, ebp; dwErrCode
0x180005dc9  call    cs:__imp_SetLastError
0x180005dcf  mov     [rsi], r14
0x180005dd2  jmp     short loc_180005DDB
0x180005dd4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005dd9  mov     ebx, eax
0x180005ddb  mov     rbp, [rsp+38h+arg_8]
0x180005de0  mov     eax, ebx
0x180005de2  mov     rbx, [rsp+38h+arg_0]
0x180005de7  mov     rsi, [rsp+38h+arg_10]
0x180005dec  mov     rdi, [rsp+38h+arg_18]
0x180005df1  add     rsp, 30h
0x180005df5  pop     r14
0x180005df7  retn
0x180005df8  mov     rcx, [rsp+38h]; this
0x180005dfd  mov     edx, 9D1h; void *
0x180005e02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
