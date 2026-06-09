# ??1?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ

- ea: `0x180013ecc`
- end: `0x180013efe`
- name: `??1?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180030f52`

## callees

- `0x18000c5d4`
- `0x180013ecc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013ed8`

## string_xrefs

- `0x180013eec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v2);
  }
}

```

## disassembly

```asm
0x180013ecc  sub     rsp, 28h
0x180013ed0  mov     rcx, [rcx]; hObject
0x180013ed3  test    rcx, rcx
0x180013ed6  jz      short loc_180013EE2
0x180013ed8  call    cs:__imp_CloseHandle
0x180013ede  test    eax, eax
0x180013ee0  jz      short loc_180013EE7
0x180013ee2  add     rsp, 28h
0x180013ee6  retn
0x180013ee7  mov     rcx, [rsp+28h]; this
0x180013eec  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013ef3  mov     edx, 0A0Bh; void *
0x180013ef8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
