# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18001dd3c`
- end: `0x18001ddd3`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001de38`
- `0x18001e1ac`

## callees

- `0x18000944c`
- `0x18001d95c`
- `0x18001dd3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dd64`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001dd64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dd8b`

## string_xrefs

- `0x18001ddc1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        void **a1,
        int *a2)
{
  int v3; // r8d
  HANDLE Event; // rsi
  const char *v5; // r9
  void *v6; // rdi
  DWORD LastError; // ebp
  unsigned int v8; // r8d
  const char *v9; // r9
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
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(LastError);
  }
  *a1 = Event;
  return a1;
}

```

## disassembly

```asm
0x18001dd3c  mov     [rsp+arg_0], rcx
0x18001dd41  push    rbx
0x18001dd42  push    rbp
0x18001dd43  push    rsi
0x18001dd44  push    rdi
0x18001dd45  sub     rsp, 28h
0x18001dd49  mov     rbx, rcx
0x18001dd4c  mov     r8d, [rdx]
0x18001dd4f  mov     qword ptr [rcx], 0
0x18001dd56  and     r8d, 3; dwFlags
0x18001dd5a  xor     edx, edx; lpName
0x18001dd5c  xor     ecx, ecx; lpEventAttributes
0x18001dd5e  mov     r9d, 1F0003h; dwDesiredAccess
0x18001dd64  call    cs:__imp_CreateEventExW
0x18001dd6a  mov     rsi, rax
0x18001dd6d  test    rax, rax
0x18001dd70  jz      short loc_18001DDBC
0x18001dd72  call    cs:__imp_GetLastError
0x18001dd78  mov     rdi, [rbx]
0x18001dd7b  test    rdi, rdi
0x18001dd7e  jz      short loc_18001DDA2
0x18001dd80  call    cs:__imp_GetLastError
0x18001dd86  mov     ebp, eax
0x18001dd88  mov     rcx, rdi; hObject
0x18001dd8b  call    cs:__imp_CloseHandle
0x18001dd91  mov     rcx, [rsp+48h]; this
0x18001dd96  test    eax, eax
0x18001dd98  jz      short loc_18001DDB1
0x18001dd9a  mov     ecx, ebp; dwErrCode
0x18001dd9c  call    cs:__imp_SetLastError
0x18001dda2  mov     [rbx], rsi
0x18001dda5  mov     rax, rbx
0x18001dda8  add     rsp, 28h
0x18001ddac  pop     rdi
0x18001ddad  pop     rsi
0x18001ddae  pop     rbp
0x18001ddaf  pop     rbx
0x18001ddb0  retn
0x18001ddb1  mov     edx, 0A0Bh; void *
0x18001ddb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ddbc  mov     rcx, [rsp+48h]; this
0x18001ddc1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ddc8  mov     edx, 1CC8h; void *
0x18001ddcd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
