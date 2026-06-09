# ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z

- ea: `0x180015ba8`
- end: `0x180015be6`
- name: `?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b720`
- `0x180032318`

## callees

- `0x180015ba8`
- `0x1800274c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015bb2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180015bb2`

## string_xrefs

- `0x180015bd0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
bool __fastcall _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
        HANDLE *a1,
        DWORD a2)
{
  DWORD v2; // eax
  const char *v3; // r9
  bool v4; // zf
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = WaitForSingleObjectEx(*a1, a2, 0);
  if ( v2 == 258 )
    return 0;
  v4 = v2 == 0;
  if ( v2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB0F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v3);
  return v4;
}

```

## disassembly

```asm
0x180015ba8  sub     rsp, 28h
0x180015bac  mov     rcx, [rcx]; hHandle
0x180015baf  xor     r8d, r8d; bAlertable
0x180015bb2  call    cs:__imp_WaitForSingleObjectEx
0x180015bb8  cmp     eax, 102h
0x180015bbd  jz      short loc_180015BE2
0x180015bbf  test    eax, eax
0x180015bc1  jnz     short loc_180015BCB
0x180015bc3  setz    al
0x180015bc6  add     rsp, 28h
0x180015bca  retn
0x180015bcb  mov     rcx, [rsp+28h]; this
0x180015bd0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015bd7  mov     edx, 0B0Fh; void *
0x180015bdc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015be2  test    eax, eax
0x180015be4  jmp     short loc_180015BC3
```
