# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180012184`
- end: `0x180012202`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a614`

## callees

- `0x18000d5a8`
- `0x180012114`
- `0x180012184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001219d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001219d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800121d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800121c4`

## string_xrefs

- `0x1800121f0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180012184  push    rbx
0x180012186  push    rbp
0x180012187  push    rsi
0x180012188  push    rdi
0x180012189  sub     rsp, 28h
0x18001218d  mov     rdi, rcx
0x180012190  mov     r9d, 1F0003h; dwDesiredAccess
0x180012196  xor     ecx, ecx; lpEventAttributes
0x180012198  xor     r8d, r8d; dwFlags
0x18001219b  xor     edx, edx; lpName
0x18001219d  call    cs:__imp_CreateEventExW
0x1800121a3  mov     rbp, rax
0x1800121a6  test    rax, rax
0x1800121a9  jz      short loc_1800121DD
0x1800121ab  call    cs:__imp_GetLastError
0x1800121b1  mov     rbx, [rdi]
0x1800121b4  test    rbx, rbx
0x1800121b7  jz      short loc_1800121D6
0x1800121b9  call    cs:__imp_GetLastError
0x1800121bf  mov     rcx, rbx; hObject
0x1800121c2  mov     esi, eax
0x1800121c4  call    cs:__imp_CloseHandle
0x1800121ca  test    eax, eax
0x1800121cc  jz      short loc_1800121EB
0x1800121ce  mov     ecx, esi; dwErrCode
0x1800121d0  call    cs:__imp_SetLastError
0x1800121d6  mov     [rdi], rbp
0x1800121d9  xor     eax, eax
0x1800121db  jmp     short loc_1800121E2
0x1800121dd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800121e2  add     rsp, 28h
0x1800121e6  pop     rdi
0x1800121e7  pop     rsi
0x1800121e8  pop     rbp
0x1800121e9  pop     rbx
0x1800121ea  retn
0x1800121eb  mov     rcx, [rsp+48h]; this
0x1800121f0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800121f7  mov     edx, 0A0Bh; void *
0x1800121fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
