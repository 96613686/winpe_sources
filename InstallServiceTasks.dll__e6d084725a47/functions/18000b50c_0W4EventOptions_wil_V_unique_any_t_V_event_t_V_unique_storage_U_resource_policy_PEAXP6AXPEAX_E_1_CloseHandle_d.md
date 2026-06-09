# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18000b50c`
- end: `0x18000b56f`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `99`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ca1c`
- `0x1800150ac`
- `0x1800154f4`
- `0x18001abe4`
- `0x18001ae44`
- `0x18001c58c`

## callees

- `0x18000a958`
- `0x18000b50c`
- `0x180010128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000b536`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000b536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b544`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        _QWORD *a1,
        int *a2)
{
  int v3; // r8d
  void *v4; // rdx
  HANDLE Event; // rdi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  Event = CreateEventExW(0, 0, v3 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v6, v7);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x18000b50c  mov     [rsp+arg_8], rbx
0x18000b511  mov     [rsp+arg_0], rcx
0x18000b516  push    rdi
0x18000b517  sub     rsp, 20h
0x18000b51b  mov     rbx, rcx
0x18000b51e  mov     r8d, [rdx]
0x18000b521  mov     qword ptr [rcx], 0
0x18000b528  and     r8d, 3; dwFlags
0x18000b52c  xor     edx, edx; lpName
0x18000b52e  xor     ecx, ecx; lpEventAttributes
0x18000b530  mov     r9d, 1F0003h; dwDesiredAccess
0x18000b536  call    cs:__imp_CreateEventExW
0x18000b53c  mov     rdi, rax
0x18000b53f  test    rax, rax
0x18000b542  jz      short loc_18000B564
0x18000b544  call    cs:__imp_GetLastError
0x18000b54a  mov     rdx, rdi
0x18000b54d  mov     rcx, rbx
0x18000b550  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000b555  nop
0x18000b556  mov     rax, rbx
0x18000b559  mov     rbx, [rsp+28h+arg_8]
0x18000b55e  add     rsp, 20h
0x18000b562  pop     rdi
0x18000b563  retn
0x18000b564  mov     rcx, [rsp+28h]; this
0x18000b569  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
