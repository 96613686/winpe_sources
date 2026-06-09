# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x14000b8f4`
- end: `0x14000b93f`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `75`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007adc`
- `0x140007c48`
- `0x14000a3b4`
- `0x14000a434`

## callees

- `0x1400081e0`
- `0x14000b8f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b90d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000b90d`

## pseudocode

```c
_QWORD *__fastcall _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        HANDLE *a1,
        _QWORD *a2)
{
  HANDLE v2; // rbx
  DWORD v4; // eax
  void *v5; // rdx
  __int64 v6; // r8
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
0x14000b8f4  mov     [rsp+arg_0], rbx
0x14000b8f9  push    rdi
0x14000b8fa  sub     rsp, 20h
0x14000b8fe  mov     rbx, [rcx]
0x14000b901  mov     rdi, rdx
0x14000b904  mov     rcx, rbx; hHandle
0x14000b907  xor     r8d, r8d; bAlertable
0x14000b90a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000b90d  call    cs:__imp_WaitForSingleObjectEx
0x14000b913  cmp     eax, 102h
0x14000b918  jz      short loc_14000B92C
0x14000b91a  test    eax, 0FFFFFF7Fh
0x14000b91f  jz      short loc_14000B92E
0x14000b921  mov     rcx, [rsp+28h]; this
0x14000b926  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000b92c  xor     ebx, ebx
0x14000b92e  mov     [rdi], rbx
0x14000b931  mov     rax, rdi
0x14000b934  mov     rbx, [rsp+28h+arg_0]
0x14000b939  add     rsp, 20h
0x14000b93d  pop     rdi
0x14000b93e  retn
```
