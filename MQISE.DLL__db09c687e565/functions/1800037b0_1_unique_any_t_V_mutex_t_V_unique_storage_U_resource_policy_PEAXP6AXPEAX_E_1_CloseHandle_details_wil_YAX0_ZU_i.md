# ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ

- ea: `0x1800037b0`
- end: `0x1800037db`
- name: `??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000fa30`
- `0x18000fa78`
- `0x18000fc64`
- `0x18000fc76`

## callees

- `0x1800037b0`
- `0x18000b3c8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800037bc`
- `KERNEL32!CloseHandle` at `0x1800037bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  __int64 v2; // r8
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v2, v3);
  }
}

```

## disassembly

```asm
0x1800037b0  sub     rsp, 28h
0x1800037b4  mov     rcx, [rcx]; hObject
0x1800037b7  test    rcx, rcx
0x1800037ba  jz      short loc_1800037CB
0x1800037bc  call    cs:__imp_CloseHandle
0x1800037c2  mov     rcx, [rsp+28h]; this
0x1800037c7  test    eax, eax
0x1800037c9  jz      short loc_1800037D0
0x1800037cb  add     rsp, 28h
0x1800037cf  retn
0x1800037d0  mov     edx, 0A0Bh; void *
0x1800037d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
