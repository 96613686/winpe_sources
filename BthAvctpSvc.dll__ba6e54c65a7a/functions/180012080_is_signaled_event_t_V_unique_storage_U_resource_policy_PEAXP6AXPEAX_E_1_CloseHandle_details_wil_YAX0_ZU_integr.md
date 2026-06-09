# ?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NXZ

- ea: `0x180012080`
- end: `0x1800120e1`
- name: `?is_signaled@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NXZ`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010cd0`
- `0x180054ab0`

## callees

- `0x180004bd8`
- `0x180012080`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012095`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800120b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012095`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800120b0`

## string_xrefs

- `0x1800120bf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
bool __fastcall _is_signaled___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NXZ(
        HANDLE *a1)
{
  HANDLE v1; // rdi
  DWORD v2; // eax
  const char *v3; // r9
  DWORD v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  v2 = WaitForSingleObjectEx(*a1, 0, 0);
  v4 = v2;
  if ( v2 != 258 && (v2 || WaitForSingleObjectEx(v1, 0, 0)) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB07,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v3);
  return v4 == 0;
}

```

## disassembly

```asm
0x180012080  mov     [rsp+arg_0], rbx
0x180012085  push    rdi
0x180012086  sub     rsp, 20h
0x18001208a  mov     rdi, [rcx]
0x18001208d  xor     r8d, r8d; bAlertable
0x180012090  mov     rcx, rdi; hHandle
0x180012093  xor     edx, edx; dwMilliseconds
0x180012095  call    cs:__imp_WaitForSingleObjectEx
0x18001209b  mov     ebx, eax
0x18001209d  cmp     eax, 102h
0x1800120a2  jz      short loc_1800120D1
0x1800120a4  test    eax, eax
0x1800120a6  jnz     short loc_1800120BA
0x1800120a8  xor     r8d, r8d; bAlertable
0x1800120ab  xor     edx, edx; dwMilliseconds
0x1800120ad  mov     rcx, rdi; hHandle
0x1800120b0  call    cs:__imp_WaitForSingleObjectEx
0x1800120b6  test    eax, eax
0x1800120b8  jz      short loc_1800120D1
0x1800120ba  mov     rcx, [rsp+28h]; this
0x1800120bf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800120c6  mov     edx, 0B07h; void *
0x1800120cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800120d1  test    ebx, ebx
0x1800120d3  mov     rbx, [rsp+28h+arg_0]
0x1800120d8  setz    al
0x1800120db  add     rsp, 20h
0x1800120df  pop     rdi
0x1800120e0  retn
```
