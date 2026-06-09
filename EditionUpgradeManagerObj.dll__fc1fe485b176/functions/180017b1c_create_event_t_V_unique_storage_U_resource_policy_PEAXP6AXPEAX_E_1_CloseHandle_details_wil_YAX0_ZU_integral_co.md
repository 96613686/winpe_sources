# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180017b1c`
- end: `0x180017b93`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de6c`
- `0x18000e0b4`
- `0x18000e2fc`
- `0x18000e544`

## callees

- `0x1800051f8`
- `0x1800086fc`
- `0x180017b1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017b35`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017b35`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b5c`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x180017b1c  push    rbx
0x180017b1e  push    rbp
0x180017b1f  push    rsi
0x180017b20  push    rdi
0x180017b21  sub     rsp, 28h
0x180017b25  mov     rdi, rcx
0x180017b28  mov     r9d, 1F0003h; dwDesiredAccess
0x180017b2e  xor     ecx, ecx; lpEventAttributes
0x180017b30  xor     r8d, r8d; dwFlags
0x180017b33  xor     edx, edx; lpName
0x180017b35  call    cs:__imp_CreateEventExW
0x180017b3b  mov     rbp, rax
0x180017b3e  test    rax, rax
0x180017b41  jz      short loc_180017B75
0x180017b43  call    cs:__imp_GetLastError
0x180017b49  mov     rbx, [rdi]
0x180017b4c  test    rbx, rbx
0x180017b4f  jz      short loc_180017B6E
0x180017b51  call    cs:__imp_GetLastError
0x180017b57  mov     rcx, rbx; hObject
0x180017b5a  mov     esi, eax
0x180017b5c  call    cs:__imp_CloseHandle
0x180017b62  test    eax, eax
0x180017b64  jz      short loc_180017B83
0x180017b66  mov     ecx, esi; dwErrCode
0x180017b68  call    cs:__imp_SetLastError
0x180017b6e  mov     [rdi], rbp
0x180017b71  xor     eax, eax
0x180017b73  jmp     short loc_180017B7A
0x180017b75  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017b7a  add     rsp, 28h
0x180017b7e  pop     rdi
0x180017b7f  pop     rsi
0x180017b80  pop     rbp
0x180017b81  pop     rbx
0x180017b82  retn
0x180017b83  mov     rcx, [rsp+48h]; this
0x180017b88  mov     edx, 0A0Bh; void *
0x180017b8d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
