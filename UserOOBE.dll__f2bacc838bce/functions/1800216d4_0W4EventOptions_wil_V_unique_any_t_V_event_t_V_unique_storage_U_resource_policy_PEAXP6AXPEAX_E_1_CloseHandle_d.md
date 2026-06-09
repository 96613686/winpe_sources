# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x1800216d4`
- end: `0x180021737`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027510`
- `0x18002e840`

## callees

- `0x180007e34`
- `0x1800164a0`
- `0x1800216d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800216fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800216fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170c`

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
0x1800216d4  mov     [rsp+arg_8], rbx
0x1800216d9  mov     [rsp+arg_0], rcx
0x1800216de  push    rdi
0x1800216df  sub     rsp, 20h
0x1800216e3  mov     rbx, rcx
0x1800216e6  mov     r8d, [rdx]
0x1800216e9  mov     qword ptr [rcx], 0
0x1800216f0  and     r8d, 3; dwFlags
0x1800216f4  xor     edx, edx; lpName
0x1800216f6  xor     ecx, ecx; lpEventAttributes
0x1800216f8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800216fe  call    cs:__imp_CreateEventExW
0x180021704  mov     rdi, rax
0x180021707  test    rax, rax
0x18002170a  jz      short loc_18002172C
0x18002170c  call    cs:__imp_GetLastError
0x180021712  mov     rdx, rdi
0x180021715  mov     rcx, rbx
0x180021718  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002171d  nop
0x18002171e  mov     rax, rbx
0x180021721  mov     rbx, [rsp+28h+arg_8]
0x180021726  add     rsp, 20h
0x18002172a  pop     rdi
0x18002172b  retn
0x18002172c  mov     rcx, [rsp+28h]; this
0x180021731  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
