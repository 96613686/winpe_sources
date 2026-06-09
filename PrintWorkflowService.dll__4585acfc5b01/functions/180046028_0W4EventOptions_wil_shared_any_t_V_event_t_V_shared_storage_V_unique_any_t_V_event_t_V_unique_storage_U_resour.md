# ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x180046028`
- end: `0x180046093`
- name: `??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `107`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180046fc0`

## callees

- `0x180011a98`
- `0x180046028`
- `0x180047a28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004605a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004605a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046068`

## pseudocode

```c
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
0x180046028  mov     [rsp+arg_8], rbx
0x18004602d  mov     [rsp+arg_0], rcx
0x180046032  push    rdi
0x180046033  sub     rsp, 20h
0x180046037  mov     rbx, rcx
0x18004603a  mov     r8d, [rdx]
0x18004603d  mov     qword ptr [rcx], 0
0x180046044  mov     qword ptr [rcx+8], 0
0x18004604c  and     r8d, 3; dwFlags
0x180046050  xor     edx, edx; lpName
0x180046052  xor     ecx, ecx; lpEventAttributes
0x180046054  mov     r9d, 1F0003h; dwDesiredAccess
0x18004605a  call    cs:__imp_CreateEventExW
0x180046060  mov     rdi, rax
0x180046063  test    rax, rax
0x180046066  jz      short loc_180046088
0x180046068  call    cs:__imp_GetLastError
0x18004606e  mov     rdx, rdi
0x180046071  mov     rcx, rbx
0x180046074  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180046079  nop
0x18004607a  mov     rax, rbx
0x18004607d  mov     rbx, [rsp+28h+arg_8]
0x180046082  add     rsp, 20h
0x180046086  pop     rdi
0x180046087  retn
0x180046088  mov     rcx, [rsp+28h]; this
0x18004608d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
