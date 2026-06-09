# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180004c94`
- end: `0x180004cbf`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004e10`
- `0x1800050b0`
- `0x1800128e0`
- `0x180015eb0`
- `0x180015ee0`
- `0x180016020`

## callees

- `0x180004c94`
- `0x1800174e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ca0`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  unsigned int v2; // r8d
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
0x180004c94  sub     rsp, 28h
0x180004c98  mov     rcx, [rcx]; hObject
0x180004c9b  test    rcx, rcx
0x180004c9e  jz      short loc_180004CAA
0x180004ca0  call    cs:__imp_CloseHandle
0x180004ca6  test    eax, eax
0x180004ca8  jz      short loc_180004CAF
0x180004caa  add     rsp, 28h
0x180004cae  retn
0x180004caf  mov     rcx, [rsp+28h]; this
0x180004cb4  mov     edx, 0A0Bh; void *
0x180004cb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
