# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000d13c`
- end: `0x18000d1b8`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc90`
- `0x1800285a0`

## callees

- `0x18000bb04`
- `0x18000d018`
- `0x18000d13c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d158`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d18b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d174`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d17f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d17f`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2)
{
  void *v3; // rdx
  HANDLE Event; // rbp
  unsigned int v5; // r8d
  const char *v6; // r9
  void *v7; // rbx
  DWORD LastError; // esi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  v7 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x18000d13c  push    rbx
0x18000d13e  push    rbp
0x18000d13f  push    rsi
0x18000d140  push    rdi
0x18000d141  sub     rsp, 28h
0x18000d145  and     edx, 3
0x18000d148  mov     rdi, rcx
0x18000d14b  mov     r8d, edx; dwFlags
0x18000d14e  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d154  xor     edx, edx; lpName
0x18000d156  xor     ecx, ecx; lpEventAttributes
0x18000d158  call    cs:__imp_CreateEventExW
0x18000d15e  mov     rbp, rax
0x18000d161  test    rax, rax
0x18000d164  jz      short loc_18000D1AD
0x18000d166  call    cs:__imp_GetLastError
0x18000d16c  mov     rbx, [rdi]
0x18000d16f  test    rbx, rbx
0x18000d172  jz      short loc_18000D191
0x18000d174  call    cs:__imp_GetLastError
0x18000d17a  mov     rcx, rbx; hObject
0x18000d17d  mov     esi, eax
0x18000d17f  call    cs:__imp_CloseHandle
0x18000d185  test    eax, eax
0x18000d187  jz      short loc_18000D19D
0x18000d189  mov     ecx, esi; dwErrCode
0x18000d18b  call    cs:__imp_SetLastError
0x18000d191  mov     [rdi], rbp
0x18000d194  add     rsp, 28h
0x18000d198  pop     rdi
0x18000d199  pop     rsi
0x18000d19a  pop     rbp
0x18000d19b  pop     rbx
0x18000d19c  retn
0x18000d19d  mov     rcx, [rsp+48h]; this
0x18000d1a2  mov     edx, 0A0Bh; void *
0x18000d1a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d1ad  mov     rcx, [rsp+48h]; this
0x18000d1b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
