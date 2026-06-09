# ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z

- ea: `0x18000fd54`
- end: `0x18000fd93`
- name: `?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d670`
- `0x18001ab60`
- `0x18001ac74`
- `0x18001b1d0`
- `0x18001b42c`

## callees

- `0x1800063cc`
- `0x18000fd54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fd61`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fd61`

## string_xrefs

- `0x18000fd77`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(
        HANDLE *a1)
{
  DWORD v1; // eax
  const char *v2; // r9
  bool v3; // zf
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v1 == 258 )
    return 0;
  v3 = v1 == 0;
  if ( v1 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v2);
  return v3;
}

```

## disassembly

```asm
0x18000fd54  sub     rsp, 28h
0x18000fd58  mov     rcx, [rcx]; hHandle
0x18000fd5b  xor     r8d, r8d; bAlertable
0x18000fd5e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fd61  call    cs:__imp_WaitForSingleObjectEx
0x18000fd67  cmp     eax, 102h
0x18000fd6c  jz      short loc_18000FD89
0x18000fd6e  test    eax, eax
0x18000fd70  jz      short loc_18000FD8B
0x18000fd72  mov     rcx, [rsp+28h]; this
0x18000fd77  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fd7e  mov     edx, 0B0Fh; void *
0x18000fd83  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000fd89  test    eax, eax
0x18000fd8b  setz    al
0x18000fd8e  add     rsp, 28h
0x18000fd92  retn
```
