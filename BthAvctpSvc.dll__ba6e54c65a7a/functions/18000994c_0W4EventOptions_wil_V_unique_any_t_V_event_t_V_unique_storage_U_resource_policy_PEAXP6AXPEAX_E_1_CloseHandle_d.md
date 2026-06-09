# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18000994c`
- end: `0x1800099bb`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `111`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a9b8`
- `0x18000ab10`
- `0x18000ae84`
- `0x18000f268`
- `0x18000f580`
- `0x180026ef0`
- `0x1800412d8`
- `0x180052070`
- `0x180052110`

## callees

- `0x180008d08`
- `0x18000994c`
- `0x18000dca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009976`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009984`

## string_xrefs

- `0x1800099a9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18000994c  mov     [rsp+arg_8], rbx
0x180009951  mov     [rsp+arg_0], rcx
0x180009956  push    rdi
0x180009957  sub     rsp, 20h
0x18000995b  mov     rbx, rcx
0x18000995e  mov     r8d, [rdx]
0x180009961  mov     qword ptr [rcx], 0
0x180009968  and     r8d, 3; dwFlags
0x18000996c  xor     edx, edx; lpName
0x18000996e  xor     ecx, ecx; lpEventAttributes
0x180009970  mov     r9d, 1F0003h; dwDesiredAccess
0x180009976  call    cs:__imp_CreateEventExW
0x18000997c  mov     rdi, rax
0x18000997f  test    rax, rax
0x180009982  jz      short loc_1800099A4
0x180009984  call    cs:__imp_GetLastError
0x18000998a  mov     rdx, rdi
0x18000998d  mov     rcx, rbx
0x180009990  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009995  nop
0x180009996  mov     rax, rbx
0x180009999  mov     rbx, [rsp+28h+arg_8]
0x18000999e  add     rsp, 20h
0x1800099a2  pop     rdi
0x1800099a3  retn
0x1800099a4  mov     rcx, [rsp+28h]; this
0x1800099a9  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800099b0  mov     edx, 1CC8h; void *
0x1800099b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
