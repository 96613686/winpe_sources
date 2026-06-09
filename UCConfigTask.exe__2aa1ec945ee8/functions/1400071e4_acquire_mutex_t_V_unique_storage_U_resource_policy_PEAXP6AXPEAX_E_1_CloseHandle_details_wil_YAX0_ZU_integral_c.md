# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x1400071e4`
- end: `0x14000722f`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `75`
- prototype: `_QWORD *__fastcall(HANDLE *, _QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140002d38`
- `0x140003478`
- `0x1400035e4`
- `0x140005e20`

## callees

- `0x140003a9c`
- `0x1400071e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400071fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400071fd`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  v4 = WaitForSingleObjectEx(*a1, 0xFFFFFFFF, 0);
  if ( v4 == 258 )
  {
    v2 = 0;
  }
  else if ( (v4 & 0xFFFFFF7F) != 0 )
  {
    wil::details::in1diag3::FailFast_Unexpected(retaddr, v5, v6, v7);
  }
  *a2 = v2;
  return a2;
}

```

## disassembly

```asm
0x1400071e4  mov     [rsp+arg_0], rbx
0x1400071e9  push    rdi
0x1400071ea  sub     rsp, 20h
0x1400071ee  mov     rbx, [rcx]
0x1400071f1  mov     rdi, rdx
0x1400071f4  mov     rcx, rbx; hHandle
0x1400071f7  xor     r8d, r8d; bAlertable
0x1400071fa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400071fd  call    cs:__imp_WaitForSingleObjectEx
0x140007203  cmp     eax, 102h
0x140007208  jz      short loc_14000721C
0x14000720a  test    eax, 0FFFFFF7Fh
0x14000720f  jz      short loc_14000721E
0x140007211  mov     rcx, [rsp+28h]; this
0x140007216  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000721c  xor     ebx, ebx
0x14000721e  mov     [rdi], rbx
0x140007221  mov     rax, rdi
0x140007224  mov     rbx, [rsp+28h+arg_0]
0x140007229  add     rsp, 20h
0x14000722d  pop     rdi
0x14000722e  retn
```
