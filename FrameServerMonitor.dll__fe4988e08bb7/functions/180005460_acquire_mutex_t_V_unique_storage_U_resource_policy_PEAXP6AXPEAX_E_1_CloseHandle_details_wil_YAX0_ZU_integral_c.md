# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x180005460`
- end: `0x1800054b7`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003314`
- `0x180004a80`

## callees

- `0x180003730`
- `0x180005460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005479`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005479`

## string_xrefs

- `0x180005492`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v5);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x180005460  mov     [rsp+arg_0], rbx
0x180005465  push    rdi
0x180005466  sub     rsp, 20h
0x18000546a  mov     rbx, [rcx]
0x18000546d  mov     rdi, rdx
0x180005470  mov     rcx, rbx; hHandle
0x180005473  xor     r8d, r8d; bAlertable
0x180005476  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005479  call    cs:__imp_WaitForSingleObjectEx
0x18000547f  cmp     eax, 102h
0x180005484  jz      short loc_1800054A4
0x180005486  test    eax, 0FFFFFF7Fh
0x18000548b  jz      short loc_1800054A6
0x18000548d  mov     rcx, [rsp+28h]; this
0x180005492  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005499  mov     edx, 0E01h; void *
0x18000549e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800054a4  xor     ebx, ebx
0x1800054a6  mov     [rdi], rbx
0x1800054a9  mov     rax, rdi
0x1800054ac  mov     rbx, [rsp+28h+arg_0]
0x1800054b1  add     rsp, 20h
0x1800054b5  pop     rdi
0x1800054b6  retn
```
