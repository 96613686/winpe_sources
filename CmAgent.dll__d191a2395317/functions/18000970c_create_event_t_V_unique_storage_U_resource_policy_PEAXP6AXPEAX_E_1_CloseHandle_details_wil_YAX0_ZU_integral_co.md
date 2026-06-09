# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000970c`
- end: `0x1800097a3`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c44`
- `0x1800178e0`

## callees

- `0x1800067fc`
- `0x180009518`
- `0x18000970c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009726`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180009726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000974e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000973a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000974e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009771`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000975f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000975f`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x18000970c  push    rbx
0x18000970e  push    rbp
0x18000970f  push    rsi
0x180009710  push    rdi
0x180009711  sub     rsp, 28h
0x180009715  xor     edx, edx; lpName
0x180009717  mov     rdi, rcx
0x18000971a  xor     ecx, ecx; lpEventAttributes
0x18000971c  mov     r9d, 1F0003h; dwDesiredAccess
0x180009722  lea     r8d, [rdx+1]; dwFlags
0x180009726  call    cs:__imp_CreateEventExW
0x18000972d  nop     dword ptr [rax+rax+00h]
0x180009732  mov     rbp, rax
0x180009735  test    rax, rax
0x180009738  jz      short loc_180009784
0x18000973a  call    cs:__imp_GetLastError
0x180009741  nop     dword ptr [rax+rax+00h]
0x180009746  mov     rbx, [rdi]
0x180009749  test    rbx, rbx
0x18000974c  jz      short loc_18000977D
0x18000974e  call    cs:__imp_GetLastError
0x180009755  nop     dword ptr [rax+rax+00h]
0x18000975a  mov     rcx, rbx; hObject
0x18000975d  mov     esi, eax
0x18000975f  call    cs:__imp_CloseHandle
0x180009766  nop     dword ptr [rax+rax+00h]
0x18000976b  test    eax, eax
0x18000976d  jz      short loc_180009793
0x18000976f  mov     ecx, esi; dwErrCode
0x180009771  call    cs:__imp_SetLastError
0x180009778  nop     dword ptr [rax+rax+00h]
0x18000977d  mov     [rdi], rbp
0x180009780  xor     eax, eax
0x180009782  jmp     short loc_180009789
0x180009784  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009789  add     rsp, 28h
0x18000978d  pop     rdi
0x18000978e  pop     rsi
0x18000978f  pop     rbp
0x180009790  pop     rbx
0x180009791  retn
0x180009793  mov     rcx, [rsp+48h]; this
0x180009798  mov     edx, 0A0Bh; void *
0x18000979d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
