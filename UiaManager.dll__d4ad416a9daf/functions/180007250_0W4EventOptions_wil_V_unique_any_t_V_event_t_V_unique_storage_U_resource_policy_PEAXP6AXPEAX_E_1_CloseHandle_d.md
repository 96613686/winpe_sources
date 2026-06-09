# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x180007250`
- end: `0x1800072bf`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007d688`

## callees

- `0x180007250`
- `0x1800075b4`
- `0x18002a514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000727a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000727a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007288`

## string_xrefs

- `0x1800072ad`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        _QWORD *a1,
        int *a2)
{
  int v3; // r8d
  HANDLE Event; // rdi
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

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
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x180007250  mov     [rsp+arg_8], rbx
0x180007255  mov     [rsp+arg_0], rcx
0x18000725a  push    rdi
0x18000725b  sub     rsp, 20h
0x18000725f  mov     rbx, rcx
0x180007262  mov     r8d, [rdx]
0x180007265  mov     qword ptr [rcx], 0
0x18000726c  and     r8d, 3; dwFlags
0x180007270  xor     edx, edx; lpName
0x180007272  xor     ecx, ecx; lpEventAttributes
0x180007274  mov     r9d, 1F0003h; dwDesiredAccess
0x18000727a  call    cs:__imp_CreateEventExW
0x180007280  mov     rdi, rax
0x180007283  test    rax, rax
0x180007286  jz      short loc_1800072A8
0x180007288  call    cs:__imp_GetLastError
0x18000728e  mov     rdx, rdi
0x180007291  mov     rcx, rbx
0x180007294  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007299  nop
0x18000729a  mov     rax, rbx
0x18000729d  mov     rbx, [rsp+28h+arg_8]
0x1800072a2  add     rsp, 20h
0x1800072a6  pop     rdi
0x1800072a7  retn
0x1800072a8  mov     rcx, [rsp+28h]; this
0x1800072ad  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800072b4  mov     edx, 1CC8h; void *
0x1800072b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
