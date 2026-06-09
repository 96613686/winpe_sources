# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_failfast_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x1800e4140`
- end: `0x1800e419d`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_failfast_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800e41a4`

## callees

- `0x180061e54`
- `0x1800e4140`
- `0x1800e44a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800e4165`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800e4165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e4173`

## pseudocode

```c
_QWORD *__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_failfast_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        _QWORD *a1,
        int *a2)
{
  int v2; // r8d
  void *v4; // rdx
  HANDLE Event; // rdi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a2;
  *a1 = 0;
  Event = CreateEventExW(0, 0, v2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::FailFast_GetLastError(retaddr, v4, v6, v7);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x1800e4140  mov     [rsp+arg_0], rbx
0x1800e4145  push    rdi
0x1800e4146  sub     rsp, 20h
0x1800e414a  mov     r8d, [rdx]
0x1800e414d  mov     rbx, rcx
0x1800e4150  mov     qword ptr [rcx], 0
0x1800e4157  and     r8d, 3; dwFlags
0x1800e415b  xor     ecx, ecx; lpEventAttributes
0x1800e415d  xor     edx, edx; lpName
0x1800e415f  mov     r9d, 1F0003h; dwDesiredAccess
0x1800e4165  call    cs:__imp_CreateEventExW
0x1800e416b  mov     rdi, rax
0x1800e416e  test    rax, rax
0x1800e4171  jz      short loc_1800E4192
0x1800e4173  call    cs:__imp_GetLastError
0x1800e4179  mov     rdx, rdi
0x1800e417c  mov     rcx, rbx
0x1800e417f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800e4184  mov     rax, rbx
0x1800e4187  mov     rbx, [rsp+28h+arg_0]
0x1800e418c  add     rsp, 20h
0x1800e4190  pop     rdi
0x1800e4191  retn
0x1800e4192  mov     rcx, [rsp+28h]; this
0x1800e4197  call    ?FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_GetLastError(void *,uint,char const *)
```
