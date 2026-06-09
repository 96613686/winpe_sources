# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000d044`
- end: `0x18000d0bb`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000caac`
- `0x180011700`

## callees

- `0x180005518`
- `0x180008fdc`
- `0x18000d044`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d05d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d05d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d090`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d084`

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
0x18000d044  push    rbx
0x18000d046  push    rbp
0x18000d047  push    rsi
0x18000d048  push    rdi
0x18000d049  sub     rsp, 28h
0x18000d04d  mov     rdi, rcx
0x18000d050  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d056  xor     ecx, ecx; lpEventAttributes
0x18000d058  xor     r8d, r8d; dwFlags
0x18000d05b  xor     edx, edx; lpName
0x18000d05d  call    cs:__imp_CreateEventExW
0x18000d063  mov     rbp, rax
0x18000d066  test    rax, rax
0x18000d069  jz      short loc_18000D09D
0x18000d06b  call    cs:__imp_GetLastError
0x18000d071  mov     rbx, [rdi]
0x18000d074  test    rbx, rbx
0x18000d077  jz      short loc_18000D096
0x18000d079  call    cs:__imp_GetLastError
0x18000d07f  mov     rcx, rbx; hObject
0x18000d082  mov     esi, eax
0x18000d084  call    cs:__imp_CloseHandle
0x18000d08a  test    eax, eax
0x18000d08c  jz      short loc_18000D0AB
0x18000d08e  mov     ecx, esi; dwErrCode
0x18000d090  call    cs:__imp_SetLastError
0x18000d096  mov     [rdi], rbp
0x18000d099  xor     eax, eax
0x18000d09b  jmp     short loc_18000D0A2
0x18000d09d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d0a2  add     rsp, 28h
0x18000d0a6  pop     rdi
0x18000d0a7  pop     rsi
0x18000d0a8  pop     rbp
0x18000d0a9  pop     rbx
0x18000d0aa  retn
0x18000d0ab  mov     rcx, [rsp+48h]; this
0x18000d0b0  mov     edx, 0A0Bh; void *
0x18000d0b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
