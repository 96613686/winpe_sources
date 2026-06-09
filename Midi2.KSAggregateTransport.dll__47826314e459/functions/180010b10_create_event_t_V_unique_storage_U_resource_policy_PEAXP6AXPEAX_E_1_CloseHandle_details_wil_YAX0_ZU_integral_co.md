# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180010b10`
- end: `0x180010b8c`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d1e8`
- `0x180049100`

## callees

- `0x18000c684`
- `0x180010438`
- `0x180010b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010b2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010b2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b53`

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
0x180010b10  push    rbx
0x180010b12  push    rbp
0x180010b13  push    rsi
0x180010b14  push    rdi
0x180010b15  sub     rsp, 28h
0x180010b19  and     edx, 3
0x180010b1c  mov     rdi, rcx
0x180010b1f  mov     r8d, edx; dwFlags
0x180010b22  mov     r9d, 1F0003h; dwDesiredAccess
0x180010b28  xor     edx, edx; lpName
0x180010b2a  xor     ecx, ecx; lpEventAttributes
0x180010b2c  call    cs:__imp_CreateEventExW
0x180010b32  mov     rbp, rax
0x180010b35  test    rax, rax
0x180010b38  jz      short loc_180010B81
0x180010b3a  call    cs:__imp_GetLastError
0x180010b40  mov     rbx, [rdi]
0x180010b43  test    rbx, rbx
0x180010b46  jz      short loc_180010B65
0x180010b48  call    cs:__imp_GetLastError
0x180010b4e  mov     rcx, rbx; hObject
0x180010b51  mov     esi, eax
0x180010b53  call    cs:__imp_CloseHandle
0x180010b59  test    eax, eax
0x180010b5b  jz      short loc_180010B71
0x180010b5d  mov     ecx, esi; dwErrCode
0x180010b5f  call    cs:__imp_SetLastError
0x180010b65  mov     [rdi], rbp
0x180010b68  add     rsp, 28h
0x180010b6c  pop     rdi
0x180010b6d  pop     rsi
0x180010b6e  pop     rbp
0x180010b6f  pop     rbx
0x180010b70  retn
0x180010b71  mov     rcx, [rsp+48h]; this
0x180010b76  mov     edx, 0A0Bh; void *
0x180010b7b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b81  mov     rcx, [rsp+48h]; this
0x180010b86  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
