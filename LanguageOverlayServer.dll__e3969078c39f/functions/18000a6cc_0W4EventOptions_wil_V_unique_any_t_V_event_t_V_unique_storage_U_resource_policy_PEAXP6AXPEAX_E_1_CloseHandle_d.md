# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18000a6cc`
- end: `0x18000a76a`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `158`
- prototype: `void **__fastcall(void **, int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011ccc`
- `0x180044864`
- `0x1800452d8`
- `0x18004b2f8`
- `0x18004be00`
- `0x18004c324`
- `0x180050b40`
- `0x180050f50`
- `0x18005cccc`

## callees

- `0x18000a008`
- `0x18000a6cc`
- `0x180011318`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a6f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a6f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a710`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a72c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a72c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a71b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a71b`

## string_xrefs

- `0x18000a741`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000a758`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void **__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        void **a1,
        int *a2)
{
  int v3; // r8d
  HANDLE Event; // rsi
  const char *v5; // r9
  void *v6; // rdi
  DWORD LastError; // ebp
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  Event = CreateEventExW(0, 0, v3 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  v6 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(LastError);
  }
  *a1 = Event;
  return a1;
}

```

## disassembly

```asm
0x18000a6cc  mov     [rsp+arg_0], rcx
0x18000a6d1  push    rbx
0x18000a6d2  push    rbp
0x18000a6d3  push    rsi
0x18000a6d4  push    rdi
0x18000a6d5  sub     rsp, 28h
0x18000a6d9  mov     rbx, rcx
0x18000a6dc  mov     r8d, [rdx]
0x18000a6df  mov     qword ptr [rcx], 0
0x18000a6e6  and     r8d, 3; dwFlags
0x18000a6ea  xor     edx, edx; lpName
0x18000a6ec  xor     ecx, ecx; lpEventAttributes
0x18000a6ee  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a6f4  call    cs:__imp_CreateEventExW
0x18000a6fa  mov     rsi, rax
0x18000a6fd  test    rax, rax
0x18000a700  jz      short loc_18000A753
0x18000a702  call    cs:__imp_GetLastError
0x18000a708  mov     rdi, [rbx]
0x18000a70b  test    rdi, rdi
0x18000a70e  jz      short loc_18000A732
0x18000a710  call    cs:__imp_GetLastError
0x18000a716  mov     ebp, eax
0x18000a718  mov     rcx, rdi; hObject
0x18000a71b  call    cs:__imp_CloseHandle
0x18000a721  mov     rcx, [rsp+48h]; this
0x18000a726  test    eax, eax
0x18000a728  jz      short loc_18000A741
0x18000a72a  mov     ecx, ebp; dwErrCode
0x18000a72c  call    cs:__imp_SetLastError
0x18000a732  mov     [rbx], rsi
0x18000a735  mov     rax, rbx
0x18000a738  add     rsp, 28h
0x18000a73c  pop     rdi
0x18000a73d  pop     rsi
0x18000a73e  pop     rbp
0x18000a73f  pop     rbx
0x18000a740  retn
0x18000a741  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a748  mov     edx, 0A0Bh; void *
0x18000a74d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a753  mov     rcx, [rsp+48h]; this
0x18000a758  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a75f  mov     edx, 1CC8h; void *
0x18000a764  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
