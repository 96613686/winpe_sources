# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800092dc`
- end: `0x180009378`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ee4`

## callees

- `0x180006b60`
- `0x180007848`
- `0x1800092dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009306`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180009306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009322`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000932d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000932d`

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
0x1800092dc  mov     rax, rsp
0x1800092df  mov     [rax+8], rbx
0x1800092e3  mov     [rax+10h], rbp
0x1800092e7  mov     [rax+18h], rsi
0x1800092eb  mov     [rax+20h], rdi
0x1800092ef  push    r14
0x1800092f1  sub     rsp, 30h
0x1800092f5  mov     rsi, rcx
0x1800092f8  mov     dword ptr [rax-10h], 1F0003h
0x1800092ff  xor     ebx, ebx
0x180009301  xor     ecx, ecx; lpSemaphoreAttributes
0x180009303  mov     [rax-18h], ebx
0x180009306  call    cs:__imp_CreateSemaphoreExW
0x18000930c  mov     r14, rax
0x18000930f  test    rax, rax
0x180009312  jz      short loc_180009344
0x180009314  call    cs:__imp_GetLastError
0x18000931a  mov     rdi, [rsi]
0x18000931d  test    rdi, rdi
0x180009320  jz      short loc_18000933F
0x180009322  call    cs:__imp_GetLastError
0x180009328  mov     rcx, rdi; hObject
0x18000932b  mov     ebp, eax
0x18000932d  call    cs:__imp_CloseHandle
0x180009333  test    eax, eax
0x180009335  jz      short loc_180009368
0x180009337  mov     ecx, ebp; dwErrCode
0x180009339  call    cs:__imp_SetLastError
0x18000933f  mov     [rsi], r14
0x180009342  jmp     short loc_18000934B
0x180009344  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009349  mov     ebx, eax
0x18000934b  mov     rbp, [rsp+38h+arg_8]
0x180009350  mov     eax, ebx
0x180009352  mov     rbx, [rsp+38h+arg_0]
0x180009357  mov     rsi, [rsp+38h+arg_10]
0x18000935c  mov     rdi, [rsp+38h+arg_18]
0x180009361  add     rsp, 30h
0x180009365  pop     r14
0x180009367  retn
0x180009368  mov     rcx, [rsp+38h]; this
0x18000936d  mov     edx, 9D1h; void *
0x180009372  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
