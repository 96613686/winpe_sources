# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180018f0c`
- end: `0x180018f97`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `139`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800198c8`
- `0x18006e878`

## callees

- `0x18000c018`
- `0x180018750`
- `0x180018f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018f30`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180018f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f57`

## string_xrefs

- `0x180018f7a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  void *v5; // rdx
  HANDLE Event; // rbp
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rbx
  DWORD LastError; // esi
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(a4, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v5, v7, v8);
  GetLastError();
  v9 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v9) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x180018f0c  push    rbx
0x180018f0e  push    rbp
0x180018f0f  push    rsi
0x180018f10  push    rdi
0x180018f11  sub     rsp, 28h
0x180018f15  and     edx, 3
0x180018f18  mov     r10, r9
0x180018f1b  mov     rax, r8
0x180018f1e  mov     rdi, rcx
0x180018f21  mov     r8d, edx; dwFlags
0x180018f24  mov     r9d, 1F0003h; dwDesiredAccess
0x180018f2a  mov     rdx, rax; lpName
0x180018f2d  mov     rcx, r10; lpEventAttributes
0x180018f30  call    cs:__imp_CreateEventExW
0x180018f36  mov     rbp, rax
0x180018f39  test    rax, rax
0x180018f3c  jz      short loc_180018F8C
0x180018f3e  call    cs:__imp_GetLastError
0x180018f44  mov     rbx, [rdi]
0x180018f47  test    rbx, rbx
0x180018f4a  jz      short loc_180018F69
0x180018f4c  call    cs:__imp_GetLastError
0x180018f52  mov     rcx, rbx; hObject
0x180018f55  mov     esi, eax
0x180018f57  call    cs:__imp_CloseHandle
0x180018f5d  test    eax, eax
0x180018f5f  jz      short loc_180018F75
0x180018f61  mov     ecx, esi; dwErrCode
0x180018f63  call    cs:__imp_SetLastError
0x180018f69  mov     [rdi], rbp
0x180018f6c  add     rsp, 28h
0x180018f70  pop     rdi
0x180018f71  pop     rsi
0x180018f72  pop     rbp
0x180018f73  pop     rbx
0x180018f74  retn
0x180018f75  mov     rcx, [rsp+48h]; this
0x180018f7a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018f81  mov     edx, 0A0Bh; void *
0x180018f86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018f8c  mov     rcx, [rsp+48h]; this
0x180018f91  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
