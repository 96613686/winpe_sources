# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x18000fa64`
- end: `0x18000fabb`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a670`
- `0x18000a6f4`
- `0x18000af98`
- `0x18000b104`

## callees

- `0x18000b68c`
- `0x18000fa64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fa7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000fa7d`

## string_xrefs

- `0x18000fa96`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xE01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x18000fa64  mov     [rsp+arg_0], rbx
0x18000fa69  push    rdi
0x18000fa6a  sub     rsp, 20h
0x18000fa6e  mov     rbx, [rcx]
0x18000fa71  mov     rdi, rdx
0x18000fa74  mov     rcx, rbx; hHandle
0x18000fa77  xor     r8d, r8d; bAlertable
0x18000fa7a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000fa7d  call    cs:__imp_WaitForSingleObjectEx
0x18000fa83  cmp     eax, 102h
0x18000fa88  jz      short loc_18000FAA8
0x18000fa8a  test    eax, 0FFFFFF7Fh
0x18000fa8f  jz      short loc_18000FAAA
0x18000fa91  mov     rcx, [rsp+28h]; this
0x18000fa96  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000fa9d  mov     edx, 0E01h; void *
0x18000faa2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000faa8  xor     ebx, ebx
0x18000faaa  mov     [rdi], rbx
0x18000faad  mov     rax, rdi
0x18000fab0  mov     rbx, [rsp+28h+arg_0]
0x18000fab5  add     rsp, 20h
0x18000fab9  pop     rdi
0x18000faba  retn
```
