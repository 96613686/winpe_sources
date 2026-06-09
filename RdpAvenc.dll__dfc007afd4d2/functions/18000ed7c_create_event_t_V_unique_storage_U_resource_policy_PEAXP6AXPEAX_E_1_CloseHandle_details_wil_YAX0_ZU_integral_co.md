# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000ed7c`
- end: `0x18000ee04`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c5a0`
- `0x1800363a8`
- `0x1800425b4`
- `0x180050c50`
- `0x1800530c0`
- `0x180053e7c`
- `0x180057e0c`

## callees

- `0x18000b07c`
- `0x18000e82c`
- `0x18000ed7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ed98`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000ed98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000edcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edbf`

## string_xrefs

- `0x18000edf2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2)
{
  HANDLE Event; // rbp
  const char *v4; // r9
  void *v5; // rbx
  DWORD LastError; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  v5 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x18000ed7c  push    rbx
0x18000ed7e  push    rbp
0x18000ed7f  push    rsi
0x18000ed80  push    rdi
0x18000ed81  sub     rsp, 28h
0x18000ed85  and     edx, 3
0x18000ed88  mov     rdi, rcx
0x18000ed8b  mov     r8d, edx; dwFlags
0x18000ed8e  mov     r9d, 1F0003h; dwDesiredAccess
0x18000ed94  xor     edx, edx; lpName
0x18000ed96  xor     ecx, ecx; lpEventAttributes
0x18000ed98  call    cs:__imp_CreateEventExW
0x18000ed9e  mov     rbp, rax
0x18000eda1  test    rax, rax
0x18000eda4  jz      short loc_18000EDED
0x18000eda6  call    cs:__imp_GetLastError
0x18000edac  mov     rbx, [rdi]
0x18000edaf  test    rbx, rbx
0x18000edb2  jz      short loc_18000EDD1
0x18000edb4  call    cs:__imp_GetLastError
0x18000edba  mov     rcx, rbx; hObject
0x18000edbd  mov     esi, eax
0x18000edbf  call    cs:__imp_CloseHandle
0x18000edc5  test    eax, eax
0x18000edc7  jz      short loc_18000EDDD
0x18000edc9  mov     ecx, esi; dwErrCode
0x18000edcb  call    cs:__imp_SetLastError
0x18000edd1  mov     [rdi], rbp
0x18000edd4  add     rsp, 28h
0x18000edd8  pop     rdi
0x18000edd9  pop     rsi
0x18000edda  pop     rbp
0x18000eddb  pop     rbx
0x18000eddc  retn
0x18000eddd  mov     rcx, [rsp+48h]; this
0x18000ede2  mov     edx, 0A0Bh; void *
0x18000ede7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000eded  mov     rcx, [rsp+48h]; this
0x18000edf2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000edf9  mov     edx, 1CC8h; void *
0x18000edfe  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
