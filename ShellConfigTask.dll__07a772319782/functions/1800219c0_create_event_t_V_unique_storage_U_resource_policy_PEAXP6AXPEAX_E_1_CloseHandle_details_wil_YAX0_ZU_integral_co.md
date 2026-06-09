# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x1800219c0`
- end: `0x180021a41`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `129`
- prototype: `__int64 __fastcall(void **, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f604`
- `0x18001f998`
- `0x180021a48`

## callees

- `0x180007c58`
- `0x18000c5d4`
- `0x1800219c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021a0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800219dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800219dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021a03`

## string_xrefs

- `0x180021a2f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2)
{
  wil::details *v3; // rcx
  HANDLE Event; // rbp
  void *v5; // rbx
  DWORD LastError; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v3);
  GetLastError();
  v5 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x1800219c0  push    rbx
0x1800219c2  push    rbp
0x1800219c3  push    rsi
0x1800219c4  push    rdi
0x1800219c5  sub     rsp, 28h
0x1800219c9  and     edx, 3
0x1800219cc  mov     rdi, rcx
0x1800219cf  mov     r8d, edx; dwFlags
0x1800219d2  mov     r9d, 1F0003h; dwDesiredAccess
0x1800219d8  xor     edx, edx; lpName
0x1800219da  xor     ecx, ecx; lpEventAttributes
0x1800219dc  call    cs:__imp_CreateEventExW
0x1800219e2  mov     rbp, rax
0x1800219e5  test    rax, rax
0x1800219e8  jz      short loc_180021A1C
0x1800219ea  call    cs:__imp_GetLastError
0x1800219f0  mov     rbx, [rdi]
0x1800219f3  test    rbx, rbx
0x1800219f6  jz      short loc_180021A15
0x1800219f8  call    cs:__imp_GetLastError
0x1800219fe  mov     rcx, rbx; hObject
0x180021a01  mov     esi, eax
0x180021a03  call    cs:__imp_CloseHandle
0x180021a09  test    eax, eax
0x180021a0b  jz      short loc_180021A2A
0x180021a0d  mov     ecx, esi; dwErrCode
0x180021a0f  call    cs:__imp_SetLastError
0x180021a15  mov     [rdi], rbp
0x180021a18  xor     eax, eax
0x180021a1a  jmp     short loc_180021A21
0x180021a1c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021a21  add     rsp, 28h
0x180021a25  pop     rdi
0x180021a26  pop     rsi
0x180021a27  pop     rbp
0x180021a28  pop     rbx
0x180021a29  retn
0x180021a2a  mov     rcx, [rsp+48h]; this
0x180021a2f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021a36  mov     edx, 0A0Bh; void *
0x180021a3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
