# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180008b34`
- end: `0x180008b8b`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005a6c`
- `0x180006078`
- `0x1800104bc`
- `0x180010a1c`

## callees

- `0x1800063cc`
- `0x180008b34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008b4d`

## string_xrefs

- `0x180008b66`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    wil::details::in1diag3::FailFast_Unexpected(
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
0x180008b34  mov     [rsp+arg_0], rbx
0x180008b39  push    rdi
0x180008b3a  sub     rsp, 20h
0x180008b3e  mov     rbx, [rcx]
0x180008b41  mov     rdi, rdx
0x180008b44  mov     rcx, rbx; hHandle
0x180008b47  xor     r8d, r8d; bAlertable
0x180008b4a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008b4d  call    cs:__imp_WaitForSingleObjectEx
0x180008b53  cmp     eax, 102h
0x180008b58  jz      short loc_180008B78
0x180008b5a  test    eax, 0FFFFFF7Fh
0x180008b5f  jz      short loc_180008B7A
0x180008b61  mov     rcx, [rsp+28h]; this
0x180008b66  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008b6d  mov     edx, 0E01h; void *
0x180008b72  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008b78  xor     ebx, ebx
0x180008b7a  mov     [rdi], rbx
0x180008b7d  mov     rax, rdi
0x180008b80  mov     rbx, [rsp+28h+arg_0]
0x180008b85  add     rsp, 20h
0x180008b89  pop     rdi
0x180008b8a  retn
```
