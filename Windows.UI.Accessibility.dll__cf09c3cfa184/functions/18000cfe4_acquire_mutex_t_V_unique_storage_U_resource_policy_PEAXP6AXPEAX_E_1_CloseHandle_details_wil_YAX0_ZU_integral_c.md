# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x18000cfe4`
- end: `0x18000d03b`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008c0c`
- `0x180008c90`
- `0x1800094b4`
- `0x180009620`

## callees

- `0x180009cc8`
- `0x18000cfe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cffd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000cffd`

## string_xrefs

- `0x18000d016`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000cfe4  mov     [rsp+arg_0], rbx
0x18000cfe9  push    rdi
0x18000cfea  sub     rsp, 20h
0x18000cfee  mov     rbx, [rcx]
0x18000cff1  mov     rdi, rdx
0x18000cff4  mov     rcx, rbx; hHandle
0x18000cff7  xor     r8d, r8d; bAlertable
0x18000cffa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000cffd  call    cs:__imp_WaitForSingleObjectEx
0x18000d003  cmp     eax, 102h
0x18000d008  jz      short loc_18000D028
0x18000d00a  test    eax, 0FFFFFF7Fh
0x18000d00f  jz      short loc_18000D02A
0x18000d011  mov     rcx, [rsp+28h]; this
0x18000d016  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d01d  mov     edx, 0E01h; void *
0x18000d022  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d028  xor     ebx, ebx
0x18000d02a  mov     [rdi], rbx
0x18000d02d  mov     rax, rdi
0x18000d030  mov     rbx, [rsp+28h+arg_0]
0x18000d035  add     rsp, 20h
0x18000d039  pop     rdi
0x18000d03a  retn
```
