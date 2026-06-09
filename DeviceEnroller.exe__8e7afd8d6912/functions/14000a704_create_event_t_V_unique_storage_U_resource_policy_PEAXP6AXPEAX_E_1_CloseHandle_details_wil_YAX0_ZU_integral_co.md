# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x14000a704`
- end: `0x14000a77b`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `119`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006b8c`
- `0x14000b37c`
- `0x1400521c4`

## callees

- `0x140008298`
- `0x14000a6a8`
- `0x14000a704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000a71d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14000a71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a750`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a744`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a744`

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
0x14000a704  push    rbx
0x14000a706  push    rbp
0x14000a707  push    rsi
0x14000a708  push    rdi
0x14000a709  sub     rsp, 28h
0x14000a70d  mov     rdi, rcx
0x14000a710  mov     r9d, 1F0003h; dwDesiredAccess
0x14000a716  xor     ecx, ecx; lpEventAttributes
0x14000a718  xor     r8d, r8d; dwFlags
0x14000a71b  xor     edx, edx; lpName
0x14000a71d  call    cs:__imp_CreateEventExW
0x14000a723  mov     rbp, rax
0x14000a726  test    rax, rax
0x14000a729  jz      short loc_14000A75D
0x14000a72b  call    cs:__imp_GetLastError
0x14000a731  mov     rbx, [rdi]
0x14000a734  test    rbx, rbx
0x14000a737  jz      short loc_14000A756
0x14000a739  call    cs:__imp_GetLastError
0x14000a73f  mov     rcx, rbx; hObject
0x14000a742  mov     esi, eax
0x14000a744  call    cs:__imp_CloseHandle
0x14000a74a  test    eax, eax
0x14000a74c  jz      short loc_14000A76B
0x14000a74e  mov     ecx, esi; dwErrCode
0x14000a750  call    cs:__imp_SetLastError
0x14000a756  mov     [rdi], rbp
0x14000a759  xor     eax, eax
0x14000a75b  jmp     short loc_14000A762
0x14000a75d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000a762  add     rsp, 28h
0x14000a766  pop     rdi
0x14000a767  pop     rsi
0x14000a768  pop     rbp
0x14000a769  pop     rbx
0x14000a76a  retn
0x14000a76b  mov     rcx, [rsp+48h]; this
0x14000a770  mov     edx, 0A0Bh; void *
0x14000a775  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
