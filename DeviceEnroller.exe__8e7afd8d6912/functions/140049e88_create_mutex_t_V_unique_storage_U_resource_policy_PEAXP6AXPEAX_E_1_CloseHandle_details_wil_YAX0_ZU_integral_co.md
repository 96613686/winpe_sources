# ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140049e88`
- end: `0x140049f00`
- name: `?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `120`
- prototype: `__int64 __fastcall(void **, const WCHAR *, __int64, __int64, LPSECURITY_ATTRIBUTES lpMutexAttributes)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a9a4`
- `0x140053430`
- `0x140054320`

## callees

- `0x140008298`
- `0x14000a6a8`
- `0x140049e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140049ea2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140049ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140049ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049ed5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049ed5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140049ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140049ec9`

## pseudocode

```c
__int64 __fastcall _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        LPSECURITY_ATTRIBUTES lpMutexAttributes)
{
  wil::details *v6; // rcx
  HANDLE Mutex; // rbp
  void *v8; // rbx
  DWORD LastError; // esi
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Mutex = CreateMutexExW(lpMutexAttributes, a2, 0, 0x1F0001u);
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  GetLastError();
  v8 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
    SetLastError(LastError);
  }
  *a1 = Mutex;
  return 0;
}

```

## disassembly

```asm
0x140049e88  push    rbx
0x140049e8a  push    rbp
0x140049e8b  push    rsi
0x140049e8c  push    rdi
0x140049e8d  sub     rsp, 28h
0x140049e91  mov     rdi, rcx
0x140049e94  mov     r9d, 1F0001h; dwDesiredAccess
0x140049e9a  mov     rcx, [rsp+48h+lpMutexAttributes]; lpMutexAttributes
0x140049e9f  xor     r8d, r8d; dwFlags
0x140049ea2  call    cs:__imp_CreateMutexExW
0x140049ea8  mov     rbp, rax
0x140049eab  test    rax, rax
0x140049eae  jz      short loc_140049EE2
0x140049eb0  call    cs:__imp_GetLastError
0x140049eb6  mov     rbx, [rdi]
0x140049eb9  test    rbx, rbx
0x140049ebc  jz      short loc_140049EDB
0x140049ebe  call    cs:__imp_GetLastError
0x140049ec4  mov     rcx, rbx; hObject
0x140049ec7  mov     esi, eax
0x140049ec9  call    cs:__imp_CloseHandle
0x140049ecf  test    eax, eax
0x140049ed1  jz      short loc_140049EF0
0x140049ed3  mov     ecx, esi; dwErrCode
0x140049ed5  call    cs:__imp_SetLastError
0x140049edb  mov     [rdi], rbp
0x140049ede  xor     eax, eax
0x140049ee0  jmp     short loc_140049EE7
0x140049ee2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140049ee7  add     rsp, 28h
0x140049eeb  pop     rdi
0x140049eec  pop     rsi
0x140049eed  pop     rbp
0x140049eee  pop     rbx
0x140049eef  retn
0x140049ef0  mov     rcx, [rsp+48h]; this
0x140049ef5  mov     edx, 0A0Bh; void *
0x140049efa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
