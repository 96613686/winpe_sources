# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000ae7c`
- end: `0x18000af0e`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001aa0`
- `0x18000a9d0`

## callees

- `0x18000717c`
- `0x18000ab2c`
- `0x18000ae7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ae9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ae9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aebf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aeca`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        char a2,
        const WCHAR *a3)
{
  void *v3; // rdx
  HANDLE Event; // rsi
  unsigned int v5; // r8d
  const char *v6; // r9
  HANDLE v7; // rbx
  DWORD LastError; // edi
  unsigned int v9; // r8d
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(0, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  v7 = AppPrioritizationUserSession::m_stopWin32MessageEvent;
  if ( AppPrioritizationUserSession::m_stopWin32MessageEvent )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    SetLastError(LastError);
  }
  AppPrioritizationUserSession::m_stopWin32MessageEvent = Event;
}

```

## disassembly

```asm
0x18000ae7c  mov     [rsp+arg_0], rbx
0x18000ae81  mov     [rsp+arg_8], rsi
0x18000ae86  push    rdi
0x18000ae87  sub     rsp, 20h
0x18000ae8b  and     edx, 3
0x18000ae8e  mov     rax, r8
0x18000ae91  mov     r8d, edx; dwFlags
0x18000ae94  mov     r9d, 1F0003h; dwDesiredAccess
0x18000ae9a  mov     rdx, rax; lpName
0x18000ae9d  xor     ecx, ecx; lpEventAttributes
0x18000ae9f  call    cs:__imp_CreateEventExW
0x18000aea5  mov     rsi, rax
0x18000aea8  test    rax, rax
0x18000aeab  jz      short loc_18000AF03
0x18000aead  call    cs:__imp_GetLastError
0x18000aeb3  mov     rbx, cs:?m_stopWin32MessageEvent@AppPrioritizationUserSession@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18000aeba  test    rbx, rbx
0x18000aebd  jz      short loc_18000AEDC
0x18000aebf  call    cs:__imp_GetLastError
0x18000aec5  mov     rcx, rbx; hObject
0x18000aec8  mov     edi, eax
0x18000aeca  call    cs:__imp_CloseHandle
0x18000aed0  test    eax, eax
0x18000aed2  jz      short loc_18000AEF3
0x18000aed4  mov     ecx, edi; dwErrCode
0x18000aed6  call    cs:__imp_SetLastError
0x18000aedc  mov     rbx, [rsp+28h+arg_0]
0x18000aee1  mov     cs:?m_stopWin32MessageEvent@AppPrioritizationUserSession@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi
0x18000aee8  mov     rsi, [rsp+28h+arg_8]
0x18000aeed  add     rsp, 20h
0x18000aef1  pop     rdi
0x18000aef2  retn
0x18000aef3  mov     rcx, [rsp+28h]; this
0x18000aef8  mov     edx, 0A0Bh; void *
0x18000aefd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000af03  mov     rcx, [rsp+28h]; this
0x18000af08  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
