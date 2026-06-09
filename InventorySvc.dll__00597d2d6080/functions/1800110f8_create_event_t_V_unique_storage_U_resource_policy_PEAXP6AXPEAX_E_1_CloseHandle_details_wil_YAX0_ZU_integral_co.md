# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800110f8`
- end: `0x18001117d`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011720`
- `0x18001ff40`
- `0x18002867c`
- `0x18002e458`
- `0x18002fd04`
- `0x1800c0f44`
- `0x1800c3e78`
- `0x1800c860c`

## callees

- `0x18000fc4c`
- `0x1800108d4`
- `0x1800110f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011116`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001113d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001113d`

## string_xrefs

- `0x180011160`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        __int64 a2,
        __int64 a3,
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

  Event = CreateEventExW(a4, 0, 1u, 0x1F0003u);
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
0x1800110f8  push    rbx
0x1800110fa  push    rbp
0x1800110fb  push    rsi
0x1800110fc  push    rdi
0x1800110fd  sub     rsp, 28h
0x180011101  mov     rax, r9
0x180011104  xor     edx, edx; lpName
0x180011106  mov     rdi, rcx
0x180011109  mov     r9d, 1F0003h; dwDesiredAccess
0x18001110f  mov     rcx, rax; lpEventAttributes
0x180011112  lea     r8d, [rdx+1]; dwFlags
0x180011116  call    cs:__imp_CreateEventExW
0x18001111c  mov     rbp, rax
0x18001111f  test    rax, rax
0x180011122  jz      short loc_180011172
0x180011124  call    cs:__imp_GetLastError
0x18001112a  mov     rbx, [rdi]
0x18001112d  test    rbx, rbx
0x180011130  jz      short loc_18001114F
0x180011132  call    cs:__imp_GetLastError
0x180011138  mov     rcx, rbx; hObject
0x18001113b  mov     esi, eax
0x18001113d  call    cs:__imp_CloseHandle
0x180011143  test    eax, eax
0x180011145  jz      short loc_18001115B
0x180011147  mov     ecx, esi; dwErrCode
0x180011149  call    cs:__imp_SetLastError
0x18001114f  mov     [rdi], rbp
0x180011152  add     rsp, 28h
0x180011156  pop     rdi
0x180011157  pop     rsi
0x180011158  pop     rbp
0x180011159  pop     rbx
0x18001115a  retn
0x18001115b  mov     rcx, [rsp+48h]; this
0x180011160  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011167  mov     edx, 0A0Bh; void *
0x18001116c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011172  mov     rcx, [rsp+48h]; this
0x180011177  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
