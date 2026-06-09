# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18004f710`
- end: `0x18004f78e`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `126`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b4b0`
- `0x18004b738`
- `0x18004b9c0`
- `0x180050308`
- `0x180050594`

## callees

- `0x180007ed8`
- `0x18000a008`
- `0x18004f710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004f729`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004f729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f745`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f75c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f75c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f750`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f750`

## string_xrefs

- `0x18004f77c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v6);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x18004f710  push    rbx
0x18004f712  push    rbp
0x18004f713  push    rsi
0x18004f714  push    rdi
0x18004f715  sub     rsp, 28h
0x18004f719  mov     rdi, rcx
0x18004f71c  mov     r9d, 1F0003h; dwDesiredAccess
0x18004f722  xor     ecx, ecx; lpEventAttributes
0x18004f724  xor     r8d, r8d; dwFlags
0x18004f727  xor     edx, edx; lpName
0x18004f729  call    cs:__imp_CreateEventExW
0x18004f72f  mov     rbp, rax
0x18004f732  test    rax, rax
0x18004f735  jz      short loc_18004F769
0x18004f737  call    cs:__imp_GetLastError
0x18004f73d  mov     rbx, [rdi]
0x18004f740  test    rbx, rbx
0x18004f743  jz      short loc_18004F762
0x18004f745  call    cs:__imp_GetLastError
0x18004f74b  mov     rcx, rbx; hObject
0x18004f74e  mov     esi, eax
0x18004f750  call    cs:__imp_CloseHandle
0x18004f756  test    eax, eax
0x18004f758  jz      short loc_18004F777
0x18004f75a  mov     ecx, esi; dwErrCode
0x18004f75c  call    cs:__imp_SetLastError
0x18004f762  mov     [rdi], rbp
0x18004f765  xor     eax, eax
0x18004f767  jmp     short loc_18004F76E
0x18004f769  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004f76e  add     rsp, 28h
0x18004f772  pop     rdi
0x18004f773  pop     rsi
0x18004f774  pop     rbp
0x18004f775  pop     rbx
0x18004f776  retn
0x18004f777  mov     rcx, [rsp+48h]; this
0x18004f77c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004f783  mov     edx, 0A0Bh; void *
0x18004f788  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
