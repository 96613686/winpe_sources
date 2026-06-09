# ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x1800238ec`
- end: `0x180023963`
- name: `??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `119`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023d60`
- `0x180041ad4`

## callees

- `0x1800109a8`
- `0x180014d04`
- `0x1800238ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002391e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002391e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002392c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002392c`

## string_xrefs

- `0x180023951`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        _QWORD *a1,
        int *a2)
{
  int v3; // r8d
  HANDLE Event; // rdi
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  a1[1] = 0;
  Event = CreateEventExW(0, 0, v3 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x1800238ec  mov     [rsp+arg_8], rbx
0x1800238f1  mov     [rsp+arg_0], rcx
0x1800238f6  push    rdi
0x1800238f7  sub     rsp, 20h
0x1800238fb  mov     rbx, rcx
0x1800238fe  mov     r8d, [rdx]
0x180023901  mov     qword ptr [rcx], 0
0x180023908  mov     qword ptr [rcx+8], 0
0x180023910  and     r8d, 3; dwFlags
0x180023914  xor     edx, edx; lpName
0x180023916  xor     ecx, ecx; lpEventAttributes
0x180023918  mov     r9d, 1F0003h; dwDesiredAccess
0x18002391e  call    cs:__imp_CreateEventExW
0x180023924  mov     rdi, rax
0x180023927  test    rax, rax
0x18002392a  jz      short loc_18002394C
0x18002392c  call    cs:__imp_GetLastError
0x180023932  mov     rdx, rdi
0x180023935  mov     rcx, rbx
0x180023938  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18002393d  nop
0x18002393e  mov     rax, rbx
0x180023941  mov     rbx, [rsp+28h+arg_8]
0x180023946  add     rsp, 20h
0x18002394a  pop     rdi
0x18002394b  retn
0x18002394c  mov     rcx, [rsp+28h]; this
0x180023951  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180023958  mov     edx, 1CC8h; void *
0x18002395d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
