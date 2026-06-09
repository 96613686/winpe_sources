# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x140007074`
- end: `0x1400070bf`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `75`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003ee4`
- `0x14000404c`
- `0x140005fa0`
- `0x140006020`

## callees

- `0x140004468`
- `0x140007074`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000708d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000708d`

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
0x140007074  mov     [rsp+arg_0], rbx
0x140007079  push    rdi
0x14000707a  sub     rsp, 20h
0x14000707e  mov     rbx, [rcx]
0x140007081  mov     rdi, rdx
0x140007084  mov     rcx, rbx; hHandle
0x140007087  xor     r8d, r8d; bAlertable
0x14000708a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000708d  call    cs:__imp_WaitForSingleObjectEx
0x140007093  cmp     eax, 102h
0x140007098  jz      short loc_1400070AC
0x14000709a  test    eax, 0FFFFFF7Fh
0x14000709f  jz      short loc_1400070AE
0x1400070a1  mov     rcx, [rsp+28h]; this
0x1400070a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400070ac  xor     ebx, ebx
0x1400070ae  mov     [rdi], rbx
0x1400070b1  mov     rax, rdi
0x1400070b4  mov     rbx, [rsp+28h+arg_0]
0x1400070b9  add     rsp, 20h
0x1400070bd  pop     rdi
0x1400070be  retn
```
