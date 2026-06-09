# ??0?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@PEBG@Z

- ea: `0x1800111f8`
- end: `0x180011255`
- name: `??0?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@PEBG@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013760`
- `0x180013b40`

## callees

- `0x180007e34`
- `0x1800111f8`
- `0x1800164a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001121c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001121c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001122a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001122a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall __0__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_PEBG_Z(
        _QWORD *a1,
        const WCHAR *a2)
{
  void *v3; // rdx
  HANDLE Mutex; // rdi
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  Mutex = CreateMutexExW(0, a2, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v5, v6);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Mutex);
  return a1;
}

```

## disassembly

```asm
0x1800111f8  mov     [rsp+arg_8], rbx
0x1800111fd  mov     [rsp+arg_0], rcx
0x180011202  push    rdi
0x180011203  sub     rsp, 20h
0x180011207  mov     rbx, rcx
0x18001120a  mov     qword ptr [rcx], 0
0x180011211  mov     r9d, 1F0001h; dwDesiredAccess
0x180011217  xor     r8d, r8d; dwFlags
0x18001121a  xor     ecx, ecx; lpMutexAttributes
0x18001121c  call    cs:__imp_CreateMutexExW
0x180011222  mov     rdi, rax
0x180011225  test    rax, rax
0x180011228  jz      short loc_18001124A
0x18001122a  call    cs:__imp_GetLastError
0x180011230  mov     rdx, rdi
0x180011233  mov     rcx, rbx
0x180011236  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001123b  nop
0x18001123c  mov     rax, rbx
0x18001123f  mov     rbx, [rsp+28h+arg_8]
0x180011244  add     rsp, 20h
0x180011248  pop     rdi
0x180011249  retn
0x18001124a  mov     rcx, [rsp+28h]; this
0x18001124f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
