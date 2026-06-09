# ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x180024898`
- end: `0x180024910`
- name: `??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `120`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180024f40`
- `0x180026280`
- `0x180026b60`

## callees

- `0x180024898`
- `0x180027b60`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800248ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800248ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
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
  a1[1] = 0;
  Event = CreateEventExW(0, 0, v3 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v6, v7);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x180024898  mov     [rsp+arg_8], rbx
0x18002489d  mov     [rsp+arg_0], rcx
0x1800248a2  push    rdi
0x1800248a3  sub     rsp, 20h
0x1800248a7  mov     rbx, rcx
0x1800248aa  mov     r8d, [rdx]
0x1800248ad  mov     qword ptr [rcx], 0
0x1800248b4  mov     qword ptr [rcx+8], 0
0x1800248bc  and     r8d, 3; dwFlags
0x1800248c0  xor     edx, edx; lpName
0x1800248c2  xor     ecx, ecx; lpEventAttributes
0x1800248c4  mov     r9d, 1F0003h; dwDesiredAccess
0x1800248ca  call    cs:__imp_CreateEventExW
0x1800248d1  nop     dword ptr [rax+rax+00h]
0x1800248d6  mov     rdi, rax
0x1800248d9  test    rax, rax
0x1800248dc  jz      short loc_180024905
0x1800248de  call    cs:__imp_GetLastError
0x1800248e5  nop     dword ptr [rax+rax+00h]
0x1800248ea  mov     rdx, rdi
0x1800248ed  mov     rcx, rbx
0x1800248f0  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x1800248f5  nop
0x1800248f6  mov     rax, rbx
0x1800248f9  mov     rbx, [rsp+28h+arg_8]
0x1800248fe  add     rsp, 20h
0x180024902  pop     rdi
0x180024903  retn
0x180024905  mov     rcx, [rsp+28h]; this
0x18002490a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
