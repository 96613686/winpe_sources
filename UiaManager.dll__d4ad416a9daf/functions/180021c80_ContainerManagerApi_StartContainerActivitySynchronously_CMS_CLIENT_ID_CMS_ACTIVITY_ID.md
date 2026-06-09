# ContainerManagerApi::StartContainerActivitySynchronously(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)

- ea: `0x180021c80`
- end: `0x180021d6b`
- name: `?StartContainerActivitySynchronously@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022360`

## callees

- `0x180016010`
- `0x1800205cc`
- `0x180021c80`
- `0x180021d74`
- `0x180022204`
- `0x180022870`
- `0x180031540`

## import_xrefs

- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180021cda`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x180021cda`

## string_xrefs

- `0x180021cec`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180021d1c`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`
- `0x180021d40`: `onecore\windows\accessibletech\common\containermanagerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ContainerManagerApi::StartContainerActivitySynchronously(__int64 a1, _QWORD *a2, __int64 a3)
{
  int started; // eax
  int v6; // [rsp+20h] [rbp-48h]
  char *v7; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v8[40]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  ContainerManagerApi::GetContainerActivity(a1, a2, a3, 0x2710u);
  anonymous_namespace_::ContainerActivityStartedContext::ContainerActivityStartedContext(&v7);
  _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (__int64)v8,
    0,
    0,
    0);
  started = CmsStartActivityAsync(a2[1], lambda_4a0f9229d2502bb657bc5d9827238909_::_lambda_invoker_cdecl_, &v7);
  if ( started < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)started,
      v6);
  if ( !(unsigned __int8)_wait___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                           v8,
                           5000) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)0x80131505LL,
      v6);
  if ( (int)v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\containermanagerapi.cpp",
      (const char *)(unsigned int)v7,
      v6);
  anonymous_namespace_::ContainerActivityStartedContext::_ContainerActivityStartedContext(&v7);
  return a2;
}

```

## disassembly

```asm
0x180021c80  mov     [rsp+arg_0], rbx
0x180021c85  mov     [rsp+arg_8], rdx
0x180021c8a  push    rdi
0x180021c8b  sub     rsp, 60h
0x180021c8f  mov     rbx, rdx
0x180021c92  mov     [rsp+68h+var_38], 0
0x180021c9a  mov     r9d, 2710h
0x180021ca0  call    ?GetContainerActivity@ContainerManagerApi@@QEAA?AVContainerActivityGuard@1@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z; ContainerManagerApi::GetContainerActivity(_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)
0x180021ca5  mov     [rsp+68h+var_38], 1
0x180021cad  lea     rcx, [rsp+68h+var_30]
0x180021cb2  call    _anonymous_namespace___ContainerActivityStartedContext__ContainerActivityStartedContext
0x180021cb7  nop
0x180021cb8  xor     r9d, r9d
0x180021cbb  xor     r8d, r8d
0x180021cbe  xor     edx, edx
0x180021cc0  lea     rcx, [rsp+68h+var_28]
0x180021cc5  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021cca  lea     r8, [rsp+68h+var_30]
0x180021ccf  lea     rdx, _lambda_4a0f9229d2502bb657bc5d9827238909____lambda_invoker_cdecl_
0x180021cd6  mov     rcx, [rbx+8]
0x180021cda  call    cs:__imp_CmsStartActivityAsync
0x180021ce0  mov     rcx, [rsp+68h]; this
0x180021ce5  test    eax, eax
0x180021ce7  jns     short loc_180021CFE
0x180021ce9  mov     r9d, eax; char *
0x180021cec  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021cf3  mov     edx, 1B3h; void *
0x180021cf8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021cfe  mov     rdi, [rsp+68h]
0x180021d03  mov     edx, 1388h
0x180021d08  lea     rcx, [rsp+68h+var_28]
0x180021d0d  call    ?wait@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x180021d12  test    al, al
0x180021d14  jnz     short loc_180021D31
0x180021d16  mov     r9d, 80131505h; char *
0x180021d1c  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021d23  mov     edx, 1B5h; void *
0x180021d28  mov     rcx, rdi; this
0x180021d2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021d31  mov     r9d, dword ptr [rsp+68h+var_30]; char *
0x180021d36  mov     rcx, [rsp+68h]; this
0x180021d3b  test    r9d, r9d
0x180021d3e  jns     short loc_180021D52
0x180021d40  lea     r8, aOnecoreWindows_19; "onecore\\windows\\accessibletech\\commo"...
0x180021d47  mov     edx, 1B6h; void *
0x180021d4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021d52  lea     rcx, [rsp+68h+var_30]
0x180021d57  call    _anonymous_namespace___ContainerActivityStartedContext___ContainerActivityStartedContext
0x180021d5c  mov     rax, rbx
0x180021d5f  mov     rbx, [rsp+68h+arg_0]
0x180021d64  add     rsp, 60h
0x180021d68  pop     rdi
0x180021d69  retn
```
