# ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18001607c`
- end: `0x1800160f3`
- name: `??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `44`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007404`
- `0x180015d30`
- `0x180015e54`
- `0x18001bbdc`
- `0x18001bdac`
- `0x18001bf80`
- `0x18001c144`
- `0x18001c308`
- `0x18001c4f0`
- `0x18001c6d8`
- `0x18001c89c`
- `0x18001ca70`
- `0x18001cc34`
- `0x18001cdf8`
- `0x18001cfbc`
- `0x18001d180`
- `0x18001d344`
- `0x18001d4f8`
- `0x18001d6bc`
- `0x18001dab8`
- `0x18001dc7c`
- `0x18001de84`
- `0x18001e048`
- `0x18001e20c`
- `0x18001e3d0`
- `0x18001e594`
- `0x18001e758`
- `0x18001e91c`
- `0x18001eae0`
- `0x18001eca4`
- `0x18001ee74`
- `0x18001f0ec`
- `0x18001f7d4`
- `0x18001f9d4`
- `0x18002039c`
- `0x180020cc4`
- `0x180020e40`
- `0x18002154c`
- `0x1800217c8`
- `0x180022204`
- `0x18006dbd0`
- `0x18006df9c`
- `0x1800756cc`
- `0x18007d688`

## callees

- `0x18001607c`
- `0x1800160fc`
- `0x18002a514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800160ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800160ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800160bc`

## string_xrefs

- `0x1800160e1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
0x18001607c  mov     [rsp+arg_8], rbx
0x180016081  mov     [rsp+arg_0], rcx
0x180016086  push    rdi
0x180016087  sub     rsp, 20h
0x18001608b  mov     rbx, rcx
0x18001608e  mov     r8d, [rdx]
0x180016091  mov     qword ptr [rcx], 0
0x180016098  mov     qword ptr [rcx+8], 0
0x1800160a0  and     r8d, 3; dwFlags
0x1800160a4  xor     edx, edx; lpName
0x1800160a6  xor     ecx, ecx; lpEventAttributes
0x1800160a8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800160ae  call    cs:__imp_CreateEventExW
0x1800160b4  mov     rdi, rax
0x1800160b7  test    rax, rax
0x1800160ba  jz      short loc_1800160DC
0x1800160bc  call    cs:__imp_GetLastError
0x1800160c2  mov     rdx, rdi
0x1800160c5  mov     rcx, rbx
0x1800160c8  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x1800160cd  nop
0x1800160ce  mov     rax, rbx
0x1800160d1  mov     rbx, [rsp+28h+arg_8]
0x1800160d6  add     rsp, 20h
0x1800160da  pop     rdi
0x1800160db  retn
0x1800160dc  mov     rcx, [rsp+28h]; this
0x1800160e1  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800160e8  mov     edx, 1CC8h; void *
0x1800160ed  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
